# Chapter 3 — Traversal in JavaScript and Dry Run

> **Lesson 2 › Chapter 3 of 5**

---

## 📍 Progress

```
Lesson 2 — Traversal
│
├── ✅ Chapter 1 — Understanding Traversal
├── ✅ Chapter 2 — Types and Mental Model
├── 🔵 Chapter 3 — JavaScript and Dry Run     ← You are here
├── ⬜ Chapter 4 — Mistakes and Recognition
└── ⬜ Chapter 5 — Practice and Assessment
```

---

## 🎯 Goals

After this chapter you will be able to:

- Write the standard traversal `for` loop in JavaScript
- Explain every single part of that loop and *why* it exists
- Distinguish between `i` (index) and `arr[i]` (value)
- Dry-run any traversal loop step by step
- Fill in a dry-run table for any array problem

---

## Part 1 — Traversal in JavaScript

### The Problem

You have:

```js
const arr = [10, 20, 30, 40];
```

Your brain wants to visit `10 → 20 → 30 → 40`. But JavaScript needs explicit instructions.

Those instructions are a **loop**.

---

### Why the `for` Loop?

Three options exist for looping in JavaScript:

| Loop | Gives index access? | Common in DSA? |
|---|---|---|
| `for (let i = 0; ...)` | ✅ Yes, directly | ✅ Most common |
| `while` | ✅ Yes, with manual variable | ✅ Used sometimes |
| `for...of` | ❌ No index by default | ⚠️ Limited use |

DSA problems frequently require the **current index**, the **previous index**, or the **next index**. The `for` loop gives direct control over all of these, making it the standard choice.

---

### The Standard Traversal Template

```js
for (let i = 0; i < arr.length; i++) {
    // Current Index:   i
    // Current Value:   arr[i]
    // Process the current element here
}
```

You will write this **thousands of times** during your DSA journey. Let's understand every single part.

---

### Part-by-Part Breakdown

#### `let i = 0` — Starting Point

```
Arrays start at index 0.
So traversal begins at index 0.

Index:   0     1     2     3
       ┌─────┬─────┬─────┬─────┐
       │ 10  │ 20  │ 30  │ 40  │
       └─────┴─────┴─────┴─────┘
         ↑
    Start here (i = 0)
```

> **Why `i`?** — It stands for **index**. `i` stores a position, not a value.

---

#### `i < arr.length` — Stopping Condition

```js
const arr = [10, 20, 30]; // length = 3, valid indexes: 0, 1, 2
```

| `i` value | Condition `i < 3` | Enter loop? |
|---|---|---|
| 0 | `0 < 3` ✅ | Yes |
| 1 | `1 < 3` ✅ | Yes |
| 2 | `2 < 3` ✅ | Yes |
| 3 | `3 < 3` ❌ | No — stop |

> ⚠️ **Never write `i <= arr.length`**  
> At `i = 3`, `arr[3]` doesn't exist. JavaScript returns `undefined`. That is an **off-by-one error**.

---

#### `i++` — Moving Forward

After processing the current element, move to the next index:

```
0 → 1 → 2 → 3 (stop)
```

> ⚠️ **If you forget `i++`**, the loop stays at index 0 forever → **infinite loop**.

---

### `i` vs `arr[i]` — The Single Most Important Distinction

```js
const arr = [50, 80, 20];
// i = 1

console.log(i);       // → 1    (the POSITION)
console.log(arr[i]);  // → 80   (the VALUE at that position)
```

```
       i = 1
         ↓
Index:  0    1    2
      ┌────┬────┬────┐
      │ 50 │ 80 │ 20 │
      └────┴────┴────┘
              ↑
         arr[i] = 80
```

| Expression | Meaning | Example (i=1) |
|---|---|---|
| `i` | Current index (position) | `1` |
| `arr[i]` | Current value (element) | `80` |

**This confusion is the #1 beginner mistake in traversal.** Keep the table above in mind.

---

### Full Traversal Example

```js
const arr = [10, 20, 30];

for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
}
// Output:
// 10
// 20
// 30
```

---

### Left-to-Right vs Right-to-Left Templates

#### Left → Right (Default)

```js
for (let i = 0; i < arr.length; i++) {
    // process arr[i]
}
```

#### Right → Left

```js
for (let i = arr.length - 1; i >= 0; i--) {
    // process arr[i]
}
```

Why `arr.length - 1` as the start?

```js
const arr = [10, 20, 30, 40]; // length = 4
// Last valid index = 4 - 1 = 3
// arr[3] = 40 ← the last element
```

Why `i >= 0` as the stop condition?

Index `0` is still valid (it holds the first element). We stop when `i` becomes `-1`.

---

### Why Not `for...of` in DSA?

```js
// for...of — simple but limited
for (const value of arr) {
    console.log(value); // ✅ works
    // but what is the current index?
    // what is arr[i - 1]? what is arr[i + 1]?
    // ❌ not directly accessible
}
```

In DSA you frequently need to know *where* you are, not just *what* the current value is. The `for` loop gives you that control.

---

## Part 2 — Dry Run

### What is a Dry Run?

> **Dry Run** — executing an algorithm manually, step by step, on paper or in your head, *without* running it on a computer.

Think of it as a rehearsal. Actors rehearse before a play. Engineers rehearse code before executing it.

---

### Why Do Interviewers Care?

If an interviewer asks:

> *"Can you tell me what this code outputs?"*

And you need to run it in VS Code every time — you will struggle. Good engineers mentally execute simple code. A dry run is exactly that skill.

---

### The Six-Step Dry Run Process

For every iteration of a loop, ask these in order:

```
1. What is the current value of i?
2. Is the loop condition true?
3. Which element am I visiting? (arr[i])
4. What action is performed?
5. What happens to i after this iteration?
6. Repeat.
```

---

### Full Dry Run Example

```js
const arr = [10, 20, 30];

for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
}
```

**Before the loop:**

```
Array:
Index:   0     1     2
       ┌─────┬─────┬─────┐
       │ 10  │ 20  │ 30  │
       └─────┴─────┴─────┘

i = not yet created
```

**Iteration 1:**

```
i = 0
Condition: 0 < 3  ✅
arr[0] = 10
Action: print 10
i++ → i = 1
```

**Iteration 2:**

```
i = 1
Condition: 1 < 3  ✅
arr[1] = 20
Action: print 20
i++ → i = 2
```

**Iteration 3:**

```
i = 2
Condition: 2 < 3  ✅
arr[2] = 30
Action: print 30
i++ → i = 3
```

**Stop check:**

```
i = 3
Condition: 3 < 3  ❌
Loop ends.
```

---

### The Dry Run Table

Experienced engineers trace loops with a table. This format is also useful in interviews when explaining your solution.

| Iteration | `i` | Condition | `arr[i]` | Action | `i` after |
|---|---|---|---|---|---|
| 1 | 0 | `0 < 3` ✅ | 10 | print 10 | 1 |
| 2 | 1 | `1 < 3` ✅ | 20 | print 20 | 2 |
| 3 | 2 | `2 < 3` ✅ | 30 | print 30 | 3 |
| — | 3 | `3 < 3` ❌ | — | stop | — |

---

### The Moving Pointer Animation

Mentally visualise a pointer moving across the array:

```
Step 1:  [10]  20   30   40
Step 2:   10  [20]  30   40
Step 3:   10   20  [30]  40
Step 4:   10   20   30  [40]
Step 5:   loop ends (i = 4, condition false)
```

---

### Dry Run with State Variable

For more complex traversals, extend the table to include state:

```js
const arr = [5, 15, 25, 35];
let sum = 0;

for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
}
console.log(sum); // 80
```

| Iteration | `i` | `arr[i]` | `sum` before | `sum` after |
|---|---|---|---|---|
| Init | — | — | 0 | — |
| 1 | 0 | 5 | 0 | 5 |
| 2 | 1 | 15 | 5 | 20 |
| 3 | 2 | 25 | 20 | 45 |
| 4 | 3 | 35 | 45 | 80 |

---

### A Dry Run Debugging Checklist

Whenever your traversal gives wrong output, build this table:

| Iteration | `i` | `arr[i]` | Action |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

**Most bugs become immediately visible.** Did you visit the right elements? Did the state variable update correctly? Did the loop stop at the right place?

---

### The Golden Dry Run Rule

```
┌───────────────────────────────────────────────┐
│  Never write code before you can dry-run it.  │
│                                               │
│  If you cannot trace your algorithm for a    │
│  small example, you do not fully understand  │
│  it yet.                                     │
└───────────────────────────────────────────────┘
```

This rule becomes even more important for Sliding Window, Trees, Graphs, and Dynamic Programming — where a correct dry run often reveals bugs before you ever execute the code.

---

## ✅ Chapter 3 Summary

| Concept | Key Point |
|---|---|
| Standard template | `for (let i = 0; i < arr.length; i++)` |
| `i` | Stores the current **index** (position) |
| `arr[i]` | Gives the current **value** (element) |
| Stopping condition | Use `<` not `<=` — the last valid index is `arr.length - 1` |
| Forgetting `i++` | Causes an infinite loop |
| Reverse traversal | `for (let i = arr.length - 1; i >= 0; i--)` |
| Dry run | Trace the algorithm manually, iteration by iteration |
| Dry run table | Columns: `i`, condition, `arr[i]`, action, state |

---

## 🧪 Concept Check

Given: `const arr = [5, 10, 15];`

**Q1.** What is the value of `i` in the first iteration?

**Q2.** What does `arr[i]` return in the second iteration?

**Q3.** Why do we write `i < arr.length` instead of `i <= arr.length`?

**Q4.** What is the difference between `i` and `arr[i]`?

**Q5.** What happens if we remove `i++`?

---

Dry run this code without executing it:

```js
const arr = [4, 8, 12];

for (let i = 0; i < arr.length; i++) {
    console.log(arr[i]);
}
```

**Q6.** What is `i` during the first iteration?

**Q7.** What is `arr[i]` during the second iteration?

**Q8.** What is the final value of `i` after the loop ends?

**Q9.** How many times does the loop body execute?

**Q10.** What is the complete output?

<details>
<summary>Answers</summary>

1. `0`
2. `10`
3. Because the last valid index is `arr.length - 1`. At `i = arr.length`, `arr[i]` is `undefined`.
4. `i` is the position; `arr[i]` is the value at that position
5. Infinite loop — `i` never changes, loop never progresses
6. `0`
7. `8`
8. `3` (loop exits when `i = 3` because `3 < 3` is false)
9. Three times (for i = 0, 1, 2)
10. `4`, `8`, `12`

</details>

---

## Explanation Order for All Code Examples

From this chapter onward, every code example follows this fixed structure:

```
1. Read the problem
2. Explain the algorithm idea (without code)
3. Show the code
4. Explain every line
5. Dry run the code
6. Analyse time and space complexity
7. Discuss common mistakes
```

This mirrors how senior engineers review solutions.

---

## ➡️ Next

[Chapter 4 — Common Mistakes and Interview Recognition](./chapter-4-mistakes-and-recognition.md)

In Chapter 4 you will learn the 10 most common traversal mistakes beginners make, and how to instantly recognise whether a given interview problem requires traversal.
