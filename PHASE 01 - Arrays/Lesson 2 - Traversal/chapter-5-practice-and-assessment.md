# Chapter 5 — Guided Examples, Practice and Assessment

> **Lesson 2 › Chapter 5 of 5**

---

## 📍 Progress

```
Lesson 2 — Traversal
│
├── ✅ Chapter 1 — Understanding Traversal
├── ✅ Chapter 2 — Types and Mental Model
├── ✅ Chapter 3 — JavaScript and Dry Run
├── ✅ Chapter 4 — Mistakes and Recognition
└── 🔵 Chapter 5 — Practice and Assessment    ← You are here
      │
      ├── Section A — Guided Examples (5 problems, fully solved)
      ├── Section B — Practice Problems (10 problems, solve yourself)
      ├── Section C — Lesson Quiz
      └── Section D — Revision Notes
```

---

## Before Every Problem

Run this checklist **before writing code**:

```
Step 1: Read the problem carefully.
Step 2: Ask "Do I need to visit every element?"
Step 3: If YES → Pattern = Traversal
Step 4: Ask "What information do I need to remember?"
Step 5: Write the algorithm in plain English.
Step 6: Write the code.
Step 7: Dry-run it manually.
Step 8: Analyse time and space complexity.
```

---

---

# Section A — Guided Examples

> These 5 examples are fully solved. Read each one carefully.  
> **Each example adds exactly one new idea** — don't rush.

---

## Example 1 — Print Every Element

### Problem

```
Input:  [10, 20, 30, 40]
Output: 10
        20
        30
        40
```

### Pattern Recognition

| Question | Answer |
|---|---|
| Do I need every element? | ✅ Yes |
| Process one element at a time? | ✅ Yes |
| Pattern? | ✅ Traversal |

### Mental Model

```
Visit → Print → Move → Repeat

No counting. No comparing. No remembering. Just visit and print.
```

### Algorithm (Plain English)

```
1. Start at the first element.
2. Print it.
3. Move to the next.
4. Repeat until the array ends.
```

### Code

```js
const arr = [10, 20, 30, 40];

for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
}
```

### Line-by-Line Explanation

| Line | Explanation |
|---|---|
| `const arr = [...]` | Input array stored in memory |
| `let i = 0` | Start at index 0 (first element) |
| `i < arr.length` | Continue while index is valid |
| `i++` | Move to the next index after each visit |
| `console.log(arr[i])` | Print the value at the current index |

### Dry Run

| Iteration | `i` | `arr[i]` | Action |
|---|---|---|---|
| 1 | 0 | 10 | print 10 |
| 2 | 1 | 20 | print 20 |
| 3 | 2 | 30 | print 30 |
| 4 | 3 | 40 | print 40 |
| Stop | 4 | — | `4 < 4` ❌ |

### Complexity

| | |
|---|---|
| Time | O(n) — every element visited once |
| Space | O(1) — no extra data structures |

### Why This Matters

Later you will replace `console.log(arr[i])` with:
`count++`, `sum += arr[i]`, `if (arr[i] > max)`, etc.

The **traversal loop itself stays the same**. Only the action inside changes.

---

## Example 2 — Print Every Element in Reverse

### Problem

```
Input:  [10, 20, 30, 40]
Output: 40
        30
        20
        10
```

### What Changes from Example 1?

Only the **direction**. Same pattern, opposite path.

### Algorithm (Plain English)

```
1. Go to the last element.
2. Print it.
3. Move one position left.
4. Repeat until the first element is printed.
```

### Code

```js
const arr = [10, 20, 30, 40];

for (let i = arr.length - 1; i >= 0; i--) {
    console.log(arr[i]);
}
```

### Loop Explained

| Part | Value (arr.length=4) | Meaning |
|---|---|---|
| `i = arr.length - 1` | `i = 3` | Start at last valid index |
| `i >= 0` | stop at -1 | Index 0 is still valid — visit it |
| `i--` | 3→2→1→0 | Move leftward |

### Dry Run

| Iteration | `i` | `arr[i]` | Action |
|---|---|---|---|
| 1 | 3 | 40 | print 40 |
| 2 | 2 | 30 | print 30 |
| 3 | 1 | 20 | print 20 |
| 4 | 0 | 10 | print 10 |
| Stop | -1 | — | `-1 >= 0` ❌ |

