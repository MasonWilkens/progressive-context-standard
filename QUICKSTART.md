# PCS quick adoption guide

**For:** Authors or maintainers adding PCS to an existing project.  
**Edition:** 0.2.0-draft.  
**Status:** Informative summary, not a replacement for the specification.

## Start with the existing entry point

Keep the project's current hub, index, instruction file, or documentation homepage. Identify what the collection covers and where a reader starts.

For each context unit, make the purpose and location discoverable. Explain when to use the unit and expose any restriction that changes that choice. A clear index description can do this without YAML.

Keep each unit coherent. Do not create a file for every sentence or load all details into the entry point. Important conditions belong with the instructions they qualify.

## Label the next read

Prefer “Read the release policy before publishing externally” to “See also: policy.”

Distinguish required prerequisites from optional depth and source evidence. Do not automatically read all linked resources.

A reader who reaches a procedure directly still needs its material prerequisites. Do not rely on an invisible path through parent documents.

## Keep claims precise

Preserve names, values, units, and reference syntax. Use consistent terms, but keep useful aliases for search.

Distinguish approved policy, observed state, inferred conclusions, and examples. Link changing factual summaries to their sources. A recent edit or a successful link check does not prove correctness.

## Validate proportionately

Check internal routes and required dependencies. Review whether instructions are clear and appropriately qualified. Report what was not checked.

Automated relinking needs evidence of identity, not just a similar filename. Do not delete an unreferenced document solely because it has no incoming link.

## Adopt without increasing every task's context

An entry point can say, in project-approved wording:

> This collection uses PCS 0.2.0-draft. Start from the existing context index. Select resources by purpose and applicability. Read relevant prerequisites before acting. Follow optional links only when needed. Consult the full PCS specification when authoring or auditing context, not automatically for every task.

Replace “the existing context index” with an actual project location. Referencing this guide does not authorize operations or override host instructions.

## Declare the adoption honestly

Record the edition, selected profile, entry points, and coverage. Mark the adoption as in progress until its mandatory requirements have been evaluated.

Core documentation conformance does not require a new loader, maintainer, file extension, or storage platform. Consumer and Maintainer are separate optional claims.

Use CONFORMANCE.md as a report template. The complete requirements are in SPECIFICATION.md.
