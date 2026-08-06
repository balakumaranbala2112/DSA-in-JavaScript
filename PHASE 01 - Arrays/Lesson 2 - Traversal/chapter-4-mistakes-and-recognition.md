# Chapter 4 — Common Mistakes and Interview Recognition

> **Lesson 2 › Chapter 4 of 5**

---

## 📍 Progress

```
Lesson 2 — Traversal
│
├── ✅ Chapter 1 — Understanding Traversal
├── ✅ Chapter 2 — Types and Mental Model
├── ✅ Chapter 3 — JavaScript and Dry Run
├── 🔵 Chapter 4 — Mistakes and Recognition   ← You are here
└── ⬜ Chapter 5 — Practice and Assessment
```

---

## 🎯 Goals

After this chapter you will be able to:

- Recognise and avoid the 10 most common traversal mistakes
- Use a debugging checklist to fix traversal bugs quickly
- Identify whether an interview problem requires traversal
- Distinguish pure traversal problems from problems that need other patterns
- Think in patterns before thinking in code

---

## Part 1 — Common Beginner Mistakes

> **Note:** Almost all of these are *thinking* mistakes, not JavaScript mistakes. DSA interviews evaluate how you reason about problems. The code is simply the language you use to express that reasoning.

---

### Mistake 1 — Confusing Index with Value ❌ (Most Common)

```js
const arr = [50, 80, 20];
```

Many beginners see `i = 1` and think *"the current value is 1"*.

**Wrong.** `i` stores the **position**, not the value.

```
Index:   0     1     2
       ┌─────┬─────┬─────┐
       │ 50  │ 80  │ 20  │
       └─────┴─────┴─────┘
                ↑
           i = 1  →  arr[i] = 80
```

```
i       → Position (1)
arr[i]  → Value    (80)
```

---

### Mistake 2 — Starting at Index 1

```js
// ❌ Wrong
for (let i = 1; i < arr.length; i++) { ... }
```

```
arr = [10, 20, 30]

Visited:    20, 30
Skipped:    10   ← first element never processed
```

Unless the problem **explicitly** says to start from index 1 (as in *"compare with the previous element"*), always start at `i = 0`.

---

### Mistake 3 — Using `<=` Instead of `<`

```js
// ❌ Wrong — causes off-by-one error
for (let i = 0; i <= arr.length; i++) { ... }

// arr = [10, 20, 30], length = 3
// Loop runs for i = 0, 1, 2, 3
// arr[3] → undefined ← bug
```

```js
// ✅ Correct
for (let i = 0; i < arr.length; i++) { ... }
// Loop runs for i = 0, 1, 2 — exactly the valid indexes
```

---

### Mistake 4 — Forgetting `i++`

```js
let i = 0;
while (i < arr.length) {
    console.log(arr[i]);
    // ❌ forgot: i++
}
// → Infinite loop — prints arr[0] forever
```

**Always ask:** *"How does my traversal move to the next element?"*

---

### Mistake 5 — Thinking About the Entire Array at Once

```
arr = [8, 3, 15, 6, 11]

❌ Beginner thinks:  8, 3, 15, 6, 11 all at once → overwhelmed

✅ Professional thinks:
   Current = 8  → process → move
   Current = 3  → process → move
   ...
```

Focus on **one element, one decision, move**. The loop handles the repetition.

---

### Mistake 6 — Stopping Too Early (Missing the Last Element)

```js
// ❌ Wrong — misses the last element
for (let i = 0; i < arr.length - 1; i++) { ... }

// arr = [10, 20, 30, 40]
// Visits: 10, 20, 30
// Skips:  40  ← last element never processed
```

**Always verify:** *"Does my loop visit the last valid index?"*

---

### Mistake 7 — Hardcoding Array Indexes

```js
const arr = [5, 10, 15];

// ❌ Wrong
console.log(arr[2]); // hardcoded "last element"

// Tomorrow the array might be [5, 10, 15, 20, 25]
// Now arr[2] is 15, not the last element
```

```js
// ✅ Correct
console.log(arr[arr.length - 1]); // always the last element
```

Write code that works for arrays of **any size**.

---

### Mistake 8 — Memorising Loops Without Understanding

Many beginners can write `for (let i = 0; i < arr.length; i++)` from memory but cannot explain **why each part exists**.

If asked *"Why `<` instead of `<=`?"* — you should be able to answer immediately.

```
Why start at 0?         → Arrays are zero-indexed
Why stop at arr.length? → Last valid index is arr.length - 1
Why i++?                → Move to the next element after each visit
```

