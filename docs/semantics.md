# Semantics

This document describes the dynamic semantics of My Language.

## Evaluation

Programs are evaluated according to the following rules.

### Integer Evaluation

```text
n ⇓ n
```

### Addition

```text
e1 ⇓ n1
e2 ⇓ n2
──────────────────
e1 + e2 ⇓ n1 + n2
```

### Variable Lookup

```text
σ(x) = v
────────────
x ⇓ v
```

where σ is the environment.

## Operational Semantics

A program executes by repeatedly applying transition rules.

### Assignment

```text
⟨x = e, σ⟩ → ⟨skip, σ[x ↦ v]⟩
```

where:

```text
e ⇓ v
```

### Conditional

```text
e ⇓ true
────────────────
if e then P else Q → P
```

```text
e ⇓ false
────────────────
if e then P else Q → Q
```

## Errors

The following situations produce runtime errors:

* Division by zero
* Undefined variable access
* Invalid function calls

## Determinism

Evaluation is deterministic:

```text
If e ⇓ v1 and e ⇓ v2,
then v1 = v2.
```

## Future Work

Potential extensions:

* Concurrency
* Modules
* Effect system
* Type inference
