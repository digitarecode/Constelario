# Constelario

Constelario is a curated family cultural-discovery product for music, film, series, documentaries, and books.

Its purpose is not to replace streaming services or become a social network. It gives families a trustworthy map for discovering culture, understanding context, recording progress, and creating shared memory.

## Current phase

The project is in product-foundation and navigation-design. Music is the first complete vertical slice. Frontend implementation starts only after the navigation model, media variants, content contracts, and acceptance criteria are approved.

## Source of truth

| Concern | Authority |
|---|---|
| Product contracts, architecture, ADRs, schemas, QA | This GitHub repository |
| Editorial catalog and curation workflow | Notion |
| Human-readable dossier and original assets | Google Drive |
| Preview hosting during the first implementation | Lovable |

Notion is an editorial source, not a runtime database. Spotify and iBroadcast are discovery/import inputs, not canonical authorities.

## Start here

1. Read [`docs/PROJECT_FOUNDATION.md`](docs/PROJECT_FOUNDATION.md).
2. Read [`docs/HANDOFF.md`](docs/HANDOFF.md).
3. Complete the readiness response required by [`AGENTS.md`](AGENTS.md).
4. Wait for acceptance by the architecture lead before changing product code or contracts.

## Working agreement

- `main` is stable.
- Work happens in focused branches and pull requests.
- Decisions that change a contract require an ADR.
- No secrets, personal playlists, tokens, or private Notion data are committed.
- The repository intentionally has no public license while it remains private.

