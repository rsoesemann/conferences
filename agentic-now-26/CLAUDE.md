# Agentic now! — How to make the best out of Agentforce

Robert Soesemann · Aquiva · CzechDreamin May 29, 2026
Demo repo: github.com/aquivalabs/my-org-butler


## Format

Scrollable HTML presentation (not PPTX). File: `czechdreamin-26.html`
- Full-viewport slides with CSS scroll-snap
- Arrow key navigation, slide counter
- Must look like PowerPoint at 100% browser zoom
- Aquiva branding (logo says "AQUIVA" — no "Labs")
- CzechDreamin branding: conference bar at top
- Skill file: `aquiva-slides.skill` documents the HTML approach, brand, layout rules


## Slide Structure (10 slides, 0-indexed)

0. **Cover** — photo (robert.jpeg, round), "Agentic now!", subtitle, blue bar, Aquiva logo
1. **Intro** — "Agentforce now. Here's why." — why tips, who I am, Aquiva intro, My Org Butler
2. **Tip 1** — "Fewer but more powerful actions"
3. **Tip 2** — "Supercharge actions with APIs"
4. **Tip 3** — "Use Data Cloud for grounding" *(needs better title)*
5. **Tip 4** — "Let your agent learn with memory"
6. **Tip 5** — "Headless agents work while you don't"
7. **Tip 6** — "Testing Center is not enough"
8. **Summary** — "What I didn't cover" *(blue accent slide)*
9. **Closing** — photo, "Danke! Feedback?", QR code


## Tip Slide Structure

Each tip slide has:
- **Top:** Icon + "TIP N" label + short punchy title (a real tip, not a topic description)
- **Middle:** Two-column layout — bullets on left, iframe mock on right
- **Bottom:** "IN MY ORG BUTLER" footer — concrete action names

Mocks are iframes in `mocks/` folder, auto-scaled to fill container.
Image placeholders = dashed boxes → replace with screenshots before talk.


## Action Names in My Org Butler

- Tip 1: `ExploreOrgSchema`, `QueryRecordsWithSoql`
- Tip 2: `CallRestApi`, `CallMetadataApi`
- Tip 3: `QueryDataCloud`, `AnswerFromDataLibrary`, `AnswerWithCurrentFile`
- Tip 4: `LoadCustomInstructions`, `StoreCustomInstruction`
- Tip 5: `HeadlessAgent`, `PlanForLater`, `NotifyUser`
- Tip 6: Claude Code skill for promptfoo testing


## Open Items — Presentation

- [ ] Tip 3 title "Use Data Cloud for grounding" is bland — needs a punchy tip-style title
- [ ] "What I didn't cover" bullets are placeholders — Robert will add more topics (current: packaging, AgentScript)
- [ ] Closing "Danke! Feedback?" — Robert hasn't explicitly approved
- [ ] mock-tip2: validation rule scenario implemented but not yet confirmed final by Robert
- [ ] mock-tip3: shows Opportunity SOQL vs hybrid search — actual tests use conversation data, decide if mock stays conceptual
- [ ] mock-tip5 (memory): verify action names match `LoadCustomInstructions` + `StoreCustomInstruction`
- [ ] mock-tip7 (testing): consider adding promptfoo output panel
- [ ] Replace all screenshot placeholders with actual demo screenshots
- [ ] Verify even/odd alternating slide backgrounds look right
- [ ] Test full presentation in browser: all slides, navigation, iframe scaling, Safari fullscreen


## Open Items — my-org-butler repo

From GitHub issue #49 (Data Library chunking):

- [ ] Data Library chunking fails in scratch orgs — no reliable test data for Tip 3 demo
- [ ] QueryDataCloud / AnswerFromDataLibrary need scratch org setup docs or test fixture

From Tip 2 demo scenario:

- [ ] Validation rule `HighValue_Pipeline` (Amount > 100000 AND Probability < 50) needed for demo — create unpackaged or document as manual setup step
- [ ] Confirm whether External Services GitHub integration is still planned (Anmol TODO, may be dropped)

General:

- [ ] Claude Code skill for promptfoo testing — already exists in repo, mention in Tip 6 footer


## Visual Notes

- Butler bar: compact (icon 32px, 1.3rem text, bottom 1.2rem)
- Bullets: 2.2rem
- Mock width: 56%, fade gradient 400px, top 3.4rem
- Title text-shadow for readability over mocks; disabled on blue slide (`.slide-tip-blue .tip-h`)
- Speaker photo: robert.jpeg, 100px on cover, 120px on closing, both round with white border
- Two accent slides: Summary blue gradient (no other slides use blue or dark)
