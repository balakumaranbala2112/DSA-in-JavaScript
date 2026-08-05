# **DSA in JavaScript (Interview-Focused)**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **🔵 Chapter 7 — Common Beginner Mistakes**

---

## **📍 Where We Are**

DSA in JavaScript  
│  
└── Phase 1 — Arrays  
      │  
      └── Module 1 — Foundations  
            │  
            └── Lesson 2 — Traversal  
                  │  
                  ✅ Chapter 1 → What is Traversal?  
                  ✅ Chapter 2 → Why Do We Need Traversal?  
                  ✅ Chapter 3 → Types of Traversal  
                  ✅ Chapter 4 → Traversal Mental Model  
                  ✅ Chapter 5 → Traversal in JavaScript  
                  ✅ Chapter 6 → Dry Run  
                  🔵 Chapter 7 → Common Beginner Mistakes  
                  ⬜ Chapter 8 → Interview Recognition

                  ⬜ Guided Examples  
                  ⬜ Practice Problems  
                  ⬜ Lesson Quiz  
                  ⬜ Revision Notes

---

# **🎯 Goal**

After this chapter, you should be able to recognize and avoid the most common mistakes beginners make while traversing arrays.

These mistakes appear in interviews, coding contests, assignments, and even production code.

---

# **Mistake 1 — Confusing Index with Value**

This is the **\#1 beginner mistake**.

Suppose

const arr \= \[50, 80, 20\];

Many beginners think:

i \= 1

means

Current Value \= 1

Wrong.

`i` stores the **index**, not the value.

Visualize it.

Index

0      1      2  
┌────┬────┬────┐  
│50  │80  │20  │  
└────┴────┴────┘

If

i \= 1;

Then

arr\[i\]

becomes

arr\[1\]

which returns

80

Remember:

i        → Position

arr\[i\]   → Value

---

# **Mistake 2 — Starting at Index 1**

Wrong

for (let i \= 1; i \< arr.length; i++)

What happens?

Suppose

const arr \= \[10,20,30\];

Visited

20

↓

30

Skipped

10

The first element was never processed.

Unless the problem specifically says to start from index `1`, traversal begins at index `0`.

---

# **Mistake 3 — Using `<=` Instead of `<`**

Suppose

const arr \= \[10,20,30\];

Length

3

Indexes

0

1

2

Wrong

for (let i \= 0; i \<= arr.length; i++)

Iterations

0

1

2

3 ❌

Index `3` doesn't exist.

JavaScript returns

undefined

Correct

i \< arr.length

---

# **Mistake 4 — Forgetting to Move Forward**

Suppose

let i \= 0;

But you forget

i++

Now the program keeps checking

Index 0

↓

Index 0

↓

Index 0

↓

Index 0

Forever.

This is called an **infinite loop**.

Always ask:

> "How does my traversal move to the next element?"

---

# **Mistake 5 — Thinking About the Entire Array**

Suppose

\[8,3,15,6,11\]

Beginners often think

8

3

15

6

11

all at once.

That's overwhelming.

Professionals think

Current Element

↓

Process

↓

Move

↓

Repeat

One element at a time.

---

# **Mistake 6 — Forgetting the Last Element**

Suppose

const arr \= \[10,20,30,40\];

If your loop stops too early,

you never visit

40

Always verify:

> "Does my loop visit the last valid index?"

---

# **Mistake 7 — Hardcoding Values**

Suppose

const arr \= \[5,10,15\];

Wrong

arr\[2\]

to get the last element.

Why?

Tomorrow the array may become

\[5,10,15,20,25\]

Now index `2` is no longer the last element.

Correct

arr\[arr.length \- 1\]

Always write code that works for arrays of any size.

---

# **Mistake 8 — Memorizing Loops Without Understanding**

Many beginners memorize

for (let i \= 0; i \< arr.length; i++)

But if asked

> "Why `<` instead of `<=`?"

they can't explain.

Don't memorize.

Understand.

You should know the purpose of every part:

* Why start at `0`?  
* Why stop at `arr.length`?  
* Why increment `i`?

---

# **Mistake 9 — Ignoring Dry Runs**

Some beginners immediately run the code.

They never trace it manually.

Result:

When the output is wrong,

they don't know **where** it went wrong.

A 30-second dry run often finds bugs faster than repeatedly executing the code.

---

# **Mistake 10 — Focusing on Syntax Instead of the Pattern**

When beginners see

for (...)

they think

> "This is a for-loop problem."

That's the wrong mindset.

Think:

> "This is a traversal problem."

The `for` loop is only one way to implement traversal.

The pattern is more important than the syntax.

---

# **Summary Table**

| Mistake | Correct Thinking |
| ----- | ----- |
| Confusing `i` and `arr[i]` | `i` \= index, `arr[i]` \= value |
| Starting at `1` | Start at `0` (unless required otherwise) |
| Using `<=` | Use `< arr.length` |
| Forgetting `i++` | Always move to the next element |
| Thinking about the whole array | Focus on one current element |
| Stopping early | Ensure the last element is visited |
| Hardcoding indexes | Use `arr.length` when appropriate |
| Memorizing loops | Understand each part |
| Skipping dry runs | Trace code manually first |
| Thinking about syntax | Think about the traversal pattern |

---

# **Debugging Checklist**

Whenever your traversal doesn't work, ask these questions:

✅ Did I start at the correct index?

✅ Is my stopping condition correct?

✅ Am I moving to the next element?

✅ Am I processing the current element?

✅ Did I visit every required element exactly once?

✅ Am I confusing index and value?

✅ Did I dry run the algorithm?

This checklist alone will solve a large percentage of beginner traversal bugs.

---

# **Interview Tip**

Many interview bugs come from **off-by-one errors**.

Before submitting your solution, always test it mentally with:

* An empty array `[]`  
* A single-element array `[5]`  
* A two-element array `[5, 10]`

If your traversal works correctly for these small cases, it's much more likely to work for larger inputs.

---

# **Quick Concept Check**

Answer without writing code.

### **Q1**

Which variable stores the **index** during traversal?

---

### **Q2**

Which expression gives the **current element**?

---

### **Q3**

Why is `i <= arr.length` usually incorrect?

---

### **Q4**

What happens if you forget `i++`?

---

### **Q5**

Which is more important in DSA?

A. Memorizing the loop syntax.

B. Understanding the traversal pattern.

---

# **Progress Update**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 2 — Traversal

✅ Chapter 1 → What is Traversal?  
✅ Chapter 2 → Why Do We Need Traversal?  
✅ Chapter 3 → Types of Traversal  
✅ Chapter 4 → Traversal Mental Model  
✅ Chapter 5 → Traversal in JavaScript  
✅ Chapter 6 → Dry Run  
🟩 Chapter 7 → Common Beginner Mistakes (Completed)

Next:  
🔵 Chapter 8 → Interview Recognition

At the end of this chapter, you should notice that almost all the mistakes are **thinking mistakes**, not JavaScript mistakes. That's intentional—DSA interviews evaluate how you reason about problems, and the code is simply the language you use to express that reasoning.

