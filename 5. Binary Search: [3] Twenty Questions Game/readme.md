
# Twenty Questions Game Solver

## Learning Objective

![Learning Objective](/icons/book-closed_lightgray.svg) We will solve the Twenty Questions game problem using binary search.

## Problem

![Problem](/icons/book-closed_lightgray.svg) The Twenty questions game is a game where we try to guess a random integer X that the other person is thinking of by asking yes/no questions.

- If the range of X is greater than or equal to S and less than or equal to T, then we can ask the question, “Is X greater than the midpoint M of S and T?”
  - If the answer is yes ⇒ then set S to M+1 and continue the game.
  - If the answer is No ⇒ then set T to M and continue the game.
  - If S and T become the same value, we can determine that X is equal to that value.

## Step 1: Check background knowledge for problem solving

![Step 1](/icons/book-closed_lightgray.svg) Check background knowledge for problem-solving:

![How to play Twenty question game](/icons/book-closed_lightgray.svg) How to play Twenty questions game:

- X = 69
- Value between 1 and 100
  - 1 is low
  - 50 is mid
  - 100 is high
    - Q. Is X bigger than 50?
      - A. Yes
    - 51 is low
    - 75 is mid
    - 100 is high
      - Q. Is X bigger than 75?
        - A. No
      - 75 is high
      - 63 is mid
      - 51 is low
        - Q. Is X bigger than 63?
          - A. Yes
        - 64 is low
        - 69 is mid
        - 75 is high
          - Q. Is X bigger than 69?
            - A. No
          - 69 is high
          - 68 is mid
          - 64 is low
            - Q. Is X bigger than 68?
              - A. Yes
            - 69 is low
            - 69 is high

## Step 2: Create Solution

![Step 2](/icons/book-closed_lightgray.svg) Create Solution:

### Solution 1: Iteration

![Solution 1](/icons/star_lightgray.svg) **Iteration:**

#### Flowchart

```plaintext
[Start]
   |
[Input S, T]
   |
[Input SEED]
   |
[Generate X using SEED]
   |
[Call solve(X, S, T)]
   |
[Initialize low = S, high = T]
   |
+--------------------------------+
|    While low < high            |
|           |                    |
|  [Calculate mid = (low + high) // 2]
|           |                    |
| [Print "Bigger than mid?" with end=" "]
|           |                    |
|     [x > mid?]                 |
|           |         /---------Yes
|        Yes  <--------           |
|           |         \---------No
|           |                    |
|     [Print "Yes" or "No"]      |
|           |                    |
|     [low = mid + 1]             |
|     [Print "Your X is low"]     |
|           |                    |
|           |                    |
|           |                    |
+--------------------------------+
   |
[Return low]
   |
[End]
```

### Solution 2: Recursive

![Solution 2](/icons/star_lightgray.svg) **Recursive:**

#### Flowchart

```plaintext
[Start]
   |
[Input S, T]
   |
[Input SEED]
   |
[Generate X using SEED]
   |
[Call solve(X, S, T)]
   |
+-------------------------------------+
|  If low >= high                     |
|         |                           |
|  [Print "Your X is low"]            |
|         |                           |
|  [Return low]                       |
|         |                           |
+---------|---------------------------+
           |
+----------|---------------------------+
| Else                                  |
|         |                           |
|  [Calculate mid = (low + high) // 2]|
|         |                           |
|  [Print "Bigger than mid?" with end=" "]
|         |                           |
|  [Check x > mid]                    |
|  Yes  <-----------------------------|
|  No       ----------------->        |
|         |                           |
|  [Print "Yes" or "No"]              |
|         |                           |
|  [Return solve(x, mid + 1, high)]   |
|  OR       ----------------->        |
|  [Return solve(x, low, mid)]        |
+-------------------------------------+
```