Understand. Don't memorise.

---

### Mistake 9 — Skipping the Dry Run

Some beginners write code and immediately execute it. When the output is wrong, they don't know *where* it went wrong.

A 30-second dry run often finds bugs faster than repeated execution and debugging. **Always trace first.**

---

### Mistake 10 — Focusing on Syntax Instead of Pattern

```
❌ "This problem needs a for loop."
✅ "This problem needs traversal."
```

The `for` loop is one way to implement traversal. You could also use `while`, `for...of`, or recursion. The **pattern** (traversal) is more important than the **syntax** (for loop).

---

### Summary Table

| # | Mistake | Correct Approach |
|---|---|---|
| 1 | Confusing `i` with `arr[i]` | `i` = index, `arr[i]` = value |
| 2 | Starting at index 1 | Start at `0` unless problem says otherwise |
| 3 | Using `<= arr.length` | Use `< arr.length` |
| 4 | Forgetting `i++` | Always move to the next element |
| 5 | Thinking about the whole array | Focus on one current element |
| 6 | Stopping early (missing last element) | Verify last index is visited |
| 7 | Hardcoding indexes | Use `arr.length` dynamically |
| 8 | Memorising loops | Understand each part |
| 9 | Skipping dry runs | Trace code manually first |
| 10 | Focusing on syntax | Think about the traversal pattern |

---

### Debugging Checklist

When your traversal produces wrong output, check these in order:

```
[ ] Did I start at the correct index?
[ ] Is my stopping condition correct (< not <=)?
[ ] Am I moving to the next element (i++ or i--)?
[ ] Am I processing the correct element (arr[i], not i)?
[ ] Did I visit every required element exactly once?
[ ] Am I confusing index and value?
[ ] Did I dry-run the algorithm?
```

---

### Interview Edge Cases

Before submitting any traversal solution, mentally test with:

| Test Case | Why It Matters |
|---|---|
| `[]` — empty array | Does the loop execute 0 times? |
| `[5]` — single element | Does it work for just one element? |
| `[5, 10]` — two elements | Does it handle the boundary between elements? |

If your traversal handles these correctly, it almost certainly handles larger inputs too.

---

## Part 2 — Interview Recognition

### The Biggest Beginner Mistake

A beginner reads:

> *"Find the largest number in an array."*

And immediately thinks: *"Which algorithm should I use?"*

An experienced engineer thinks: *"Let me identify the pattern first."*

**That difference in thinking is what you are building in this lesson.**

---

### The Pattern Recognition Process

When you see an array problem, ask these four questions **before writing any code**:

---

#### Question 1: Do I need to visit every element?

```
Problem: Find the maximum element.
Can I know the maximum without seeing every element? → No
→ Traversal is involved.
```

---

#### Question 2: Can I process each element exactly once?

```
Problem: Count even numbers.
Do I need to come back to any element? → No
→ One-pass traversal.
```

---

#### Question 3: Does the problem require information about distant elements?

```
Problem: Find the maximum.
While looking at 50, do I need to know the next five elements? → No
Each element is processed individually → Traversal.
```

---

#### Question 4: Do I only need the current element to make a decision?

```
Problem: Count negative numbers.
Current number → negative? → increment count → move
No other element is needed to make this decision → Traversal.
```

---

### Visual Recognition Flow

```
See array problem
       ↓
Do I need every element?
       │
      YES
       ↓
Can I process one element at a time?
       │
      YES
       ↓
  → THINK: TRAVERSAL
       ↓
What additional state do I need?
(count? sum? max? min? found?)
```

---

### Interview Keywords

When you see these words in a problem, **think traversal first**:

| Keyword | Example Problem |
|---|---|
| **Find** | Find maximum, find minimum, find first occurrence |
| **Count** | Count even numbers, count positives, count zeros |
| **Sum** | Total sum, sum of positives, running total |
| **Check** | Check if all elements are positive, check if value exists |
| **Print** | Print all elements, print in reverse, print even elements |
| **Replace** | Replace negatives with zero |
| **Average** | Average of all marks |

---

### Pure Traversal Problems

These problems are solved primarily by traversal:

| Problem | What You Maintain |
|---|---|
| Print all elements | Nothing (just traverse and print) |
| Find maximum | `max` variable |
| Find minimum | `min` variable |
| Sum of array | `sum` variable |
| Average of array | `sum` + final division |
| Count even numbers | `count` variable |
| Count values above X | `count` variable |
| Search for a target (linear search) | `found` boolean |
| Print in reverse | Right-to-left traversal |
| Replace negatives with 0 | Traversal + update |
| Largest even number | `max` variable with even check |

