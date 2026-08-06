# Chapter 1 — Understanding Traversal

> **Lesson 2 › Chapter 1 of 5**

---

## 📍 Progress

```
Lesson 2 — Traversal
│
├── 🔵 Chapter 1 — Understanding Traversal     ← You are here
├── ⬜ Chapter 2 — Types and Mental Model
├── ⬜ Chapter 3 — JavaScript and Dry Run
├── ⬜ Chapter 4 — Mistakes and Recognition
└── ⬜ Chapter 5 — Practice and Assessment
```

---

## 🎯 Goals

After this chapter you will be able to answer:

- What does the word "traverse" mean?
- What is array traversal?
- Why do we need to traverse an array?
- Why is traversal a *process* and not an *algorithm*?
- Which problems require traversal before they can be solved?

---

## Part 1 — What is Traversal?

### The Word Itself

The English word **traverse** means:

> **To move through something from one end to the other while visiting every part.**

Three words are critical here:

| Word | Meaning |
|---|---|
| **Move through** | You are actively going through it, not jumping around |
| **One end to the other** | You start from a defined beginning |
| **Visit every part** | Nothing is skipped |

---

### Real-Life Examples

#### 📖 Reading a Book

```
Page 1
  ↓
Page 2
  ↓
Page 3
  ↓
Page 4
  ↓
Page 5
```

If you read every page in order — without skipping any — you are **traversing the book**.

---

#### 🎓 Attendance

A teacher calls attendance for a row of students:

```
Rahul  → ✓
Priya  → ✓
John   → ✓
Sara   → ✓
David  → ✓
```

The teacher visited every student **exactly once**, in order. That is traversal.

---

#### 🏠 House Inspection

```
Room 1 → inspected
Room 2 → inspected
Room 3 → inspected
Room 4 → inspected
```

The inspector does not inspect Room 1 ten times. He does not skip Room 3. Each room visited once — traversal.

---

### Traversal in Arrays

Given an array:

```js
const arr = [12, 5, 30, 18, 9];
```

Visual layout:

```
Index:   0     1     2     3     4
       ┌─────┬─────┬─────┬─────┬─────┐
       │ 12  │  5  │ 30  │ 18  │  9  │
       └─────┴─────┴─────┴─────┴─────┘
```

Traversal means visiting each value, one by one:

```
12 → 5 → 30 → 18 → 9
```

---

### The Conveyor Belt Analogy

Imagine the array is a conveyor belt:

```
[4] → [8] → [2] → [7] → [5]
         you stand here
```

Each element comes in front of you one at a time. For each element you ask:

> *"Do I need to do something with this?"*

Maybe add it, count it, compare it, or ignore it. Then the belt moves.

**Traversal simply gives you the chance to process each element once.**

---

### Important Observation

> ⚠️ Traversal is **not** a problem.
> ⚠️ Traversal is **not** an algorithm.
> ✅ Traversal is a **process**.

It means: *"Visit every element."*

What you do **while visiting** depends entirely on the problem.

---

## Part 2 — Why Do We Need Traversal?

### The Core Reason

Suppose you have:

```js
const marks = [82, 91, 76, 88, 95];
```

And I ask: **What is the highest mark?**

Can you answer immediately? **No.**

Why? Because you cannot know the maximum until you have seen **all** the values.

---

### Three Examples That Prove This

#### Example A — Find Maximum

```
82  →  is it the max so far? Yes  (current max = 82)
91  →  is it the max so far? Yes  (current max = 91)
76  →  is it the max so far? No   (current max = 91)
88  →  is it the max so far? No   (current max = 91)
95  →  is it the max so far? Yes  (current max = 95)
```

You had to inspect every value before you could answer.

---

#### Example B — Count Scores Above 80

```
82  →  ✓ above 80   count = 1
91  →  ✓ above 80   count = 2
76  →  ✗             count = 2
88  →  ✓ above 80   count = 3
95  →  ✓ above 80   count = 4
```

