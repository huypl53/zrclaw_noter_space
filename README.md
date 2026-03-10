# ZeroClaw Obsidian Assistant Workspace

This repository is a prompt workspace for a ZeroClaw assistant that:

- receives requests from chat channels such as TUI and Telegram
- turns long or messy user input into tidy Obsidian notes centered on core ideas
- uses Google Workspace through `gog` when the task is about Gmail, Calendar, Drive, Contacts, Sheets, or Docs
- commits and pushes note changes from the Obsidian vault repo after successful edits

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

## Current Setup Gaps

- `TOOLS.md` still needs the real vault path, inbox folder, branch, remote, and naming conventions.
- `gog` skill is present, but the `gog` CLI is not installed on this machine yet.
- `obsidian-cli` workflow depends on a running Obsidian instance.

## Notes

- The routing rules are defined in `AGENTS.md`.
- The assistant should classify tasks by user intent, not just keywords.
- The assistant should extract core ideas first and use Mermaid only when it materially improves understanding.
- If a request combines Google Workspace retrieval with note creation, the assistant should complete both parts of the workflow.
