# ADR 0001: Source-of-truth and initial platform boundaries

**Status:** Accepted  
**Date:** 2026-09-20

## Context

Constelario spans editorial research, private family context, product design, application code, and preview hosting. Letting one convenience tool own every concern would obscure authority and increase lock-in and drift. The intended audience includes a 12-year-old, so platform age constraints and privacy posture materially affect platform choice.

## Decision

- GitHub owns versioned product contracts, schemas, ADRs, code, and technical QA evidence.
- Notion owns editorial catalog work and approval status.
- Google Drive owns the human-readable dossier and original project assets.
- Codex local is the primary design and engineering environment.
- Lovable may provide early preview/hosting while its output remains replaceable and synchronized with GitHub.
- ChatGPT Sites is not the primary frontend platform at this stage.
- The operational application will read from a validated runtime database, never directly from Notion.

## Consequences

- Synchronization is an explicit pipeline with validation and provenance.
- Cross-tool conflicts are escalated instead of silently overwritten.
- Early work invests in contracts and navigation before frontend polish.
- Platform choices can be revisited through a new ADR when maturity, cost, policy, or requirements change.

## Rejected alternatives

### Notion as runtime database

Rejected because editorial convenience does not supply the runtime contract, performance boundary, validation, or browser-security posture required by the product.

### ChatGPT Sites as primary frontend now

Rejected for the current phase because the platform is still evolving and its age-targeting constraints do not safely match the intended family use.

### Lovable as sole source of truth

Rejected because preview convenience must not own architecture, product contracts, or the only copy of implementation history.

