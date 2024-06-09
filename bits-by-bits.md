---
title: Bits by Bits
date: 2024-06-09
layout: ../../layouts/RequestResponse.astro
---

## What is a bit?
- A bit can be `1` or `0`

## What are bits?
- A sequence of bits. `10110100`

## Can we only have 8 bits at a time?
- No, we can have infinite length of bits

## What is bit size of  `10110100`?
- 8, since it has 8 bits

## What do bits represent?
- Bits can be `set` ie `1` or `unset` ie `0`

## Can we toggle bits from set to unset and vice versa?
- Yes we can. Thanks `NOT` operation

## What is NOT of `10110100`?
- `01001011`

## Is there a shorthand for `NOT OPERATION`?
- Yes, there is. `~`. `~10110100` = `01001011`

## What are other ways we can combine 2 bits?
- We can set the result bit if and only if both the bits are set. Thanks `AND` Operation.

 |        |   |       |   |       |   |   |       |   |
 |--------|---|-------|---|-------|---|---|-------|---|
 | Bits A | 1 | **1** | 0 | **1** | 0 | 1 | **1** | 1 |
 | Bits B | 0 | **1** | 0 | **1** | 1 | 0 | **1** | 0 |
 | Result | 0 | **1** | 0 | **1** | 0 | 0 | **1** | 0 |

## Is there a shorthand for `AND OPERATION`?
- Yes, there is. `&`. `11010111` & `01011010` = `01010010`

## Can we set a bit if either of the bits are set?
- Yes, thanks `OR` Operation

 |        |       |       |   |       |       |       |       |   |
 |--------|-------|-------|---|-------|-------|-------|-------|---|
 | Bits A | **1** | **1** | 0 | **1** | 0     | **1** | **1** | 0 |
 | Bits B | 0     | **1** | 0 | **1** | **1** | 0     | **1** | 0 |
 | Result | **1** | **1** | 0 | **1** | **1** | **1** | **1** | 0 |

## Is there a shorthand for `AND OPERATION`?
- Yes, there is. `|`. `11010110` | `01011010` = `11011110`

## Can we set a bit if and only if both the bits are different?
- Yes, thanks `Exclusive Or`(`XOR`) Operation

 |        |       |   |   |   |       |       |   |   |
 |--------|-------|---|---|---|-------|-------|---|---|
 | Bits B | **0** | 1 | 0 | 1 | **1** | **0** | 1 | 0 |
 | Result | **1** | 0 | 0 | 0 | **1** | **1** | 0 | 0 |
 | Bits A | **1** | 1 | 0 | 1 | **0** | **1** | 1 | 0 |

## How about shifting bits left or right?
- Yes, thanks to `LEFT SHIFT` and `RIGHT SHIFT` Operations
- Shifting `11010110` left by 1 = `10101100`
- Shifting `11010110` right by 1 = `01101011`

## How can we shift 2 bits to left for `11010110`?
- We can drop left 2 bits and pad right 2 bits by `0`

## How about shifting right 2 bits?
- We can drop right 2 bits and pad left 2 bits by `0`

## Are there shorthands for `LEFT SHIFT` and `RIGHT SHIFT`?
- Yes, `LEFT SHIFT` is `<<` and `RIGHT SHIFT` is `>>`
