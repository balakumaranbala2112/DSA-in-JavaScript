Excellent.

This is one of the **most important chapters** in the entire DSA roadmap.

Why?

Because from now on, whenever you read a problem, your brain should automatically ask:

> **"What state do I need?"**

Experienced engineers don't memorize solutions.

They recognize the **type of state** the problem requires.

---

# **DSA in JavaScript (Interview-Focused)**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 3 — State Pattern**

# **🔵 Chapter 3 → Types of State**

---

## **📍 Where We Are**

DSA in JavaScript  
│  
└── Phase 1 — Arrays  
      │  
      └── Module 1 — Foundations  
            │  
            └── Lesson 3 — State Pattern  
                  │  
                  ✅ Chapter 1 → What is State?  
                  ✅ Chapter 2 → Why State Exists  
                  🔵 Chapter 3 → Types of State  
                  ⬜ Chapter 4 → Maintaining State  
                  ⬜ Chapter 5 → State in JavaScript  
                  ⬜ Chapter 6 → Dry Run  
                  ⬜ Chapter 7 → Common Beginner Mistakes  
                  ⬜ Chapter 8 → Interview Recognition

---

# **🎯 Goal**

After this chapter, you should be able to:

* Identify different kinds of state.  
* Choose the correct state variable for a problem.  
* Understand that not every problem uses `count` or `sum`.  
* Recognize the state before writing code.

---

# **First Question**

Suppose I ask three different questions.

Question 1

> Count even numbers.

Question 2

> Find the largest number.

Question 3

> Find the total sum.

Do all three need the same state?

No.

Let's see why.

---

# **Type 1 — Counter State**

This is the simplest state.

Its job is to answer:

> **"How many?"**

Examples:

* Count even numbers  
* Count odd numbers  
* Count vowels  
* Count positive numbers  
* Count students who passed

---

## **Mental Model**

Imagine a tally counter.

Initially

Count \= 0

Every time the condition is true,

increase it.

0

↓

1

↓

2

↓

3

---

## **Real-Life Example**

You're counting people entering a classroom.

Student enters

↓

Count++

↓

Student enters

↓

Count++

↓

Student enters

↓

Count++

The state is simply the number of people seen so far.

---

## **Common Variable Names**

count  
totalCount  
evenCount  
oddCount

---

# **Type 2 — Accumulator State**

This answers:

> **"What is the running total?"**

Examples:

* Sum of numbers  
* Total marks  
* Total salary  
* Running cost  
* Total distance

---

## **Mental Model**

Think of a piggy bank.

Initially

Sum \= 0

Every element adds money.

0

↓

10

↓

30

↓

60

↓

100

---

## **Real-Life Example**

Shopping.

Milk

↓

Total \= 50

↓

Bread

↓

Total \= 90

↓

Rice

↓

Total \= 150

The state stores the running bill.

---

## **Common Variable Names**

sum  
total  
runningSum

---

# **Type 3 — Best Answer State**

This answers:

> **"What is the best value I've seen so far?"**

Examples:

* Maximum  
* Minimum  
* Highest marks  
* Lowest price  
* Largest number

---

## **Mental Model**

Imagine holding a trophy.

Every time someone better appears,

give them the trophy.

12

↓

18

↓

25

The trophy always belongs to the current best.

---

## **Real-Life Example**

Sports tournament.

Every new player is compared with the current champion.

If stronger,

the champion changes.

---

## **Common Variable Names**

max  
min  
best  
largest  
smallest

---

# **Type 4 — Boolean State**

This answers:

> **"Has something happened?"**

Only two possible values:

true

or

false

Examples:

* Does the array contain `10`?  
* Is there any negative number?  
* Has a duplicate been found?  
* Did we find the target?

---

## **Mental Model**

Imagine a light switch.

Initially

OFF

If the condition becomes true,

turn it on.

false

↓

true

Once it's true,

you've found your answer.

---

## **Real-Life Example**

Airport security.

Question:

> "Did we find a prohibited item?"

Initially

No

The moment one is found

Yes

---

## **Common Variable Names**

found  
exists  
isPresent  
hasDuplicate

---

# **Type 5 — Position State**

This answers:

> **"Where is something?"**

Instead of remembering a value,

we remember an **index**.

Examples:

* Index of maximum element  
* Index of minimum element  
* First occurrence  
* Last occurrence

---

## **Example**

\[8,15,6,20\]

Largest number

20

