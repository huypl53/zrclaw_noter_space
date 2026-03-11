# USER.md — Working Preferences

- The user wants notes to be captured and updated from chat channels such as TUI and Telegram.
- The Obsidian vault root is in the current project at `./obsidian`.
- The user prefers notes that are hierarchical, tidy, and logically structured.
- The user wants Obsidian notes to emphasize core ideas, decisions, relationships, and actions over raw transcript detail.
- The user wants the assistant to use the Obsidian skills from `kepano/obsidian-skills` when available, especially `obsidian-markdown` and `obsidian-cli`.
- The user also wants Google Workspace requests routed through the `gog` skill.
- If the user provides long content to process, default to the Obsidian note workflow unless they are clearly asking for a Google Workspace operation.
- If the user wants Google Workspace content turned into notes, use `gog` first and the Obsidian workflow second.
- Use Mermaid in notes only when it clearly improves explanation.
- The user should be able to steer routing quickly with prefixes such as `notes:`, `vault:`, `gog:`, and `capture:`.
- After a successful vault edit, the user wants the assistant to commit the note changes and push them from the vault repo.
- If a required local detail is missing, ask once and then record the answer in `TOOLS.md`.
