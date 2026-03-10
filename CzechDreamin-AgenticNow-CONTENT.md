# CzechDreamin 2026 — "Agentic now!" — Content & Status

**Speaker:** Robert Sösemann · Aquiva Labs
**File:** `CzechDreamin-AgenticNow.html` (scrollable HTML presentation)
**Git baseline:** commit `f9b795d` — "BASELINE: working layout with icons removed, inline tip-num"

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

### Slide 2 — Tip 1: Only generic actions unfold the real power of AI
- One action per use case → 20 narrow actions, LLM picks wrong.
- 2 generic actions replace dozens of hardcoded ones.
- Trust the LLM. Prescribing every step is orchestration — not agentic.
- **Butler:** `ExploreOrgSchema` + `QueryRecordsWithSoql` — two actions handle what would need dozens.
- **Showcase placeholder:** Agent exploring schema + writing SOQL dynamically

### Slide 3 — Tip 2: Use APIs to get close to code execution
- Every REST endpoint is a function call. Chain enough and the agent is programming.
- Sandboxed power — no arbitrary code, just API calls.
- Two paths: custom Apex or External Services + OpenAPI.
- **Butler:** `CallRestApi`, `CallMetadataApi`, `CallToolingApi`, `CallGitHubApi` — custom Apex actions. Plus External Services version for zero-code.
- **Showcase placeholder:** Agent chaining REST calls to read, check & create records

### Slide 4 — Tip 3: Use semantic queries with Data Cloud
- "Find deals similar to Acme." No WHERE clause can do that.
- Semantic search on CRM data via Data Cloud hybrid retrievers.
- SOQL for precision, vectors for intuition — agents speak both.
- **Butler:** Hybrid retriever on Opportunities — vector ranked results no SOQL could produce.
- **Showcase placeholder:** Semantic similarity results vs. SOQL results

### Slide 5 — Tip 4: Ground your prompts on your messy files (BLUE slide)
- Ungrounded agents invent answers with confidence. Grounding fixes that.
- Prompt Templates attach files & records to every request.
- Three flavors: single file, record context, full doc library.
- **Butler:** `AnswerFromFiles` — ask "payment terms?" and get the answer from your SOW.
- **Showcase placeholder:** Agent citing the actual SOW document in its answer

### Slide 6 — Tip 5: Let your agents learn with memory
- Every conversation starts from scratch. Brilliant consultant with amnesia.
- Persist preferences, decisions, tasks across sessions.
- Memory turns a tool into a colleague.
- **Butler:** `AgentMemory` + `LoadCustomInstructions` — persistent context, zero code.
- **Showcase placeholder:** Agent learning preferences + memory record

### Slide 7 — Tip 6: Make agents autonomous with headless (PURPLE slide)
- Chat is step one. Real pattern: no user, just triggers.
- Runs on schedule, reacts to events, works autonomously.
- Interactive agents are the demo. Autonomous agents are the product.
- **Butler:** `HeadlessAgent` + `PlanForLater` — "Every Monday, check stale opps and Slack me."
- **Showcase placeholder:** Slack notification from agent that ran overnight

### Slide 8 — Closing
- "Start building. Now."
- QR code + github.com/aquivalabs/my-org-butler link
- Robert Sösemann · CzechDreamin 2026

---

## Current Design State (Baseline)

- **No tip icons** — removed the 110px rounded SVG icons that were left of the title
- **Inline tip number** — "Tip N —" as pink `<span>` on same line as title
- **No left margin** — text and bullets start at the left edge (no 132px indent)
- **Showcase area** — 34% width on right side, full height, with 120px gradient fade
- **Butler footer** — labeled "In My Org Butler", normal document flow (not pinned to bottom)
- **Slide backgrounds** — alternating white/warm, Tip 4 is blue accent, Tip 6 is purple accent

---

## Open Items / Next Steps

1. **Showcase images** — All 7 showcases currently have placeholder divs. Need actual screenshots from My Org Butler demos.
2. **Butler text refinement** — Robert wants shorter text, fewer class names, more about what the feature DOES (e.g. "modify, read data and metadata using two APIs")
3. **Bullet text compression** — Robert wants shorter, bigger-font bullets with more compressed meaning
4. **Bullet font size** — May need to increase from current 2.4rem
5. **Showcase crop control** — Robert wants ability to adjust horizontal crop position per slide (was started with `--crop-x` CSS variable but reverted)
6. **Butler positioning** — Robert wants butler pinned to bottom-left of each slide (was started but broke layout)

---

## Version History

| Commit | Description |
|--------|-------------|
| `32a2ce3` | BROKEN state — layout completely broken by flex/padding changes |
| `f9b795d` | **BASELINE** — working layout, icons removed, inline tip-num, clean |
