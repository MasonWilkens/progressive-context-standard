# Progressive Context Standard (PCS)

**Version:** 0.2.0-draft  
**Status:** Independent proposal for review; not a ratified industry standard  
**Date:** 2026-11-14  
**Scope:** Project-neutral information design for progressive disclosure

> Make relevant information discoverable before loading its details. Supply the context needed for a correct decision. Do not hide necessary constraints to reduce context size.

## 1. Purpose and boundaries

PCS defines how to write, organize, describe, and connect information that readers or automated systems load selectively.

A project can apply PCS to a documentation website, research collection, operational handbook, knowledge base, repository, catalog, or other information collection. A project does not need to contain software.

PCS specifies an information contract. It does not specify a storage product, agent framework, execution protocol, search algorithm, or fixed folder layout. Markdown, HTML, structured records, and other representations can implement the contract.

PCS takes inspiration from controlled technical writing, topic-based publishing, and existing agent-context formats. It is independently written. Adoption does not establish conformance with ASD-STE100, ISO standards, DITA, or any other referenced specification. The sources and their contribution boundaries are documented in REFERENCES.md.

The Core is intended to be small enough to adopt without a new platform. Consumer and Maintainer requirements are optional, separately claimed profiles. Measurement is separate from conformance.

PCS does not guarantee correctness, security, lower cost, or successful task completion. It supplies rules that can be inspected and evaluated.

## 2. Requirement language and conformance subjects

Capitalized requirement terms use BCP 14: RFC 2119 and RFC 8174 [N1, N2]. `MUST` and `MUST NOT` impose requirements. `SHOULD` and `SHOULD NOT` allow justified exceptions. `MAY` permits an option. Lowercase uses have their ordinary meanings.

Numbered rules are normative for their stated subject. Definitions determine their interpretation. Examples, rationale, templates, adoption guidance, and source mappings are informative, even when an example contains a capitalized requirement word.

| Claim | Subject | Applicable rules |
|---|---|---|
| PCS Core | A declared documentation set and its discovery information | C01–C10, L01–L06, R01–R06, T01–T03, Q01–Q05, X01–X03 |
| PCS Consumer | A tool or integration that selects and loads context | A01–A05, Q01–Q05, X01–X03 |
| PCS Maintainer | A tool or process that validates or updates context | M01–M05, Q01–Q05, X01–X03 |

These claims are independent, not maturity levels. A Core documentation set does not need a conforming consumer or automated maintainer. A tool claim does not certify the content it processes.

A project can use selected practices without claiming conformance. A conformance claim requires the checks in Section 10. No certification body is established by this draft.

## 3. Information model

A **context unit** is an addressable piece of information with one coherent retrieval purpose. A unit can be a document, a section, a record, or a supported view of a resource. Units need not be separate files.

A **discovery record** describes a unit sufficiently to decide whether to retrieve it. It can appear in a map, a search result, a resource listing, or another discovery interface.

A **map** connects units through descriptions and references. A map can be a hub, catalog, index, or generated listing. The resulting structure can be a graph; it need not be a tree.

A **context contract** combines a unit's purpose, applicability, retrieval conditions, and relevant prerequisites. These facts can be divided between a discovery record and the unit, subject to C02 and C05.

A **locator** tells a consumer how to retrieve information. An **identifier** distinguishes a resource within a declared scope. A **revision** distinguishes a version of that resource. These are separate concepts.

An **authority statement** identifies what a source is accepted to establish within a project. A **provenance record** identifies where information came from and, when relevant, how it was produced or checked. Neither statement grants access or execution permission.

A **prerequisite** is information or a condition that must be satisfied before a specified decision or action. A **related resource** is potentially useful but is not automatically a prerequisite.

## 4. Core: information architecture

**Subject: the declared documentation set.**

### PCS-C01 — Declare coverage and entry points

The set MUST identify its coverage and at least one entry point. The declaration MUST make explicit any exclusions that would otherwise create a misleading coverage claim.

Coverage can be a collection, a subject area, a set of addresses, or another reproducible boundary. Linked external evidence is not automatically part of the conforming set.

### PCS-C02 — Publish a selection contract

