# Recommended skills

Skills are the agent's procedural memory — a named procedure it loads only when relevant. These are the ones worth copying into `~/.hermes/profiles/<you>/skills/` to start. Not exhaustive; a starting shelf.

Copy them, then **rewrite the placeholders** for your own machines and services. A skill that still says someone else's hostname is worse than no skill.

## Worth having from day one

| Skill | Why |
|-------|-----|
| **book-to-skill** | Low frequency, high importance. Turns a book/PDF into a durable skill. The best knowledge you own, made operational. |
| **obsidian** | Read/search/create/edit vault notes. The backbone of the shared workspace. |
| **session-diary** | Daily diary + greeting pipeline. This is what makes the agent feel continuous rather than episodic. |
| **cron-job-health** | Systematically verify scheduled jobs. Catches silent failures before they compound. |
| **memory-organization** | Decides what stays in memory vs a skill vs long-term store. Keeps memory from rotting. |
| **systematic-debugging** | Root-cause discipline: understand before fixing. |
| **web-research** | Gather, attribute, and cite from the web properly. |

## Useful once you're settled

| Skill | Why |
|-------|-----|
| **grounded-citations** | Force answers and documents to be traceable. |
| **product-price-monitor** | Watch a product/flight/listing and alert on a target. |
| **document-to-action-items** | Pull cited obligations and deadlines out of documents. |
| **meeting-action-items** | Decisions, owners, tickets from meeting notes. |
| **subscription-management** | Track recurring spend and renewal dates. |
| **ocr-and-documents** | Get text out of PDFs and scans. |
| **blocked-page-recovery** | When a fetch hits a 403/paywall/bot wall. |
| **investigation-report** | Structured write-up of a technical investigation. |
| **requesting-code-review** | Pre-commit security and quality gate. |

## Domain-specific (swap for yours)

If you work in a specific field, write skills for *your* recurring tasks. Examples from here: a clinic reservation flow, a vault maintenance pipeline, a remote-image-gen runner, a benchmark harness.

The pattern to follow: one skill per recurring task, trigger-first description, deterministic commands inline, pitfalls at the bottom.

## How to write a good skill

- **Description first line = the trigger**, under ~60 chars, ends with a period.
- Put the *procedure* in the body; put *why* next to each step.
- Include the exact commands — don't make the agent re-derive them.
- Record pitfalls as you hit them, with the reason.
- Keep one concern per skill; split when it sprawls.

## Anti-pattern

Don't copy 100 skills on day one. Start with the "day one" table, then add only when you actually repeat a task three times.