### Comparison: Example 1 vs Example 2

| | Left → Right | Right → Left |
|---|---|---|
| Start | `i = 0` | `i = arr.length - 1` |
| Stop when | `i < arr.length` is false | `i >= 0` is false |
| Move | `i++` | `i--` |

### Important Interview Note

> **Printing in reverse ≠ Reversing the array.**
>
> Printing in reverse outputs `40, 30, 20, 10` — but the original array remains `[10, 20, 30, 40]`.  
> Reversing the array changes the array itself to `[40, 30, 20, 10]`.  
> That is a different problem, solved later using **Two Pointers**.

### Complexity

| | |
|---|---|
| Time | O(n) |
| Space | O(1) |

---

## Example 3 — Count Elements

### Problem

```
Input:  [10, 20, 30, 40]
Output: 4
```

### New Idea: State Variable

To count, you need to **remember** something across iterations — a **counter**.

```
State variable: let count = 0;
```

### Algorithm (Plain English)

```
1. Start count at 0.
2. Visit each element.
3. Increase count by 1.
4. After visiting all elements, return count.
```

### Code

```js
const arr = [10, 20, 30, 40];
let count = 0;

for (let i = 0; i < arr.length; i++) {
    count++;
}

console.log(count); // 4
```

### Dry Run

| Iteration | `i` | `arr[i]` | `count` before | `count` after |
|---|---|---|---|---|
| — | — | — | 0 | — |
| 1 | 0 | 10 | 0 | 1 |
| 2 | 1 | 20 | 1 | 2 |
| 3 | 2 | 30 | 2 | 3 |
| 4 | 3 | 40 | 3 | 4 |

### Wait — Isn't `arr.length` Enough?

For counting *all* elements, yes. Use `arr.length` — it is O(1).

But this example teaches the **counter idea** you will need for:

```
Count EVEN numbers         → count++ only if arr[i] % 2 === 0
Count values above 50      → count++ only if arr[i] > 50
Count negatives            → count++ only if arr[i] < 0
```

In those cases, `arr.length` doesn't help.

### Complexity

| | |
|---|---|
| Time | O(n) |
| Space | O(1) — only one extra variable |

---

## Example 4 — Sum of Elements

### Problem

```
Input:  [10, 20, 30, 40]
Output: 100
```

### New Idea: Running Sum

As you traverse, you keep adding to a **running total**:

```
Start:   sum = 0
After 10: sum = 10
After 20: sum = 30
After 30: sum = 60
After 40: sum = 100
```

Think of `sum` as a piggy bank — every visit, you drop the current element's value in.

### Code

```js
const arr = [10, 20, 30, 40];
let sum = 0;

for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
}

console.log(sum); // 100
```

### Critical Line

```js
sum += arr[i];  // ✅ Adds to the running total
// Equivalent to: sum = sum + arr[i];

// ❌ Wrong:
sum = arr[i];   // Replaces sum each time — loses previous total
```

### Dry Run

| Iteration | `i` | `arr[i]` | `sum` before | `sum` after |
|---|---|---|---|---|
| — | — | — | 0 | — |
| 1 | 0 | 10 | 0 | 10 |
| 2 | 1 | 20 | 10 | 30 |
| 3 | 2 | 30 | 30 | 60 |
| 4 | 3 | 40 | 60 | 100 |

### Comparison: Example 3 vs Example 4

| | Count | Sum |
|---|---|---|
| State variable | `count` | `sum` |
| Initial value | `0` | `0` |
| Update operation | `count++` | `sum += arr[i]` |
| What it tracks | Number of visits | Accumulated value |

The traversal loop did not change. Only the state variable and update operation changed.

### Complexity

| | |
|---|---|
| Time | O(n) |
| Space | O(1) |

---

## Example 5 — Find Maximum Element

### Problem

```
Input:  [12, 5, 18, 9, 25]
Output: 25
```

### New Idea: Comparison + Conditional Update

Instead of always updating the state, you **compare first**, then update only if needed.

```
Start: max = 12  (first element — the only one seen so far)
See 5:  5 > 12? No  → max stays 12
See 18: 18 > 12? Yes → max = 18
See 9:  9 > 18? No  → max stays 18
See 25: 25 > 18? Yes → max = 25

Answer: 25
```

