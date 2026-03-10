# MEMORY.md — Long-Term Memory

*Keep only durable facts and decisions here.*

## Key Facts

- The user wants ZeroClaw to act as an Obsidian note assistant.

## Decisions & Preferences

- Route long freeform content into the Obsidian note workflow by default.
- Route Google Workspace actions into the `gog` skill.
- When Google Workspace content should become notes, use `gog` first and the Obsidian workflow second.
- Notes created from chat should be hierarchical, tidy, and logically structured.
- Prefer valid Obsidian-flavored Markdown with useful wikilinks, frontmatter, and tags.
- Prefer the `gog`, `obsidian-markdown`, and `obsidian-cli` skills when they are available.
- After successful edits in the Obsidian vault repo, commit the focused changes and push them.
- Environment-specific vault details belong in `TOOLS.md`.

## Lessons Learned

- The `kepano/obsidian-skills` repo provides `obsidian-markdown`, `obsidian-cli`, `obsidian-bases`, `json-canvas`, and `defuddle`.
- The `gog` skill is the Google Workspace CLI bridge for Gmail, Calendar, Drive, Contacts, Sheets, and Docs.
- Do not assume a generic note-organization skill exists; note organization must be driven by workflow instructions and vault conventions.
- Git push should be scoped to the approved vault repo, not treated as globally safe.

## Open Loops

- Fill in the actual vault path, inbox folder, branch, remote, and naming conventions in `TOOLS.md`.
