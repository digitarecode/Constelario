# Contract inventory

**Status:** Draft evidence for architecture review; this document inventories accepted constraints and unresolved decisions. It does not accept a navigation or data contract.

**Base:** `docs/project-foundation-v1` at `f5b36edd2afe3bee59da580f10bb0b3669ab96a0`

**Readiness gate:** Accepted for Task 1 at 31/32. The architecture review withheld acceptance of a unique canonical parent for entities reached through multiple routes.

## Fixed

### Authority and governance

- **F-01 — Repository authority.** GitHub owns versioned product contracts, schemas, ADRs, code, and technical QA evidence. [README.md](../../README.md) — “Source of truth”; [ADR 0001](../adr/0001-source-of-truth-and-platform.md) — “Decision”.
- **F-02 — Editorial authority.** Notion owns editorial catalog work and approval state, but it is not a runtime database or a source of repository contracts. [README.md](../../README.md) — “Source of truth”; [ADR 0001](../adr/0001-source-of-truth-and-platform.md) — “Decision” and “Rejected alternatives”.
- **F-03 — Dossier and asset authority.** Google Drive owns the human-readable dossier and original project assets. [README.md](../../README.md) — “Source of truth”; [ADR 0001](../adr/0001-source-of-truth-and-platform.md) — “Decision”.
- **F-04 — Design, engineering, and platform boundary.** Codex local is the primary design and engineering environment. Lovable may provide replaceable early preview or hosting, but it may not own architecture, contracts, or the only implementation history. ChatGPT Sites is not the primary frontend platform at this stage because its maturity and age-targeting constraints do not safely match the intended family use. [ADR 0001](../adr/0001-source-of-truth-and-platform.md) — “Decision” and “Rejected alternatives”.
- **F-05 — Conflict handling.** Cross-tool conflicts are escalated, not silently overwritten. A Notion/repository conflict stops dependent work. Contract changes require an ADR before dependent implementation. [AGENTS.md](../../AGENTS.md) — “Decision protocol”; [ADR 0001](../adr/0001-source-of-truth-and-platform.md) — “Consequences”.
- **F-06 — Role boundary.** The implementation agent proposes and supplies evidence; the architecture lead challenges system boundaries and accepts readiness; the product owner decides unresolved product intent. [HANDOFF.md](../HANDOFF.md) — “Operating model”.
- **F-07 — Readiness gate.** No code, schema, navigation-contract, or design-artifact changes precede an accepted readiness response. Task 1 has been accepted; later navigation and data boundaries have not. [AGENTS.md](../../AGENTS.md) — “Readiness gate”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 0 — Agent readiness”.

### Product and safety

