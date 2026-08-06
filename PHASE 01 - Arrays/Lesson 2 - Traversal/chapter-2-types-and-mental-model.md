# Chapter 2 — Types of Traversal and Mental Model

> **Lesson 2 › Chapter 2 of 5**

---

## 📍 Progress

```
Lesson 2 — Traversal
│
├── ✅ Chapter 1 — Understanding Traversal
├── 🔵 Chapter 2 — Types and Mental Model      ← You are here
├── ⬜ Chapter 3 — JavaScript and Dry Run
├── ⬜ Chapter 4 — Mistakes and Recognition
└── ⬜ Chapter 5 — Practice and Assessment
```

---

## 🎯 Goals

After this chapter you will be able to answer:

- What are the different ways to traverse an array?
- When is each traversal type used?
- Which type should I master first?
- What should my brain be doing at each element?
- What is the four-step mental cycle?

---

## Part 1 — Types of Traversal

### What Does "Type" Mean?

Traversal means: *visit the elements*. But it does not specify the **order**.

Think of a street with houses. You can visit every house by:

- Walking left to right
- Walking right to left
- Starting from both ends simultaneously
- Moving in a circle

You still visit the houses. Only the **path** changes. Traversal types work the same way.

---

### Type 1 — Left to Right ⭐ (Default)

Start at the first element. Move toward the last.

```
arr = [10, 20, 30, 40, 50]

Direction:  →  →  →  →

   10 → 20 → 30 → 40 → 50
```

This is the **most common traversal** in all of DSA. Whenever someone says *"traverse the array"* without specifying direction, assume **left to right**.

**Used for:** sum, maximum, minimum, counting, frequency counting, linear search, most interview problems.

---

### Type 2 — Right to Left

Start at the last element. Move toward the first.

```
arr = [10, 20, 30, 40, 50]

Direction:  ←  ←  ←  ←

   10 ← 20 ← 30 ← 40 ← 50
   (visited: 50, 40, 30, 20, 10)
```

**Used for:** reverse printing, suffix-based algorithms, certain dynamic programming problems.

---

### Type 3 — Two-End Traversal

Two pointers start from opposite ends and move toward the centre.

```
arr = [10, 20, 30, 40, 50]

        ↑                ↑
       Left            Right

Step 1: compare 10 and 50, move both inward
        10  [20  30  40]  50
              ↑        ↑
Step 2: compare 20 and 40 ...
```

This traversal type eventually becomes the **Two Pointers Pattern** (Module 2).

**Used for:** palindrome check, pair sum, reverse array, remove duplicates from sorted array.

---

### Type 4 — Circular Traversal

When you reach the end, you wrap back to the beginning:

```
arr = [1, 2, 3, 4]

  1 → 2 → 3 → 4
  ↑              ↓
  └──────────────┘
```

**Used for:** circular queues, rotating arrays, next greater element (circular). This is an advanced traversal — do not worry about it now.

---

### Type 5 — Matrix Traversal

For two-dimensional arrays (grids), traversal can go in many directions:

```
Matrix:
  1  2  3
  4  5  6
  7  8  9

Row by row:     1→2→3, 4→5→6, 7→8→9
Column by col:  1→4→7, 2→5→8, 3→6→9
Spiral:         1→2→3→6→9→8→7→4→5
```

**Covered in:** Module 8 — Matrix.

---

### Comparison Table

| Type | Direction | Interview Frequency | When Covered |
|---|---|---|---|
| Left → Right | Start to end | ⭐⭐⭐⭐⭐ Very Common | **Now (Lesson 2)** |
| Right → Left | End to start | ⭐⭐⭐ Common | As needed |
| Two Ends | Both ends inward | ⭐⭐⭐⭐⭐ Very Common | Module 2 |
| Circular | Wrap-around | ⭐⭐ Occasionally | Advanced |
| Matrix | 2D directions | ⭐⭐⭐⭐ Common | Module 8 |

> **Focus now: Left → Right only.** The others will be taught when they naturally appear.

---

### How Types Connect to Future Modules

```
Left → Right
      │
      ├── State Pattern      (Lesson 3)
      ├── Simulation         (Lesson 4)
      ├── Frequency Counting (Lesson 5)
      ├── Sliding Window     (Module 3)
      └── Prefix Sum / Kadane (Module 4/5)

Two Ends
      │
      └── Two Pointers       (Module 2)

Matrix
      │
      └── Matrix Problems    (Module 8)
```

---

## Part 2 — The Traversal Mental Model

### First: Forget the Code

Do not think about JavaScript. Do not think about `for` loops.

Think only about **what your brain is doing** at each element.

---

### The Street Analogy

Imagine a street with five houses. You are asked to count the blue ones.

```
🏠  🏠  🏠  🏠  🏠
 1   2   3   4   5
```

You don't magically know the answer. You walk house by house. At **every house** you ask one question:

> *Is this house blue?*

If yes, increase your count. Then move to the next house.

Notice: your brain repeats the **same process** at every single house. That is the mental model.

---

### Arrays Work Exactly the Same Way

```
arr = [8, 3, 15, 6, 11]
```

Traversal means:

```
Visit 8   → think → do something → move
Visit 3   → think → do something → move
Visit 15  → think → do something → move
Visit 6   → think → do something → move
Visit 11  → think → done
```

