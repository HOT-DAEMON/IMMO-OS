# Atomic Work Unit Template

Copy this template for each implementation increment. Keep one file per work item under `docs/work/IMMO-<DOMAIN>-<NNN>.md` when the work is substantial enough to need a persistent specification.

---

# <WORK-ID> — <short outcome>

## Status
Proposed | In progress | Blocked | Partial | Done

## 1. User/system outcome
Describe one observable outcome in plain language. Avoid implementation-first goals such as "create a service" unless the service itself is the required deliverable.

## 2. Baseline
- Observed:
- Existing paths and entry points:
- Existing tests:
- Runtime behavior:
- Unknowns:

## 3. Scope
### In scope
- 

### Explicitly out of scope
- 

## 4. Domain and contract
- Domain owner:
- Inputs:
- Outputs:
- Invariants:
- Validation rules:
- Units / coordinate reference / currency / time zone, where relevant:
- Errors and failure behavior:
- Permissions and audit requirements:

## 5. Acceptance criteria
Write observable, testable statements. Each criterion must have a verification method.

| ID | Acceptance criterion | Verification |
|---|---|---|
| AC-01 | | Automated test / runtime / visual proof |
| AC-02 | | |

## 6. Edge cases and threat review
Consider missing, malformed, duplicated, stale and conflicting data; boundary values; retries; concurrent edits; unauthorized access; network failure; localization; accessibility; and applicable domain-specific exceptions.

Record only relevant cases, but explain why omitted risks do not apply.

## 7. Minimal design
- Components/files to change:
- Contract changes:
- Data/migration changes:
- Dependencies:
- Alternatives considered:
- Why this is the smallest coherent design:

## 8. Test plan
- Unit:
- Integration:
- Contract:
- Regression:
- Manual/runtime:
- Commands to run:

## 9. Evidence plan
- Actual application state or workflow to capture:
- Required screenshots:
- Required data/response/log evidence:
- Reproduction steps:
- Evidence destination: `docs/evidence/<WORK-ID>/`

## 10. Implementation log
Record meaningful changes and deviations from the plan. Do not use this section as a substitute for a useful commit history.

## 11. Review and debt
- Diff reviewed:
- Security/privacy review:
- Performance considerations:
- Debt introduced:
- Debt retired:

## 12. Completion
- Status:
- Acceptance criteria passed:
- Tests/checks and exact results:
- Runtime result:
- Evidence links/paths:
- Remaining limitations:
- Decision-log references:
