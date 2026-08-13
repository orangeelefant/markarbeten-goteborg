# CLAUDE.md

Project context for Claude Code sessions in this repository.

## What This Is

Webraketen — joint regional guide for markarbeten Göteborg (ES Sten + MS Entreprenad)

**Live:** https://esstenochanlaggning.se

## Stack

Ingen kod ännu. Repot innehåller bara dokumentation och designkontrakt — sajten är inte byggd.

## Layout

- `DESIGN.md` — designkontraktet
- `ABOUT.md`, `README.md` — bakgrund
- Ingen `src/`, ingen `package.json`

## Commands

```bash
Inga. Repot har inget bygge ännu.
```

## Conventions

- Match existing patterns; don't introduce new abstractions without reason.
- Keep files under 500 lines.
- Swedish copy for client-facing text unless otherwise specified.
- Secrets live in `~/.secrets` and are referenced via `${VAR}`.

## Definition of Done

A change is done when:

1. Code works (built and verified locally).
2. `CHANGELOG.md` updated under `[Unreleased]`.
3. `TODO.md` reconciled (completed items removed or ticked, follow-ups added).
4. Committed and pushed to `main`.

See `AGENTS.md` for the full agent contract.