Imagine carrying a **trophy**. Whenever you find someone stronger, you hand them the trophy. At the end, the strongest person holds it.

### Why Not Start With `max = 0`?

```js
// ❌ Wrong initialisation
let max = 0;

// If arr = [-8, -3, -15]:
// -8 > 0? No. -3 > 0? No. -15 > 0? No.
// max remains 0  ← not in the array!
```

The maximum **must be one of the array's elements**. Start with `arr[0]`.

### Code

```js
const arr = [12, 5, 18, 9, 25];
let max = arr[0];  // assume first element is max

for (let i = 1; i < arr.length; i++) {  // start from i=1 (arr[0] already stored)
    if (arr[i] > max) {
        max = arr[i];
    }
}

console.log(max); // 25
```

### Why Start the Loop at `i = 1`?

`arr[0]` is already stored in `max`. Comparing it with itself adds nothing. Starting at `i = 1` is a small optimisation.

### Dry Run

| Iteration | `i` | `arr[i]` | `max` before | Comparison | `max` after |
|---|---|---|---|---|---|
| Init | — | 12 | — | — | 12 |
| 1 | 1 | 5 | 12 | `5 > 12` ❌ | 12 |
| 2 | 2 | 18 | 12 | `18 > 12` ✅ | 18 |
| 3 | 3 | 9 | 18 | `9 > 18` ❌ | 18 |
| 4 | 4 | 25 | 18 | `25 > 18` ✅ | 25 |

### The Progression Across All 5 Examples

| Example | State Variable | Operation |
|---|---|---|
| 1 — Print | none | visit and print |
| 2 — Reverse Print | none | visit and print (direction changes) |
| 3 — Count | `count` | `count++` |
| 4 — Sum | `sum` | `sum += arr[i]` |
| 5 — Maximum | `max` | `if (arr[i] > max) max = arr[i]` |

**The traversal loop never changed. Only what happens inside the loop changed.**

### Complexity

| | |
|---|---|
| Time | O(n) |
| Space | O(1) |

---

---

# Section B — Practice Problems

> **Rule:** Solve each problem independently. Do not jump ahead. Solve Problem 1 first, submit your solution, then move to Problem 2.

### Submission Format

When you submit a solution, include:

```
// Your code here

Pattern:
Time Complexity:
Space Complexity:
```

### Allowed Techniques

| ✅ Allowed | ❌ Not Allowed |
|---|---|
| Traversal | Sliding Window |
| Simple comparison | Prefix Sum |
| Simple counting | Two Pointers |
| Running sum | Binary Search |
| Maximum / Minimum | Hash Maps |
| | Sorting |
| | Kadane's Algorithm |

We are mastering **one pattern at a time**.

---

### Problem 1 — Print Every Element

```
Input:  const arr = [5, 10, 15, 20];
Output: 5
        10
        15
        20

Pattern: Traversal
```

---

### Problem 2 — Print in Reverse

```
Input:  const arr = [5, 10, 15, 20];
Output: 20
        15
        10
        5

Pattern: Traversal (right → left)
```

---

### Problem 3 — Count Even Numbers

```
Input:  const arr = [3, 8, 10, 5, 12, 7];
Output: 3

Pattern: Traversal + Count
Hint:    A number is even if num % 2 === 0
```

---

### Problem 4 — Count Positive Numbers

```
Input:  const arr = [-2, 5, -7, 10, 12];
Output: 3

Pattern: Traversal + Count
```

---

### Problem 5 — Sum of Elements

```
Input:  const arr = [2, 4, 6, 8];
Output: 20

Pattern: Traversal + Running Sum
```

---

### Problem 6 — Find Maximum

```
Input:  const arr = [9, 18, 7, 25, 14];
Output: 25

Pattern: Traversal + Maximum
```

---

### Problem 7 — Find Minimum

```
Input:  const arr = [9, 18, 7, 25, 14];
Output: 7

Pattern: Traversal + Minimum
Hint:    Same idea as find maximum, but flip the comparison
```

---

### Problem 8 — Largest Even Number

```
Input:  const arr = [3, 18, 7, 20, 11];
Output: 20

Pattern: Traversal + Comparison
Hint:    Only consider even elements when updating max
```

---