Only after checking every element can you answer: **4 students scored above 80**.

---

#### Example C — Search for a Specific Value

> *Is there a student who scored exactly 76?*

You cannot know without checking every element until you either find 76 or reach the end.

---

### The Pattern Across All Problems

| Problem | What you must do first |
|---|---|
| Find maximum | Look at every element |
| Find minimum | Look at every element |
| Count even numbers | Look at every element |
| Find the sum | Look at every element |
| Search for a value | Look at every element (unless position is known) |

**Different problems. Same first step: Traversal.**

---

### Why Can't We Skip Elements?

```
arr = [12, 45, 8, 99, 23]
```

Task: Find the largest number.

If you skip index 3 (`99`) and inspect only `12, 45, 8, 23`:

```
Your answer → 45   ❌  Wrong
Correct answer → 99
```

**Skipping even one element can change the answer.**

---

### Why Can't We Visit the Same Element Repeatedly?

```
Visiting 45 three times in a row?
45, 45, 45 ...
```

Reading it again gives no new information. You are wasting time. A good traversal visits **each element exactly once**.

---

### The Golden Rule

```
1. Don't skip any required element.
2. Don't visit the same element unnecessarily.
→  Visit each element exactly once.
```

---

### Traversal is NOT the Solution

This is a critical distinction:

```
Problem: Find the maximum number.

Traversal alone → only lets you SEE each number.
                  It does NOT find the maximum.

To actually find the maximum you need an
additional idea: maintaining the current maximum.
→ That is the State Pattern (Lesson 3).
```

Think of it this way:

```
Traversal  =  the road
Algorithm  =  the vehicle travelling on that road
```

The road does not decide the destination. Your algorithm does.

---

### One Pass

You will hear the phrase **"one pass"** constantly in interviews.

```
One pass = one complete traversal

Array: [10, 20, 30]

Pass 1:
  10 → 20 → 30   (done)

If you traverse again:
  10 → 20 → 30   (Pass 2)
```

When an interviewer says *"can you solve this in one pass?"*, they are asking: *"can you do it without traversing more than once?"*

---

### Why Traversal Comes First

Almost every array algorithm begins with traversal:

```
Two Pointers     → still traverses
Sliding Window   → still traverses
Prefix Sum       → still traverses
Kadane's Algo    → still traverses
Frequency Count  → still traverses
```

Traversal is the **foundation**. Everything else is built on top.

---

## ✅ Chapter 1 Summary

| Concept | Key Point |
|---|---|
| Definition | Visit every element, one at a time, from one end to the other |
| Why needed | Most problems require inspecting all elements before producing an answer |
| Process, not algorithm | Traversal is the "how to move"; the algorithm decides "what to do" |
| One pass | One complete traversal from start to finish |
| Foundation | Every major array pattern still relies on traversal |

---

## 🧪 Concept Check

Array: `[25, 18, 40, 12]`

**Q1.** Traversing left to right — which value do you visit first?

**Q2.** Which value do you visit last?

**Q3.** During one traversal, how many times do you visit `40`?

**Q4.** If you perform two traversals, how many times is each element visited?

**Q5.** True or False: *Traversal itself finds the maximum element.*

**Q6.** To find the maximum, can you skip the value `40`? Why or why not?

**Q7.** Does reading `18` three times help you find the maximum faster?

**Q8.** Complete the sentence: *Traversal is the ______. The algorithm decides what to do with each element.*

<details>
<summary>Answers</summary>

1. `25`
2. `12`
3. Once
4. Twice (once per traversal)
5. False — traversal lets you see each number; an additional idea (State Pattern) finds the maximum
6. No — skipping any element may cause you to miss the maximum
7. No — re-reading gives no new information
8. Road (or foundation)

</details>

---

## ➡️ Next

[Chapter 2 — Types of Traversal and Mental Model](./chapter-2-types-and-mental-model.md)

In Chapter 2 you will learn the different directions you can traverse an array, and the four-step mental cycle that professionals use while traversing.