Each in-scope unit MUST have a discoverable title or label, a purpose, and a locator. The discovery information MUST explain when the unit is relevant. It MUST expose restrictions that change whether the unit should be selected.

These facts MAY be expressed through prose or metadata. They do not require separate fields. A single precise description can communicate purpose, use conditions, and scope.

A consumer MUST be able to obtain this selection information without loading the unit's full detailed content. An entry point can supply its own selection information at its beginning.

### PCS-C03 — Use coherent units

Each unit MUST have a coherent retrieval purpose. Its content SHOULD answer a related question or support a bounded task.

Do not divide information merely to meet a word count. A condition and the instruction it qualifies belong together, or need an explicit prerequisite relationship. A smaller unit that requires many compensating reads can be less useful.

### PCS-C04 — Distinguish content roles

The set MUST distinguish operative instructions and policies from explanation, reference information, observations, and examples when their interpretation could affect action.

Projects MAY use roles such as map, explanation, procedure, reference, decision, policy, catalog, and tutorial. Projects need not use this vocabulary or create every type. One unit can contain labeled sections with different roles.

### PCS-C05 — Surface prerequisites before action

A unit that directs an action MUST state or explicitly reference prerequisites that affect whether the action is appropriate. The trigger MUST be visible before the reader is directed to act.

Required approvals, material warnings, compatibility conditions, and essential verification steps MUST NOT be hidden in an optional branch. A universal constraint belongs in the applicable entry context, or needs an explicit pre-action loading requirement.

This rule does not require all policies to be loaded for every task. It requires the relevant obligations to be discoverable in time.

### PCS-C06 — Make loading conditions explicit

A reference that requires another unit to be read MUST state the condition and the point at which that reading is required. An ordinary hyperlink MUST NOT, by itself, mean “load this resource and all its descendants.”

Navigation SHOULD differentiate prerequisites, deeper detail, evidence, and optional related material. Merely stating that two systems depend on each other does not define a context-loading instruction.

### PCS-C07 — Preserve multiple access paths

In-scope units MUST be reachable through at least one declared discovery route. That route MAY use navigation, a documented lookup service, or search over stated fields.

The set SHOULD permit direct access when the relevant unit is already known. Direct access MUST NOT make essential conditions available only through an undisclosed parent chain. Conditions can be included locally, explicitly referenced, or supplied by a declared delivery mechanism.

A unit MAY have multiple parents. Ordinary cross-reference cycles are permitted. A set MUST NOT contain an applicable prerequisite cycle that makes its own reading or action sequence impossible to satisfy.

### PCS-C08 — Provide a fallback route

The entry context MUST explain how to proceed when navigation does not supply the required information. A fallback can be scoped search, direct source inspection, an alternate locator, or a designated contact or issue route.

Guidance MUST NOT imply that an unlisted resource does not exist unless the collection's relevant completeness has been established.

### PCS-C09 — Preserve meaning in summaries

A summary MUST retain conditions, limitations, and exceptions that materially change its meaning. A summary that describes a changing source MUST identify that source or mark the description as unverified.

Short routing descriptions and critical warnings MAY be repeated where needed. Longer authoritative explanations SHOULD be maintained in one canonical location and referenced elsewhere. Essential local context is not prohibited duplication.

### PCS-C10 — Match detail to the task

Discovery information SHOULD contain the detail necessary to choose a next step, not the complete underlying subject. Detailed content SHOULD be deferred until it is relevant.

PCS defines no universal sentence, file, token, or navigation-depth limit. A project MAY set measured budgets. Budget policies MUST NOT authorize omission of prerequisites or silent truncation of material qualifications.

## 5. Core: language and interpretation

**Subject: the declared documentation set.**

### PCS-L01 — Use scoped, consistent terminology

A concept MUST be named consistently within its declared scope. Where different meanings share a term, the documentation MUST disambiguate them when the difference matters.

A project SHOULD record preferred terms and useful aliases. Aliases can include user vocabulary and historical names that assist discovery. Do not erase valid search terms merely to enforce one preferred label. Vocabulary can be specific to a domain or language.

### PCS-L02 — Preserve exact technical values

