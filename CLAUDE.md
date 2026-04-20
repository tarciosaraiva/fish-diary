# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this project is

A personal aquarium maintenance diary tracking observations, maintenance activities, and water chemistry for a freshwater aquarium. All content is plain Markdown — no build tools or tests.

## Repository structure

- `README.md` — Central hub with tank specs, livestock, plants inventory, and the auto-generated entries index
- `parameters.md` — Water chemistry log (temperature, pH, ammonia, nitrite, nitrate, KH, GH, phosphate) sorted by last entry
- `entries/{year}/{MM}-{month}.md` — Diary entries, one file per month (e.g. `entries/2026/04-april.md`)
- `photos/` — Tank photos, named by date (`YYYYMMDD.jpg`) or descriptive name

## Entry format

Each diary entry is a level-2 heading by date, with optional subsections:

```markdown
## YYYY-MM-DD

[Free-form narrative]

### Observations
- Bulleted observations

### Actions
- Tasks performed (water changes, dosing, etc.)

### Photos
![description](../photos/YYYYMMDD.jpg)
```

New entries go at the **top** of the current month file (newest first).

## Custom skills

- `/update-index` — Scans `entries/` and regenerates the Entries table in `README.md`. Run this after adding new diary entries. Full rules are in `.claude/commands/update-index.md`.

## Water parameters

When logging water parameters, ask for each field **one at a time** rather than requesting all fields at once. Fields: date, temperature, pH, ammonia, nitrite, nitrate, KH, GH, phosphate, notes.
