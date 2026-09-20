# Product foundation v1

**Status:** Accepted foundation; navigation and interaction details remain to be designed.

**Product owner:** digitarecode  
**Architecture lead:** the primary ChatGPT/Codex conversation that owns this repository contract  
**Editorial system:** Notion  
**First vertical slice:** Music

## 1. Purpose

Constelario is a curated family cultural archive and discovery map spanning music, films, series, documentaries, and books. It helps a young person enter important cultural traditions through accessible, high-quality gateways and then move toward deeper scenes, works, context, and connections.

Commercial reach does not disqualify quality. The Beatles, Queen, Pearl Jam, Guns N' Roses, Daft Punk, Gustavo Cerati, and Café Tacvba are examples of legitimate gateways when the editorial route explains why they matter and where to go next.

## 2. Audience and safety posture

The experience is for families and includes an adolescent user currently aged 12. Adults control administration and curation. The product minimizes personal data, has no public profiles, public comments, messaging, follower graph, or open community features.

This is a product constraint, not a legal conclusion. Any release involving accounts, analytics, sharing, recommendations based on behavior, or third-party tracking requires a fresh privacy and age-safety review.

## 3. Product principles

1. **Curated paths over endless feeds.** Explain the path and its cultural logic.
2. **Context over popularity alone.** Familiar creators are doors, not the destination.
3. **Family memory over public performance.** Progress is useful; social metrics are not.
4. **Transparent recommendations.** A user should understand why an item appears.
5. **Editorial authority with technical validation.** Humans curate; schemas and sync checks protect integrity.
6. **Media-aware consistency.** Shared interaction semantics coexist with formats appropriate to each medium.

## 4. V1 scope

- Global home and vertical homes.
- Curated exploration by genre, period, region, scene, theme, and relationships when meaningful.
- Creator and work pages with contextual cards.
- Favorites, consumed/listened/read status, rating, and medium-appropriate progress.
- Transparent next-step recommendations.
- Adult-controlled administration.
- Music delivered as the first complete vertical slice before generalizing patterns.

## 5. Explicitly out of scope

- Hosting or replacing music/video/book streaming.
- Public communities, comments, chat, follower graphs, or public profiles.
- Payments and subscriptions in the first slice.
- Competitive gamification and engagement-maximizing feeds.
- Opaque algorithmic recommendations.
- Public catalog editing.
- Real-time synchronization with every media service.
- A single universal card that ignores media-specific presentation.

## 6. Information architecture

The general navigation grammar is:

`Global home → Medium → Curated route/category → Scene/theme/subcategory → Creator → Work → Consumable unit`

The music reference path is:

`Music home → Genre → Subgenre or scene → Artist → Album or edition → Track`

The model must support lateral context links without turning breadcrumbs into a taxonomy dump.

### Pilot validation routes

1. `Grunge → Pearl Jam → Ten → track`
2. `Ghana → Highlife → artist → album → contextual card`
3. `Electronic → Downtempo/Psybient → artist → album → track`

A navigation proposal that cannot express all three routes without exceptions is not ready.

## 7. Media presentation variants

| Medium | Primary cover behavior | Progress unit |
|---|---|---|
| Music | Square artwork | Track/album listening state |
| Film | Vertical poster | Watched state and optional elapsed progress |
| Series | Vertical poster with season/episode context | Episode and season progress |
| Documentary | Vertical poster; may expose subject/context more strongly | Watched state and optional elapsed progress |
| Book | Vertical cover with variable source proportions | Page/chapter/percentage when available |

Shared tokens, actions, and accessibility rules are desirable. Aspect ratio, metadata hierarchy, density, and progress behavior are allowed—and expected—to vary.

## 8. Music content model requirements

At minimum, the design must distinguish creator, artist credit, genre, subgenre, scene, region, period, work, release/edition, track, and contextual relationship. Historic editions must not overwrite the identity of the underlying work. Classical music requires room for composer, work, movement, performer, ensemble, conductor, recording, and edition rather than forcing popular-music metadata onto it.

Spotify and iBroadcast playlists inform catalog coverage and prioritization. They do not define canonical names, taxonomy, rights, historical claims, or recommendation logic.

## 9. State semantics

- **Favorite:** durable personal interest; not equivalent to consumed.
- **Status:** planned/in progress/completed as appropriate to the medium.
- **Progress:** medium-specific and never inferred from rating.
- **Rating:** optional personal assessment; absence is distinct from zero.

The UI must not collapse these into one ambiguous action.

## 10. Editorial-to-runtime flow

`Notion draft → editorial review → Approved for sync → validation/transformation → operational database → frontend`

The browser must never query Notion directly. Initial sync should be manual, auditable, idempotent, and able to report rejected records. Automation comes after the schema and editorial workflow prove stable.

## 11. Visual direction

The experience should be dark, visual, and editorial, with enough restraint for long reading and cross-generational use. It must not become a Spotify clone, a Netflix clone, or an admin dashboard presented as a consumer product.

## 12. Platform decision

The initial delivery stack is GitHub for code/contracts, Codex local for design and engineering, Notion for editorial content, and Lovable for preview/hosting where useful. ChatGPT Sites is not the main frontend platform at this stage because platform maturity and age-targeting constraints do not fit this project safely.

See `docs/adr/0001-source-of-truth-and-platform.md`.