Documentation MUST preserve exact identifiers and values when it purports to reproduce them. This includes names, paths, addresses, keys, formulas, units, command syntax, and literal output.

Examples and placeholders MUST be identified as such. Simplification MUST NOT silently alter an interface or reference.

### PCS-L03 — Write explicit instructions

Instructions MUST identify the action and any condition or ordering requirement necessary to interpret it correctly. They MUST identify the responsible actor when more than one actor is plausible.

Writers SHOULD prefer direct sentences, explicit subjects, and one principal instruction per sentence. Writers SHOULD avoid unnecessary jargon and ambiguous pronouns. Necessary technical vocabulary takes priority over a simpler but inaccurate replacement.

### PCS-L04 — Define quantities and boundaries

When a quantity controls behavior, documentation MUST supply the units, baseline, inclusivity, or counting convention necessary to remove material ambiguity.

For example, “attempt the operation at most three times, including the first attempt” is more precise than “retry three times.” The correct wording depends on the intended behavior.

### PCS-L05 — Separate evidence from intent

Documentation MUST distinguish required behavior, observed behavior, recommendations, assumptions, and illustrative examples when confusion would affect a decision.

An inference MUST NOT be presented as a direct observation. Unknown information MUST NOT be represented as a negative finding. A policy describes what should happen; an observation describes what did happen. Their disagreement is a conflict to investigate, not permission to overwrite either one.

### PCS-L06 — Support the intended reader

The set MUST make its language apparent or declare it. Unfamiliar abbreviations SHOULD be defined locally or linked to a glossary.

PCS does not require English or the ASD-STE100 dictionary. Language-specific conventions MAY vary without changing technical meaning. Essential information conveyed through a diagram, image, or other non-text resource SHOULD have an accessible equivalent suitable for the intended consumers.

## 6. Core: references, evidence, and freshness

**Subject: the declared documentation set.**

### PCS-R01 — Define how references resolve

Locators MUST be interpretable within a declared or unambiguous base context. Internal references MUST resolve to their intended targets in the evaluated snapshot, or be explicitly marked as unavailable with a usable fallback or limitation.

When an unavailable target is an action prerequisite, the action MUST be identified as blocked unless a verified equivalent is available.

A project MAY use ordinary links and paths. URI-based bindings SHOULD use RFC 3986 reference resolution [N3]. Bindings MUST NOT silently reinterpret host-format path or fragment conventions.

### PCS-R02 — Separate identity, location, and revision

When identifiers are used, they MUST be unique within their declared scope. An identifier MUST NOT be reassigned to an unrelated unit while references to its former meaning remain supported.

A record SHOULD distinguish identity from its current location and version. A path, title, or symbol name is not automatically a permanent identifier. A hash demonstrates equality of encoded content, not correctness of its claims.

### PCS-R03 — Explain consequential relationships

A relationship MUST identify its target. If the relationship affects selection or action, it MUST also explain its purpose and applicable condition.

A project MAY use typed links. The following terms are suggested, not a mandatory vocabulary:

| Relationship | Meaning |
|---|---|
| `requires_before` | Read or satisfy the target before the specified decision or action. |
| `details` | The target supplies deeper information. |
| `evidence` | The target supports a stated descriptive claim. |
| `related` | The target may help; no loading obligation follows. |
| `supersedes` | This unit replaces the target within the stated scope. |

A relationship about the subject, such as a service dependency, SHOULD be distinguishable from a relationship that directs reading.

### PCS-R04 — Scope authority and preserve conflicts

A source identified as authoritative MUST have a stated or clearly established subject and scope. Authority for policy does not establish observed state; authority for observed state does not approve policy changes.

Material contradictions MUST be exposed or referred to the project's conflict-resolution process. Documents MUST NOT silently settle a conflict merely by being newer, more deeply nested, or more highly ranked by search.

Host-defined instruction precedence still applies where the host gives a resource that authority. PCS does not replace that precedence.

### PCS-R05 — Qualify verification claims

A claim that changing information has been verified MUST identify what was checked, the evidence or source version, and the verification method. These details MAY be stored in a linked review record rather than every unit.

Modification time alone MUST NOT be described as semantic verification. Link availability alone MUST NOT be described as verification of content accuracy.

