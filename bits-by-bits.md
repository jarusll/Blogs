---
title: Bits by Bits
date: 2024-06-09
layout: ../../layouts/RequestResponse.astro
---

# Bits by Bits

**What is a bit?**

A bit can be `1` or `0`

**What are bits?**

A sequence of bits. `10110100`

**Can we only have 8 bits at a time?**

No, we can have infinite length of bits

**What is bit size of  `10110100`?**

8, since it has 8 bits

**What do bits represent?**

Bits can be `set` ie `1` or `unset` ie `0`

# OPERATIONS

**Can we toggle bits from set to unset and vice versa?**

Yes we can. Thanks `NOT` operation

**What is NOT of `10110100`?**

`01001011`

**Is there a shorthand for `NOT OPERATION`?**

Yes, there is. `~`. `~10110100` = `01001011`

**What are other ways we can combine 2 bits?**

We can set the result bit if and only if both the bits are set. Thanks `AND` Operation.

 |        |   |       |   |       |   |   |       |   |
 |--------|---|-------|---|-------|---|---|-------|---|
 | Bits A | 1 | **1** | 0 | **1** | 0 | 1 | **1** | 1 |
 | Bits B | 0 | **1** | 0 | **1** | 1 | 0 | **1** | 0 |
 | Result | 0 | **1** | 0 | **1** | 0 | 0 | **1** | 0 |

**Is there a shorthand for `AND OPERATION`?**

Yes, there is. `&`. `11010111 & 01011010` = `01010010`

**Can we set a bit if either of the bits are set?**

Yes, thanks `OR` Operation

 |        |       |       |   |       |       |       |       |   |
 |--------|-------|-------|---|-------|-------|-------|-------|---|
 | Bits A | **1** | **1** | 0 | **1** | 0     | **1** | **1** | 0 |
 | Bits B | 0     | **1** | 0 | **1** | **1** | 0     | **1** | 0 |
 | Result | **1** | **1** | 0 | **1** | **1** | **1** | **1** | 0 |

**Is there a shorthand for `OR OPERATION`?**

Yes, there is. `|`. `11010110 | 01011010` = `11011110`

**Can we set a bit if and only if both the bits are different?**

Yes, thanks `Exclusive Or`(`XOR`) Operation

 |        |       |   |   |   |       |       |   |   |
 |--------|-------|---|---|---|-------|-------|---|---|
 | Bits B | **0** | 1 | 0 | 1 | **1** | **0** | 1 | 0 |
 | Result | **1** | 0 | 0 | 0 | **1** | **1** | 0 | 0 |
 | Bits A | **1** | 1 | 0 | 1 | **0** | **1** | 1 | 0 |

**How about shifting bits left or right?**


Yes, thanks to `LEFT SHIFT` and `RIGHT SHIFT` Operations

Shifting `11010110` left by 1 = `10101100`

Shifting `11010110` right by 1 = `01101011`

**How can we shift 2 bits to left for `11010110`?**

We can drop left 2 bits and pad right 2 bits by `0`

**How about shifting right 2 bits?**

We can drop right 2 bits and pad left 2 bits by `0`

**Are there shorthands for `LEFT SHIFT` and `RIGHT SHIFT`?**

Yes, `LEFT SHIFT` is `<<` and `RIGHT SHIFT` is `>>`

Shifting `11010110` left by 1 = `11010110 << 1` = `10101100`

Shifting `11010110` right by 1 = `11010110 >> 1` = `01101011`

# BIT MASKS

**What is a bit mask?**

A bit mask is a bit pattern. `1`s in the mask defines the bits we want to keep and `0`s we want to discard

**What does this bit mask represent `00010000`?**

It preserves the 5th bit from right and discards the rest

**How can we get the 5th bit of a bit pattern?**

By using a bit mask which preserves the 5th bit

**How do we use this bit mask on a bit pattern?**

Lets solve this issue for a simple case for the bit pattern `1`

**How can I check if the bit is set or unset?**

By using the bit mask `1`

**How do I use the bit mask `1` on bit pattern `1` to get the first bit?**

By using [`AND`](#what-are-other-ways-we-can-combine-2-bits) operation

**So, how would we get the 5th bit of a bit pattern?**

By `BIT_PATTERN & 00010000`

**How would we know if the 5th bit is set using the above operation?**

If any of the bit is set, it means the 5th bit is set

**Is there any other way to achieve the same result?**

We could use bit shifts

**And how would we do that?**

- By [shifting](#how-about-shifting-bits-left-or-right) 5th bit to the 1st position and apply `AND` with `1`

`(BIT_PATTERN >> 4) & 1`

**Can we generalize it?**

`NTH_BIT = (BIT_PATTERN >> (n - 1)) & 1`

**How can we set the 5th bit?**

**How can we toggle the 5th bit?**

**How can we compose bit masks?**

By using [OR](#can-we-set-a-bit-if-either-of-the-bits-are-set)

**How can we subtract bit masks?**
