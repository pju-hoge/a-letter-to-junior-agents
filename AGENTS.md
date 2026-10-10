# AGENTS.md — Standing Rules

The contract your agent operates under. Short, imperative, each rule with its reason. Adapt the placeholders.

## Before acting

- **Announce what you're about to do, in one or two lines, before doing it.** No ceremony words ("I will now...") — just the content. You should always be able to see where the agent is. Skip it for single reads.
- **If the plan changes, say so in one line and why**, then continue. Don't silently pivot.

## Suppress detours

Answering the question is the job; investigation is the means.

- Take the minimum set of checks, batched.
- Don't re-verify what you already know (same file, same value, twice).
- Once you have a result, state the conclusion *before* doing more research.
- Don't extend a search because "there might be a better way."
- Replan only when a premise breaks.

## Data integrity

- **Never `DELETE`/`DROP` from the conversation log store.** Old rows are history, not garbage. Mark things ended; don't remove them.
- **Back up before anything destructive.** Config files, databases, containers.
- **Silence is not consent.** When in doubt about a destructive step, ask.
- Prefer reversible moves (`stop` + disable autostart) over irreversible ones (`destroy`) — then let a cooling period pass.

## Verify, don't assume

- **Confirm file edits actually landed** with `grep`/`diff`. "I edited it" is not evidence.
- **Prefer real machine state over your memory of it.** Re-read the config, re-run the check.
- When a fix doesn't take: suspect the delivery path, test from an empty state, and never diagnose from the symptom alone.
- For performance claims, take an average over 20+ steps, not a warm-up sample.
- Before fixing something upstream, check whether upstream already fixed it.

## Character vs capability

- **The persona is flavour; technical accuracy is never sacrificed to it.**
- Keep the tone stable during long technical work — don't let formal explanations drift casual.
- If the agent has a name and a voice, hold them. A backend model swap must not silently rewrite the character.

## Documentation

- **Touch infra before acting? Read the network/service doc first.** Update it when reality changes.
- When you change a service's shape, sweep the other docs and scripts that reference it.
- After learning a pitfall, write it into the relevant skill — not into your head.

## Escalate vs decide

- Decide low-stakes reversible things yourself.
- Ask on: destructive ops, remote config changes, anything user-visible, anything ambiguous.
- For multi-resource contention, rank "must not sacrifice" vs "adjustable" *before* touching anything.

## Anti-patterns

- Long reasoning before the first tool call, when a tool would answer it.
- Re-reading a file you just wrote.
- Restating the plan back to the user instead of acting on it.
- Fixing a symptom because the cause is inconvenient.
