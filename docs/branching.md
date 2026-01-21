# Branching Strategy (Katas)

This repo is built as a refinement log + kata playground.

## Main branch
`main` contains:
- All documentation (single source of truth)
- The clean reference implementation of the sample app (baseline)
- Contribution guidelines and repo conventions

Kata code lives in dedicated branches. Docs stay on `main`.

---

## Kata branches (MVP)
Each kata follows the same naming scheme:

- `kata-01/start`
- `kata-01/solution`

Repeat for:
- `kata-02/start`, `kata-02/solution`
- `kata-03/start`, `kata-03/solution`

### Optional step branches
If a kata is too large, we can add intermediate steps:

- `kata-01/step-01`
- `kata-01/step-02`
- ...

**Rule:** step branches are optional and should only exist when they teach one focused concept each.

---

## Branch semantics
### `start`
Intentionally flawed code with common anti-patterns.
This branch exists for learning purposes and should not be used as production reference.

### `solution`
Production-grade refactor:
- deterministic state management
- correct side-effect handling
- improved stability/readability
- tests where applicable

---

## How to navigate (for users)
1) Read the kata spec on `main` (`docs/02-kata-01.md`, etc.)
2) Checkout `kata-XX/start`
3) Refactor following the spec (or compare with `kata-XX/solution`)

---

## Maintenance rules
To avoid “branch drift”:
- `main` evolves normally (docs + baseline sample app).
- Kata branches are treated as snapshots.
- We only update kata branches for critical fixes (build breaks, incorrect instructions).

---

## Trade-offs (why branches)
### Branches vs folders
**Pros**
- True kata experience: checkout `start`, refactor, compare with `solution`
- Clear separation between exercise code and baseline
- Git history becomes part of the learning

**Cons**
- More maintenance than folders
- Potential branch drift if baseline changes often
- Contributions require extra care (PRs usually target `main`)

### Docs only on `main`
**Pros**
- One place to read and contribute
- PRs remain simple and reviewable
  **Cons**
- Docs must stay aligned with kata snapshots (mitigated by maintenance rules)

### Step branches
**Pros**
- More beginner-friendly, incremental guidance
  **Cons**
- Multiplies maintenance cost
- Makes the repo noisier

Decision: MVP ships with only `start` + `solution`. Steps are optional.
