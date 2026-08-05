# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **🔵 Chapter 3 — Types of Traversal**

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
                  🔵 Chapter 3 → Types of Traversal  
                  ⬜ Chapter 4 → Traversal Mental Model  
                  ⬜ Chapter 5 → Traversal in JavaScript  
                  ⬜ Chapter 6 → Dry Run  
                  ⬜ Chapter 7 → Common Beginner Mistakes  
                  ⬜ Chapter 8 → Interview Recognition

---

# **🎯 Goal**

After this chapter, you should be able to answer:

* What are the different ways to traverse an array?  
* When do we use each type?  
* Which traversal types are common in interviews?  
* Which ones will we study later?

---

# **What Does "Type of Traversal" Mean?**

Traversal means:

> Visit the elements of an array.

But it **doesn't specify the order**.

Think of a city with many streets.

You can visit every house by:

* Walking from left to right.  
* Walking from right to left.  
* Starting from both ends.  
* Moving in a circular path.

You still visit the houses.

Only the **path changes**.

Traversal works the same way.

---

# **Type 1 — Left to Right Traversal**

This is the **most common traversal**.

You start at the first element and move toward the last element.

Example:

\[10, 20, 30, 40, 50\]

Traversal:

10

↓

20

↓

30

↓

40

↓

50

You visit every element exactly once.

### **Used For**

* Sum of array  
* Maximum  
* Minimum  
* Counting  
* Frequency counting  
* Running sum  
* Most interview problems

**This is the default traversal.**

Whenever someone says:

> "Traverse the array."

Assume **left to right** unless stated otherwise.

---

# **Type 2 — Right to Left Traversal**

Instead of starting from the beginning...

Start from the end.

Example:

\[10, 20, 30, 40, 50\]

Traversal:

50

↓

40

↓

30

↓

20

↓

10

---

### **When Is It Useful?**

Examples:

* Reverse printing  
* Reverse copying  
* Some suffix-based algorithms  
* Certain dynamic programming problems

You'll use this much less often than left-to-right traversal.

---

# **Type 3 — Two-End Traversal**

Imagine two people.

One starts here.

10

Another starts here.

50

Visual:

10   20   30   40   50  
 ↑                   ↑  
Left              Right

Both move toward the center.

10   20   30   40   50  
      ↑         ↑

Eventually they meet.

This traversal becomes the **Two Pointers Pattern**, which is Module 2\.

Examples:

* Check palindrome  
* Pair sum  
* Reverse array  
* Remove duplicates (sorted)

---

# **Type 4 — Circular Traversal**

Suppose the array is:

\[1,2,3,4\]

Instead of stopping at the end...

You continue from the beginning.

Visual:

1 → 2 → 3 → 4  
↑           ↓  
└───────────┘

The array behaves like a circle.

Used in:

* Circular queues  
* Circular arrays  
* Next greater element (circular)  
* Rotating arrays

This is an advanced traversal.

Don't worry about it now.

---

# **Type 5 — Matrix Traversal**

Until now we've worked with a one-dimensional array.

Example:

\[1,2,3,4\]

A matrix is two-dimensional.

1 2 3

4 5 6

7 8 9

Now traversal becomes more interesting.

You can traverse:

* Row by row  
* Column by column  
* Spiral  
* Diagonal  
* Zigzag

We'll study this in **Module 8 — Matrix**.

---

# **Comparison**

| Traversal Type | Direction | Interview Frequency |
| ----- | ----- | ----- |
| Left → Right | Beginning to end | ⭐⭐⭐⭐⭐ Very Common |
| Right → Left | End to beginning | ⭐⭐⭐ Common |
| Two Ends | Both ends toward center | ⭐⭐⭐⭐⭐ Very Common (later as Two Pointers) |
| Circular | Wrap around | ⭐⭐ Occasionally |
| Matrix | 2D directions | ⭐⭐⭐⭐ Common |

---

# **Which Types Should You Learn Now?**

Right now, only focus on:

✅ Left → Right Traversal

Everything else will be taught later when it naturally appears.

For example:

| Traversal Type | Learned In |
| ----- | ----- |
| Left → Right | Lesson 2 |
| Two Ends | Module 2 (Two Pointers) |
| Circular | Advanced Array Problems |
| Matrix | Module 8 |
| Right → Left | As needed |

This prevents information overload.

---

# **Real Interview Examples**

### **Left → Right**

Question:

> Find the sum of all numbers.

Traversal:

1

↓

2

↓

3

↓

4

---

### **Right → Left**

Question:

> Print the array in reverse.

Traversal:

4

↓

3

↓

2

↓

1

---

### **Two Ends**

Question:

> Is this string a palindrome?

Traversal:

r a c e c a r

↑           ↑

Compare both ends.

---

### **Matrix**

Question:

> Print all elements row by row.

Traversal:

1 → 2 → 3

↓

4 → 5 → 6

↓

7 → 8 → 9

---

# **Common Beginner Mistakes**

### **Mistake 1**

Thinking traversal always means left to right.

It usually does for arrays, but not always.

---

### **Mistake 2**

Trying to learn every traversal type at once.

Master one.

Then build on it.

---

### **Mistake 3**

Confusing **Two-End Traversal** with **Two Pointers**.

Two-End Traversal is simply a way of moving.

The **Two Pointers Pattern** includes additional logic and techniques.

We'll study that in Module 2\.

---

# **Connection to Future Lessons**

This chapter shows that traversal is **more than a single `for` loop**.

Here's how it connects to future modules:

Left → Right  
        │  
        ├── State Pattern  
        ├── Simulation  
        ├── Frequency Counting  
        ├── Sliding Window  
        ├── Prefix Sum  
        └── Kadane

Two Ends  
        │  
        └── Module 2 → Two Pointers

Matrix  
        │  
        └── Module 8 → Matrix Problems

Circular  
        │  
        └── Advanced Array Problems

---

# **Quick Concept Check**

Array:

\[5, 10, 15, 20\]

### **Q1**

Which traversal starts with `5`?

---

### **Q2**

Which traversal starts with `20`?

---

### **Q3**

Which traversal uses both the first and last element at the same time?

---

### **Q4**

True or False:

> Matrix traversal is used for one-dimensional arrays.

---

### **Q5**

Which traversal type should you master first before learning other patterns?

---

# **Progress Update**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 2 — Traversal

✅ Chapter 1 → What is Traversal?  
✅ Chapter 2 → Why Do We Need Traversal?  
🟩 Chapter 3 → Types of Traversal (Completed)

Next:  
🔵 Chapter 4 → Traversal Mental Model

**One note:** Although we've introduced all traversal types, for the rest of Module 1 we'll use **only Left → Right Traversal**. The others will be revisited in their dedicated modules, so you don't need to practice them yet.