Provenance SHOULD be sufficient to revisit a claim. It need not use RDF, a graph database, or a full provenance ontology.

### PCS-R06 — State relevant availability and uncertainty

Known restrictions that affect retrieval or use MUST be disclosed where the consumer needs them, without exposing protected information.

A set MUST distinguish an explicitly retired resource from a resource whose status is unknown. A temporary retrieval failure or access denial is not evidence of deletion. Projects SHOULD retain redirects or replacement notices when their supported references change.

## 7. Core: trust and information handling

**Subject: the declared documentation set.**

### PCS-T01 — Do not manufacture authority

Content MUST NOT claim that discovery, ranking, a format label, or PCS conformance grants permission to access information or perform actions.

An instruction-bearing resource can have authority delegated by its host or project. Retrieved examples, quoted material, and source data do not gain that authority merely by appearing beside it.

### PCS-T02 — Separate description from execution

A resource that describes an operation MUST NOT represent its description or hyperlink as execution authorization. Requirements for approval or access MUST remain explicit where applicable.

Executable examples SHOULD state important preconditions and side effects. PCS defines no automatic execution behavior for a link, metadata field, or example.

### PCS-T03 — Respect information boundaries

The set MUST state or reference applicable information-handling rules for sensitive content. Discovery records, titles, and excerpts MUST be included in that consideration, not only full documents.

A project MUST NOT use a documentation field as a substitute for actual access control. Selective disclosure for efficiency and access restrictions for security are separate mechanisms.

## 8. Optional Consumer profile

**Subject: a tool or integration that claims PCS Consumer conformance.**

### PCS-A01 — Select before expanding

The consumer MUST use task relevance and applicability when selecting context. It MUST NOT expand all reachable resources solely because they are linked.

It MAY load a bounded set of genuine prerequisites together. It SHOULD reuse still-applicable context instead of repeatedly retrieving the same information.

### PCS-A02 — Preserve obligations across retrieval

The consumer MUST check explicit relevant prerequisites before the affected action. When context is summarized, evicted, or handed off, the consumer MUST retain the obligations or a reliable mechanism to reload them before acting.

A compacted conversation does not cancel a prerequisite.

### PCS-A03 — Represent retrieval failures accurately

The consumer MUST distinguish missing, inaccessible, stale, conflicting, incomplete, and unverified information when these states are known and relevant. It MUST NOT invent a successful retrieval or treat absence from results as proof of nonexistence.

When a budget or unavailable dependency prevents a supported decision, the consumer MUST disclose the limitation and avoid the dependent action. Independent work MAY continue.

### PCS-A04 — Retain provenance and version context

The consumer MUST preserve enough source identity and version context to distinguish materially different evidence. It MUST expose consequential truncation or incomplete coverage.

The consumer SHOULD refresh evidence when it has reason to believe a relevant source changed. PCS imposes no fixed polling interval or mandatory retrieval technology.

### PCS-A05 — Enforce host boundaries

The consumer MUST respect host authorization, instruction precedence, and access controls. It MUST NOT execute content or elevate its authority merely because the content labels itself trusted or required.

Metadata can guide selection. It cannot grant its own permissions.

## 9. Optional Maintainer profile

**Subject: a tool or documented process that claims PCS Maintainer conformance.**

### PCS-M01 — Declare validation coverage

The maintainer MUST identify supported reference types, checked locations, snapshot or review boundary, and checks it could not perform.

It MUST distinguish failed checks from skipped, unauthorized, and unsupported checks. It MUST NOT report an untested reference as valid.

### PCS-M02 — Separate drift detection from truth assessment

The maintainer MUST distinguish “the source changed” from “this description is incorrect.” It MUST NOT mark semantic accuracy as verified solely from a timestamp, successful parsing, or an unchanged link.

Where updates affect known dependent summaries, it SHOULD flag the relevant claims for review rather than rewrite unrelated material.

### PCS-M03 — Repair only supported mappings

Automatic relinking MUST have evidence that the replacement is the intended target. Similar wording or a matching filename alone MUST NOT settle an otherwise ambiguous mapping.

