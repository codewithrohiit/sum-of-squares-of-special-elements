# Sum of Squares of Special Elements

## Problem Description

Given an integer array `nums` of size `n`, calculate the sum of squares of all elements whose **1-based indices divide the array size `n` exactly**.

An element `nums[i]` is included in the sum if:

\[
n \bmod (i+1) = 0
\]

Here, `i + 1` represents the 1-based index of the element.

## Algorithm Name

**Linear Traversal with a Divisibility Check**

## Approach

1. Initialize a variable `ans` to `0` to store the sum of squares.
2. Iterate through the array using a loop from index `0` to `n - 1`.
3. Check whether the array size `n` is divisible by the element's 1-based index `i + 1`.
4. If the condition is satisfied, add the square of the current element to `ans`.
5. Return `ans` after processing all elements.

## C Solution

```c
int sumOfSquares(int* nums, int numsSize) {
    int ans = 0;

    for (int i = 0; i < numsSize; i++) {
        if (numsSize % (i + 1) == 0) {
            ans += nums[i] * nums[i];
        }
    }

    return ans;
}
```

## Example

**Input:**

```text
nums = [1, 2, 3, 4]
```

**Explanation:**

The array size is `4`.

| 1-Based Index | Element | Divides 4? | Contribution |
|---:|---:|:---:|---:|
| 1 | 1 | Yes | 1² = 1 |
| 2 | 2 | Yes | 2² = 4 |
| 3 | 3 | No | 0 |
| 4 | 4 | Yes | 4² = 16 |

**Output:**

```text
21
```

**Calculation:**

`1² + 2² + 4² = 1 + 4 + 16 = 21`

## Complexity Analysis

- **Time Complexity:** `O(n)` — The algorithm traverses the array once.
- **Space Complexity:** `O(1)` — Only a constant amount of extra space is used.

## Key Concepts

- Arrays
- Loops and conditional statements
- Modulo operator (`%`)
- Basic mathematical operations

## Language

**C**

## Conclusion

This solution efficiently finds the sum of squares of elements at positions that are divisors of the array size. A single traversal makes the implementation simple and efficient.
