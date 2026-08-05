# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **🔵 Chapter 6 — Dry Run**

---

# **📍 Where We Are**

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
                  🔵 Chapter 6 → Dry Run  
                  ⬜ Chapter 7 → Common Beginner Mistakes  
                  ⬜ Chapter 8 → Interview Recognition

                  ⬜ Guided Examples  
                  ⬜ Practice Problems  
                  ⬜ Lesson Quiz  
                  ⬜ Revision Notes

---

# **🎯 Goal**

After this chapter, you should be able to:

* Understand what a dry run is.  
* Trace a traversal step by step.  
* Predict every value of `i`.  
* Predict every value of `arr[i]`.  
* Debug simple traversal code without executing it.

---

# **What is a Dry Run?**

A **Dry Run** means:

> **Executing the algorithm manually on paper (or in your mind) without running the code on a computer.**

Think of it as a rehearsal.

Just like actors rehearse before a play, programmers rehearse code before executing it.

---

# **Why Do Interviewers Care?**

Imagine you're in an interview.

The interviewer asks:

> "Can you tell me what this code outputs?"

If you need to run it in VS Code every time...

You'll struggle.

Good engineers can mentally execute simple code.

That's exactly what a dry run teaches.

---

# **Our Example**

const arr \= \[10, 20, 30\];

for (let i \= 0; i \< arr.length; i++) {  
    console.log(arr\[i\]);  
}

Don't think about `console.log()`.

Focus on what happens step by step.

---

# **Step 1 — Before the Loop Starts**

Array:

Index

0      1      2  
┌────┬────┬────┐  
│10  │20  │30  │  
└────┴────┴────┘

Current value of `i`?

Not created yet.

The loop hasn't started.

---

# **Step 2 — Initialization**

let i \= 0;

Now:

i \= 0

Question:

Which element are we pointing to?

Index

0

Value

10

---

# **Step 3 — Check Condition**

i \< arr.length

Current values:

i \= 0

arr.length \= 3

Question:

Is

0 \< 3

True?

Yes.

So the loop enters.

---

# **Step 4 — Execute the Loop Body**

console.log(arr\[i\]);

Current values:

i \= 0

Therefore

arr\[i\]

becomes

arr\[0\]

Output:

10

---

# **Step 5 — Increment**

i++

Now

i \= 1

Notice something.

The first iteration is completely finished.

---

# **Second Iteration**

Current values:

i \= 1

Condition:

1 \< 3

True.

Enter loop.

Current element:

arr\[1\]

Output:

20

Increment:

i \= 2

---

# **Third Iteration**

Current values:

i \= 2

Condition:

2 \< 3

True.

Current element:

arr\[2\]

Output:

30

Increment:

i \= 3

---

# **Fourth Check**

Now

i \= 3

Condition:

3 \< 3

False.

Loop stops.

---

# **Complete Dry Run Table**

This is how senior engineers usually trace loops.

| Iteration | `i` | Condition | `arr[i]` | Output |
| ----- | ----- | ----- | ----- | ----- |
| 1 | 0 | `0 < 3` ✅ | 10 | 10 |
| 2 | 1 | `1 < 3` ✅ | 20 | 20 |
| 3 | 2 | `2 < 3` ✅ | 30 | 30 |
| Stop | 3 | `3 < 3` ❌ | — | End |

---

# **The Mental Animation**

Instead of imagining the entire array, imagine a pointer moving.

Start

       ↓  
\[10\] 20 30

Move

10 \[20\] 30

Move

10 20 \[30\]

Move

10 20 30

Finished.

---

# **Another Example**

const arr \= \[5, 15, 25, 35\];

Mentally:

Iteration 1

i \= 0

↓

Current Element \= 5

Iteration 2

i \= 1

↓

Current Element \= 15

Iteration 3

i \= 2

↓

Current Element \= 25

Iteration 4

i \= 3

↓

Current Element \= 35

Stop.

---

# **The Dry Run Formula**

Whenever you see a loop, ask these questions **in order**:

### **Question 1**

What is the current value of `i`?

---

### **Question 2**

Is the loop condition true?

---

### **Question 3**

Which element am I currently visiting?

(`arr[i]`)

---

### **Question 4**

What action is performed?

(Currently, we're just printing.)

---

### **Question 5**

What happens to `i`?

(It increases.)

---

### **Question 6**

Repeat.

This six-step process works for almost every traversal problem.

---

# **Common Beginner Mistakes**

## **Mistake 1**

Skipping the condition check.

Many beginners jump directly to the next iteration.

Always check:

Is i \< arr.length?

---

## **Mistake 2**

Confusing

i

with

arr\[i\]

Remember:

i

↓

Position

arr\[i\]

↓

Value

---

## **Mistake 3**

Not updating `i`.

If `i` never changes,

the loop never progresses.

---

## **Mistake 4**

Trying to think about all iterations at once.

Don't.

Think only about the **current iteration**.

---

# **Interview Tip**

Whenever you're stuck,

draw this table.

| Iteration | `i` | `arr[i]` | Action |
| ----- | ----- | ----- | ----- |
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |

Many bugs become obvious immediately.

Experienced engineers do this regularly when debugging unfamiliar code.

---

# **Quick Dry Run Exercise**

Without running the code, predict the output.

const arr \= \[4, 8, 12\];

for (let i \= 0; i \< arr.length; i++) {  
    console.log(arr\[i\]);  
}

Answer these:

### **Q1**

What is `i` during the first iteration?

---

### **Q2**

What is `arr[i]` during the second iteration?

---

### **Q3**

What is the final value of `i` after the loop ends?

---

### **Q4**

How many times does the loop body execute?

---

### **Q5**

What is the complete output?

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
🟩 Chapter 6 → Dry Run (Completed)

Next:  
🔵 Chapter 7 → Common Beginner Mistakes

---

## **🔑 One Rule From Today On**

**Never write code before you can dry-run it.**

If you can't manually trace your algorithm for a small example, you don't fully understand it yet.

This rule will become even more valuable when we reach Sliding Window, Trees, Graphs, and Dynamic Programming, where a correct dry run often reveals mistakes before you ever execute the code.