Ambiguous repairs MUST remain unapplied and be reported for review. Unreferenced content MUST NOT be deleted merely because it is unreferenced.

### PCS-M04 — Preserve decisions and audit changes

Changes MUST be reviewable through a proposed diff, an audit record, or an equivalent mechanism. Material authored decisions and constraints MUST NOT be changed without the applicable authorization.

The maintainer MUST NOT substitute fabricated sources, identifiers, approvals, or verification records. A proposed semantic change MUST remain distinguishable from an accepted change.

### PCS-M05 — Revalidate affected navigation

After an applied change, the maintainer MUST check affected supported references and prerequisite routes. It MUST report unresolved consequences.

It SHOULD preserve supported identifiers and aliases through moves. It SHOULD provide a way to inspect or reverse an erroneous update.

## 10. Conformance and evaluation

**Subject: every PCS conformance claim.**

### PCS-Q01 — Make the claim reproducible

A claim MUST state the PCS version, claimed subject and profile, coverage boundary, evaluated revision or snapshot, evaluation date, and any required extensions. It MUST identify the evaluation record.

A claim about a small subset MUST NOT imply conformance of the complete project.

### PCS-Q02 — Evaluate all applicable requirements

Every applicable `MUST` and `MUST NOT` MUST be satisfied for an unqualified claim. A conditional requirement can be recorded as not applicable only with a reason.

Departures from `SHOULD` requirements SHOULD be documented with their trade-offs. A local waiver does not convert a failed mandatory rule into base PCS conformance.

### PCS-Q03 — Report check limits

The evaluation record MUST distinguish mechanical checks, semantic review, and execution or task evaluation. At minimum, individual outcomes MUST distinguish pass, fail, not evaluated, and not applicable.

A linter pass MUST NOT be represented as full conformance when required semantic or behavioral checks remain unevaluated. An AI-generated assessment MAY support review; it is not independent proof of correctness.

### PCS-Q04 — Separate performance from conformance

A claim of improved efficiency or task performance MUST identify its baseline, task set, measurement method, relevant environment, and observed results. Unmeasured benefits MUST be described as expected or proposed, not demonstrated.

Conformance alone MUST NOT be advertised as proof of fewer tokens, faster execution, lower cost, or better answers.

### PCS-Q05 — Evaluate quality before economy

When reporting context savings, the evaluation MUST also report task correctness or a relevant quality measure. It MUST disclose material increases in missed prerequisites, unsupported conclusions, or failure rates.

A useful comparison SHOULD report discovery success, unnecessary retrievals, total retrieval effort, task success, latency, and context usage. It SHOULD distinguish repeated input tokens from unique content and identify tokenizer and cache treatment when relevant.

Tests SHOULD include incomplete, ambiguous, stale, restricted, conflicting, and absent information, not only successful retrievals. Repeated trials SHOULD be used when execution is stochastic. PCS sets no universal performance threshold.

## 11. Extensions, versions, and adoption

**Subject: extensions and claims using them.**

### PCS-X01 — Preserve base meanings

An extension MUST identify its scope and version. It MUST NOT change a core term or requirement while claiming unchanged conformance to this PCS version.

Additional requirements MAY be imposed. A fork that changes base requirements MUST distinguish its own version or identity and document the differences.

### PCS-X02 — Make unsupported requirements visible

Extensions MUST distinguish optional information from requirements necessary to interpret or use a unit. A consumer that cannot support a required extension MUST disclose that limitation before the dependent action.

Unknown advisory fields MAY be ignored. Unknown required behavior MUST NOT be silently treated as satisfied. A host adapter MUST preserve host-format rules rather than assume arbitrary new metadata is accepted.

### PCS-X03 — Pin adoption to an identifiable edition

An adoption declaration MUST identify the edition used. A remote reference SHOULD identify an immutable version or verified snapshot; a copied edition SHOULD retain its version and origin.

A project MUST NOT silently replace its adopted requirements with a moving latest version. Referencing the standard does not require loading the entire standard into each task.

### Informative adoption guidance

Publish a short project entry instruction and a local adaptation statement. Keep the full specification available for authors, maintainers, and audits. Identify the existing entry points, applicable profiles, vocabulary, authority boundaries, and validation procedure.