---

### The Four-Step Mental Cycle

Every traversal follows this exact cycle:

```
┌─────────────────────────┐
│   1. Current Element    │
│         ↓               │
│   2. Observe            │
│         ↓               │
│   3. Process            │
│         ↓               │
│   4. Move Forward       │
│         ↓               │
│       Repeat            │
└─────────────────────────┘
```

Let's break down each step.

---

#### Step 1 — Current Element

At any moment, you are focused on **exactly one element**.

```
arr = [8, 3, 15, 6, 11]
         ↑
    Only thinking about 8.
    Not 3. Not 15. Only 8.
```

This is the most important rule: **one element at a time**.

---

#### Step 2 — Observe

Ask yourself what you know about this element:

- Is it even or odd?
- Is it larger than the current maximum?
- Is it negative?
- Does it equal the target?

You are simply **examining** the current element.

---

#### Step 3 — Process

Decide what to do with it:

| Situation | Action |
|---|---|
| Counting | Increment counter |
| Summing | Add to total |
| Finding max | Compare and update |
| Searching | Compare with target |
| Filtering | Skip or keep |

The action depends entirely on the problem.

---

#### Step 4 — Move Forward

After processing, you leave this element **permanently**. Move to the next one and repeat the exact same four-step cycle.

```
8  →  3  →  15  →  6  →  11
done  done   done   done  done
```

---

### The Spotlight Analogy

Imagine a spotlight moving across the array:

```
arr = [4, 7, 2, 9]

[4]  7   2   9    ← spotlight on 4
 4  [7]  2   9    ← spotlight on 7
 4   7  [2]  9    ← spotlight on 2
 4   7   2  [9]   ← spotlight on 9
```

**Your thinking moves with the spotlight.** Only the highlighted element matters at any given moment.

---

### The Cashier Analogy

Imagine you are a cashier. Customers arrive one by one:

```
Customer 1 → read bill → calculate → collect payment → next
Customer 2 → read bill → calculate → collect payment → next
Customer 3 → read bill → calculate → collect payment → next
```

You never process all customers simultaneously. Same with arrays.

---

### Why Beginners Get Confused

When solving *"Find the maximum"*, beginners try to think about all elements at once:

```
8, 3, 15, 6, 11 — brain tries to process all simultaneously → overwhelmed
```

The professional approach:

```
Current element = 8 → compare → result → next
Current element = 3 → compare → result → next
...
```

**One element. One decision. Move.**

---

### The Traversal Formula

Whenever you see an array problem, run this mental script:

```
Start
  ↓
Look at current element
  ↓
Ask: "What should I do with it?"
  ↓
Do that action
  ↓
Move to next element
  ↓
Repeat
  ↓
End
```

Only the *"What should I do?"* part changes from problem to problem.

---

### The Four-Step Cycle Applied to Different Problems

```
Find Maximum:
  Current element → Compare with max → Update if larger → Move

Count Even Numbers:
  Current element → Check if even → Increment count if yes → Move

Sum of Array:
  Current element → Add to sum → Move

Linear Search:
  Current element → Compare with target → Stop if found / Move
```

**Same traversal. Different processing.**

---

### The Most Important Rule

```
┌──────────────────────────────────────────────────┐
│  Never think about the whole array at once.      │
│  Think only about THE CURRENT ELEMENT.           │
└──────────────────────────────────────────────────┘
```

---

## ✅ Chapter 2 Summary

| Concept | Key Point |
|---|---|
| Types of traversal | Left→Right (default), Right→Left, Two-End, Circular, Matrix |
| Focus now | Left → Right only |
| Mental model | Four-step cycle: Current → Observe → Process → Move |
| One element at a time | Never think about the whole array simultaneously |
| The cycle repeats | The same four steps at every single element |

---

## 🧪 Concept Check

Array: `[5, 10, 15, 20]`

**Q1.** Which traversal starts with `5`?

**Q2.** Which traversal starts with `20`?

**Q3.** Which traversal uses both the first and last element at the same time?

**Q4.** True or False: *Matrix traversal is used for one-dimensional arrays.*

**Q5.** Which traversal type should you master first?

**Q6.** Name the four steps of the mental cycle.

**Q7.** While traversing, should you think about all three elements at once?

**Q8.** Fill in the cycle: `Current Element → _______ → Process → Move Forward`

<details>
<summary>Answers</summary>

1. Left → Right traversal
2. Right → Left traversal
3. Two-End traversal
4. False — matrix traversal is for 2D arrays
5. Left → Right
6. Current Element → Observe → Process → Move Forward
7. No — focus on one element at a time
8. Observe

</details>

---

## 🧠 Mental Model Cheat Code

Before writing any code for an array problem, ask yourself these four questions:

```
1. What is my current element?
2. What do I need to check about it?
3. What action should I perform?
4. Can I move to the next element now?
```

If this becomes automatic, many interview problems become significantly easier.

---

## ➡️ Next

[Chapter 3 — Traversal in JavaScript and Dry Run](./chapter-3-javascript-and-dry-run.md)

In Chapter 3 you will translate this mental model into JavaScript code, understand every part of the `for` loop, and learn how to trace your code manually before running it.
