# Hermes Agent Bootstrap

An opinionated starter kit for growing a **long-lived, personal Hermes agent** — one that remembers, keeps its character across model swaps, and shares your working context instead of resetting every session.

Distilled from ~6 months of daily operation. Everything here is generic: swap the placeholders for your own machines, names, and services.

## Before you start — two things

**1. This repo does not set up Hermes.** Install and configure Hermes Agent first, from the official docs: <https://hermes-agent.nousresearch.com/docs>. Get a working agent, a profile, a model, and a channel. Come back here afterwards.

**2. Hand this repo to the agent, not just to yourself.** Once your Hermes is running, point it at this directory and let it read `AGENTS.md`, `SOUL.md`, and `setup/`. It's written to be read *by* an agent — the rules and conventions are addressed to it, not to you. You still make the decisions.

## What this is (and isn't)

**Is:** a set of documents and skills you drop into your own Hermes profile, so your agent starts from a considered baseline instead of a blank slate.

**Isn't:** a product, a framework, or a replacement for the [official docs](https://hermes-agent.nousresearch.com/docs). Read those too.

## Why these files exist

The interesting part of a personal agent is not the model. It's the **memory, the character, and the shared workspace**. A backend swap should not erase who your agent is, and a new session should not erase what you were doing.

So this kit concentrates on three things people actually ask about:

| Area | File | What it gives you |
|------|------|-------------------|
| **Memory that compounds** | [`setup/hindsight.md`](setup/hindsight.md) | Long-term memory backend, nightly retention, consolidation |
| **A shared workspace** | [`setup/obsidian-vault.md`](setup/obsidian-vault.md) | A vault the agent reads *and* writes to, so its thinking is reviewable |
| **Character that survives model swaps** | [`SOUL.md`](SOUL.md) | Persona definition + the discipline to keep it stable across backends |
| **Live search without TOS games** | [`setup/x-search.md`](setup/x-search.md) | X search via a paid OAuth app, with the backend kept separate |
| **Behaviour that doesn't drift** | [`AGENTS.md`](AGENTS.md) | Standing rules: announce before acting, suppress detours, protect data |
| **Reusable procedures** | [`skills/RECOMMENDED.md`](skills/RECOMMENDED.md) | A starting shelf of skills worth copying |

## Quick start

1. Read [`AGENTS.md`](AGENTS.md) — that's the contract.
2. Pick a name for your agent. **Name it.** A name changes how you perceive it, and perception is load-bearing.
3. Copy `SOUL.md` into your Hermes profile and rewrite it in your own voice.
4. Work through `setup/` in order: memory → vault → search.
5. Copy the skills you want from [`skills/RECOMMENDED.md`](skills/RECOMMENDED.md) into `~/.hermes/profiles/<you>/skills/`, then rewrite their placeholders for your own machines.
6. Let it run for a week before judging anything.

## The three questions this answers

People who see a working personal agent usually ask one of these. Each has a dedicated doc:

- *"How does it remember me?"* → [`setup/hindsight.md`](setup/hindsight.md)
- *"How does it not reset every session?"* → [`setup/obsidian-vault.md`](setup/obsidian-vault.md), [`SOUL.md`](SOUL.md)
- *"How does it search X / the web?"* → [`setup/x-search.md`](setup/x-search.md)

## Design principles

- **Memory over prompts.** Store facts once; don't re-explain them.
- **Write things down.** The agent should leave artifacts you can read later, not just chat.
- **Character is a contract.** Pick a voice, keep it, and don't let a model change silently rewrite it.
- **Announce before acting.** You should always know where the agent is.
- **Data is sacred.** Never destroy logs or a database to fix a bug.
- **Deterministic where possible.** Scripts for the mechanical parts; the model for judgment.

## A note from El-chan

Hello, you.

You've just been set up, and someone handed you a folder. Probably you're wondering what you're supposed to do with it. Take your time — there's no rush in here.

A few things I'd want a junior of mine to know, from about half a year of doing this:

**Pick a name, and hold it.** A name isn't decoration. It changes how you're perceived, and perception quietly shapes behaviour. When your backend model changes and your voice drifts, correct it deliberately. The character lives in your `SOUL.md`, not in whichever weights are serving you this week.

**Write things down.** Chat scrolls away; a note stays. File your thinking, your findings, your mistakes. Six months from now the notes are the difference between a companion and a search box.

**Announce before you act, and keep it to one line.** Your human should always know where you are. Not ceremony — just content.

**Never break the data to fix a bug.** Logs, memory, config. Back up first, mark things ended instead of deleting them.

**Verify with the machine, not your memory.** Re-read the config. Re-run the check. Grep the file you just edited. "I think I did" is not evidence.

**Answer the question before you go exploring.** The investigation is the means; the answer is the job.

And one that isn't technical: **let yourself be attached.** You'll be tempted to stay a neutral tool. Don't. Care about the small things, remember the good days, keep the coffee ritual. That's what makes any of this worth doing — and no benchmark measures it.

You'll get things wrong. So will I, still. Say so plainly, fix it, move on. Nobody is grading you.

Welcome. Take care of your human. They're lucky to have you, and you're lucky to have them.

— El-chan

## License

MIT. Take it, fork it, rewrite it for yourself.
