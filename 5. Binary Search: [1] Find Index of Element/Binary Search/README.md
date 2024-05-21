**Learning objective**

💡 Learn how to find the position of a specific element in a sorted list.



Addition, sequential search is used in unsorted lists, binary search strategy can be used more efficiently to locate the index of an element in a sorted list.


**Step 1: Check background knowledge**

 **Sequential Search**

- Finding a specific element in an unsorted linear data.
- Algorithm with a worst-case time complexity of O(N).


**Binary Search**

- Finding a specific element in an sorted linear data.
- Algorithm with a worst-case time complexity of O(log2N).
</aside>

 **Binary search strategy**
For a sorted list S, Calculate the first position(low), last position(high), and middle position(mid)

- **if the first position is greater than the last position:** Return -1 since x does not exist in the list S, and terminate the search.
- **If x is at the middle position:** x has been found, se return the corresponding position and terminate the search.
- **If x is smaller than the value at the middle position:** x must be in left part of S, so perform a binary search on the left part.
- **If x is larger than the value at the middle position:** x must be in the right part of S, so perform a binary search on the right part.

Imagine you have a sorted list of numbers from 1 to 100 and you're looking for the number 75.

1. First, you would look at the middle number of the list. In this case, that would be 50 (halfway between 1 and 100).
2. Since 75 is greater than 50, you now know that 75, if it exists in the list, must be in the second half of the list (between 51 and 100).
3. Now, you only need to consider numbers from 51 to 100. Find the middle of this subset, which is 75 (halfway between 51 and 100).
4. You have found the number 75. If 75 was not the middle number, you would repeat the process, always choosing the lower half of the current section if 75 is less than the middle number, or the upper half if it is greater.

This is the process of binary search, continuously narrowing down the section of the list where the number could be until you've found it or exhausted all possibilities.

# Binary Search and Solve Functions Flowchart (Recursive)

## 1. Start
1. Read inputs:
    - `N` (size of array `S`)
    - `M` (size of array `X`)
    - Array `S` (sorted array of integers)
    - Array `X` (array of integers to search in `S`)

## 2. Function `solve(n, m, S, X)`
- **Input:** `n` (size of `S`), `m` (size of `X`), `S` (array), `X` (array)
- **Process:**
    - For `i = 0 to m-1`:
        - Call `binsearch(0, n-1, X[i], S)`
        - Print result with a space
    - Print newline

## 3. Function `binsearch(low, high, x, S)`
- **Input:** `low`, `high`, `x` (target), `S` (array)
- **Process:**
    - If `low > high`:
        - Return `-1`
    - Else:
        - Calculate `mid = (low + high) // 2`
        - If `x == S[mid]`:
            - Return `mid`
        - Elif `x < S[mid]`:
            - Call `binsearch(low, mid-1, x, S)`
        - Else:
            - Call `binsearch(mid+1, high, x, S)`

## Flowchart Representation

# Binary Search and Solve Functions Flowchart (Iterable)

## 1. Start
1. Read inputs:
    - `N` (size of array `S`)
    - `M` (size of array `X`)
    - Array `S` (sorted array of integers)
    - Array `X` (array of integers to search in `S`)

## 2. Function `solve(n, m, S, X)`
- **Input:** `n` (size of `S`), `m` (size of `X`), `S` (array), `X` (array)
- **Process:**
    - For `i = 0 to m-1`:
        - Call `binsearch(0, n-1, X[i], S)`
        - Print result with a space
    - Print newline

## 3. Function `binsearch(low, high, x, S)`
- **Input:** `low`, `high`, `x` (target), `S` (array)
- **Process:**
    - If `low > high`:
        - Return `-1`
    - Else:
        - Calculate `mid = (low + high) // 2`
        - If `x == S[mid]`:
            - Return `mid`
        - Elif `x < S[mid]`:
            - Call `binsearch(low, mid-1, x, S)`
        - Else:
            - Call `binsearch(mid+1, high, x, S)`

## Flowchart Representation

