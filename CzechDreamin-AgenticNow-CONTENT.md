# CzechDreamin 2026 — "Agentic now!" — Content & Design Bible

**Speaker:** Robert Sösemann · Aquiva Labs
**File:** `CzechDreamin-AgenticNow.html` (scrollable HTML presentation, fullscreen in browser)
**Git repo:** `/sessions/awesome-quirky-gates/mnt/conference/.git/`

---

## CRITICAL: Read This Before Touching the File

1. **ALWAYS git commit before making any changes.** Run: `cd /sessions/awesome-quirky-gates/mnt/conference && git add -A && git commit -m "Pre-change snapshot"`
2. **Make ONE change at a time**, then commit. NEVER batch multiple layout changes.
3. **Do NOT add `display: flex; flex-direction: column` to `.slide-tip .slide-inner`** — this broke the entire layout previously.
4. **Do NOT add `align-items: stretch` to `.slide-tip`** — also broke layout.
5. **Do NOT add `padding-right` to `.slide-tip .slide-inner`** — broke layout.
6. The file contains base64-embedded Aquiva logos making it ~88KB. This is normal.

---

## Slide Structure (9 slides)

### Slide 0 — Cover
- Title: "Agentic now!"
- Subtitle: "Tips & tricks from the trenches with Agentforce"
- Meta: Robert Sösemann · CzechDreamin · June 2026

### Slide 1 — Intro: Why now — The right time to go agentic
- We brought more Agentforce projects through security review than most.
- Customers are coming back — not just PoCs anymore, they actually deliver.
- The time to start is now. AgentScript is coming and will add complexity.
- Building a mental model is easier while Agentforce is still simple.
- **Butler:** Open source. Everything we learned. github.com/aquivalabs/my-org-butler
- **Showcase:** Screenshot: My Org Butler in action

### Slide 2 — Tip 1: Only generic actions unfold the real power of AI
- One action per use case → 20 narrow actions, LLM picks wrong.
- 2 generic actions replace dozens of hardcoded ones.
- Trust the LLM. Prescribing every step is orchestration — not agentic.
- **Butler:** `ExploreOrgSchema` + `QueryRecordsWithSoql` — two actions handle what would need dozens.
- **Showcase:** Agent exploring schema + writing SOQL dynamically

### Slide 3 — Tip 2: Use APIs to get close to code execution
- Every REST endpoint is a function call. Chain enough and the agent is programming.
- Sandboxed power — no arbitrary code, just API calls.
- Two paths: custom Apex or External Services + OpenAPI.
- **Butler:** `CallRestApi`, `CallMetadataApi`, `CallToolingApi`, `CallGitHubApi` — custom Apex actions. Plus External Services version for zero-code.
- **Showcase:** Agent chaining REST calls to read, check & create records

### Slide 4 — Tip 3: Use semantic queries with Data Cloud
- "Find deals similar to Acme." No WHERE clause can do that.
- Semantic search on CRM data via Data Cloud hybrid retrievers.
- SOQL for precision, vectors for intuition — agents speak both.
- **Butler:** Hybrid retriever on Opportunities — vector ranked results no SOQL could produce.
- **Showcase:** Semantic similarity results vs. SOQL results

### Slide 5 — Tip 4: Ground your prompts on your messy files
- Ungrounded agents invent answers with confidence. Grounding fixes that.
- Prompt Templates attach files & records to every request.
- Three flavors: single file, record context, full doc library.
- **Butler:** `AnswerFromFiles` — ask "payment terms?" and get the answer from your SOW.
- **Showcase:** Agent citing the actual SOW document in its answer

### Slide 6 — Tip 5: Let your agents learn with memory
- Every conversation starts from scratch. Brilliant consultant with amnesia.
- Persist preferences, decisions, tasks across sessions.
- Memory turns a tool into a colleague.
- **Butler:** `AgentMemory` + `LoadCustomInstructions` — persistent context, zero code.
- **Showcase (2 stacked images, showcase-multi):**
  - TOP: `tip5-memory-record.png` — Salesforce record detail page showing a "MyOrgButler Memory" record titled "Prefers Amount and CloseDate for opportunities". Content field says "When showing opportunities, include Amount and CloseDate fields." Created by User User on 3/2/2026.
  - BOTTOM: `tip5-memory-conversation.png` — Agentforce Builder conversation preview. Left side shows agent reasoning with "Action Launched: Store Custom Instruction" and the JSON input/output. Right side shows the chat: user asks for 3 most urgent opportunities, agent responds with a list, user asks for more detailed textual summaries, agent says "Got it! From now on, I'll provide more detailed textual summaries" and re-responds with expanded opportunity details including stage, amounts, and close dates.

### Slide 7 — Tip 6: Make agents autonomous with headless (PURPLE accent slide)
- Chat is step one. Real pattern: no user, just triggers.
- Runs on schedule, reacts to events, works autonomously.
- Interactive agents are the demo. Autonomous agents are the product.
- **Butler:** `HeadlessAgent` + `PlanForLater` — "Every Monday, check stale opps and Slack me."
- **Showcase:** Slack notification from agent that ran overnight

### Slide 8 — Closing
- "Start building. Now."
- QR code + github.com/aquivalabs/my-org-butler link
- Robert Sösemann · CzechDreamin 2026

---

## Current Design State