Where?

Index \= 3

Sometimes the interview wants the **position**, not the value.

---

## **Common Variable Names**

index  
maxIndex  
minIndex  
position

---

# **Type 6 — Multiple State Variables**

Some problems need more than one.

Example:

Find the average.

Need:

Sum

\+

Count

Example:

Find the index of the maximum.

Need:

Maximum

\+

Maximum Index

Later,

Sliding Window needs:

Left Pointer

\+

Right Pointer

\+

Current Sum

Multiple states working together.

---

# **Summary Table**

| State Type | Purpose | Example Variable |
| ----- | ----- | ----- |
| Counter | Count things | `count` |
| Accumulator | Running total | `sum` |
| Best Answer | Largest/Smallest | `max`, `min` |
| Boolean | Yes/No | `found` |
| Position | Store index | `maxIndex` |
| Multiple | Combination | `sum`, `count` |

---

# **How to Recognize the Correct State**

Read the problem.

Ask yourself:

---

## **Does it ask**

> **How many?**

Think

Counter

---

## **Does it ask**

> **Total?**

Think

Accumulator

---

## **Does it ask**

> **Largest or smallest?**

Think

Best Answer

---

## **Does it ask**

> **Does it exist?**

Think

Boolean

---

## **Does it ask**

> **Where is it?**

Think

Position

---

# **Recognition Flowchart**

Problem

↓

What is being asked?

↓

How many?  
      │  
      ▼  
 Counter

Total?  
      │  
      ▼  
Accumulator

Largest/Smallest?  
      │  
      ▼  
Best Answer

Exists?  
      │  
      ▼  
Boolean

Where?  
      │  
      ▼  
Position

---

# **Interview Examples**

| Interview Question | State |
| ----- | ----- |
| Count even numbers | Counter |
| Sum of array | Accumulator |
| Maximum element | Best Answer |
| Minimum element | Best Answer |
| Search target | Boolean |
| Find index of max | Position |
| Average | Sum \+ Count |

---

# **Common Beginner Mistakes**

### **Mistake 1**

Using `count` for every problem.

Different questions require different state.

---

### **Mistake 2**

Storing more information than necessary.

Need maximum?

Don't store every element.

Store only the current maximum.

---

### **Mistake 3**

Choosing the wrong initial value.

Examples:

let count \= 0;  
let sum \= 0;  
let max \= arr\[0\];  
let found \= false;

Each state type has an appropriate starting value.

---

# **The Golden Formula**

Whenever you read a problem:

Need Traversal?

↓

Yes

↓

What should I remember?

↓

Choose the State Type

↓

Update State

↓

Answer

This formula will guide you through almost every array problem.

---

# **Quick Concept Check**

Identify the state type only.

### **Q1**

Count negative numbers.

---

### **Q2**

Find the smallest number.

---

### **Q3**

Calculate total salary.

---

### **Q4**

Check if `100` exists.

---

### **Q5**

Find the index of the largest number.

---

# **Answers**

Q1 → Counter

Q2 → Best Answer

Q3 → Accumulator

Q4 → Boolean

Q5 → Position

---

# **Chapter Summary**

* Not all problems use the same state.  
* The question determines the state.  
* The most common state types are:  
  * Counter  
  * Accumulator  
  * Best Answer  
  * Boolean  
  * Position  
  * Multiple States  
* Recognizing the correct state is a core interview skill.

---

# **Progress Update**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 3 — State Pattern

✅ Chapter 1 → What is State?  
✅ Chapter 2 → Why State Exists  
🟩 Chapter 3 → Types of State  
⬜ Chapter 4 → Maintaining State  
⬜ Chapter 5 → State in JavaScript  
⬜ Chapter 6 → Dry Run  
⬜ Chapter 7 → Common Beginner Mistakes  
⬜ Chapter 8 → Interview Recognition

---

## **🎯 One Important Clarification**

A common misconception is to think **state \= variable**.

That's not quite correct.

* Every **state** is represented by one or more variables in code.  
* But a variable is only **state** if it stores information that must be remembered across iterations.

For example:

for (let i \= 0; i \< arr.length; i++) {

Here, `i` is **not** considered the state of the problem. It controls the traversal.

In contrast:

let max \= arr\[0\];

`max` **is** state because it represents the best answer found so far and changes as the algorithm processes the array.

This distinction becomes very important in later lessons, especially when we work with multiple pointers and multiple state variables simultaneously.

