# Quality gates

Quality assurance is a sequence of evidence gates, not a final cosmetic review.

## Gate 0 — Agent readiness

- All handoff questions answered with repository citations.
- Score meets the handoff threshold.
- Open questions and assumptions are explicit.
- Architecture lead accepts the first increment's scope.

## Gate 1 — Contract integrity

- No contradiction with the product foundation or accepted ADRs.
- Every new entity, field, route, and state has a single defined meaning.
- Changes to boundaries arrive with an ADR before dependent work.
- Private data, credentials, and unpublished playlist contents are absent from Git history.

## Gate 2 — Navigation proof

- All three pilot music routes work without special-case navigation.
- Back navigation and orientation are defined at every level.
- Lateral context links cannot masquerade as canonical hierarchy.
- An adolescent can find a familiar gateway and reach a deeper recommendation with an explainable reason.

## Gate 3 — Cross-media fit

- Shared actions keep the same meaning across media.
- Music, film, series, documentary, and book art retain appropriate proportions.
- Progress semantics are medium-specific and accessible.
- The system does not require empty or fabricated metadata to fit a universal component.

## Gate 4 — Editorial/runtime boundary

- Notion remains unreachable from the browser client.
- Only `Approved for sync` records can enter validation.
- Invalid and ambiguous records are rejected with actionable reasons.
- Re-running the same input is idempotent.
- Provenance and transformation results are auditable.

## Gate 5 — Implementation evidence

- Tests are written at the contract boundary, not only at component snapshots.
- Accessibility checks cover keyboard navigation, focus, labels, contrast, reduced motion, and semantic structure.
- Responsive behavior is verified at representative phone, tablet, and desktop widths.
- Empty, loading, error, missing-art, long-title, multi-credit, and unknown-progress states are exercised.
- The PR states commands run and includes their fresh results.

## Definition of ready for visual polish

Visual polish may start only after Gates 0–3 pass for the three pilot routes. Passing means recorded evidence in the PR, not confidence.

## Definition of ready for merge

- Required gates for the increment pass.
- The architecture lead has adversarially reviewed drift risks.
- Product-owner decisions are resolved or explicitly deferred outside the increment.
- Documentation and contracts match the behavior being merged.
- The branch is current with its target and CI is green when CI exists.

