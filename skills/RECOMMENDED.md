# Recommended skills

Skills are the agent's procedural memory — a named procedure it loads only when relevant.

**Important:** this list is limited to skills a reader can actually obtain. Every entry here comes from a shipped or third-party source (Hermes' bundled set, the skills hub, or an upstream repo) — *not* something hand-written for one particular setup. If a skill only exists in someone's profile, a newcomer can't get it, so it doesn't belong here.

Obtain them via the skills hub / your Hermes install, then **rewrite the placeholders** for your own machines. A skill that still says someone else's hostname is worse than no skill.

## Worth having from day one

| Skill | Source | Why |
|-------|--------|-----|
| **book-to-skill-intake** | Hermes Agent | Low frequency, high importance. Turns a book/PDF into a durable skill — your best knowledge, made operational. |
| **obsidian** | Teknium, Hermes Agent | Read/search/create/edit vault notes. The backbone of a shared workspace. |
| **systematic-debugging** | adapted from obra/superpowers | Root-cause discipline: understand before fixing. |
| **writing-plans** | adapted from obra/superpowers | Plan before code; bite-sized tasks with paths. |
| **requesting-code-review** | adapted from obra/superpowers | Pre-commit security and quality gate. |

## Useful once you're settled

| Skill | Source | Why |
|-------|--------|-----|
| **test-driven-development** | adapted from obra/superpowers | RED-GREEN-REFACTOR, tests before code. |
| **subagent-driven-development** | adapted from obra/superpowers | Execute plans via isolated subagents with review. |
| **github** | Ben Barclay | PRs, issues, reviews via `gh`. |
| **product-price-monitor** | Ben Barclay | Watch a product/flight/listing and alert on a target. |
| **grounded-citations** | Hermes Agent, Teknium | Force answers and documents to be traceable. |
| **ocr-and-documents** | Hermes Agent | Get text out of PDFs and scans. |
| **native-mcp** | Hermes Agent | Connect MCP servers and register their tools safely. |
| **x-search-operators** | Grok (via pju) | The operator syntax that makes X search actually precise. |

## Domain-specific

Write your own for *your* recurring tasks (a clinic booking flow, a benchmark harness, a deploy pipeline). These won't be on any shelf — and that's fine.

The pattern to follow: one skill per recurring task, trigger-first description, deterministic commands inline, pitfalls at the bottom.

## How to write a good skill

- **Description first line = the trigger**, under ~60 chars, ends with a period.
- Put the *procedure* in the body; put *why* next to each step.
- Include the exact commands — don't make the agent re-derive them.
- Record pitfalls as you hit them, with the reason.
- Keep one concern per skill; split when it sprawls.

## Anti-pattern

Don't copy 100 skills on day one. Start with the "day one" table, then add only when you actually repeat a task three times.