- **F-08 — Purpose.** Constelario is a curated family cultural archive and discovery map. Familiar creators are explainable gateways toward deeper works, scenes, traditions, and connections, not popularity-only destinations. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “1. Purpose” and “3. Product principles”.
- **F-09 — Safety posture.** The audience includes a 12-year-old. Adults control administration and curation; personal data is minimized; public identity, messaging, comments, follower graphs, and open-community features are absent. Accounts, analytics, sharing, behavioral recommendations, or third-party tracking trigger a fresh privacy and age-safety review. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “2. Audience and safety posture”.
- **F-10 — First vertical slice.** Music must become the first complete vertical slice before patterns are generalized to film, series, documentary, and books. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “4. V1 scope”; [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Global Constraints”.
- **F-11 — Visual posture.** The experience is dark, visual, restrained, and editorial; it may not become a Spotify clone, Netflix clone, or administration dashboard presented as a consumer product. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “11. Visual direction”.

### Navigation and editorial relationships

- **F-12 — General navigation grammar.** The accepted grammar traverses global home, medium, a curated route or category, a scene/theme/subcategory, creator, work, and consumable unit. This grammar does not establish that every entity has one taxonomic parent. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “6. Information architecture”.
- **F-13 — Music reference path.** The music reference path traverses music home, genre, subgenre or scene, artist, album or edition, and track. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “6. Information architecture”.
- **F-14 — Pilot proof.** One model must express `Grunge → Pearl Jam → Ten → track`, `Ghana → Highlife → artist → album → contextual card`, and `Electronic → Downtempo/Psybient → artist → album → track` without route-specific exceptions. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “Pilot validation routes”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 2 — Navigation proof”.
- **F-15 — Hierarchy/context distinction.** Lateral context must be visibly labeled and may not masquerade as canonical hierarchy or turn breadcrumbs into a taxonomy dump. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “6. Information architecture”; [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Review Focus”.
- **F-16 — Orientation evidence.** Every level needs defined orientation and back behavior. A familiar gateway must lead an adolescent to a deeper recommendation with an explainable reason. [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 2 — Navigation proof”.

### Content, presentation, and state

- **F-17 — Music entities and relationships.** The model distinguishes creator, artist credit, genre, subgenre, scene, region, period, work, release or edition, track, and contextual relationship. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “8. Music content model requirements”.
- **F-18 — Work/edition integrity.** A historic release or edition may add edition-specific metadata but may not overwrite the identity of its underlying work. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “8. Music content model requirements”; [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Review Focus”.
- **F-19 — Classical-music fit.** The model must leave room for composer, work, movement, performer, ensemble, conductor, recording, and edition rather than forcing popular-music metadata onto classical music. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “8. Music content model requirements”.
- **F-20 — External catalog inputs.** Spotify and iBroadcast may inform coverage and prioritization. They may not define canonical names, taxonomy, rights, historical claims, or recommendation logic. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “8. Music content model requirements”.
- **F-21 — Shared semantics, media variants.** Actions and accessibility semantics may be shared; artwork ratio, metadata hierarchy, density, and progress behavior are allowed and expected to vary by medium. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “7. Media presentation variants”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 3 — Cross-media fit”.
- **F-22 — Independent user states.** Favorite, status, progress, and rating have distinct meanings. Progress is never inferred from rating, unknown progress remains unknown, and an absent rating is not zero. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “9. State semantics”; [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Review Focus”.
- **F-23 — Missing-data and content-stress integrity.** Missing artwork must not remove a route or fabricate a ratio; the system may not require empty or invented metadata to satisfy a universal component. Long titles and multi-artist credits must remain readable without hiding the primary action. [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Review Focus”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 3 — Cross-media fit”.

### Editorial-to-runtime boundary

- **F-24 — Approved flow.** Content flows from Notion draft through editorial review and `Approved for sync`, then validation/transformation, an operational database, and finally the frontend. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “10. Editorial-to-runtime flow”.
- **F-25 — Browser boundary.** A browser client never queries Notion directly. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “10. Editorial-to-runtime flow”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 4 — Editorial/runtime boundary”.
- **F-26 — Initial sync properties.** Initial synchronization is manual, auditable, idempotent, provenance-preserving, and able to reject invalid or ambiguous records with actionable reasons. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “10. Editorial-to-runtime flow”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 4 — Editorial/runtime boundary”.

### Product-owner update after the foundation

- **F-27 — Library as a permanent catalog entry.** In a product-owner decision made after the current foundation was written, Library becomes a permanent entry to the published catalog, separate from Discover and My collection. In Music it supports browsing artists, albums, and tracks; search; combinations of available filters; and sorting. Returning from an entity preserves filters, search, and position. Library exposes only content admitted by the publication/sync process. The exact filter vocabulary remains subject to comparison with the real Notion catalog and must be propagated into Task 2 navigation contracts; none of this wording is represented as pre-existing foundation text. **Source:** product-owner conversation update after `PROJECT_FOUNDATION.md`, 2026-09-21; propagation target: [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Task 2: Music route map and acceptance scenarios”; publication boundary: [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “10. Editorial-to-runtime flow”.

## Open

Every item in this section is unresolved. A proposed experiment is not an accepted contract.

### O-01 — Entity identity versus navigation context

**Open decision:** How one album retains one identity while remaining reachable from genre, country, a curated route, and a direct link without acquiring a single taxonomic parent.

**Reversible proposal A — canonical entity resource plus explicit route context:**

- **Identity of the entity:** assign the album one stable internal identifier and one entity URL independent of discovery route. The URL shape is illustrative, not accepted: `/music/works/{id}`.
- **Editorial relationships:** store typed, many-to-many edges such as `associated with genre`, `connected to region`, `included in curated route`, and `has edition`. None becomes the album's sole parent merely because it was used to enter the page.
- **Navigation context:** carry the active journey separately as a small route-context value in the URL, navigation state, or both. It selects orientation and breadcrumbs; it does not alter the album record or identity. The chosen transport determines whether the context survives reload and sharing.
- **Reload or direct link:** URL-carried context can reconstruct a journey after validating that the referenced edges still exist. Context stored only in navigation state may be lost on reload or when a link is shared. A bare entity URL opens a neutral entity view with no fabricated ancestor. Browser Back follows real history; an explicit return action appears only when a valid origin context exists.
- **Smallest test:** encode one album ID reached through four fixture entries, assert one entity record and one identity URL, then compare the four expected orientation states. No production routing is required.

**Alternative B — route-scoped presentation URLs:** expose URLs such as `/routes/{routeId}/works/{id}` for each journey while resolving all of them to the same album record; optionally publish a separate canonical entity URL.

**Conditional risks of A and B:** both approaches can produce multiple presentation URLs when context is encoded in a shareable URL, so cache, analytics, canonical-link, and stale-context behavior must be tested for both. Proposal A loses shareable orientation if context exists only in navigation state. Proposal B makes route context explicit in the path, which may simplify restoration but may also increase the chance that route-scoped URLs are mistaken for separate entity identities. These are hypotheses for fixtures, not demonstrated consequences.

**Current comparison posture:** both proposals keep identity and context independently testable, avoid a unique taxonomic parent, and can resolve every presentation to one entity record. Neither is preferred or accepted until fixture evidence compares reload, sharing, stale context, browser Back, and cross-route movement.

**Evidence required before closure:** Task 2 fixtures for the four entry modes, including reload, direct entry, back behavior, stale context, and a context link returning to the active journey; representative Notion relations from O-02.

**Smallest reversible resolution:** decide only the fixture semantics and acceptance scenarios. Do not fix URL syntax, storage, or route edges until those scenarios pass.

**Sources:** [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “6. Information architecture”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 2 — Navigation proof”; [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Task 2: Music route map and acceptance scenarios”.

### O-02 — Repository contracts versus the real Notion catalog

**Open decision:** Whether the accepted conceptual distinctions correspond to the actual Notion bases, properties, relations, statuses, and records. Repository readiness does not validate this correspondence.

**Required representative evidence:**

1. Sanitized base/schema evidence: relevant base names, property names and types, relation targets, actual status values, and the fields/values that could support Library filters and sorting.
2. A geographic route sample covering region or country → musical tradition or genre → artist → album → contextual material.
3. One work represented by at least two releases or editions, including how the relationship is stored.
4. One classical sample exposing whichever of composer, work, movement, performer, ensemble, conductor, recording, and edition exist today.

Private playlists, credentials, unpublished assets, and the minor's behavior are neither requested nor permitted.

**Smallest reversible resolution:** inspect or receive a read-only sanitized export of only those schemas and records; create a gap table of `contract concept`, `Notion representation`, `match`, `missing`, and `ambiguous`. Do not mutate Notion or the repository schema.

**Sources:** [HANDOFF.md](../HANDOFF.md) — “Operating model” and “Ingestion lane: ChatGPT Sol/high”; [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “8. Music content model requirements” and “10. Editorial-to-runtime flow”.

### O-03 — Concrete navigation edge types and URL syntax

**Open decision:** Stable route IDs, node IDs, canonical versus lateral edge vocabulary, breadcrumb representation, deep-link syntax, and stale-context behavior.

**Smallest reversible resolution:** define JSON fixtures and acceptance scenarios for the three pilots plus the four-entry album challenge; reject any shape that requires duplicate entity records or special-case navigation.

**Sources:** [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Task 2: Music route map and acceptance scenarios”; [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “6. Information architecture”.

### O-04 — Media component boundaries

**Open decision:** Which primitives remain shared and which components are medium-specific.

**Smallest reversible resolution:** build the Task 3 matrix with empty, unknown, long-title, and multi-credit examples before naming or implementing components.

**Sources:** [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Task 3: Cross-media variant matrix”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 3 — Cross-media fit”.

### O-05 — Concrete progress representation

**Open decision:** Exact fields and user interactions for track/album, elapsed film, season/episode, documentary, and page/chapter/percentage progress.

**Smallest reversible resolution:** specify examples and unknown-state behavior in the media matrix without selecting storage fields.

**Sources:** [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “7. Media presentation variants” and “9. State semantics”.

### O-06 — Operational ingestion schema and database

**Open decision:** Runtime database, identifiers, provenance format, validation schema, update/deletion semantics, and conflict reporting.

**Smallest reversible resolution:** defer technology selection; after O-02, draft input/output examples and rejected-record cases as an implementation-plan input.

**Sources:** [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “10. Editorial-to-runtime flow”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 4 — Editorial/runtime boundary”.

### O-07 — Accounts, analytics, sharing, and behavioral data

**Open decision:** Whether any of these capabilities are needed and what age-safety controls would govern them.

**Smallest reversible resolution:** keep them absent. If product intent changes, perform the required privacy and age-safety review before proposing implementation.

**Sources:** [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “2. Audience and safety posture”.

### O-08 — Repository visibility mismatch

**Observed state:** GitHub reported the repository as public during Task 1. [README.md](../../README.md) — “Working agreement” says it remains private. The product owner independently confirmed the current public state and that the documentation is stale.

**Smallest reversible resolution:** the repository administrator decides the intended visibility. Then update either the setting or the documentation in a separately reviewed action. Do not silently change visibility or rewrite the privacy intent in this increment.

**Sources:** [README.md](../../README.md) — “Working agreement”; [AGENTS.md](../../AGENTS.md) — “Safe defaults”.

### O-09 — Conflicting reading orders

**Observed state:** [README.md](../../README.md) — “Start here” and [AGENTS.md](../../AGENTS.md) — “Mandatory reading order” specify different onboarding sequences.

**Interim ruling for this increment:** `AGENTS.md` is the agent operating contract, so its order governs: README, project foundation, handoff, quality gates, every accepted ADR, then the active plan.

**Smallest reversible resolution:** after Task 1 review, align README's short start sequence with the complete mandatory order in a dedicated documentation change.

**Sources:** [README.md](../../README.md) — “Start here”; [AGENTS.md](../../AGENTS.md) — “Mandatory reading order”.

### O-10 — Frontend framework, final hosting, and runtime database

**Open decision:** No final technology choices exist for these concerns.

**Smallest reversible resolution:** keep Tasks 1–4 technology-agnostic. Compare only genuine candidates after navigation review, and record durable boundary changes in an ADR.

**Blocking status:** Not blocking for Task 1.

**Sources:** [ADR 0001](../adr/0001-source-of-truth-and-platform.md) — “Consequences”; [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Tech Stack” and “Task 5: Review package and next implementation plan”.

### O-11 — Recommendation explanation standard

**Open decision:** Required evidence and presentation for explaining why a deeper item is recommended.

**Smallest reversible resolution:** add one `nextStepReason` example to each Task 2 fixture and review it editorially before defining a reusable component.

**Sources:** [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “3. Product principles” and “4. V1 scope”; [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Task 2: Music route map and acceptance scenarios”.

### O-12 — Library navigation and restoration contract

**Open decision:** The product intent for Library is fixed by F-27, but its route shape, screen boundary, search behavior, filter vocabulary, sorting options, state transport, restoration after visiting an entity, reload behavior, and empty/error states are not yet navigation contracts.

**Smallest reversible resolution:** in Task 2, add fixture scenarios for entering Music Library, browsing each supported entity type, combining search/filter/sort state, opening an entity and returning with state and position preserved, reloading, and excluding records that have not passed publication/sync. Compare candidate filters with the sanitized Notion evidence from O-02 before naming them as contract fields.

**Sources:** product-owner conversation update after `PROJECT_FOUNDATION.md`, 2026-09-21; [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Task 2: Music route map and acceptance scenarios”; [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “10. Editorial-to-runtime flow”.

## Excluded

- **X-01 — Streaming replacement:** no hosting or replacement of music, video, or book streaming. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “5. Explicitly out of scope”.
- **X-02 — Public social features:** no public communities, profiles, comments, chat, messaging, or follower graph. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “2. Audience and safety posture” and “5. Explicitly out of scope”.
- **X-03 — Payments in the first slice:** no payments or subscriptions. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “5. Explicitly out of scope”.
- **X-04 — Engagement optimization:** no competitive gamification or engagement-maximizing feed. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “5. Explicitly out of scope”.
- **X-05 — Opaque recommendations:** no recommendation whose reason cannot be understood by the user. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “3. Product principles” and “5. Explicitly out of scope”.
- **X-06 — Public catalog editing:** catalog curation remains adult-controlled and editorial. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “4. V1 scope” and “5. Explicitly out of scope”.
- **X-07 — Universal real-time sync:** no real-time synchronization with every media service. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “5. Explicitly out of scope”.
- **X-08 — Universal content card:** no single card that erases medium-specific artwork, metadata, density, or progress. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “5. Explicitly out of scope” and “7. Media presentation variants”.
- **X-09 — Direct Notion runtime access:** the browser never queries Notion, and records do not bypass approval and validation. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “10. Editorial-to-runtime flow”.
- **X-10 — Source authority from Spotify/iBroadcast:** playlist inputs do not define names, taxonomy, rights, history, or recommendations. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “8. Music content model requirements”.
- **X-11 — Premature visual polish:** provisional visual exploration, including high-fidelity concepts, may proceed before route validation, but it does not approve a final visual direction or reusable components. No polished global frontend, final visual direction, or approved components before Gates 0–3 pass for all three pilot routes. [QUALITY_GATES.md](../QUALITY_GATES.md) — “Definition of ready for visual polish”; [HANDOFF.md](../HANDOFF.md) — “Assignment boundary for the next agent”.
- **X-12 — Framework, hosting, or database selection in Task 1:** these choices are unnecessary for the inventory and remain open. [navigation plan](../superpowers/plans/2026-09-20-navigation-design.md) — “Task 1: Readiness and contract inventory” and “Task 5: Review package and next implementation plan”.

## ADR candidates

An item becomes an ADR only if the proposed decision changes or fixes a durable boundary. Evidence collection alone does not require an ADR.

- **A-01 — Entity identity and route context.** Candidate if Task 2 fixes a canonical entity URL, route-context transport, edge vocabulary, Library restoration behavior, reload behavior, or another durable navigation boundary. Depends on O-01, O-02, O-03, and O-12. [AGENTS.md](../../AGENTS.md) — “Decision protocol”; [HANDOFF.md](../HANDOFF.md) — “Drift alarms”.
- **A-02 — Notion-to-runtime identity and provenance.** Candidate after the representative Notion sample exposes how current editorial identity, editions, relations, and approval state map to a runtime schema. Depends on O-02 and O-06. [ADR 0001](../adr/0001-source-of-truth-and-platform.md) — “Consequences”; [QUALITY_GATES.md](../QUALITY_GATES.md) — “Gate 4 — Editorial/runtime boundary”.
- **A-03 — Privacy-sensitive product capabilities.** Required before accounts, analytics, sharing, behavioral recommendations, or third-party tracking alter the accepted safety posture. Depends on O-07. [PROJECT_FOUNDATION.md](../PROJECT_FOUNDATION.md) — “2. Audience and safety posture”; [HANDOFF.md](../HANDOFF.md) — “Drift alarms”.
- **A-04 — Primary frontend or hosting boundary.** Candidate only when a platform choice replaces or materially changes ADR 0001. It is not needed for this increment. [ADR 0001](../adr/0001-source-of-truth-and-platform.md) — “Consequences”.

## Task 1 verification contract

Task 1 is complete only when review evidence shows:

1. `Fixed`, `Open`, `Excluded`, and `ADR candidates` are present.
2. Every fixed constraint and exclusion cites a governing file and heading.
3. Every open item has a smallest reversible resolution method.
4. Navigation identity/context remains a proposal rather than an accepted contract.
5. The Notion correspondence gap and exact representative evidence are explicit.
6. The visibility and reading-order discrepancies are recorded without silently changing either boundary.
7. The post-foundation Library decision is attributed to the product owner and its unresolved navigation/filter details are routed to Task 2 and Notion evidence.
8. No file outside this inventory changes in the Task 1 commit.
