---
title: "Middle of Linked List"
author: ["Suraj Yadav"]
date: 2022-05-29
tags: ["solution"]
draft: false
layout: ../../layouts/RequestResponse.astro
---

## Middle of Linked list

**In the list `1->2->3->4->5`, `S` and `F` point to 1. What are `S` and `F` when `S` moves by 1 element and `F` moves by 2 elements?**

-   `S` is slow pointer and `F` is fast pointer

**Will `S` travel half the distance of `F` at any given point?**

-   Yes, since `F` is twice as fast as `S`

**Will `S` be at middle of list when `F` is at the end?**

-   Yes

**Do we have our base case and reduction case?**

-   Yes we do
