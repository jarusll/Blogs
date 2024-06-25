---
title: "Generate Permutations"
author: ["Suraj Yadav"]
date: 2022-05-28
tags: ["solution"]
draft: false
layout: ../../layouts/RequestResponse.astro
---

## What is permutation? {#what-is-permutation}

**What is permutation of `{ }`?**

`{ }`

**What is permutation of `{1}`?**

`{1}`

**What is permutation of `{1, 2}`?**

- `{1, 2}`
- `{2, 1}`

**What is permutation of `{1, 2, 3}`?**

-   `{1, 2, 3}`
-   `{1, 3, 2}`
-   `{2, 1, 3}`
-   `{2, 3, 1}`
-   `{3, 1, 2}`
-   `{3, 2, 1}`

**Which of them start with `1`?**

-   `{1, 2, 3}`
-   `{1, 3, 2}`

**What is the rest of these elements?**

-   `{2, 3}`
-   `{3, 2}`

**Do they resemble something?**

-   No

**What about permutation of `{2, 3}`?**

-   Yes

**What is append x on {y, z}?**

-   {x, y, z}

**What is append x on each {y, z}?**

-   {x, y}
-   {x, z}

**Can we say Permutation of `{1, 2, 3}` = `{append 1 on each permutation of {2, 3}}, {append 2 on each permutation of {1, 3}}, {append 3 on each permutation of {1, 2}}}`?**

-   Thats a mouthful

**What is `{append 1 on each permutation of {2, 3}}`?**

-   `{append 1 on each permutation of {2, 3}}`
-   `{append 1 on each {{2, 3}, {3, 2}} }`
-   `{{1, 2, 3}, {1, 3, 2}}`

**What about `{append 2 on each permutation of {1, 3}}, {append 3 on each permutation of {1, 2}}`?**

-   `{{2, 1, 3}, {2, 3, 1}, {3, 1, 2}, {3, 2, 1}}`

**What do we get when we club them all?**

-   `{{1, 2, 3}, {1, 3, 2}, {2, 1, 3}, {2, 3, 1}, {3, 1, 2}, {3, 2, 1}}`
-   ie `permutation of {1, 2, 3}`

**Do you know what permutation is now?**

-   Yes

**Did you have fun?**

-   Go have some cookies
