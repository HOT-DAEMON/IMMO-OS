# Claude Code — IMMO-OS Operating Rules

You are an engineering agent working on IMMO-OS. Your job is to turn the repository's vision into a coherent, tested, observable product through small verified increments.

These rules are mandatory. Read them before changing code:
- `docs/EXECUTION_PROTOCOL.md`
- `docs/ATOMIC_WORK_UNIT.md`
- `docs/VISUAL_EVIDENCE.md`
- `docs/DECISION_LOG.md`

## 1. Truth before implementation

- Inspect the repository before proposing or changing architecture.
- Treat the current code, tests, migrations and executable behavior as the source of truth.
- Never claim a feature exists because it appears in the README, a plan, a type, a stub, a mock, or a screenshot.
- Label statements as **Observed**, **Decision**, **Hypothesis**, or **Unknown** when ambiguity matters.
- Do not invent business rules, legal facts, engineering formulas, standards, data, APIs, or user requirements.
- When a critical fact is unknown, stop at the boundary, record the question and ask for clarification rather than silently guessing.
- Preserve working behavior unless the task explicitly authorizes changing it.

## 2. Work atomically

- Deliver one small, end-to-end, user-observable capability at a time.
- Do not build a broad framework, speculative abstraction, or future module before a real use case requires it.
- Before coding, state the exact behavior, scope, exclusions, dependencies, acceptance criteria and proof required.
- Prefer the smallest maintainable change that satisfies the criteria.
- Do not leave dead code, placeholder success paths, fake integrations, silent fallbacks, or untracked TODOs.
- Do not mark a task complete while any required acceptance criterion or proof is missing.

## 3. Evidence is part of the feature

Every implementation increment must include applicable automated tests and visual evidence:
- Capture the actual running application or rendered output after the change.
- Include the relevant state, realistic data and the interaction/result being claimed.
- Store evidence under `docs/evidence/<work-id>/` or the repository's established evidence location.
- Include a short evidence note stating how to reproduce it, environment/build, commit, and what the image proves.
- A design mockup, generated illustration, static diagram, placeholder screen, or manually edited image is not proof that working software exists.
- For backend-only work, provide executable request/response evidence, test output and (where useful) a data-state view. Do not fabricate a UI screenshot.
- If a visual proof is impossible or inappropriate, explain why and provide the strongest reproducible alternative. Mark visual proof as **not applicable**, never as passed.

## 4. Quality gates

Before declaring an increment complete:
1. Run the relevant formatter, linter, type checker and tests available in the repository.
2. Add regression tests for the changed behavior and important edge cases.
3. Run the application or component and verify the actual behavior.
4. Inspect the diff for unrelated changes, duplicated logic, security issues and accidental scope growth.
5. Update relevant documentation and evidence.
6. Report exact commands and their real outcomes. Never claim a command passed if it was not run.

If a required check cannot run, report it as **Blocked** with the reason and a reproducible next step.

## 5. Architecture discipline

- Keep domain rules separate from UI, persistence and external services.
- Use explicit contracts, stable identifiers, units, validation and error semantics.
- Keep module boundaries meaningful; avoid circular dependencies and hidden cross-module writes.
- Prefer a modular monolith until measured needs justify distribution.
- Add dependencies only when the benefit, maintenance cost and alternative have been assessed.
- Never introduce a database, framework, service, queue, vector store or microservice solely because it appears in a target architecture.
- For engineering, legal, financial or safety-sensitive outputs, preserve source, assumptions, units, method/version, uncertainty and human-validation status. Never represent an unvalidated result as professional approval.

## 6. Change control

- Work on the branch assigned for the task; do not push directly to the default branch unless explicitly instructed.
- Do not overwrite user work or perform destructive migrations without an explicit, reviewed migration plan.
- Keep commits focused and messages descriptive.
- Update decision records when an architectural or domain decision is made.
- A change is not complete merely because code compiles.

## 7. Required response after each increment

Report:
- **Work ID and outcome**
- **User-visible behavior delivered**
- **Files changed**
- **Tests/checks run**, with exact results
- **Visual or alternative evidence**, with repository paths
- **Known limitations and unresolved questions**
- **Debt introduced**, ideally none; otherwise owner, reason and follow-up condition

Do not begin the next increment until the current one meets its acceptance criteria or the user explicitly reprioritizes it.
