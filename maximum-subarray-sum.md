+++
title = "Maximum subarray sum"
author = ["Suraj Yadav"]
date = 2022-05-31
tags = ["solution"]
draft = true
+++

## Maximum Subarray Sum {#maximum-subarray-sum}

-   What is maximum subarray sum of `{}`?
    -   0

-   What is maximum subarray sum of `{1}`?
    -   1

-   What is maximum subarray sum of `{1, -2}`?
    -   1, because including -2 will make the sum negative

-   What is the subarray sum of `{1}` in the considered array `{1, ...}`?
    -   The sum of subarray `{1}` is 1

-   Assuming there is potential positive sum subarray head, should we include the subarray `{1}` in the array `{1, ...}`?
    -   if we include `{1}`, it will bring the subarray sum up by `1`
    -   So yes

-   Should we include the first two elements `{1, -2}` for subarray sum in the array `{1, -2, ...}`?
    -   The sum of the two elements is `-1`
    -   Assuming there is a potential positive sum subarray ahead, including the elements will bring down the sum by `1`

-   What about `{4, -3}` in the array `{4, -3, ...}`?
    -   The sum of `{4, -3}` is `1`, so yes