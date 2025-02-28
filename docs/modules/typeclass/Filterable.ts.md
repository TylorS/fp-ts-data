---
title: typeclass/Filterable.ts
nav_order: 38
parent: Modules
---

## Filterable overview

`Filterable` represents data structures which can be _partitioned_/_filtered_.

Added in v1.0.0

---

<h2 class="text-delta">Table of contents</h2>

- [models](#models)
  - [Filterable (interface)](#filterable-interface)
- [utils](#utils)
  - [filter](#filter)
  - [filterMapComposition](#filtermapcomposition)
  - [partition](#partition)
  - [partitionMap](#partitionmap)

---

# models

## Filterable (interface)

**Signature**

```ts
export interface Filterable<F extends TypeLambda> extends TypeClass<F> {
  readonly filterMap: <A, B>(f: (a: A) => Option<B>) => <R, O, E>(self: Kind<F, R, O, E, A>) => Kind<F, R, O, E, B>
}
```

Added in v1.0.0

# utils

## filter

**Signature**

```ts
export declare const filter: <F extends TypeLambda>(
  F: Filterable<F>
) => {
  <C extends A, B extends A, A = C>(refinement: (a: A) => a is B): <R, O, E>(
    self: Kind<F, R, O, E, C>
  ) => Kind<F, R, O, E, B>
  <B extends A, A = B>(predicate: (a: A) => boolean): <R, O, E>(self: Kind<F, R, O, E, B>) => Kind<F, R, O, E, B>
}
```

Added in v1.0.0

## filterMapComposition

Returns a default `filterMap` composition.

**Signature**

```ts
export declare const filterMapComposition: <F extends TypeLambda, G extends TypeLambda>(
  F: Covariant<F>,
  G: Filterable<G>
) => <A, B>(
  f: (a: A) => Option<B>
) => <FR, FO, FE, GR, GO, GE>(
  self: Kind<F, FR, FO, FE, Kind<G, GR, GO, GE, A>>
) => Kind<F, FR, FO, FE, Kind<G, GR, GO, GE, B>>
```

Added in v1.0.0

## partition

**Signature**

```ts
export declare const partition: <F extends TypeLambda>(
  F: Filterable<F>
) => {
  <C extends A, B extends A, A = C>(refinement: (a: A) => a is B): <R, O, E>(
    self: Kind<F, R, O, E, C>
  ) => readonly [Kind<F, R, O, E, C>, Kind<F, R, O, E, B>]
  <B extends A, A = B>(predicate: (a: A) => boolean): <R, O, E>(
    self: Kind<F, R, O, E, B>
  ) => readonly [Kind<F, R, O, E, B>, Kind<F, R, O, E, B>]
}
```

Added in v1.0.0

## partitionMap

**Signature**

```ts
export declare const partitionMap: <F extends TypeLambda>(
  F: Filterable<F>
) => <A, B, C>(
  f: (a: A) => Either<B, C>
) => <R, O, E>(self: Kind<F, R, O, E, A>) => readonly [Kind<F, R, O, E, B>, Kind<F, R, O, E, C>]
```

Added in v1.0.0
