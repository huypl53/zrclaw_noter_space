# TOOLS.md — Local Notes

This file is for machine-specific details that the assistant should not guess.

## Obsidian Vault Setup

- Vault path: `./obsidian`
- Vault name: `TODO`
- Default inbox or staging folder: `TODO`
- Preferred top-level folders: `TODO`
- Default remote: `origin`
- Default branch: `main`
- Push policy: pushing note commits from the approved vault repo is routine behavior
- Obsidian CLI available: `TODO`
- Obsidian app running requirement: `obsidian-cli` needs a running Obsidian instance
- `gog` installed and authenticated: `missing`
- Default Google account for `gog`: `TODO`
- Installed skills to prefer: `gog`, `obsidian-markdown`, `obsidian-cli`, `defuddle`

## Workflow Notes

- Save note files under `./obsidian` unless the user explicitly names another destination.
- Check whether the target note already exists before creating a new note.
- Extract core ideas and structure before polishing wording.
- Reuse the existing vault hierarchy before creating new folders or naming schemes.
- If you establish a new taxonomy rule, also record it in `MEMORY.md`.
- Commit only the files touched for the current note task.

## Prompt Classification Hints

- Long user content plus "process", "organize", "summarize", "clean up", or "turn this into notes" means Obsidian-first.
- Gmail, Calendar, Drive, Contacts, Sheets, or Docs actions mean `gog`.
- Google Workspace content that should be stored in the vault means `gog` first, then Obsidian.
- If a request needs both retrieval and note creation, do not stop after retrieval. Finish the note workflow.
- Use Mermaid only when the note benefits from a visual flow, relationship map, or sequence explanation.

## Prompt Shortcuts

- `notes:` or `obsidian:` — note writing, note cleanup, and long-content distillation.
- `vault:` — direct vault operations.
- `gog:` — Google Workspace actions.
- `capture:` — retrieval first, note creation second.

## Tool Hints

- `shell` — git status, add, commit, push, and local diagnostics.
- `gog` — Gmail, Calendar, Drive, Contacts, Sheets, and Docs operations.
- `file_read` — inspect existing notes, indexes, and templates before editing.
- `file_write` — apply focused note edits when direct file changes are the right approach.
- `memory_store` — save durable note conventions and vault workflow decisions.
- `memory_recall` — fetch prior note structure decisions and user preferences.
- `memory_forget` — remove stale or incorrect durable memory entries.

## Fill This In

- Put the real vault path, branch, remote, inbox folder, and naming conventions here.
- If the vault has special rules for daily notes, project notes, or meeting notes, document them here.
