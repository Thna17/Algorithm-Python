
# 5. Binary Search: [2] Performance Analysis of Binary Search

## Learning Objective

When applying the binary search strategy, we will solve the problem of counting the number of comparison operations, thereby understanding that the time complexity of binary search is O(log n).

## Problem Statement

Given `N` positive integers in a sorted list `S` and `M` positive integers in list `X`, the task is to output the total number of unit operations when performing binary search for all elements in `X`.

### Input

1. The first line of input contains two positive integers, `N` and `M`.
2. The second line contains the `N`-element integer list `S`.
3. The third line contains the `M`-element integer list `X`.

### Output

The first line of output shows the total number of unit operations executed when performing binary search for all elements in `X`.


## Step 1: Check Background Knowledge

### Performance of Binary Search

- **Input size**: Size of the list `S` to be searched, `N`.
- **Basic Operation**: Comparison operation between the element `x` to be found and the middle value `S[mid]` of `S`.

#### Best Case Scenario

When the element `x` is located at `S[mid]`: T(N) = 1

#### Worst Case Scenario

When the element `x` is greater than the maximum value in `S`: T(N) = 1 + T(N ÷ 2)

In this case, we need to continue searching until we discover that `x` does not exist in `S`.

In other words, during recursive calls, we perform the comparison operation between `x` and the mid-value of `S`.

At this point, we perform a recursive call that reduces the search range to `n/2`.

## Step 2: Create Solution

### Solution 1: Iteration

#### Flowchart

**Binsearch Function Flowchart**

```
[Start]
   |
[Initialize low = 0, high = n - 1, cnt = 0]
   |
+-------------------------------------+
|         While low <= high           |
|                  |                  |
|      [Calculate mid = (low + high) // 2]
|                  |                  |
|            [Increment cnt]          |
|                  |                  |
|        x == S[mid]?                 |
|             /  \                    |
|         Yes     No                  |
|        /         \                  |
|   [Return cnt]   x < S[mid]?        |
|                  /  \               |
|              Yes     No             |
|             /         \             |
| [high = mid - 1]   [low = mid + 1]  |
|                  |                  |
+-------------------------------------+
   |
[Return cnt]
```

**Solve Function Flowchart**

```
[Start]
   |
[Input N, M]
   |
[Input S, X]
   |
[Initialize total = 0]
   |
+-------------------------------+
|     Loop through i in 0 to m-1 |
|               |                |
| [Call binsearch(X[i], n, S)]   |
|               |                |
| [Add result to total]          |
+-------------------------------+
   |
[Print total]
   |
[End]
```

### Solution 2: Recursive

#### Flowchart

**Binsearch Function Flowchart**

```
[Start]
   |
[low > high?]
   |       \
  Yes      No
   |         \
[Return 0]    [mid = (low + high) // 2]
              |
       [x == S[mid]?]
              |       \
            Yes       No
              |         \
        [Return 1]      [x < S[mid]?]
                           |       \
                          Yes      No
                           |         \
            [Return 1 + binsearch(low, mid - 1, x, S)]
                           |
            [Return 1 + binsearch(mid + 1, high, x, S)]
```

**Solve Function Flowchart**

```
[Start]
   |
[Input N, M]
   |
[Input S, X]
   |
[Initialize total = 0]
   |
[Loop through i in 0 to m-1]
   |
[Call binsearch(0, n-1, X[i], S)]
   |
[Add result to total]
   |
[Print total]
   |
[End]
```

---