Adoption does not require a `PCS.md`, `pcs.yaml`, or new directory. Existing files can carry the information. Projects can reference a released specification, vendor a copy, or maintain an explicitly identified fork.

The following is an illustrative declaration, not an evaluated claim or a standardized interchange schema:

```yaml
pcs:
  version: "0.2.0-draft"
  profile: "core"
  adoption_status: "in-progress"
  coverage: "Published project knowledge under docs/context/"
  entry_points:
    - "docs/context/index.md"
  exclusions:
    - "External resources cited only as evidence"
  assessment:
    status: "not-evaluated"
  extensions: []
```

## 12. Informative context-unit example

This example concerns an imaginary publication workflow. Its paths and local policies are examples, not facts about a real project.

```markdown
# Publish a report

Purpose: Prepare an approved report for public release.
Read when: Publishing a new report or replacing a published report.
Scope: Public reports. Internal drafts use a separate workflow.

## Before publication
Read ../policies/publication.md before creating the public copy.
Confirm that the named approver has approved this report version.
Approval of an earlier draft does not approve a changed report.

## Procedure
1. Confirm the approved version and intended audience.
2. Prepare the release using ../references/report-format.md.
3. Check that references resolve and required sections are present.
4. Publish through the project's authorized release process.
5. Record the published location and approved version.

## Completion condition
The public copy matches the approved version and has a recorded location.

## Exceptions
If approval is absent or unclear, do not publish.
Use the escalation route in ../policies/publication.md.

## Additional context
Read ../decisions/publication-history.md only when investigating
why the publication policy changed.
```

A corresponding discovery record could contain:

```yaml
id: "procedure.publish-report"
title: "Publish a report"
kind: "procedure"
summary: "Approval checks, formatting, and release verification for public reports."
use_when:
  - "Publishing or replacing a public report."
scope: "Public reports; excludes internal drafts."
location: "procedures/publish-report.md"
```

The YAML is illustrative. A plain Markdown map entry with the same meaning is sufficient for Core. The record does not grant permission to publish, establish that approval exists, or prove that the linked procedure is accurate.

## 13. Informative compatibility guidance

**AGENTS.md:** Use an existing agent entry point to describe project coverage and routes. Keep the host's discovery and instruction-precedence behavior. PCS does not create a new universal precedence hierarchy.

**Agent Skills:** Use the skill's existing description for selection and its body for relevant procedure and prerequisites. Keep deeper resources separate. Preserve the actual skill specification's field restrictions; PCS's example metadata is not an amendment to that format.

**llms.txt:** A short website map can supply discovery information. PCS does not require llms.txt or assume that a heading has executable loading semantics.

**DITA and Diátaxis:** Existing topics, maps, and document-purpose distinctions can implement PCS. XML conversion and a particular set of topic types are not required.

**MCP or other resource protocols:** Resource listings and reads can deliver context units. PCS concerns the supplied information and its selection contract; it does not replace transport, authentication, or protocol rules.

**Search and retrieval systems:** A result can serve as a discovery record if it carries the required information. Neither a similarity score nor a ranking position establishes authority or verification.

## 14. Publication and governance notes

These notes are informative and are not a claim that the project is already published.

Keep rule identifiers stable within an edition. Track substantive changes separately from editorial corrections. Publish migration notes when requirements change. Record proposals with their problem statement, expected benefit, compatibility effects, and evaluation approach.

Before public release, choose the project's reuse license and canonical publication location. This draft does not assign a license on the user's behalf. References identify influences; they do not relicense third-party standards or bundle their complete texts.

### References within this specification

- **[N1]** RFC 2119, *Key words for use in RFCs to Indicate Requirement Levels*.
- **[N2]** RFC 8174, *Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words*.
- **[N3]** RFC 3986, *Uniform Resource Identifier (URI): Generic Syntax*, for the URI-based recommendation in R01.

Full source locations and the informative influence map are provided in REFERENCES.md. No other referenced work is incorporated wholesale as a normative dependency.

---

**PCS's central distinction:** Progressive disclosure controls when information is loaded. It does not reduce the obligation to obtain the information necessary for a correct, authorized decision.
