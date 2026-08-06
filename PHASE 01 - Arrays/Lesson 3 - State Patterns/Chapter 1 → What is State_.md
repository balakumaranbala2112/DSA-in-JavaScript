Excellent. We're now moving to what I consider the **first real DSA pattern**.

Traversal tells us **how to move** through an array.

State Pattern tells us **what to remember while moving**.

Without the State Pattern, many interview problems become impossible to solve efficiently.

---

# **DSA in JavaScript (Interview-Focused)**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

# **🟩 Lesson 3 — State Pattern**

---

## **📍 Where We Are**

DSA in JavaScript  
│  
└── Phase 1 — Arrays  
      │  
      └── Module 1 — Foundations  
            │  
            ├── ✅ Lesson 1 — Array Basics  
            ├── ✅ Lesson 2 — Traversal  
            ├── 🟩 Lesson 3 — State Pattern  
            ├── ⬜ Lesson 4 — Simulation  
            ├── ⬜ Lesson 5 — Frequency Counting  
            ├── ⬜ Lesson 6 — Pattern Recognition  
            ├── ⬜ Lesson 7 — Revision  
            └── ⬜ Lesson 8 — Assessment

---

# **Lesson 3 Structure (Locked)**

Lesson 3 — State Pattern

Chapter 1 → What is State?  
Chapter 2 → Why State Exists  
Chapter 3 → Types of State  
Chapter 4 → Maintaining State  
Chapter 5 → State in JavaScript  
Chapter 6 → Dry Run  
Chapter 7 → Common Beginner Mistakes  
Chapter 8 → Interview Recognition

Guided Examples  
Practice Problems  
Lesson Quiz  
Revision Notes

This structure is fixed.

---

# **🔵 Chapter 1 → What is State?**

---

# **🎯 Goal**

After this chapter, you should understand:

* What "state" means in DSA.  
* Why almost every interview problem uses state.  
* Why variables like `sum`, `count`, and `max` are called **state variables**.

---

# **First, Forget Programming**

Imagine you're walking from your house to college.

While walking, I ask you:

> **How many red cars have you seen so far?**

At the beginning:

Red Cars Seen \= 0

You walk.

You see a red car.

Red Cars Seen \= 1

Walk again.

Another red car.

Red Cars Seen \= 2

Walk again.

No red car.

Red Cars Seen \= 2

Notice something.

The number changes **while you move**.

That changing information is called **state**.

---

# **Another Real-Life Example**

Suppose you're playing a game.

❤️❤️❤️  
Lives \= 3

You lose one life.

❤️❤️

Lives \= 2

Later you gain one.

❤️❤️❤️

Lives \= 3

The number isn't fixed.

It changes during the game.

That's state.

---

# **Definition**

> **State is any information that changes while solving a problem and must be remembered for the next step.**

Read that again.

There are two important parts:

1. It **changes**.  
2. You **remember** it.

If both are true, it's state.

---

# **Arrays Example**

Suppose

\[10,20,30,40\]

Question:

Find the sum.

Initially

sum \= 0

Visit `10`

sum \= 10

Visit `20`

sum \= 30

Visit `30`

sum \= 60

Visit `40`

sum \= 100

What changed?

sum

What did we remember?

sum

Therefore,

`sum` is a **state variable**.

---

# **Another Example**

Find the maximum.

Array

\[12,5,18,9\]

Initially

max \= 12

After visiting `5`

max \= 12

After visiting `18`

max \= 18

After visiting `9`

max \= 18

Again,

`max` keeps changing.

It remembers the best answer so far.

So `max` is also state.

---

# **Another Example**

Count even numbers.

Initially

count \= 0

Visit `8`

count \= 1

Visit `5`

count \= 1

Visit `12`

count \= 2

Again,

the value changes.

We keep remembering it.

So `count` is state.

---

# **State is Memory**

Think of state as your notebook.

Imagine solving a problem without remembering anything.

Suppose I ask:

> Add these numbers.

10

20

30

If you forget the previous total every time,

you'll never reach the correct answer.

State is simply your algorithm's memory.

---

# **Traversal vs State**

This is one of the most important distinctions in DSA.

| Traversal | State |
| ----- | ----- |
| Moves through the array | Remembers information |
| Visits elements | Stores information |
| Answers "Where am I?" | Answers "What do I know so far?" |

Think of a delivery driver.

Traversal:

> Which house am I at?

State:

> How many packages have I delivered so far?

Both work together.

---

# **Visual Model**

Array

\[8\] \[3\] \[15\] \[6\]

         ↑  
     Current Element

While moving through the array,

you carry a backpack.

Inside the backpack is your state.

Array

8 → 3 → 15 → 6

      🎒

State

Depending on the problem, the backpack might contain:

sum

or

count

or

max

or

min

or

found

The backpack travels with you through the entire array.

---

# **Why Is State So Important?**

Without state, traversal is useless.

Imagine traversing an array.

10

↓

20

↓

30

↓

40

If you don't remember anything,

what happens after reaching the end?

Nothing.

You've visited every element but learned nothing.

Traversal gives you access to the elements.

State lets you build the answer.

---

# **Interview Insight**

Most array interview problems are actually:

Traversal

\+

State

Examples:

| Problem | Traversal | State |
| ----- | ----- | ----- |
| Count Even Numbers | ✅ | `count` |
| Sum | ✅ | `sum` |
| Maximum | ✅ | `max` |
| Minimum | ✅ | `min` |
| Search | ✅ | `found` |

Notice something.

The traversal hardly changes.

The state changes depending on the question.

---

# **Common Misconception**

Many beginners think:

> "State means global variables."

No.

In DSA,

**state** simply means:

> The information your algorithm must remember while solving the problem.

Usually it's just a local variable like:

let sum \= 0;

or

let max \= arr\[0\];

---

# **Quick Concept Check**

### **Q1**

What is state in DSA?

---

### **Q2**

Does state stay the same throughout the algorithm?

---

### **Q3**

In the "find maximum" problem, what is the state variable?

---

### **Q4**

Can traversal alone solve "find the sum" without remembering anything?

---

### **Q5**

Complete the sentence:

Traversal tells us \_\_\_\_\_\_\_\_.

State tells us \_\_\_\_\_\_\_\_.

---

# **Chapter 1 Summary**

* State is **information that changes while solving a problem**.  
* State must be **remembered** between iterations.  
* Traversal moves through the array.  
* State builds the answer.  
* Most interview problems combine **Traversal \+ State**.

---

# **Progress Update**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 3 — State Pattern

🟩 Chapter 1 → What is State?  
⬜ Chapter 2 → Why State Exists  
⬜ Chapter 3 → Types of State  
⬜ Chapter 4 → Maintaining State  
⬜ Chapter 5 → State in JavaScript  
⬜ Chapter 6 → Dry Run  
⬜ Chapter 7 → Common Beginner Mistakes  
⬜ Chapter 8 → Interview Recognition

---

## **📌 Connection to the Previous Lesson**

Lesson 2 taught you:

Traversal

Lesson 3 begins with:

Traversal  
        \+  
      State

This is the foundation of almost every array algorithm you'll encounter in interviews. Once you understand how to carry and update state during traversal, you'll be ready to tackle patterns like Frequency Counting, Sliding Window, Prefix Sum, and Kadane's Algorithm.

