---
title: 1D Peak finding
date: 2022-06-10 
---

# Run this notebook
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jarusll/notebooks.git/master?labpath=peek-finding-1-d.ipynb)

# 1D Peak finding

- What is a 1D peak?
  - An element in a 1D array which is greater than its neighbour

- Which element has the least number of neighbours?
  - A one without any, Singleton

- Is `7` a peak in `[7]`? -- `Base case 1`
  - Yes, an uncontested victory.

- Whats the peak in `[7, 8]`? -- `Base case 2`
  - `8`, max(array) if array has only 2 elements

- What the next element which has the least number of neighbours?
  - Edges, since they have only 1 neighbour

- Is `7` a peak in `[7, 3, ...]`? -- `Base case left edge`
  - Yes, since `7 > 3`

- Is `7` a peak in `[..., 3, 7]`? -- `Base case right edge`
  - Yes

- Is `7` a peak in `[..., 3, 7, 4, ...]`? -- `Base case mid`
  - Yes, `7 > 3` and `7 > 4`

- Whats the peak in `[1, 2, 3, 4, 5]`, a strictly increasing array?
  - 5

- Whats the peak in `[5, 4, 3, 2, 1]`, a strictly decreasing array?
  - 5

- Whats the peak in `[5, 5, 5, 5, 5]`, a strictly leveled array?
  - 5

- Is `7` a peak in `[..., 3, 7, 9, ...]`?
  - No, since `9 > 7`

- Where should we look for a peak next?
  - `[9, ...]`, since it has atleast 1 peak

	- Reason, for the array `[9, x, ...]`
		- Considering `x is less than 9`, in this case `9` is a peak
		- Considering `x is equal to 9`, in this case `9` is a peak
		- Considering `x is greater than 9`, then the slice `[x, ...]` contains the peak element -- `Case right`

- Whats the peak in `[]`? -- `Base Case 0`
  - None

- How about finding all the peaks?
  - Can be done using the same code and complete search

```
peak([...])
	[] => None -- Base case 0
	[x] => x -- Base case 1
	[a, b, ...] and a >= b => a -- Base case start 
	[..., y, z] and y <= z => z -- Base case end
	[..., k, l, m, ...] and k <= l and l >= m => l -- Base case mid
	[..., k, l, m, ...] and k >= l => peak([..., k]) -- case left
	[..., k, l, m, ...] and l <= m => peak([m, ...]) -- case right
```
