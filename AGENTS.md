# Agent operating contract

These instructions apply to every coding or design agent working in this repository.

## Mandatory reading order

Before proposing or changing anything, read in this order:

1. `README.md`
2. `docs/PROJECT_FOUNDATION.md`
3. `docs/HANDOFF.md`
4. `docs/QUALITY_GATES.md`
5. Every accepted ADR under `docs/adr/`
6. The active plan under `docs/superpowers/plans/`

## Readiness gate

Do not edit code, schemas, navigation contracts, or design artifacts until you have answered every question in the **Readiness examination** section of `docs/HANDOFF.md` and the architecture lead has explicitly accepted the response.

Your response must:

- answer each item by number;
- cite the repository file and heading that supports the answer;
- separate facts, inferences, assumptions, and open questions;
- include contradictions or missing information you found;
- state what you will not do in the proposed work;
- finish with the exact readiness declaration specified in the handoff.

“Understood”, a generic summary, or a plan without evidence is not acceptance-worthy.

## Decision protocol

- The implementation agent proposes and produces evidence.
- The architecture lead challenges assumptions, boundaries, failure modes, and drift.
- The product owner decides product intent when evidence cannot resolve a question.
- Contract changes are recorded as ADRs before dependent implementation.
- If Notion conflicts with repository contracts, stop and escalate; do not silently choose either version.

## Safe defaults

- Preserve user work and unrelated changes.
- Prefer the smallest reversible change.
- Never expose credentials, private playlist contents, minors' personal information, or unpublished assets.
- Do not call Notion directly from a browser client.
- Do not invent catalog facts, rights status, ratings, or source attribution.
- Do not merge your own PR unless the product owner explicitly asks.

