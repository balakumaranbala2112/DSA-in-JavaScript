Excellent. These are the final three theory chapters of **Lesson 3 – State Pattern**. After these, we'll move to **Guided Examples**, where you'll start applying different state types to real problems.

---

# **DSA in JavaScript (Interview-Focused)**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 3 — State Pattern**

---

# **🔵 Chapter 6 → Dry Run**

---

## **🎯 Goal**

After this chapter, you should be able to trace how a state variable changes during each iteration.

Remember:

In Lesson 2, we dry-ran **traversal**.

Now we're dry-running **state**.

The important question is no longer:

> Which element am I visiting?

Now it is:

> **How is my state changing?**

---

# **Example 1 — Counter State**

Array

\[4,7,8,10\]

Goal

> Count even numbers.

Initially

count \= 0

---

### **Iteration 1**

Current element

4

Question

Is it even?

Yes.

Update

count \= 1

---

### **Iteration 2**

Current element

7

Even?

No.

State

count \= 1

Notice something.

The state **didn't change**.

---

### **Iteration 3**

Current element

8

Update

count \= 2

---

### **Iteration 4**

Current element

10

Update

count \= 3

Final Answer

3

---

# **Dry Run Table**

| i | arr\[i\] | Condition | count |
| ----- | ----- | ----- | ----- |
| \- | \- | Start | 0 |
| 0 | 4 | Even ✅ | 1 |
| 1 | 7 | Even ❌ | 1 |
| 2 | 8 | Even ✅ | 2 |
| 3 | 10 | Even ✅ | 3 |

---

# **Example 2 — Maximum State**

Array

\[12,5,18,9\]

Initially

max \= 12

| i | arr\[i\] | Comparison | max |
| ----- | ----- | ----- | ----- |
| \- | 12 | Start | 12 |
| 1 | 5 | 5 \> 12 ❌ | 12 |
| 2 | 18 | 18 \> 12 ✅ | 18 |
| 3 | 9 | 9 \> 18 ❌ | 18 |

Notice something.

The state changes only when the condition is true.

---

# **Example 3 — Sum State**

Array

\[2,4,6\]

Initially

sum \= 0

| i | arr\[i\] | sum |
| ----- | ----- | ----- |
| \- | \- | 0 |
| 0 | 2 | 2 |
| 1 | 4 | 6 |
| 2 | 6 | 12 |

Unlike `count` or `max`, the sum changes **every iteration**.

---

# **Dry Run Formula**

Whenever you dry-run a state problem, fill this table.

| Current Element | Previous State | Update? | New State |
| :---: | :---: | :---: | :---: |

This is how experienced engineers debug algorithms.

---

# **Common Rule**

Always track **two things**:

Current Element

\+

Current State

Ignoring either one usually causes bugs.

---

# **🔵 Chapter 7 → Common Beginner Mistakes**

---

## **🎯 Goal**

Avoid the mistakes that most beginners make while maintaining state.

---

# **Mistake 1**

## **Choosing the Wrong State**

Problem

> Count even numbers

Wrong

let sum \= 0;

Correct

let count \= 0;

Always ask:

> **What information does the problem want?**

---

# **Mistake 2**

## **Wrong Initialization**

Example

let max \= 0;

Array

\[-5,-8,-2\]

Answer becomes

0

Wrong.

Correct

let max \= arr\[0\];

---

# **Mistake 3**

## **Updating State Every Time**

Wrong

max \= arr\[i\];

Now the answer becomes the last element.

Correct

if (arr\[i\] \> max)

Update only when needed.

---

# **Mistake 4**

## **Never Updating State**

Example

let sum \= 0;

Loop

for (...) {

}

Final Answer

0

You created the state but never changed it.

---

# **Mistake 5**

## **Using Too Many State Variables**

Suppose the problem asks

> Find maximum.

Need

let max \= arr\[0\];

Not

let max \= arr\[0\];  
let sum \= 0;  
let count \= 0;  
let found \= false;

Only remember what is necessary.

---

# **Mistake 6**

## **Forgetting State Represents the Answer**

At the end of traversal,

the state itself is usually the answer.

Example

let max \= ...

Traversal finishes.

Answer

return max;

Don't calculate something again after the loop if the state already contains the answer.

---

# **Mistake 7**

## **Confusing Traversal with State**

Remember

Traversal

Moves

State

Remembers

Different responsibilities.

---

# **Golden Checklist**

Before writing code ask:

✓ What pattern?

✓ What state?

✓ Initial value?

✓ When should it update?

✓ Final answer?

---

# **🔵 Chapter 8 → Interview Recognition**

---

## **🎯 Goal**

Recognize the required state within 10 seconds of reading an interview problem.

This is one of the biggest differences between beginners and experienced candidates.

---

# **Recognition Step 1**

Read the last sentence.

Example

> Return the **largest** element.

Keyword

Largest

State

Best Answer

---

# **Recognition Step 2**

Look for Question Words

---

## **"How many"**

Examples

How many even numbers?

How many negatives?

How many students passed?

Immediately think

Counter State

---

## **"Total"**

Examples

Total marks

Total salary

Total sum

Think

Accumulator State

---

## **"Largest"**

Examples

Largest

Maximum

Highest

Longest

Think

Best Answer State

---

## **"Smallest"**

Examples

Minimum

Smallest

Lowest

Again

Best Answer State

---

## **"Exists"**

Examples

Does 10 exist?

Is there any duplicate?

Contains target?

Think

Boolean State

---

## **"Where"**

Examples

Find the index

First occurrence

Last occurrence

Think

Position State

---

# **Recognition Table**

| Problem Statement | State |
| ----- | ----- |
| Count vowels | Counter |
| Find total marks | Accumulator |
| Find largest element | Best Answer |
| Find minimum | Best Answer |
| Search target | Boolean |
| Find index of maximum | Position |
| Average | Sum \+ Count |

---

# **Interview Flowchart**

Whenever you read a problem:

Read Problem

↓

Need Traversal?

↓

YES

↓

What should I remember?

↓

Choose State

↓

Initialize

↓

Update

↓

Answer

---

# **Mini Interview Test**

Identify only the state.

### **Q1**

Find the maximum salary.

---

### **Q2**

Count failed students.

---

### **Q3**

Find total revenue.

---

### **Q4**

Check whether 50 exists.

---

### **Q5**

Find the position of the smallest element.

---

### **Answers**

Q1 → Best Answer

Q2 → Counter

Q3 → Accumulator

Q4 → Boolean

Q5 → Position

---

# **Lesson 3 Theory Completed**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 3 — State Pattern

✅ Chapter 1 → What is State?  
✅ Chapter 2 → Why State Exists  
✅ Chapter 3 → Types of State  
✅ Chapter 4 → Maintaining State  
✅ Chapter 5 → State in JavaScript  
✅ Chapter 6 → Dry Run  
✅ Chapter 7 → Common Beginner Mistakes  
✅ Chapter 8 → Interview Recognition

🔵 Next → Guided Examples

---

# **🧠 The Biggest Mental Upgrade from Lesson 3**

After Lesson 2, your thinking was:

Traversal

↓

Visit Element

↓

Move Next

After Lesson 3, your thinking should become:

Traversal

↓

Visit Current Element

↓

What is my current state?

↓

Should I update it?

↓

Move to the next element

↓

Final State \= Answer

This is the thinking pattern behind a huge number of interview problems. Once it becomes automatic, later topics like Frequency Counting, Sliding Window, Prefix Sum, Kadane's Algorithm, and Dynamic Programming will feel like natural extensions rather than completely new ideas.

