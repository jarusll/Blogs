+++
title = "Next permutation"
author = ["Suraj Yadav"]
date = 2022-05-30
tags = ["solution"]
draft = false
+++

## Next Permutation {#next-permutation}

-   Do you know what a permutation is?
    -   Yes

-   Can you tell the next lexicographic permutation for `{2, 1, 3}`?
    -   No

-   What is the permutation of `{1, 2, 3}`?
    -   `{1, 2, 3}`
    -   `{1, 3, 2}`
    -   `{2, 1, 3}`
    -   `{2, 3, 1}`
    -   `{3, 1, 2}`
    -   `{3, 2, 1}`

-   What are the bounds of the above permutations?
    -   From `{1, 2, 3}`,strictly increasing to `{3, 2, 1}`,strictly decreasing.

-   Can we say that a strictly decreasing arrangement has run out of its permutation?
    -   Yes

-   What is the direction of making a permutation?
    -   From left to right

-   Whats the direction of backtracking a permutation?
    -   From right to left

-   Whats a strictly decreasing arrangement in `{1, 3, 2}` from end?
    -   `{3, 2}`

-   Whats a strictly decreasing arrangement in `{2, 1, 3}` from end?
    -   `{3}`

| Arrangement | Vacant |
|-------------|--------|
| `{2, 1}`    | `{3}`  |

-   Have we run out of arrangements for `1`?
    -   Yes

-   What should replace `1`?
    -   The next successor in the vacant pool

| Arrangement | Vacant |
|-------------|--------|
| `{2, 3}`    | `{1}`  |

-   What should the next step be?
    -   Appending sorted Vacant to the Arrangement because every new permutation starts sorted

| Arrangement | Vacant |
|-------------|--------|
| `{2, 3, 1}` | `{}`   |

-   Is `{2, 3, 1}` the next permutation after `{2, 1, 3}`?
    -   Yes