### Typography
- **Root font-size:** `clamp(16px, 1.15vw, 22px)` — scales with viewport for fullscreen presentation
- **Title (.tip-h):** `clamp(2.6rem, 4.2vw, 3.2rem)`, Lexend font, purple color
- **Tip number (.tip-num):** inline pink `<span>` with em-dash, same line as title: `<h2 class="tip-h"><span class="tip-num">Tip N &mdash;</span> Title</h2>`
- **Bullets (.tip-bullets li):** `2.4rem`, Open Sans, dark text, blue circle bullet
- **Butler label:** `0.75rem`, uppercase, purple, Lexend
- **Butler text:** `1.1rem`, Open Sans

### Layout
- **No tip icons** — removed the 110px rounded SVG icons
- **No left margin** — text and bullets start at the left edge (no 132px indent)
- **No slide counter** — removed the "3/9" from nav bar
- **Showcase area** — 42% width on right side, full height, with 160px gradient fade
- **Showcase crop:** Use `--crop-x` CSS variable on `.tip-showcase` to shift image position (default: center). Example: `style="--crop-x: 30%"` shows left portion
- **Butler footer** — compact row: small My Org Butler icon (36px) + label + description, max-width 55%, normal document flow
- **Slide backgrounds** — alternating white/warm. Only Tip 6 has purple accent. All others white.
- **Cover** — blue gradient background
- **Nav** — fixed top, Aquiva logo left, no counter

### Key CSS Classes
- `.slide` — `min-height: 100vh; scroll-snap-align: start`
- `.slide-tip` — tip slide with border-top, relative positioning, overflow hidden
- `.slide-tip .slide-inner` — `position: relative; z-index: 1` (DO NOT add flex or padding-right!)
- `.tip-showcase` — absolute right 0, 42% width, full height, overflow hidden
- `.tip-showcase::before` — 160px gradient fade on left edge
- `.tip-showcase img` — `object-fit: cover; object-position: var(--crop-x, center) top`
- `.tip-butler` — flex row with icon + body, max-width 55%, purple border-left
- `.bg-num` — giant faded number behind each tip slide

### Key HTML Pattern (Tip Slide)
```html
<div class="slide slide-tip" data-slide="N">
  <div class="bg-num">N</div>
  <div class="tip-showcase">
    <!-- Replace placeholder with: <img src="screenshot.png" alt="Description"> -->
    <div class="showcase-placeholder"><span>Description</span></div>
  </div>
  <div class="slide-inner reveal">
    <div class="tip-header">
      <h2 class="tip-h"><span class="tip-num">Tip N &mdash;</span> Title here</h2>
    </div>
    <div class="tip-body">
      <div class="tip-content">
        <ul class="tip-bullets">
          <li>Bullet text here.</li>
        </ul>
      </div>
    </div>
    <div class="tip-butler">
      <img src="https://github.com/aquivalabs/my-org-butler/raw/main/resources/logo.png" alt="My Org Butler" class="tip-butler-icon">
      <div class="tip-butler-body">
        <div class="tip-butler-label">In My Org Butler</div>
        <p>Description with <code>ClassName</code> mentions.</p>
      </div>
    </div>
  </div>
</div>
```

### Adding a Screenshot to a Showcase
1. Place the screenshot image file in the conference folder
2. Find the slide's `<div class="tip-showcase">`
3. Replace the placeholder div with: `<img src="filename.png" alt="Description">`
4. Optionally add `style="--crop-x: 40%"` to the `.tip-showcase` div to shift the crop window
5. For two stacked screenshots, use `class="tip-showcase showcase-multi"` and add two `<img>` tags

### Screenshot Files Needed
| Slide | File(s) | Status | Description |
|-------|---------|--------|-------------|
| Intro | TBD | PLACEHOLDER | My Org Butler in action |
| Tip 1 | TBD | PLACEHOLDER | Agent exploring schema + writing SOQL dynamically |
| Tip 2 | TBD | PLACEHOLDER | Agent chaining REST calls to read, check & create records |
| Tip 3 | TBD | PLACEHOLDER | Semantic similarity results vs. SOQL results |
| Tip 4 | TBD | PLACEHOLDER | Agent citing the actual SOW document in its answer |
| Tip 5 | `tip5-memory-record.png` + `tip5-memory-conversation.png` | WIRED UP (needs files in folder) | Memory record detail + agent conversation with memory |
| Tip 6 | TBD | PLACEHOLDER | Slack notification from agent that ran overnight |

---

## Version History

| Commit | Description |
|--------|-------------|
| `32a2ce3` | BROKEN state — layout completely broken by flex/padding changes |
| `f9b795d` | BASELINE — working layout, icons removed, inline tip-num |
| `3b57d8a` | Scale root font-size with viewport for fullscreen presentation |
| `f0b7ed6` | Remove slide counter (3/9) from nav bar |
| `d441cb7` | Remove blue accent from Tip 4 — all white/warm backgrounds |
| `df68d5c` | Butler: add icon, body wrapper, constrain width to 55% |
| `6ee02b9` | Showcase: widen to 42%, add --crop-x variable, wider gradient |

---

## Things That BROKE the Layout (Never Do These Again)
1. Adding `align-items: stretch` to `.slide-tip`
2. Adding `display: flex; flex-direction: column` to `.slide-tip .slide-inner`
3. Adding `padding-right: 36%` to `.slide-tip .slide-inner`
4. Setting bullet `font-size: 2.6rem` with `max-width: 60%` on li
5. Changing butler to `margin-top: auto` (requires flex parent which breaks everything)

---

## Open Items
1. **Showcase images** — All 7 showcases have placeholder divs. Need actual screenshots from My Org Butler demos. Robert will provide these.
2. **Butler text** — Robert may want to further simplify butler descriptions (fewer class names, more about what the feature does)
3. **Bullet text** — Robert may want to compress bullet text further
