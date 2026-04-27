# CzechDreamin 26 — Editable Texts

Edit any text below. Tell Claude "übernimm die Texte" and the HTML gets updated.
Structure mirrors the slide order in `czechdreamin-26.html`.

---

## Nav (top bar, all slides)

- **Brand:** CzechDreamin 26 — Agentic now!

---

## Slide 0 — Cover

- **Speaker name:** Robert Sösemann
- **Speaker title:** Director of Engineering & AI Lead at Aquiva
- **Title (h1):** Agentic now!
- **Subtitle:** How to make the best out of Agentforce

---

## Slide 1 — Intro: "Agentforce now. Here's why"

- **Headline prefix (orange):** Agentforce now.
- **Headline rest:** Here's why

**Bullets** (each has a bold blue lead phrase + explanation):

1. **Agentic is a must.** Software stops being automated — it becomes conversational and autonomous.
2. **Salesforce is only doing Agentforce.** Everything else is on hold. This is where the platform is heading.
3. **It works.** At Aquiva, our customers moved past PoCs. They're in production and coming back.
4. **Still simple today.** AgentScript will add real complexity. Learn the basics while you can.

**Butler footer:** All our learnings, open source. → github.com/aquivalabs/my-org-butler

---

## Slide 2 — Tip 1: Fewer but more powerful actions

- **Headline:** Fewer but more powerful actions

**Bullets:**
1. 2 generic actions replace dozens of hardcoded ones.
2. If you script every step, you don't need AI.
3. More power, less guardrails. Generic actions are harder to control.
4. Same for topics. Jobs-to-be-done thinking leads to hundreds. One broad topic is better.

**Butler footer:** `ExploreOrgSchema` + `QueryRecordsWithSoql` — two actions handle what would need dozens.

---

## Slide 3 — Tip 2: Supercharge actions with APIs

- **Headline:** Supercharge actions with APIs

**Bullets:**
1. One API call is a function. A chain of them is a program.
2. REST API for data, Metadata API for config — your agent can touch everything.
3. It creates records, reads rules, deploys changes. No code, just conversation.

**Butler footer:** `CallRestApi` + `CallMetadataApi` — read data, change config, all from a conversation.

---

## Slide 4 — Tip 3: Use Data Cloud for grounding

- **Headline:** Use Data Cloud for grounding

**Bullets:**
1. Semantic queries: "Find deals similar to Acme" — no WHERE clause can do that.
2. RAG on files: answer questions from your doc library, not from hallucinations.
3. Data Cloud Foundations is free. Start today.

**Butler footer:** `QueryDataCloud` for semantic search, `AnswerFromDataLibrary` + `AnswerWithCurrentFile` for files.

---

## Slide 5 — Tip 4: Let your agent learn with memory

- **Headline:** Let your agent learn with memory

**Bullets:**
1. Every conversation starts from scratch. Brilliant consultant with amnesia.
2. Persist preferences, decisions, tasks across sessions.
3. Memory turns a tool into a colleague.

**Butler footer:** `LoadCustomInstructions` + `StoreCustomInstruction` — persistent preferences, zero code.

---

## Slide 6 — Tip 5: Headless agents work while you don't

- **Headline:** Headless agents work while you don't

**Bullets:**
1. Scheduled, triggered, autonomous — the real value runs behind the scenes.
2. Humans in the loop only when needed.
3. Chat is how you demo it. Headless is how you ship it.

**Butler footer:** `HeadlessAgent` + `PlanForLater` — "Every Monday, check stale opps and Slack me."

---

## Slide 7 — Tip 6: Testing Center is not enough

- **Headline:** Testing Center is not enough

**Bullets:**
1. One topic? Topic match is always 100%. Action order? Smart agents find different routes.
2. The LLM judge is a black box. No multi-turn. No data reset between tests.
3. Salesforce will fix this — eventually. Until then: `promptfoo` (just acquired by OpenAI).

**Butler footer:** `promptfoo` evals with `o3-mini` as judge + a Claude Code skill to run them.

---

## Slide 8 — Summary: What I didn't cover (blue accent)

- **Headline:** What I didn't cover

**Bullets:**
1. Packaging agents is painful — Agent Templates have no upgrade path.
2. AgentScript is coming. Migration won't be simple.
3. Lorem ipsum — placeholder for more topics.

**Butler footer:** Packaging, DevOps, testing and more — it's all in the repo.

---

## Slide 9 — Closing

- **Headline:** Danke! Feedback?
- **Speaker name:** Robert Sösemann
- **Speaker title:** Director of Engineering & AI Lead at Aquiva
- **QR code target:** (currently encodes a link — tell Claude if you want to change the URL)