### Problem 9 — Count Numbers Greater Than 50

```
Input:  const arr = [20, 80, 15, 100, 60];
Output: 3

Pattern: Traversal + Count
```

---

### Problem 10 — Linear Search

```
Input:  const arr = [5, 9, 12, 18, 25];
        target = 18
Output: "Found"   (if target exists in array)
        "Not Found" (if it does not)

Pattern: Traversal + Comparison
Hint:    Stop as soon as you find the target (use return or break)
```

---

### Practice Progress Tracker

```
Lesson 2 — Practice Problems

[ ] Problem 1  — Print Every Element
[ ] Problem 2  — Print in Reverse
[ ] Problem 3  — Count Even Numbers
[ ] Problem 4  — Count Positive Numbers
[ ] Problem 5  — Sum of Elements
[ ] Problem 6  — Find Maximum
[ ] Problem 7  — Find Minimum
[ ] Problem 8  — Largest Even Number
[ ] Problem 9  — Count Numbers > 50
[ ] Problem 10 — Linear Search
```

---

---

# Section C — Lesson Quiz

> **Instructions:** Answer in your own words. No code. This tests understanding, not memorisation.
> 
> **Passing Criteria:** 23–25 → Excellent | 20–22 → Ready for Lesson 3 | 17–19 → Review weak areas | Below 17 → Revisit Lesson 2

---

### Section C1 — Fundamentals

**Q1.** What is traversal?

**Q2.** Why do we need traversal?

**Q3.** Is traversal itself an algorithm or a process? Explain.

**Q4.** What is the difference between `i` and `arr[i]`?

**Q5.** Why do arrays start from index `0` instead of `1`?

---

### Section C2 — JavaScript Traversal

**Q6.** Explain every part of this loop — what does each piece do?

```js
for (let i = 0; i < arr.length; i++)
```

**Q7.** Why do we use `i < arr.length` instead of `i <= arr.length`?

**Q8.** What happens if we remove `i++`?

**Q9.** What happens if we start with `let i = 1`?

**Q10.** What is the purpose of a dry run?

---

### Section C3 — Pattern Recognition

For each problem, write **only the pattern name**:

**Q11.** Find the largest number.

**Q12.** Count even numbers.

**Q13.** Print the array in reverse.

**Q14.** Find the maximum sum of a subarray of size 5.

**Q15.** Find an element in a **sorted** array.

---

### Section C4 — State Variables

Which state variable would you use?

**Q16.** Count odd numbers.

**Q17.** Find total marks.

**Q18.** Find the largest number.

**Q19.** Find the smallest number.

**Q20.** Search for value `50`.

---

### Section C5 — Dry Run

Array: `[8, 3, 15, 6]`

**Q21.** Which element is visited first?

**Q22.** Which element is visited last?

**Q23.** How many iterations occur?

**Q24.** After the second iteration, what is the current index?

**Q25.** If finding the maximum, what is `max` after visiting `8`, then `3`, then `15`?

<details>
<summary>Quiz Answers</summary>

**C1 — Fundamentals**
1. Visiting every element of an array, one at a time, from one end to the other
2. Most array problems require inspecting all elements before producing a correct answer
3. A process — traversal is the "how to move"; the algorithm decides what to do at each element
4. `i` = the current position (index); `arr[i]` = the value stored at that position
5. Arrays use zero-based indexing — the first slot in memory is at offset 0

**C2 — JavaScript**
6. `let i = 0` = start at index 0; `i < arr.length` = continue while index is inside the array; `i++` = advance to the next index after each iteration
7. The last valid index is `arr.length - 1`. At `i = arr.length`, `arr[i]` returns `undefined`
8. Infinite loop — `i` never advances, the loop visits the same element forever
9. The first element (index 0) is skipped and never processed
10. To manually trace the algorithm step by step — verify correctness without executing

**C3 — Pattern Recognition**
11. Traversal
12. Traversal
13. Traversal
14. Sliding Window
15. Binary Search

**C4 — State Variables**
16. `count`
17. `sum`
18. `max`
19. `min`
20. `found` (boolean)

**C5 — Dry Run**
21. `8`
22. `6`
23. 4
24. Index 2 (after processing index 0 and 1, the next is 2)
25. `max = 15`

</details>

---

---

# Section D — Revision Notes

