# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

# **🔵 Lesson 2 — Traversal**

---

# **Current Progress**

Phase 1 — Arrays  
│  
└── Module 1 — Foundations  
      │  
      ├── ✅ Lesson 1 — Array Basics  
      │  
      ├── 🔵 Lesson 2 — Traversal (Current)  
      │  
      ├── ⬜ Lesson 3 — State Pattern  
      ├── ⬜ Lesson 4 — Simulation  
      ├── ⬜ Lesson 5 — Frequency Counting  
      ├── ⬜ Lesson 6 — Pattern Recognition  
      ├── ⬜ Lesson 7 — Revision  
      └── ⬜ Lesson 8 — Assessment

---

# **Lesson Objective**

After completing this lesson, you should be able to answer:

* What is traversal?  
* Why do we traverse an array?  
* When should we use traversal?  
* How do I recognize a traversal problem?  
* What information should I maintain while traversing?  
* Which interview questions are **pure traversal** questions?

If you understand these, you'll have learned your **first DSA pattern**.

---

# **Lesson Structure**

Lesson 2 — Traversal

Chapter 1 → What is Traversal?  
Chapter 2 → Why Do We Need Traversal?  
Chapter 3 → Types of Traversal  
Chapter 4 → Traversal Mental Model  
Chapter 5 → Traversal in JavaScript  
Chapter 6 → Dry Run  
Chapter 7 → Common Beginner Mistakes  
Chapter 8 → Interview Recognition  
Chapter 9 → Practice Problems  
Chapter 10 → Lesson Quiz  
Chapter 11 → Revision

We'll cover **one chapter at a time**.

---

# **Chapter 1 — What is Traversal?**

This is one of the most common words in DSA.

You'll hear people say:

* Traverse the array.  
* Traverse the tree.  
* Traverse the graph.

So let's understand the word itself.

---

## **What Does "Traverse" Mean?**

The English word **traverse** means:

> **To move through something from one end to the other while visiting every part.**

Notice the important words:

* Move through.  
* One end to the other.  
* Visit every part.

That's all traversal means.

---

## **Real-Life Example 1 — Reading a Book**

Imagine a book.

Page 1

↓

Page 2

↓

Page 3

↓

Page 4

↓

Page 5

If you read every page in order, you're **traversing the book**.

You don't jump randomly.

You don't skip pages.

You move page by page.

---

## **Real-Life Example 2 — Attendance**

Suppose a teacher has a row of students.

Rahul

↓

Priya

↓

John

↓

Sara

↓

David

The teacher calls attendance.

Rahul ✓

↓

Priya ✓

↓

John ✓

↓

Sara ✓

↓

David ✓

The teacher visited every student exactly once.

That is traversal.

---

## **Real-Life Example 3 — House Inspection**

Imagine an inspector checking rooms.

Room 1

↓

Room 2

↓

Room 3

↓

Room 4

The inspector doesn't inspect Room 1 ten times.

He doesn't skip Room 3\.

He visits each room once.

That's traversal.

---

# **Traversal in Arrays**

Suppose you have an array.

const arr \= \[12, 5, 30, 18, 9\];

Visual representation:

Index

0      1      2      3      4  
┌────┬────┬────┬────┬────┐  
│12  │ 5  │30  │18  │ 9  │  
└────┴────┴────┴────┴────┘

Traversal means:

Visit

12

↓

5

↓

30

↓

18

↓

9

One by one.

Until the end.

---

# **Important Observation**

Traversal is **not** a problem.

Traversal is **not** an algorithm.

Traversal is a **process**.

It simply means:

> "Visit every element."

What you do **while visiting** depends on the problem.

Examples:

* Sum the numbers.  
* Count even numbers.  
* Find the maximum.  
* Find the minimum.  
* Check if an element exists.  
* Replace negative values.

All of these begin with traversal.

---

# **What Happens During Traversal?**

Imagine the array is a conveyor belt.

\[4\] → \[8\] → \[2\] → \[7\] → \[5\]

Each element comes in front of you one at a time.

For each element, you ask:

> "Do I need to do something with this?"

Maybe:

* Add it to a sum.  
* Compare it with the maximum.  
* Count it.  
* Ignore it.

Then move to the next element.

Traversal is simply giving you the chance to process each element once.

---

# **Traversal Does NOT Mean Solving**

This is a common misunderstanding.

Suppose I ask:

> Find the largest number.

Traversal itself doesn't find the largest number.

Traversal only lets you **see every number**.

To actually solve the problem, you'll need another idea—maintaining the **current maximum**.

We'll learn that in **Lesson 3: State Pattern**.

This is why Lesson 2 comes **before** Lesson 3\.

---

# **One Pass**

You'll hear this phrase constantly.

What is **one pass**?

One complete traversal.

Example:

Array

\[10,20,30\]

One pass:

10

↓

20

↓

30

Done.

If you repeat it:

Pass 1

↓

Pass 2

You've traversed the array twice.

---

# **Why Is Traversal the First Pattern?**

Almost every array algorithm begins by traversing the array.

Examples:

* Two Pointers → still traverses.  
* Sliding Window → still traverses.  
* Prefix Sum → still traverses.  
* Kadane's Algorithm → still traverses.  
* Frequency Counting → still traverses.

Traversal is the foundation on which the other patterns are built.

---

# **Chapter 1 Summary**

A traversal means:

* Start from one end of the array.  
* Visit each element exactly once.  
* Process the current element.  
* Move to the next.  
* Stop after the last element.

---

# **Quick Check (No Code)**

Imagine the array:

\[25, 18, 40, 12\]

Without writing any JavaScript, answer these:

### **Q1**

If you traverse the array from left to right, which value do you visit first?

---

### **Q2**

Which value do you visit last?

---

### **Q3**

During one traversal, how many times do you visit the value `40`?

---

### **Q4**

If you perform **two traversals**, how many times is each element visited?

---

### **Q5**

True or False:

> Traversal itself finds the maximum element.

---

# **Progress Update**

Phase 1 → Arrays

Module 1 → Foundations

✅ Lesson 1 — Array Basics

Lesson 2 — Traversal

🟨 Chapter 1 — What is Traversal? (In Progress)

Next:  
⬜ Chapter 2 — Why Do We Need Traversal?

**Answer the five questions first.** Once they're correct, we'll move to **Chapter 2**, where you'll understand *why* almost every array interview problem starts with traversal.

