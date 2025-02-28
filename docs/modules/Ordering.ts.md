---
title: Ordering.ts
nav_order: 27
parent: Modules
---

## Ordering overview

Added in v1.0.0

---

<h2 class="text-delta">Table of contents</h2>

- [instances](#instances)
  - [Monoid](#monoid)
  - [Semigroup](#semigroup)
- [model](#model)
  - [Ordering (type alias)](#ordering-type-alias)
- [pattern matching](#pattern-matching)
  - [match](#match)
- [utils](#utils)
  - [reverse](#reverse)

---

# instances

## Monoid

**Signature**

```ts
export declare const Monoid: monoid.Monoid<Ordering>
```

Added in v1.0.0

## Semigroup

**Signature**

```ts
export declare const Semigroup: semigroup.Semigroup<Ordering>
```

Added in v1.0.0

# model

## Ordering (type alias)

**Signature**

```ts
export type Ordering = -1 | 0 | 1
```

Added in v1.0.0

# pattern matching

## match

**Signature**

```ts
export declare const match: <A, B, C = B>(
  onLessThan: LazyArg<A>,
  onEqual: LazyArg<B>,
  onGreaterThan: LazyArg<C>
) => (o: Ordering) => A | B | C
```

Added in v1.0.0

# utils

## reverse

**Signature**

```ts
export declare const reverse: (o: Ordering) => Ordering
```

Added in v1.0.0
