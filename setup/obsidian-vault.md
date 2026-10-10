# Sharing an Obsidian vault with your agent

The single highest-leverage thing in this kit. Give the agent a workspace it **writes into**, not just reads. Its thinking becomes reviewable, editable, and permanent — and the two of you stop starting from zero.

## Why a vault and not chat

Chat scrolls away. A vault accumulates. When the agent files its work as notes, you can read it calmly, correct it, and build on it next week. That's co-working; chat alone is just Q&A.

It also gives the agent somewhere to put *drafts* of thought, which is where the interesting material lives.

## Shape

```
vault/
  AGENTS.md            # folder conventions + file-back rules
  META.md              # cross-session preferences and lessons
  00_Inbox/            # new notes, unfiled
  10_Memo/  20_Study/ 30_Ideas/ 40_Life/ 50_Hobby/
  60_Projects/ 70_Tech/ 80_History/ 90_People/
  95_Thinking/         # unfiled thought / dialogue notes
  99_Code/             # generated scripts
```

Numbered prefixes keep sort order stable. Keep the categories boring.

## Rules to write into the vault's `AGENTS.md`

- New notes go to the inbox; **edit existing notes in place**.
- Every note gets frontmatter (`category`, `tags`, `description`, `created`, `source`).
- Add `[[wikilinks]]` to related notes.
- A "thinking" folder is exempt from auto-classification — move notes out only when they mature.
- Ask before filing a synthesis as a permanent note.

## File-back convention

When a query produces a cross-file synthesis worth keeping, propose a note with proper frontmatter and links. Ask first, then write.

## Maintenance

Run a nightly pipeline: auto-tag → re-folder → generate maps of content → lint (orphans, broken links, missing frontmatter). Deterministic scripts, not model calls, for the mechanical parts.

Keep generated code **outside** the vault and git-manage it there; the vault holds notes, not build artifacts.

## Sync

Use the vault's own sync (e.g. a continuous sync daemon) so edits from the agent appear on your devices. Don't hand-roll rsync per task.

## Pitfalls

- **Never let the agent `rm -rf` inside the vault without checking.** Symlinked directories are a classic footgun — `ls -ld` first; if it's a link, the real path is elsewhere.
- **Don't dump raw transcripts.** Write the distilled version.
- **Frontmatter matters** for search; a note without it is invisible to the pipeline.
- Keep image assets out of the vault if the vault is cloud-synced and large.

## Related

Pair this with [`hindsight.md`](hindsight.md): the vault holds edited artifacts, Hindsight holds the searchable long tail. The nightly job imports the vault diff into Hindsight.
