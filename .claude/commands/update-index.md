Update the entries index table in README.md by scanning the `entries/` directory.

Follow these rules:

1. Scan all files under `entries/` — they are organised as `entries/{year}/{MM}-{month}.md`.
2. Determine the current month using today's date.
3. For any month file **earlier than the current calendar month** (i.e. the month is over), add a single row linking to that file.
4. For the **current month's file**, read it and extract every day heading matching `## YYYY-MM-DD`. Add one row per day heading, linking directly to that heading anchor.
5. Sort all rows in descending date order (newest first).
6. Write the result into README.md as a Markdown table under a `## Entries` section. Create the section if it doesn't exist, or replace it if it does. The table should have two columns: `Date` and `Link`.

Anchor format for day links: `entries/{year}/{MM}-{month}.md#{YYYY-MM-DD}` (lowercase, hyphens only).
Link format for whole-month links: `entries/{year}/{MM}-{month}.md`

Example table:

| Date | Link |
|------|------|
| 2026-04-15 | [2026-04-15](entries/2026/04-april.md#2026-04-15) |
| 2026-04-10 | [2026-04-10](entries/2026/04-april.md#2026-04-10) |

After updating README.md, show the user the updated table and ask if they'd like to commit.
