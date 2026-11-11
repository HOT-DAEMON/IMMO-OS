# IMMO-OS — Decision and Uncertainty Log

This log records decisions that materially affect domain meaning, architecture, data, security or long-term compatibility.

Do not record every minor coding choice. Use one entry per meaningful decision. Never rewrite history silently; supersede an entry with a new one.

## Status vocabulary

- **Proposed:** under consideration; not an implementation instruction yet.
- **Accepted:** chosen direction; implementation may proceed within its stated scope.
- **Rejected:** considered and not selected.
- **Superseded:** replaced by a later decision.
- **Unknown:** evidence is insufficient to decide.

## Decision template

```text
ID: ADR-IMMO-NNN
Title:
Status:
Date:
Context / problem:
Observed facts:
Options considered:
Decision:
Reasons:
Consequences:
Risks / trade-offs:
Validation required:
Related work IDs:
Supersedes / superseded by:
```

---

## Initial project constraints and open questions

The entries below are deliberately not architecture decisions. They identify facts and questions that must be validated before implementation hardens them.

### OBS-001 — Product scope is a broad target vision

**Status:** Observed

The README describes territory, land, architecture, engineering, construction, property operations and lifecycle management. It explicitly says the repository is at the beginning of development and that the described capabilities are not necessarily implemented.

**Implication:** Do not scaffold or implement all domains at once. Select a bounded first vertical slice based on a validated user problem.

### OPEN-001 — First user and first workflow

**Status:** Unknown

Who is the first real user, what recurring task are they trying to complete, and what is the smallest end-to-end workflow that creates measurable value?

**Required evidence:** A concrete workflow, user role, input/output examples and acceptance criteria.

### OPEN-002 — Initial jurisdiction and legal model

**Status:** Unknown

Which country and jurisdiction govern the first land/property workflow? Which official sources, records and professional/legal reviews are available?

**Required evidence:** Identified sources, provenance rules, legal review boundary and explicit treatment of disputed or unverified claims.

### OPEN-003 — Canonical identity and temporal history

**Status:** Unknown

How should the system identify a site, parcel, building, space, asset and component across revisions, subdivisions, mergers and ownership/administrative changes? How will it reconstruct what was known at a past date?

**Required evidence:** Domain examples, identity lifecycle rules, event/version semantics and integrity tests.

### OPEN-004 — Geometry and coordinate reference

**Status:** Unknown

Which geometry types, coordinate reference systems, precision rules, topology constraints and import sources are required for the first workflow?

**Required evidence:** Realistic sample data, CRS documentation and validation tests.

### OPEN-005 — Technology baseline

**Status:** Unknown

The repository README proposes logical folders but does not establish a verified application stack or production architecture.

**Required evidence:** A small runnable vertical slice and measured constraints before selecting or expanding infrastructure.

## Rules for closing an open question

An open question may be closed only when:
- the evidence and source are recorded;
- the decision owner and scope are clear;
- consequences and migration/compatibility risks are understood;
- relevant tests or validation steps are identified.

A guess is not a decision. A decision is not proof that its implementation works.
