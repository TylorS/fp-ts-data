---
title: NonEmpty.ts
nav_order: 24
parent: Modules
---

## NonEmpty overview

Added in v1.0.0

---

<h2 class="text-delta">Table of contents</h2>

- [getters](#getters)
  - [unprepend](#unprepend)
- [model](#model)
  - [NonEmptyIterable (interface)](#nonemptyiterable-interface)

---

# getters

## unprepend

**Signature**

```ts
export declare const unprepend: <A>(self: NonEmptyIterable<A>) => readonly [A, Iterator<A, any, undefined>]
```

Added in v1.0.0

# model

## NonEmptyIterable (interface)

**Signature**

```ts
export interface NonEmptyIterable<A> extends Iterable<A> {
  readonly [nonEmpty]: A
}
```

Added in v1.0.0
