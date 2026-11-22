# ADR-002: License and repository visibility

- **Status:** Accepted
- **Date:** 2026-11-22

## Context and problem

The project may become a commercial product and is also a portfolio piece.
No application code exists yet. Published code cannot be taken back, so the
policy must be set before the first code commit.

## Decision drivers

1. Visibility: recruiters must be able to evaluate the work.
2. Protection: the code must not be freely copied if the project becomes commercial.

## Considered options

1. MIT license, public repository
2. AGPL-3.0 license, public repository
3. Source-available license (for example, Business Source License)
4. Private repository only
5. Hybrid: public documentation, private code

## Pros and cons

| Option              | Pros                                                     | Cons                                                                     |
| ------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------ |
| 1. MIT, public      | Maximum visibility; no extra work                        | Anyone may copy, modify and sell the code                                |
| 2. AGPL, public     | Visible; services built on it must publish their changes | Companies often avoid AGPL; does not stop copying for non-commercial use |
| 3. Source-available | Visible; restricts competing commercial use              | Not open source; adds legal complexity                                   |
| 4. Private only     | Maximum protection                                       | Recruiters cannot see anything without an invitation                     |
| 5. Hybrid           | Shows reasoning publicly and protects the code           | Two repositories to maintain; code is not publicly visible               |

## Decision outcome

Chosen option: **5. Hybrid**.

- This repository stays public and holds documentation only: vision, use
  cases, ADRs, glossary, diagrams, screenshots and demo material.
- Application code lives in a separate private repository, created before
  the first code commit. No code is committed to this public repository.
- Recruiters can evaluate the code through read-only invitations, a demo
  video, or a screen share during interviews.
- The private repository has no open source license (all rights reserved)
  until a new decision is made.

### Consequences

- Positive: design decisions stay visible to recruiters; the code stays
  protected while the commercial potential is unknown.
- Negative: more maintenance (two repositories); code quality cannot be
  judged from the public profile alone.

## Revisit when

- The first paying customer or contract appears.
- Recruiters report that they cannot evaluate the project well enough.
- A decision is made to open source part of the code.

## Follow-ups

- Review the README license section: MIT will cover only this documentation repository.
