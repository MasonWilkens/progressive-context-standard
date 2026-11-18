# PCS research notes and source map

**Research date:** 2026-11-14  
**Applies to:** PCS 0.2.0-draft  
**Status:** Informative, except for the narrowly referenced IETF definitions identified in the specification.

## Reading this comparison

PCS is not the first use of progressive disclosure for agents. Related open formats and practical implementations already exist. This review did not establish an exact equivalent of the proposed PCS combination, and is not an exhaustive novelty or name-availability search.

A formal standard, an open format, a protocol, a documentation framework, and a community implementation are different kinds of work. The table preserves those distinctions.

The PCS rules are independently drafted. A conceptual influence does not mean that PCS implements the complete source standard, that its authors endorse PCS, or that an existing client automatically recognizes PCS metadata.

| Source | Status / reviewed edition | Applicable contribution | PCS use and boundary |
|---|---|---|---|
| ASD-STE100 | Controlled-language standard; official explanatory pages and FAQ reviewed | Consistent technical terms; clear instructions; precision | L01–L04. No reproduction of the controlled dictionary, no STE compliance claim, and no compulsory English-only vocabulary. |
| ISO 24495-1:2023 | International Standard; public abstract and scope reviewed | Plain-language guidance is relevant to technical writing and multiple written languages | L06 and reader-oriented design. The full paid text was not reviewed; this is not a clause-by-clause ISO mapping. |
| OASIS DITA 1.3 | OASIS Standard; selected topic, map, and information-typing sections reviewed | Focused topics, separate maps, and different information purposes | C03, C04, C07. No XML requirement or DITA specialization model is imported. |
| Diátaxis | Documentation framework | Separate explanation, reference, how-to guidance, and tutorial needs | C04. PCS allows these roles but does not require four folders or four documents for each subject. |
| Agent Skills | Open format specification; current online specification reviewed | Discover from descriptions; load instructions and supporting resources as needed | C02, C06 and compatibility guidance. Its filename rules and size recommendations are not universal PCS requirements. |
| AGENTS.md | Open repository-instruction format; current official site reviewed | An existing entry point can carry project rules and routes | Adoption and compatibility guidance. Host instruction precedence remains host-defined. |
| llms.txt | Website-discovery proposal, v2, modified 2026-08-10 | Brief site orientation and annotated links | Discovery adapters. It is a proposal, not an ISO/OASIS standard; PCS does not give its Optional heading execution semantics. |
| RFC 2119 and RFC 8174 | IETF BCP 14 | Consistent requirement strength and uppercase-keyword interpretation | Section 2; narrow normative references. |
| RFC 3986 | IETF URI standard | Base-relative URI reference resolution | R01's URI-binding recommendation. Local host conventions still need to be identified. |
| W3C QA Framework: Specification Guidelines | W3C Recommendation, 2005 | Identify conformance subjects, requirements, extensions, and claim boundaries | Separate Core, Consumer, and Maintainer claims; Q and X rules. No automatic certification claim. |
| W3C SKOS Reference | W3C Recommendation, 2009 | Preferred and alternative labels, scoped concepts, multilingual labels | Terminology guidance in L01. No RDF or SKOS serialization requirement. |
| W3C PROV-DM | W3C Recommendation, 2013 | Distinguish information, derivation, activity, and provenance | R05 and review records. No complete PROV data model requirement. |
| Model Context Protocol | Open protocol; 2026-07-28 specification and resource sections reviewed | Resources are exposed through identifiers; authorization and trust require explicit handling | Compatibility guidance and trust boundaries. PCS is not a transport, tool protocol, or authorization implementation. |

## Primary source locations

### [S1] ASD-STE100

Organization: ASD Simplified Technical English Maintenance Group.

- About STE: `https://www.asd-ste100.org/about_STE.html`
- Official FAQ: `https://www.asd-ste100.org/STE_faq.html`
- Explanatory page on writing rules and technical terms: `https://www.asd-ste100.org/about.html`

Scope note: The older about.html page has an outdated issue statement. It was used only for its explanation of writing principles and technical terminology, not to establish the current edition. Some official pages were available through search excerpts when direct fetching returned an access error. No full official dictionary or standard text is reproduced.

### [S2] ISO 24495-1:2023

Organization: International Organization for Standardization.

Title: Plain language — Part 1: Governing principles and guidelines.

Location: `https://www.iso.org/standard/78907.html`

