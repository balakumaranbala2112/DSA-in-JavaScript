# **DSA in JavaScript (Interview-Focused)**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **🔵 Chapter 2 — Why Do We Need Traversal?**

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
                  🔵 Chapter 2 → Why Do We Need Traversal?  
                  ⬜ Chapter 3 → Types of Traversal  
                  ⬜ Chapter 4 → Traversal Mental Model  
                  ⬜ Chapter 5 → Traversal in JavaScript  
                  ⬜ Chapter 6 → Dry Run  
                  ⬜ Chapter 7 → Common Beginner Mistakes  
                  ⬜ Chapter 8 → Interview Recognition

---

# **🎯 Goal**

After this chapter, you should understand:

* Why traversal exists.  
* Why almost every array problem starts with traversal.  
* Why traversal is a **process**, not a complete solution.  
* Why every later array pattern still depends on traversal.

---

# **🤔 Imagine This Situation**

Suppose I give you an array.

const marks \= \[82, 91, 76, 88, 95\];

Now I ask you:

> **What is the highest mark?**

Can you answer immediately?

No.

Why?

Because you don't know which number is the largest until you've looked at **all** the numbers.

---

# **Example 2**

Suppose I ask:

> **How many students scored above 80?**

Again,

Can you answer without looking at every mark?

No.

You must inspect:

82 ✓

91 ✓

76 ✗

88 ✓

95 ✓

Only after checking every element can you answer.

---

# **Example 3**

Suppose I ask:

> **Is there a student who scored exactly 76?**

Again,

Can you look at only the first element?

No.

Can you look only at the last element?

No.

You must keep checking until you either:

* Find `76`, or  
* Reach the end of the array.

---

# **What's Common in All These Problems?**

Let's compare them.

| Problem | What do you have to do first? |
| ----- | ----- |
| Find maximum | Look at every element |
| Find minimum | Look at every element |
| Count even numbers | Look at every element |
| Find sum | Look at every element |
| Search for a value | Look at every element (unless you already know its position) |

Notice something?

Different problems...

Same first step.

That first step is:

> **Traversal**

---

# **Why Can't We Skip Elements?**

Suppose the array is:

\[12, 45, 8, 99, 23\]

Question:

Find the largest number.

Now imagine you skip the fourth element.

You inspect:

12

↓

45

↓

8

↓

23

You never looked at:

99

You answer:

45

Wrong.

Why?

Because you skipped one element.

**Skipping even one element can change the answer.**

---

# **Why Can't We Visit the Same Element Again and Again?**

Suppose you do this:

12

↓

45

↓

45

↓

45

↓

8

↓

23

Does visiting `45` three times help?

No.

You already know it's `45`.

Reading it again doesn't give you any new information.

You're wasting time.

---

# **The Golden Rule of Traversal**

A good traversal tries to do two things:

1. **Don't skip any required element.**  
2. **Don't visit the same element unnecessarily.**

That's why many traversal algorithms aim for:

Visit every element exactly once.

---

# **Real-Life Analogy**

Imagine you're checking attendance in a classroom.

Students:

Rahul

Priya

John

Sara

David

To know how many students are present:

You must check:

Rahul ✓

↓

Priya ✓

↓

John ✓

↓

Sara ✓

↓

David ✓

If you skip Sara, your count may be wrong.

If you check Rahul five times, your count is still wrong.

The correct approach is:

> **Visit each student exactly once.**

That's traversal.

---

# **Another Real-Life Example**

Imagine you're counting the number of red apples in a basket.

Basket:

🍎 🍏 🍎 🍌 🍎 🍊

Can you count the apples by looking only at the first fruit?

No.

Can you skip the last fruit?

No.

You inspect every fruit once.

Traversal is simply that inspection process.

---

# **Traversal is NOT the Solution**

This is where many beginners get confused.

Suppose the problem is:

> Find the maximum number.

Traversal **does not** find the maximum.

Traversal only gives you this sequence:

8

↓

3

↓

15

↓

6

↓

11

While each number comes to you, **you** decide what to do.

For example:

* Compare it.  
* Count it.  
* Add it.  
* Ignore it.

Traversal only says:

> "Here is the next element."

It does **not** decide how to use it.

---

# **A Simple Formula**

Think of solving array problems like this:

Traversal

↓

Visit current element

↓

Process current element

↓

Move to next element

↓

Repeat until end

↓

Answer

Traversal is the road.

Your algorithm is the vehicle traveling on that road.

---

# **Why Every Future Pattern Uses Traversal**

You might wonder:

> "If we're going to learn Sliding Window, Two Pointers, Prefix Sum, why spend so much time on Traversal?"

Because those patterns are **built on top of traversal**.

For example:

### **Two Pointers**

You still move through the array.

---

### **Sliding Window**

You still move through the array.

---

### **Prefix Sum**

You still visit every element.

---

### **Kadane's Algorithm**

You still visit every element.

---

### **Frequency Counting**

You still visit every element.

Traversal is the **foundation**.

The only thing that changes is **what you do while visiting each element**.

---

# **Interview Perspective**

Suppose an interviewer asks:

> Find the sum of all numbers.

Don't immediately think:

> "I need a `for` loop."

Instead think like this:

Step 1  
I need to visit every element.

↓

Step 2  
While visiting, I'll keep adding each value.

↓

Step 3  
Return the final sum.

This is how experienced engineers think.

They identify the **pattern first**, then write the code.

---

# **Chapter 2 Summary**

Traversal exists because many problems require inspecting every element before a correct answer can be produced.

It is:

* A process.  
* A foundation.  
* Not a complete algorithm by itself.

Almost every array pattern you'll learn later starts with traversal.

---

# **Quick Concept Check (No Code)**

Array:

\[18, 7, 42, 5, 30\]

### **Q1**

To find the maximum, can you skip the value `42`?

---

### **Q2**

Does reading the value `18` three times help you solve the problem?

---

### **Q3**

What is the goal of traversal?

A. Visit every required element.

B. Visit random elements.

C. Visit only the largest element.

---

### **Q4**

True or False:

> Traversal itself finds the maximum element.

---

### **Q5**

Complete the sentence:

> Traversal is the \_\_\_\_\_\_\_\_.  
> The algorithm decides what to do with each element.

(Hint: We used a road analogy.)

---

# **Progress Update**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 2 — Traversal

✅ Chapter 1 → What is Traversal?  
🟩 Chapter 2 → Why Do We Need Traversal? (Completed)

Next:  
🔵 Chapter 3 → Types of Traversal

One small improvement to the course: at the end of every chapter, I'll include a **"Connection to Future Lessons"** section that explicitly explains how the current concept will be used in Two Pointers, Sliding Window, Prefix Sum, Trees, or Graphs. This will help you see how each lesson fits into the larger DSA roadmap instead of feeling like isolated topics.

