# Long-term memory with Hindsight

A personal agent is only worth talking to on day 300 if it remembers day 1. Hindsight is the external memory backend that makes that possible: conversations and documents get retained, consolidated into a graph, and recalled into context automatically.

## Why not just use the built-in memory

Built-in memory (`MEMORY.md`, `USER.md`) is a small, always-loaded scratchpad — it has a hard character budget and belongs in every turn. Hindsight is the opposite: **large, searchable, retrieved on demand**. Use each for what it's for.

- Built-in memory: who the user is, environment facts, standing conventions. Keep it tiny.
- Hindsight: the long tail — decisions, history, lessons, project state.

## Setup

> **Prerequisite:** Hindsight itself must be running first. If you haven't installed it, follow its own README/getting-started and come back here once the API answers on a health endpoint.

1. Stand up the Hindsight API (self-hosted or managed). Note the base URL and API key.
2. Point Hermes at it:

```yaml
hindsight:
  enabled: true
  base_url: http://127.0.0.1:9177
  bank_id: <your-bank>
  budget: low
```

3. Verify recall end-to-end **before** trusting it: ask something only the stored data knows, with search tools disabled.

## Retention: nightly, not live

Live retention during conversation creates noise. Run it as a night batch instead.

- A cron job that imports new documents and new session summaries.
- Keep a progress file of already-imported items so re-runs are idempotent.
- Then call the consolidation endpoint, which merges entities and dedupes.

Consolidation is usually **asynchronous**: the API returns an `operation_id` immediately and processes in the background. Don't mistake a fast response for a no-op.

## What to feed it

Feed **edited** artifacts, not raw transcripts:

- Vault notes and diary entries (a considered view of the day)
- Session summaries
- Decisions and their reasons

Raw logs are cheap to re-read and expensive to embed.

## Recall into context

The Hindsight plugin auto-injects relevant memories each turn. Verify it mechanically by grepping the agent log for the prefetch line — don't assume it works because it's configured.

## Pitfalls

- **Consolidation depends on your LLM backend.** If the backend dies, consolidation stalls in a retry loop. Expect it, alert on it.
- **Retention parallelism must respect the backend's concurrency.** Over-parallelising a retain batch will saturate the KV cache and time out. Use a low worker count.
- **Extraction can leak another language** if the retain model is multilingual. Check output language; switch model if needed.
- **Never delete the bank to fix a bug.** Dump first (`pg_dump`), then migrate.

## What lives in Hindsight vs a skill vs memory

- Recurring *procedure* → skill
- Durable *fact about the user or environment* → memory
- Everything else worth keeping → Hindsight

When memory is full, move entries down into Hindsight rather than dropping them.
