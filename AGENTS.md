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

### Publishing documentation changes for review
For any task that changes GitBook-synced documentation content, use the **cr-create** skill (full instructions: https://gitbook.com/docs/skill/cr-create.md) to open a GitBook change request directly via the API, rather than committing Markdown files straight to this repo:

1. `GET /spaces/<space>/content/pages` to find the target page's ID, or confirm the page is genuinely new.
2. **Editing an existing page** — `update_page`: `{"operation":"update_page","page":"<pageId>","document":{"markdown":"…"}}`. This replaces the whole page. Strip the leading `# Title` line before pushing (the title is stored separately) — pushing it back duplicates the heading.
3. **Adding a new page** — `insert_page`: `{"operation":"insert_page","title":"…","document":{"markdown":"…"},"into":"<parentPageId>"}`. Only omit `into` if the page truly belongs at the space root.
4. Push via `POST /spaces/<space>/change-requests/<cr>/content` with a `changes` array — both operations above can go in the same call.
5. Report back **both** links: the CR editor link (`urls.app`) and the rendered site preview link (resolved via the site behind the space) — don't stop at just the editor link.
6. Respect the skill's confirmation gates (creating the CR, requesting reviewers). Don't skip them in an unattended session — if you can't get explicit confirmation, stop and report what you were about to do instead of proceeding anyway.

When this path is used, **do not hand-edit SUMMARY.md.** Page structure lives in the change request, not the repo file — GitBook updates SUMMARY.md on the Git side automatically once the change request merges.

### Editing files directly in this repo (fallback only)
Only bypass the change-request flow above — editing Markdown files directly in this repo — if cr-create genuinely isn't usable (no `GITBOOK_TOKEN`, no network access to `api.gitbook.com`, or the task explicitly asks for a plain git-based edit). In that case:

- When creating a new page, add a corresponding entry to `SUMMARY.md` in the same commit. Before writing the entry:
  1. Open the current `SUMMARY.md` and find the section the new page belongs with (same folder or topic as an existing entry).
  2. Match that section's exact bullet and indentation style character-for-character — don't invent a new indent width.
  3. Use the format `* [Page Title](relative/path/to/file.md)`, with `Page Title` matching the page's actual H1 heading.
