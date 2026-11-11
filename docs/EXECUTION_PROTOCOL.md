# IMMO-OS — Execution Protocol

## Purpose

This document defines how work moves from an idea to a verified product increment. It is designed to prevent technical, architectural, domain, data and visual debt from accumulating invisibly.

The protocol applies to features, refactors, integrations, data models, calculations and UI work.

## 1. Establish the baseline

Before every task, inspect:
- repository tree and existing conventions;
- relevant source files and call sites;
- tests, fixtures, migrations and configuration;
- current runtime behavior, if runnable;
- recent decisions and known limitations.

Write a concise baseline:
- **Observed:** directly confirmed in code, tests or runtime;
- **Decision:** explicitly selected direction;
- **Hypothesis:** plausible but not yet validated;
- **Unknown:** information still missing.

Do not infer that an empty or missing implementation is present.

## 2. Define a bounded increment

Each increment must have:
- a unique Work ID (example: `IMMO-CORE-001`);
- one user or system outcome;
- one clearly bounded domain responsibility;
- explicit in-scope and out-of-scope items;
- acceptance criteria that can be demonstrated;
- required automated checks;
- required visual or alternative evidence;
- dependencies and rollback considerations.

A work item is too large if it contains multiple independently useful user outcomes. Split it.

## 3. Follow the vertical-slice sequence

For each increment:

1. **Understand** — inspect the existing implementation and identify the true change boundary.
2. **Specify** — describe the behavior, contract, constraints and acceptance criteria.
3. **Challenge** — look for missing cases, invalid assumptions, security/privacy risks and simpler alternatives.
4. **Design minimally** — define only the interfaces and data structures needed for this increment.
5. **Implement** — make the smallest coherent change.
6. **Test** — add and run automated tests, including regression and boundary cases.
7. **Run** — start the real application or execute the real workflow.
8. **Observe** — capture visual evidence or reproducible non-visual evidence.
9. **Review** — inspect the diff and assess debt, coupling, performance and maintainability.
10. **Record** — update docs, decision log and evidence note.
11. **Close** — report results and stop. Do not silently continue into the next feature.

## 4. Definition of Done

An increment is **Done** only when all applicable conditions are true:

- Acceptance criteria pass.
- The implementation is connected to the real execution path; no fake success path.
- Relevant automated tests exist and pass.
- Existing relevant tests still pass.
- The actual runtime behavior has been exercised.
- Visual evidence is captured, or a reasoned not-applicable statement and alternative proof are supplied.
- Documentation and contracts match the implementation.
- No unexplained TODO, stub, skipped test or swallowed exception was introduced.
- The diff contains no unrelated changes.
- Security, privacy, authorization and data-integrity implications have been considered.
- Remaining limitations and debt are explicitly recorded.

Use **Blocked** when an essential dependency, requirement or verification is missing. Use **Partial** when some criteria pass but the Definition of Done is not met. Never relabel either as Done.

## 5. Debt register

At the end of each increment, classify debt:
- **Technical:** duplication, brittle code, missing tests, dependency risk, performance.
- **Architectural:** unclear ownership, circular dependency, leaky boundary, premature abstraction.
- **Domain:** ambiguous terminology, unvalidated rule, missing exception or jurisdiction.
- **Data:** missing provenance, weak identity, inconsistent units, migration or integrity risk.
- **Visual/UX:** unverified states, misleading feedback, inaccessible interaction, inconsistent representation.
- **Security/privacy:** excessive access, unsafe input, missing audit, retention or consent gap.

For every accepted debt item record: ID, description, impact, why it is accepted, affected paths, owner/role, and trigger or target increment for resolution. Critical security, data-loss or safety debt is not acceptable as routine backlog.

## 6. Change-size control

Prefer one behavior and a small reviewable diff. If a change touches many unrelated modules, stop and split it unless the cross-module change is essential to the same end-to-end behavior.

Do not:
- scaffold every planned folder or module in advance;
- add generic frameworks without at least one real consumer;
- rewrite unrelated code during a feature;
- replace a failing test with a weaker test;
- hide uncertainty behind permissive defaults;
- use mock data to claim a production integration works.

## 7. Engineering and regulated outputs

Any calculation or recommendation affecting construction, structural safety, property rights, legal status or financial decisions must identify:
- input data and provenance;
- units and coordinate/reference systems where relevant;
- assumptions and applicable scope;
- method, formula or engine and version;
- validation status and known uncertainty;
- required qualified human review.

A passing software test proves only the tested software behavior; it does not certify a building, legal title, financial valuation or regulatory compliance.

## 8. Completion report template

```text
Work ID:
Status: Done | Partial | Blocked
Outcome:
Acceptance criteria:
Files changed:
Commands executed:
Automated test results:
Runtime verification:
Visual evidence:
Alternative evidence (if visual N/A):
Known limitations:
Debt introduced or retired:
Decision-log entries:
Next smallest increment (not started):
```
