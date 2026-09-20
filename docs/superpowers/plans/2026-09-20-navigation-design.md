# Navigation Design Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Produce a testable navigation and media-presentation contract for Constelario, proven first through three music journeys and then checked against film, series, documentary, and book variants.

**Architecture:** Treat navigation, editorial relationships, and display variants as explicit contracts before implementing a polished frontend. The work begins with route fixtures and acceptance scenarios, then defines reusable semantics and media-specific variants; unresolved boundary changes become ADRs.

**Tech Stack:** Markdown contracts, Mermaid route diagrams when materially useful, JSON fixtures/schemas in the subsequent implementation plan, Figma or local UI prototypes only after contract approval.

**Spec:** `docs/PROJECT_FOUNDATION.md`

## Global Constraints

- Music is the first complete vertical slice.
- The three pilot routes must work without special-case navigation.
- Notion is never queried directly by the browser.
- Familiar creators are curated gateways, not popularity-only recommendations.
- Shared semantics may not force identical media presentation.
- No social graph, public contribution, opaque feed, or competitive gamification.
- The experience includes a 12-year-old; privacy and age safety are design constraints.

## Review Focus

- Ambiguous nodes that could be both hierarchy and context must render with a clear relationship label.
- Works with multiple releases must preserve work identity while allowing edition-specific metadata.
- Missing artwork must not change route availability or fabricate a media ratio.
- Long titles and multi-artist credits must remain readable without hiding the primary action.
- Unknown progress must remain unknown rather than becoming zero or incomplete.

---

### Task 1: Readiness and contract inventory

**Files:**
- Modify: `docs/HANDOFF.md` only if an actual ambiguity is found and accepted
- Create: `docs/design/00-contract-inventory.md`

**Interfaces:**
- Consumes: `AGENTS.md`, product foundation, quality gates, accepted ADRs
- Produces: a cited inventory of fixed constraints, open decisions, and excluded scope

- [ ] Answer all 16 readiness questions with citations and submit the response without changing repository files.
- [ ] Receive an architecture-lead score and correct only the failed or incomplete items.
- [ ] Write `docs/design/00-contract-inventory.md` with sections `Fixed`, `Open`, `Excluded`, and `ADR candidates`; every entry cites its governing document.
- [ ] Verify that every `Open` item has a smallest reversible resolution method and every `Excluded` item maps to the foundation.
- [ ] Commit with `docs: inventory navigation contracts`.

### Task 2: Music route map and acceptance scenarios

**Files:**
- Create: `docs/design/01-music-route-map.md`
- Create: `docs/design/fixtures/music-pilot-routes.json`

**Interfaces:**
- Consumes: the three pilot routes and the hierarchy/context distinction
- Produces: stable route identifiers, node types, edge types, breadcrumbs, and acceptance scenarios

- [ ] Define a JSON fixture shape with `routeId`, `entry`, `nodes`, `edges`, `expectedBreadcrumbs`, `contextLinks`, and `nextStepReason`.
- [ ] Encode the Grunge/Pearl Jam, Ghana/Highlife, and Electronic/Downtempo-Psybient routes without inventing unsupported catalog facts; use clearly marked fixture identifiers.
- [ ] Document canonical edge types separately from lateral context edge types.
- [ ] Add scenario checks for forward movement, back navigation, deep linking, missing artwork, and a context link returning to the canonical path.
- [ ] Validate JSON syntax with `jq empty docs/design/fixtures/music-pilot-routes.json` and record the successful command output in the PR.
- [ ] Commit with `docs: define pilot music navigation routes`.

### Task 3: Cross-media variant matrix

**Files:**
- Create: `docs/design/02-media-variant-matrix.md`

**Interfaces:**
- Consumes: state semantics and media presentation requirements
- Produces: component invariants and allowed variants for music, film, series, documentary, and books

- [ ] Define rows for artwork ratio, title hierarchy, creator credits, date/edition, duration/extent, progress, status, rating, favorite, contextual modules, and missing-data behavior.
- [ ] Mark each row as `shared semantic`, `shared token`, or `media variant`; explain every media variant.
- [ ] Include concrete empty, unknown, and multi-credit examples for all five media.
- [ ] Review the matrix against the prohibition on a universal card and list any component boundary that still hides a media-specific rule.
- [ ] Commit with `docs: define cross-media presentation variants`.

### Task 4: Low-fidelity screen and component contract

**Files:**
- Create: `docs/design/03-screen-inventory.md`
- Create: `docs/design/04-component-contracts.md`

**Interfaces:**
- Consumes: route map and media variant matrix
- Produces: screen responsibilities, component inputs, states, actions, and responsive/accessibility requirements

- [ ] Inventory screens needed by the pilot routes before adding global-home polish.
- [ ] For each screen, specify user question answered, canonical parent, available lateral context, primary action, and failure/empty states.
- [ ] Define focused component contracts; do not create a single polymorphic component whose props encode every medium.
- [ ] Specify keyboard order, focus return, semantic headings, labels, reduced-motion behavior, and responsive changes.
- [ ] Walk all three fixture routes against the screen inventory and record mismatches as contract changes or ADR candidates.
- [ ] Commit with `docs: specify navigation screens and components`.

### Task 5: Review package and next implementation plan

**Files:**
- Create: `docs/design/05-navigation-review.md`
- Create: `docs/superpowers/plans/2026-09-20-music-navigation-prototype.md`

**Interfaces:**
- Consumes: Tasks 1–4 and `docs/QUALITY_GATES.md`
- Produces: recorded gate evidence and a file-specific TDD plan for the chosen frontend stack

- [ ] Score Gates 1–3 with links to exact evidence and list failures without softening them.
- [ ] Run a drift review covering feed logic, social features, source authority, media flattening, and premature polish.
- [ ] Present unresolved product decisions to the product owner as mutually exclusive options with consequences.
- [ ] After decisions, write the prototype implementation plan with exact files, interfaces, failing tests, commands, expected results, and commits for the selected stack.
- [ ] Verify all internal Markdown links and JSON fixtures; include commands and results in the PR.
- [ ] Commit with `docs: package navigation design for review`.

## Self-review record

- Spec coverage: purpose, audience, V1 boundaries, route grammar, pilot routes, media variants, state semantics, sync boundary, and drift risks are assigned to tasks.
- Placeholder scan: no `TBD`, `TODO`, deferred implementation instruction, or unnamed test step remains.
- Type consistency: route fixture fields are defined once in Task 2 and consumed as that contract by Tasks 4–5.
- Review focus coverage: ambiguous edges, releases, missing art, long/multi-credit text, and unknown progress are explicitly exercised in Tasks 2–4.

