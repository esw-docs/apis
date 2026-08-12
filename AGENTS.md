<!-- gitbook-agent-instructions:start -->

## GitBook Documentation Editing

This repository contains documentation synced with GitBook via Git Sync.

Before editing GitBook-synced Markdown, YAML, or asset files, make sure the GitBook skill is available and up to date in your local agent environment. Prefer installing or updating it with:

```bash
npx skills add gitbookio/gitbook-skills
```

This command may add or update local agent skill files. Use them only as local agent instructions; do not commit those installed skill files or any tool-generated agent configuration unless the user explicitly asks for it.

If `npx` is unavailable, load the skill from:

https://gitbook.com/docs/skill.md

When making changes, preserve GitBook sync metadata such as frontmatter, `SUMMARY.md`, `docs.yaml`, `.gitbook/`, and asset links unless the requested edit explicitly requires changing them.

<!-- gitbook-agent-instructions:end -->

## Project-specific rules
- When creating a new page, add a corresponding entry to SUMMARY.md in the same commit. Before writing the entry:
  1. Open the current SUMMARY.md and find the section the new page belongs with (same folder or same topic as an existing entry).
  2. Match that section's exact bullet and indentation style character-for-character — don't invent a new indent width.
  3. Use the format `* [Page Title](relative/path/to/file.md)`, with Page Title matching the page's actual H1 heading.
  Example, following this repo's existing style:
  * [Microsoft Copilot Integration Guide](microsoft-copilot-integration-guide/README.md)
    * [UCP profile setup](microsoft-copilot-integration-guide/ucp-profile-setup.md)
  A new page added to that same folder should nest under that same parent bullet, one level in, exactly like `UCP profile setup` does — not appended as a new top-level entry.
- When finishing a documentation change, use the cr-create skill to open a GitBook change request for review, linked back to this pull request.
