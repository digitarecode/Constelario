# Handoff and readiness examination

This document is the entry contract for a new design or implementation agent. Its goal is to expose shallow reading before that reading becomes product drift.

## Operating model

| Role | Owns | May not silently change |
|---|---|---|
| Product owner | Product intent, priorities, final tradeoffs | Accepted technical facts without new evidence |
| Architecture lead | System boundaries, contracts, adversarial review, readiness acceptance | Product intent |
| Implementation Codex | Proposals, design/code, tests, implementation evidence | Scope, taxonomy, privacy posture, source-of-truth rules |
| Ingestion ChatGPT (Sol/high) | Heavy catalog research and controlled Notion ingestion | Repository contracts, schema, runtime architecture, approval gates |
| Notion editor/reviewer | Editorial review and `Approved for sync` state | Runtime data by bypassing validation |

The architecture lead and implementation agent should disagree productively. The agent must surface tradeoffs and evidence; the lead should attack assumptions and failure modes. The goal is not consensus theater. Unresolved contract decisions become ADRs and are decided by the product owner when necessary.

## Assignment boundary for the next agent

The next design phase defines the navigation and presentation system, starting with music and proving which patterns generalize to other media. It does **not** begin by building a polished global frontend.

Expected outputs after readiness is accepted:

1. A route map and screen inventory for the three pilot music journeys.
2. A media-variant matrix for cover ratios, metadata, actions, progress, and contextual modules.
3. Low-fidelity interaction flows and component boundaries.
4. Contract questions and ADR proposals where evidence is insufficient.
5. Acceptance tests that can detect navigation drift before visual polish.

## Readiness examination

Answer all questions from memory after reading, then verify each answer against the repository and cite the supporting file and heading.

1. In one paragraph, what problem does Constelario solve, and what three tempting products must it not become?
2. Who includes the most safety-sensitive intended user, and what concrete product restrictions follow from that fact?
3. Why are familiar artists such as Queen, Pearl Jam, Daft Punk, Cerati, or Café Tacvba valuable here, and what would make their inclusion editorially weak?
4. Name the authority for product contracts, editorial catalog, original assets/human dossier, and preview hosting. What happens when two authorities conflict?
5. Reconstruct the general navigation grammar and the music-specific reference path without copying them verbatim. Explain the difference between hierarchy and lateral context.
6. Walk through all three pilot routes. For each, name the modeling pressure it puts on the design.
7. Which interaction semantics should stay consistent across media, and which presentation or progress behaviors must vary?
8. Explain why a universal content card is out of scope even though shared design tokens and actions are desirable.
9. Describe the complete Notion-to-frontend flow. Name two prohibited shortcuts and two properties the initial sync must have.
10. What authority do Spotify and iBroadcast have, and what five kinds of decisions may they not make?
11. Give four examples of music metadata that break a simplistic `artist → album → song` model.
12. Separate favorite, status, progress, and rating using one concrete example. Identify one harmful UI collapse.
13. Why is ChatGPT Sites not the main frontend platform now, and what is the current role of Lovable and Codex local?
14. List at least six V1 exclusions and explain which two are most likely to creep back during design.
15. Identify three genuine uncertainties not answered by the repository. For each, propose the smallest reversible way to resolve it.
16. Propose the first implementation/design increment: exact deliverables, files likely to change, verification evidence, and an explicit not-doing list.

## Scoring rubric

Each answer scores:

- `0` — absent, contradicted, generic, or unsupported.
- `1` — substantially correct but incomplete, weakly evidenced, or missing implications.
- `2` — correct, specific, evidenced, and aware of tradeoffs.

Acceptance requires at least **28/32**, no zeroes, and a score of 2 on questions 2, 4, 6, 9, 10, and 16. The architecture lead records the score and either accepts readiness or requests a targeted correction. The lead should ask at least one follow-up chosen from an actual weakness in the response; a fixed ceremonial question does not count.

## Required readiness declaration

Finish the response with exactly:

> I am ready to work inside the current Constelario contracts. I have listed my uncertainties and will stop for an ADR or product-owner decision before changing a boundary.

This declaration is necessary but never sufficient; evidence and score control acceptance.

## Drift alarms

Stop and ask before proceeding if any proposal:

- optimizes time-on-app or popularity without curatorial explanation;
- adds social identity, messaging, public contribution, or behavioral targeting;
- treats Spotify/iBroadcast or Notion as the runtime authority;
- erases work/edition or classical-music distinctions;
- forces every medium into the same cover, metadata, or progress pattern;
- changes privacy posture, schemas, route grammar, or source ownership;
- begins high-fidelity visual work before the three pilot routes are coherent.

## Ingestion lane: ChatGPT Sol/high

The ingestion agent may research representative creators and works, compare them with the existing Spotify/iBroadcast inputs, detect coverage gaps, prepare citations, and add or update Notion records in the editorial workflow.

It must:

- preserve source URLs and distinguish sourced fact from editorial interpretation;
- check duplicates, aliases, editions, and existing relationships before insertion;
- leave uncertain claims flagged for review;
- use the existing status workflow and never self-promote disputed records to `Approved for sync`;
- send schema/taxonomy change requests to the architecture lane rather than improvising fields;
- avoid copying private playlist data, credentials, or a minor's personal behavior into GitHub.

Its throughput does not set product architecture. New content that exposes a missing model is evidence for an ADR, not permission to mutate the contract invisibly.

## Architecture lead review template

```markdown
Readiness score: __/32
Critical questions at 2: yes/no
Zero-score answers: none/list
Contradictions found: none/list
Follow-up challenge: ...
Decision: ACCEPTED / CORRECTION REQUIRED
Scope accepted for first increment: ...
Boundaries explicitly withheld: ...
```