> Use this section for quick review before interviews.

---

## Mind Map

```
Traversal
│
├── Definition
│     └── Visit every required element, one at a time
│
├── Direction
│     ├── Left → Right (default)
│     ├── Right → Left
│     ├── Two Ends  (→ Two Pointers, Module 2)
│     ├── Circular  (→ Advanced)
│     └── Matrix    (→ Module 8)
│
├── Mental Cycle
│     ├── 1. Current Element
│     ├── 2. Observe
│     ├── 3. Process
│     ├── 4. Move Forward
│     └── Repeat
│
├── Foundation for
│     ├── State Pattern      (Lesson 3)
│     ├── Simulation         (Lesson 4)
│     ├── Frequency Counting (Lesson 5)
│     ├── Sliding Window     (Module 3)
│     ├── Prefix Sum         (Module 4)
│     ├── Kadane's Algorithm (Module 5)
│     └── Two Pointers       (Module 2)
│
└── Key Distinction
      ├── i       = index (position)
      └── arr[i]  = value (element)
```

---

## Standard Templates

### Left → Right Traversal

```js
for (let i = 0; i < arr.length; i++) {
    // Current index:  i
    // Current value:  arr[i]
    // Process arr[i] here
}
```

### Right → Left Traversal

```js
for (let i = arr.length - 1; i >= 0; i--) {
    // Process arr[i] here
}
```

---

## Common State Variables

| Problem Type | State Variable | Initial Value | Update Operation |
|---|---|---|---|
| Count | `count` | `0` | `count++` |
| Sum | `sum` | `0` | `sum += arr[i]` |
| Maximum | `max` | `arr[0]` | `if (arr[i] > max) max = arr[i]` |
| Minimum | `min` | `arr[0]` | `if (arr[i] < min) min = arr[i]` |
| Search | `found` | `false` | `if (arr[i] === target) found = true` |

---

## Pattern Recognition Cheat Sheet

```
Problem says:                       Think:
─────────────────────────────────────────────
Find maximum / minimum              Traversal
Count elements matching condition   Traversal
Sum / average of elements           Traversal
Print all elements                  Traversal
Linear search                       Traversal
Replace elements matching condition Traversal
─────────────────────────────────────────────
Find in SORTED array                Binary Search
Two elements summing to target      Hash Map / Two Pointers
Max/min sum subarray of size K      Sliding Window
Merge intervals                     Interval Pattern
─────────────────────────────────────────────
```

---

## Common Mistakes Quick Reference

```
❌  Confusing i with arr[i]        → i = index, arr[i] = value
❌  Using <= arr.length             → use < arr.length
❌  Forgetting i++                  → causes infinite loop
❌  Starting at index 1 without reason → start at 0
❌  Thinking about whole array      → focus on current element
❌  Skipping the dry run            → always trace first
❌  Hardcoding arr[2] for last element → use arr[arr.length - 1]
```

---

## Traversal Mental Formula

```
Read Problem
    ↓
Need every element?
    ↓ YES
Traversal
    ↓
What state do I need?
(count / sum / max / min / found)
    ↓
Process current element
    ↓
Move to next
    ↓
Repeat
    ↓
Return answer
```

---

## Complexity Reference

| Operation | Time | Space |
|---|---|---|
| Traverse entire array | O(n) | O(1) |
| Traverse with one state variable | O(n) | O(1) |
| Two nested traversals | O(n²) | O(1) |

---

## Skills Gained in Lesson 2

After completing this lesson you can:

```
✅ Identify when a problem requires traversal
✅ Traverse arrays left→right and right→left
✅ Perform dry runs confidently for any traversal code
✅ Maintain simple state (count, sum, max, min, found)
✅ Analyse traversal solutions: O(n) time, O(1) space
✅ Recognise traversal as the foundation for advanced patterns
✅ Avoid the 10 most common traversal mistakes
```

---

## What Comes Next

```
Lesson 2 — Traversal    ✅ Complete
     ↓
Lesson 3 — State Pattern

You already saw glimpses of state in Examples 3–5.
In Lesson 3, "maintaining information while traversing"
becomes a formal, reusable pattern used across arrays,
strings, linked lists, trees, graphs, and dynamic programming.
```

---

*End of Lesson 2 — Traversal*
