# **DSA in JavaScript (Interview-Focused)**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **🔵 Chapter 4 — Traversal Mental Model**

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
                  🔵 Chapter 4 → Traversal Mental Model  
                  ⬜ Chapter 5 → Traversal in JavaScript  
                  ⬜ Chapter 6 → Dry Run  
                  ⬜ Chapter 7 → Common Beginner Mistakes  
                  ⬜ Chapter 8 → Interview Recognition

---

# **🎯 Goal**

After this chapter, you should be able to answer:

* What should I think while traversing?  
* What happens at each element?  
* How do experienced programmers mentally process an array?  
* Why do beginners get confused inside loops?

---

# **First, Forget Code**

Don't think about JavaScript.

Don't think about `for` loops.

Think only about **what your brain is doing**.

---

# **Imagine You're Walking Through a Street**

Suppose a street has five houses.

🏠 🏠 🏠 🏠 🏠

You are asked:

> Count how many houses are painted blue.

How do you do it?

You don't magically know the answer.

You walk.

House 1

↓

House 2

↓

House 3

↓

House 4

↓

House 5

At every house you ask one question.

> Is this house blue?

If yes,

increase your count.

Then move to the next house.

Notice something.

Your brain repeats the **same process** at every house.

That's the mental model.

---

# **Arrays Work Exactly the Same Way**

Suppose

\[8,3,15,6,11\]

Imagine the elements are standing in a line.

8

↓

3

↓

15

↓

6

↓

11

Traversal means

You visit one element.

Think.

Do something.

Move.

Repeat.

---

# **The Four-Step Mental Cycle**

Every traversal follows this cycle.

Current Element

↓

Observe

↓

Process

↓

Move Forward

↓

Repeat

This is the mental model you should remember for every traversal problem.

Let's understand each step.

---

# **Step 1 — Current Element**

At any moment, you are looking at **exactly one element**.

Example

\[8,3,15,6,11\]

Right now

you're only looking at

8

Nothing else matters.

Not `3`.

Not `15`.

Only `8`.

---

# **Step 2 — Observe**

Ask yourself:

> What do I know about this element?

Examples:

* Is it even?  
* Is it odd?  
* Is it greater than the current maximum?  
* Is it negative?  
* Is it equal to the target?

You're simply examining the current element.

---

# **Step 3 — Process**

Now decide what to do.

Examples:

* Add it to the sum.  
* Ignore it.  
* Count it.  
* Replace it.  
* Compare it.  
* Save it.

The action depends on the problem.

---

# **Step 4 — Move Forward**

After processing,

you leave this element forever.

Move to the next one.

8

↓

3

↓

15

↓

6

↓

11

Then repeat the exact same cycle.

---

# **The Golden Rule**

Never think about the whole array at once.

Think only about

> **The current element.**

Professional programmers don't process five elements simultaneously.

They process

one

then one

then one

until the array ends.

---

# **Real-Life Analogy**

Imagine you're checking exam papers.

Paper 1

↓

Paper 2

↓

Paper 3

↓

Paper 4

You don't grade all papers at once.

You grade one paper.

Finish.

Take the next.

Finish.

Repeat.

Traversal is identical.

---

# **Another Analogy**

Imagine you're a cashier.

Customers arrive.

Customer 1

↓

Customer 2

↓

Customer 3

↓

Customer 4

For every customer you perform the same routine.

1. Read the bill.  
2. Calculate the amount.  
3. Collect payment.  
4. Serve the next customer.

You never process all customers simultaneously.

---

# **Visual Mental Model**

Suppose

\[4,7,2,9\]

Imagine a spotlight.

\[4\] 7 2 9

The spotlight means:

This is the only element you're thinking about now.

Next.

4 \[7\] 2 9

Then.

4 7 \[2\] 9

Then.

4 7 2 \[9\]

The spotlight keeps moving.

Your thinking moves with it.

---

# **Why Beginners Get Confused**

Suppose they're solving

> Find the maximum.

Instead of thinking

Current element \= 8

↓

Compare

they think

8

3

15

6

11

all at once.

This overwhelms the brain.

Instead,

focus only on

the highlighted element.

---

# **The Traversal Formula**

Whenever you see an array problem, think like this:

Start

↓

Look at current element

↓

Ask:  
"What should I do with it?"

↓

Do that action

↓

Move to next element

↓

Repeat

↓

End

Notice something.

This formula works for almost every array problem.

Only the

> "What should I do?"

part changes.

---

# **Examples**

### **Find Maximum**

Current element

↓

Compare

↓

Move

---

### **Count Even Numbers**

Current element

↓

Check if even

↓

Increase count if needed

↓

Move

---

### **Sum**

Current element

↓

Add to total

↓

Move

---

### **Search**

Current element

↓

Compare with target

↓

Move

Same traversal.

Different processing.

---

# **Connection to Lesson 3**

This chapter naturally leads to the next lesson.

You now know **how** to move through an array.

But one question remains:

> While moving, **what information should I remember?**

That's exactly what **Lesson 3 — State Pattern** will answer.

---

# **Common Mistake**

Many beginners think:

> "Traversal means writing a `for` loop."

No.

The `for` loop is just JavaScript syntax.

Traversal is the **thinking process**.

You could traverse using:

* `for`  
* `while`  
* `for...of`

The mental model stays the same.

---

# **Quick Concept Check**

Imagine the array:

\[10,25,8\]

### **Q1**

While traversing, should you think about all three elements at once?

---

### **Q2**

After processing `10`, what should you do next?

---

### **Q3**

Which step comes immediately after **Observe**?

---

### **Q4**

True or False:

> Traversal means focusing on one current element at a time.

---

### **Q5**

Fill in the cycle:

Current Element

↓

\_\_\_\_\_\_\_\_

↓

Process

↓

Move Forward

---

# **Progress Update**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 2 — Traversal

✅ Chapter 1 → What is Traversal?  
✅ Chapter 2 → Why Do We Need Traversal?  
✅ Chapter 3 → Types of Traversal  
🟩 Chapter 4 → Traversal Mental Model (Completed)

Next:  
🔵 Chapter 5 → Traversal in JavaScript

---

## **🧠 Mental Model Cheat Code**

From today onward, before writing any code for an array problem, train yourself to ask these four questions:

1. **What is my current element?**  
2. **What do I need to check about it?**  
3. **What action should I perform?**  
4. **Can I move to the next element now?**

If this becomes automatic, you'll find that many interview problems become much easier because you're thinking like the algorithm instead of just writing loops.