---

### Problems That Are NOT Pure Traversal

Equally important — knowing when **not** to use just traversal:

| Problem | Why Not Traversal | Correct Pattern |
|---|---|---|
| Two sum (find pair equal to target) | Needs to check relationships between elements | Hash Map or Two Pointers |
| Maximum sum subarray of size K | Overlapping sums — traversal alone is too slow | Sliding Window |
| Find element in a **sorted** array | Traversal works but is O(n) — interviewer expects O(log n) | Binary Search |
| Merge overlapping intervals | Requires sorting first | Interval Pattern |
| Rotate array | Involves block movement, not one-by-one | Two Pointers or extra array |

---

### Full Recognition Table

| Problem | Primary Pattern |
|---|---|
| Find maximum | ✅ Traversal |
| Find minimum | ✅ Traversal |
| Sum of array | ✅ Traversal |
| Count elements matching a condition | ✅ Traversal |
| Linear search | ✅ Traversal |
| Print in reverse | ✅ Traversal (right→left) |
| Running sum | ✅ Traversal |
| Two sum | ❌ Hash Map / Two Pointers |
| Max subarray sum of size K | ❌ Sliding Window |
| Search in sorted array | ❌ Binary Search |
| Merge intervals | ❌ Interval Pattern |

---

### Interview Thinking Process

Suppose the interviewer asks: *"Find the largest number."*

```
Step 1: Do I need every element?
        → Yes (can't know max without seeing all)

Step 2: Traversal

Step 3: What do I need to remember?
        → Current maximum

Step 4: Algorithm
        → Start with max = arr[0]
        → At each element: if arr[i] > max, update max
        → Return max

Step 5: Write the code
```

Notice: you are thinking about **patterns**, not about loops.

---

### The Golden Rule

```
❌ Don't ask: "Which loop should I use?"
✅ Do ask:    "Which pattern solves this problem?"

Once you know the pattern, choosing the loop is trivial.
```

---

### Connection to Future Lessons

Pattern recognition leads directly into the rest of Module 1:

```
Recognise Traversal
       ↓
Need to remember information while traversing?
       ↓
    Lesson 3 — State Pattern

Need to simulate actions step by step?
       ↓
    Lesson 4 — Simulation

Need to count occurrences?
       ↓
    Lesson 5 — Frequency Counting
```

Recognition always comes **before** implementation.

---

## ✅ Chapter 4 Summary

| Concept | Key Point |
|---|---|
| Most common mistake | Confusing `i` (index) with `arr[i]` (value) |
| Off-by-one error | Always use `<` not `<=` in the loop condition |
| Debugging approach | Use the 7-point checklist + dry-run table |
| Pattern recognition | Ask 4 questions before writing any code |
| Traversal keywords | Find, Count, Sum, Check, Print, Replace, Average |
| Not always traversal | Sorted search → Binary Search; pair sums → Hash Map/Two Pointers |
| Golden rule | Identify the pattern first, then write the code |

---

## 🧪 Concept Check

**Q1.** Which variable stores the **index** during traversal?

**Q2.** Which expression gives the **current element**?

**Q3.** Why is `i <= arr.length` usually incorrect?

**Q4.** What happens if you forget `i++`?

**Q5.** Which is more important in DSA — memorising the loop syntax, or understanding the traversal pattern?

For each problem below, identify only whether **Traversal** is the main pattern:

**Q6.** Find the smallest number.

**Q7.** Count how many values are greater than 50.

**Q8.** Find the maximum sum of a subarray of size 3.

**Q9.** Search for a value in a **sorted** array.

**Q10.** Print every element in reverse order.

<details>
<summary>Answers</summary>

1. `i`
2. `arr[i]`
3. At `i = arr.length`, the index doesn't exist — JavaScript returns `undefined`
4. Infinite loop — the loop never advances past the first element
5. Understanding the traversal pattern
6. ✅ Traversal
7. ✅ Traversal
8. ❌ Sliding Window
9. ❌ Binary Search (expected interview solution)
10. ✅ Traversal (right-to-left)

</details>

---

## ➡️ Next

[Chapter 5 — Guided Examples, Practice and Assessment](./chapter-5-practice-and-assessment.md)

In Chapter 5 you will solve 5 guided examples with complete step-by-step explanations, then work through 10 independent practice problems, take the lesson quiz, and review the revision notes.