Scope note: The publicly available scope says the guidance includes technical writing and applies to most written languages. The full standard was not obtained. PCS does not claim ISO conformance.

### [S3] OASIS DITA 1.3

Organization: OASIS.

Edition used: Part 1, Base Edition, OASIS Standard, 17 December 2015. This identifies the referenced edition; it is not a claim that 1.3 is the newest edition.

- Specification: `https://docs.oasis-open.org/dita/dita/v1.3/os/part1-base/dita-v1.3-os-part1-base.html`
- Topic as the basic unit: `https://docs.oasis-open.org/dita/dita/v1.3/os/part1-base/archSpec/base/topicdefined.html`
- Information typing: `https://docs.oasis-open.org/dita/dita/v1.3/os/part1-base/archSpec/base/information-typing.html`
- Map definition: `https://docs.oasis-open.org/dita/dita/v1.3/os/part1-base/archSpec/base/definition-of-ditamaps.html`

### [S4] Diátaxis

Author / project: Daniele Procida and the Diátaxis documentation project.

- Framework: `https://diataxis.fr/`
- How-to guidance: `https://diataxis.fr/how-to-guides/`

### [S5] Agent Skills

Project: Agent Skills.

- Format specification: `https://agentskills.io/specification`
- Authoring guidance: `https://agentskills.io/skill-creation/best-practices`

Compatibility note: The reviewed specification defines `metadata` as a string-to-string map. A PCS adapter must not insert arbitrary nested objects there and assume conformance. Use a compatible representation or a referenced sidecar where needed.

### [S6] AGENTS.md

Project: AGENTS.md.

Official format site: `https://agents.md/`

Compatibility note: PCS does not require a new entry filename or claim that every host loads nested instructions identically.

### [S7] llms.txt

Author: Jeremy Howard.

Proposal: The /llms.txt file, v2.

Location: `https://llmstxt.org/`

Version note: The reviewed page reports modification on 10 August 2026. Its Optional section is a convention for secondary links, not an authorization or execution rule.

### [N1] RFC 2119

Author: S. Bradner. IETF Best Current Practice 14, March 1997.

Location: `https://www.rfc-editor.org/rfc/rfc2119.html`

### [N2] RFC 8174

Author: B. Leiba. IETF Best Current Practice 14, May 2017.

Location: `https://www.rfc-editor.org/rfc/rfc8174.html`

### [N3] RFC 3986

Authors: T. Berners-Lee, R. Fielding, L. Masinter. January 2005.

Location: `https://www.rfc-editor.org/rfc/rfc3986.html`

### [S8] W3C QA Framework: Specification Guidelines

W3C Recommendation, 17 August 2005.

Location: `https://www.w3.org/TR/qaframe-spec/`

### [S9] W3C SKOS Reference

W3C Recommendation, 18 August 2009.

Location: `https://www.w3.org/TR/skos-reference/`

### [S10] W3C PROV-DM

W3C Recommendation, 30 April 2013.

Location: `https://www.w3.org/TR/prov-dm/`

### [S11] Model Context Protocol

Reviewed specification: 2026-07-28.

- Specification: `https://modelcontextprotocol.io/specification/2026-07-28`
- Resources: `https://modelcontextprotocol.io/specification/2026-07-28/server/resources`

## Adjacent implementation, not a normative source

The public `pwarnock/progressive-disclosure` project implements a practical multi-tier restructuring approach for LLM-consumed documents. It demonstrates that tiered loading and reference cleanup already have community implementations. PCS need not claim those ideas as new.

Project: `https://github.com/pwarnock/progressive-disclosure`

This implementation is not incorporated into PCS and is not presented as an established industry standard.

## Important design changes from the earlier working draft

The new name is Progressive Context Standard (PCS). The text is project-neutral and does not require a repository, a programming language, or an agent.

The draft replaces a single compliance ladder with separately scoped claims. It does not require operational tool behavior to claim document conformance.

It removes fixed English sentence limits and compulsory technical dictionaries. It preserves useful aliases and makes vocabulary scoped and language-aware.

It distinguishes a reading prerequisite from a relationship between the things being documented. It permits graph navigation, direct entry, and necessary repetition of critical constraints.

It treats policy, observed behavior, and implementation as different kinds of authority. A current implementation can violate a policy; neither should silently erase the other.

It distinguishes an address that resolves from a claim that has been verified. It also separates measured performance from static conformance.
