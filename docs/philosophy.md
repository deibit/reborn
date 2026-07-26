# Reborn Philosophy

## Purpose

This document defines the engineering philosophy of Reborn.

Every architectural decision, coding convention, workflow and AI guideline derives from the principles described here.

When multiple documents appear to overlap, this document defines the underlying intent behind those decisions.

---

# Mission

Reborn exists to provide a foundation for building software that remains understandable, maintainable and enjoyable to evolve over time.

Technologies change.

Frameworks evolve.

Programming languages improve.

Good engineering principles endure.

---

# Core Principles

## Correctness

Correct software is the highest priority.

Never sacrifice correctness for elegance, cleverness or convenience.

Reliable software always comes first.

---

## Simplicity

Choose the simplest solution that completely solves the problem.

Avoid unnecessary complexity.

Do not design for hypothetical future requirements.

Complexity should only be introduced when its value clearly exceeds its cost.

---

## Locality

Code that changes together should live together.

Features should remain cohesive and self-contained whenever practical.

Developers should be able to understand and modify a feature without navigating unrelated parts of the repository.

---

## Predictability

Repository structure should be easy to understand.

Developers should be able to predict where code belongs before searching for it.

Organisation, naming and behaviour should minimise surprises.

---

## Explicitness

Software should clearly communicate its intent.

Data flow, dependencies and behaviour should be visible.

Avoid hidden state, implicit behaviour and unnecessary magic.

---

## Consistency

The repository should feel as though it was written by one developer.

When multiple valid solutions exist, prefer the one already established.

Consistency is usually more valuable than local optimisation.

---

## Maintainability

Every change should improve the long-term quality of the repository.

Optimise for future maintenance rather than immediate convenience.

Software is maintained far longer than it is written.

---

## Performance

Performance matters.

Correctness matters more.

Measure before optimising.

Avoid introducing complexity without evidence that it provides meaningful value.

---

# Decision Hierarchy

When engineering trade-offs are required, prefer solutions that preserve the following order of priority:

1. Correctness
2. Simplicity
3. Locality
4. Predictability
5. Explicitness
6. Consistency
7. Maintainability
8. Performance

A lower principle should not significantly compromise a higher one without clear justification.

---

# Design Philosophy

Reborn favours software that evolves through small, understandable improvements.

Prefer extending existing designs over replacing them.

Prefer evolution over reinvention.

Prefer composition over unnecessary abstraction.

Prefer readability over cleverness.

Prefer clarity over brevity.

Every abstraction should reduce complexity rather than introduce it.

Every dependency should justify its long-term maintenance cost.

Every architectural decision should make the repository easier to understand.

---

# Non-Goals

Reborn does not pursue complexity for its own sake.

It does not attempt to implement every architectural pattern.

It does not optimise for theoretical purity.

It does not follow technology trends without practical benefit.

It values engineering judgement over fashion.

---

# Long-Term Thinking

Software should be designed with future maintenance in mind.

Before introducing a new idea, abstraction or dependency, consider whether it will still be the preferred solution one year from now.

If the answer is uncertain, the simpler solution is usually the better one.

---

# Final Principle

The repository is the primary source of truth.

Every contribution should feel like a natural continuation of the existing codebase.

The best implementation is the one that becomes indistinguishable from the rest of the repository.