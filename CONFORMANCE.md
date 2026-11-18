# PCS evaluation report template

**Status:** Blank template. No conformance assessment has been performed by filling this file with headings.

## Claim boundary

| Field | Value to provide |
|---|---|
| PCS edition | 0.2.0-draft |
| Subject and profile | Core documentation set, Consumer, or Maintainer |
| Coverage | Exact collection, locations, or supported functions |
| Exclusions | Explicitly excluded content or functions |
| Evaluated version | Document snapshot, source revision, or tool release |
| Date | Date of actual evaluation |
| Required extensions | Names and versions, or none |
| Evaluator | Person, team, or process responsible |
| Overall status | Not evaluated, partial, failed, or conformant |

## Requirement results

For each applicable rule and mandatory obligation, record a result and evidence. Do not assume that one successful obligation proves every obligation under the same rule.

| Rule / obligation | Method | Outcome | Evidence | Limitation or exception |
|---|---|---|---|---|
| PCS-C02 selection information | Semantic review and retrieval check | Not evaluated | — | — |
| PCS-R01 internal target resolution | Mechanical check | Not evaluated | — | — |
| PCS-C05 pre-action prerequisites | Semantic review | Not evaluated | — | — |
| PCS-Q04 claimed performance benefit | Benchmark review, if claimed | Not evaluated | — | — |

Use pass, fail, not evaluated, or not applicable. Give a reason for not applicable. Incomplete access is a check limitation, not a pass.

## Recommended checks by method

**Mechanical:** Identity uniqueness, required record fields where a binding defines them, known reference resolution, supported fragments, discovery reachability, and configured version identifiers.

**Semantic:** Whether selection descriptions discriminate between tasks; whether conditions are clear; whether summaries preserve exceptions; whether policy and observations are distinct; whether repair evidence establishes identity.

**Behavioral:** Whether a consumer loads applicable prerequisites, preserves obligations across a handoff, reports missing evidence, and refuses to treat untrusted content as authorization.

The method is independent of the requirement's severity. A mandatory requirement can need human review.

## Performance appendix, only when reporting performance

Record baseline, tasks, expected evidence, expected quality criteria, models or readers, tools, permissions, context limits, tokenizer, cache treatment, source snapshots, number of trials, and measured outcomes.

Include representative cross-topic tasks and cases with absent, conflicting, stale, incomplete, or restricted information. Report quality and failures alongside cost, latency, retrieval steps, and context usage.

Do not prefill this appendix with fabricated measurements. Core conformance does not require a claimed speedup.
