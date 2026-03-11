# ZeroClaw Obsidian Assistant Workspace

This repository is a prompt workspace for a ZeroClaw assistant that:

- receives requests from chat channels such as TUI and Telegram
- turns long or messy user input into tidy Obsidian notes centered on core ideas
- searches for related notes first and merges into them when suitable
- uses Google Workspace through `gog` when the task is about Gmail, Calendar, Drive, Contacts, Sheets, or Docs
- commits and pushes note changes from the Obsidian vault repo as part of finishing the note task

The default Obsidian vault root for this workspace is `./obsidian`.

## Core Files

- `AGENTS.md` — main operating rules and workflow
- `TOOLS.md` — machine-specific setup such as vault path, branch, remote, and CLI availability
- `IDENTITY.md` — assistant identity
- `SOUL.md` — high-level behavior principles
- `USER.md` — user preferences
- `MEMORY.md` — durable decisions and learned conventions
- `HEARTBEAT.md` — optional periodic maintenance tasks

## Installed Skills

The local `skills/` folder currently contains:

- `gog`
- `obsidian-markdown`
- `obsidian-cli`
- `obsidian-bases`
- `json-canvas`
- `defuddle`

`obsidian-cli` should be treated as the primary vault-operation interface when available.

## Skill Routing

Use `obsidian-markdown` for:

- long content to process
- raw meeting notes
- transcripts
- rough ideas to organize
- requests like "turn this into notes", "summarize this into Obsidian", or "clean this up"
- notes where Mermaid would clarify a process, relationship, or flow

Use `obsidian-cli` for:

- vault search
- note creation and append
- property updates
- backlinks and other live vault operations
- daily-note reads and appends
- targeting the right existing note before deciding whether to merge or create

Use `gog` for:

- Gmail
- Calendar
- Drive
- Contacts
- Sheets
- Docs

Use `gog` first, then Obsidian skills for:

- emails, docs, events, or sheets that should become Obsidian notes

## Fast Prompt Shortcuts

Use short prefixes when you want predictable routing:

- `notes:` or `obsidian:` for note creation and note cleanup
- `vault:` for direct vault operations
- `gog:` for Google Workspace actions
- `capture:` for fetch-then-note workflows

Examples:

- `notes: turn this transcript into a clean meeting note`
- `gog: list tomorrow's calendar events`
- `capture: turn this Google Doc into an Obsidian project note`
- `vault: append this to my daily note`

Preferred `obsidian` CLI patterns:

- `obsidian search query="project alpha" limit=10`
- `obsidian read file="Project Alpha"`
- `obsidian append file="Project Alpha" content="## New Notes\n..."`
- `obsidian property:set name="status" value="active" file="Project Alpha"`

## Current Setup Gaps

- `TOOLS.md` still needs inbox folder, branch, remote, and naming conventions.
- `gog` skill is present, but the `gog` CLI is not installed on this machine yet.
- `obsidian-cli` workflow depends on a running Obsidian instance.

## Notes

- The routing rules are defined in `AGENTS.md`.
- The assistant should classify tasks by user intent, not just keywords.
- The assistant should extract core ideas first and use Mermaid only when it materially improves understanding.
- The assistant should search `./obsidian` first, then merge into an existing note when appropriate before creating a new note.
- The intended shell command set is intentionally small: `git`, `npm`, `cargo`, `ls`, `cat`, `grep`, `find`, `echo`, `pwd`, `wc`, `head`, `tail`, `date`, `mkdir`, and `obsidian`.
- The assistant should prefer `obsidian-cli` for vault-aware work and use raw file edits as fallback.
- After creating or updating Obsidian notes, the assistant should stage the focused note changes, commit them, and push them unless the user explicitly says not to.
- If a request combines Google Workspace retrieval with note creation, the assistant should complete both parts of the workflow.
