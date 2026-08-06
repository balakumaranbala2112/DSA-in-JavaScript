Good idea. From now on, for theory chapters we'll cover **2 chapters per lesson** unless one chapter is exceptionally large (like Sliding Window or Dynamic Programming).

So today we'll cover:

* ✅ Chapter 4 → Maintaining State  
* ✅ Chapter 5 → State in JavaScript

---

# **DSA in JavaScript (Interview-Focused)**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 3 — State Pattern**

---

# **🔵 Chapter 4 → Maintaining State**

---

## **🎯 Goal**

After this chapter, you should understand:

* How state changes during traversal.  
* When to update state.  
* When **not** to update state.  
* The life cycle of a state variable.

---

# **What Does "Maintaining State" Mean?**

Creating a state variable is easy.

let max \= arr\[0\];

The difficult part is:

> **How do we keep it correct throughout the algorithm?**

That's called **maintaining state**.

Think of state as a notebook.

If your notebook isn't updated correctly,

your final answer will be wrong.

---

# **The State Life Cycle**

Every state variable follows the same life cycle.

Create State

↓

Initialize State

↓

Update State

↓

Repeat

↓

Final State \= Answer

Every interview problem follows this cycle.

---

# **Step 1 — Create State**

Before traversal starts,

ask yourself:

> "What information must I remember?"

Example:

Find maximum.

Need to remember:

Current Maximum

So create:

let max \= arr\[0\];

---

# **Step 2 — Initialize State**

The initial value is extremely important.

Let's compare.

### **Counting**

Initially

count \= 0

Why?

Because nothing has been counted.

---

### **Sum**

Initially

sum \= 0

Why?

Because nothing has been added.

---

### **Maximum**

Initially

max \= arr\[0\]

Why?

Because the first element is the only candidate you've seen.

---

### **Boolean**

Initially

found \= false

Why?

Because you haven't found anything yet.

---

# **Step 3 — Update State**

This is where the algorithm works.

Suppose

\[12,5,18,9\]

Initially

max \= 12

Visit

5

Question:

5 \> 12 ?

No.

Don't update.

---

Visit

18

Question

18 \> 12 ?

Yes.

Update

max \= 18

Notice something.

State updates **only when necessary**.

---

# **Important Rule**

Don't update state every iteration.

Update it only when the problem requires it.

Examples:

---

### **Counter**

Update when?

Condition is true.

Example:

Even number?

Yes

↓

count++

---

### **Sum**

Update when?

Every iteration.

Every number contributes.

---

### **Maximum**

Update when?

Current \> Maximum

Not every iteration.

---

### **Boolean**

Update when?

Target found

---

# **Visual Example**

Find maximum.

Array

12 → 5 → 18 → 9 → 25

State

12

↓

12

↓

18

↓

18

↓

25

Notice:

State doesn't always change.

Sometimes it stays the same.

---

# **Wrong Thinking**

Some beginners do this:

Current Element

↓

Always Update State

Wrong.

Correct thinking:

Current Element

↓

Should I update?

↓

YES → Update

NO → Keep Existing State

---

# **Real-Life Analogy**

Imagine you're selecting the tallest student.

First student

170 cm

Current tallest

170

Second student

165

Change?

No.

Third student

182

Change?

Yes.

Current tallest

182

You don't replace the tallest student every time.

Only when someone taller appears.

That's maintaining state.

---

# **State Update Pattern**

Every iteration follows this cycle.

Visit Current Element

↓

Compare

↓

Condition True?

↓

YES

↓

Update State

↓

Move Next

---

# **Common Beginner Mistakes**

### **Mistake 1**

Updating state every iteration.

---

### **Mistake 2**

Never updating state.

---

### **Mistake 3**

Initializing state incorrectly.

---

### **Mistake 4**

Using the wrong condition.

---

# **Key Formula**

Initialize

↓

Visit Element

↓

Should state change?

↓

Yes → Update

↓

No → Keep Existing

↓

Repeat

---

# **Quick Concept Check**

### **Q1**

What are the four stages of a state variable's life cycle?

---

### **Q2**

Should `max` update every iteration?

---

### **Q3**

When should `count` update?

---

### **Q4**

Why is initialization important?

---

### **Q5**

True or False

State may remain unchanged during some iterations.

---

# **✅ Chapter 4 Completed**

---

# **🔵 Chapter 5 → State in JavaScript**

---

## **🎯 Goal**

After this chapter, you should know how every common state type is implemented in JavaScript.

---

# **General Template**

Almost every traversal problem follows this structure.

// 1\. Create state

// 2\. Traverse

// 3\. Update state

// 4\. Return state

Only the state variable changes.

---

# **Counter State**

Example:

Count even numbers.

let count \= 0;

for (let i \= 0; i \< arr.length; i++) {

    if (arr\[i\] % 2 \=== 0\) {  
        count++;  
    }

}

Notice:

State

count

Update

count++

---

# **Accumulator State**

Example:

Find total sum.

let sum \= 0;

for (let i \= 0; i \< arr.length; i++) {

    sum \+= arr\[i\];

}

State

sum

Update

sum \+= arr\[i\]

---

# **Best Answer State**

Example:

Maximum.

let max \= arr\[0\];

for (let i \= 1; i \< arr.length; i++) {

    if (arr\[i\] \> max) {  
        max \= arr\[i\];  
    }

}

State

max

Update

if (arr\[i\] \> max)

---

# **Boolean State**

Example:

Search target.

let found \= false;

for (let i \= 0; i \< arr.length; i++) {

    if (arr\[i\] \=== target) {  
        found \= true;  
    }

}

State

found

Update

found \= true

---

# **Position State**

Example:

Store index of maximum.

let maxIndex \= 0;

for (let i \= 1; i \< arr.length; i++) {

    if (arr\[i\] \> arr\[maxIndex\]) {  
        maxIndex \= i;  
    }

}

Notice something.

We store:

Position

NOT

Value

---

# **Multiple State Variables**

Example:

Average.

Need

let sum \= 0;  
let count \= 0;

During traversal

sum \+= arr\[i\];  
count++;

After traversal

const average \= sum / count;

One problem.

Two states.

---

# **State Template Library**

## **Counter**

let count \= 0;

---

## **Sum**

let sum \= 0;

---

## **Maximum**

let max \= arr\[0\];

---

## **Minimum**

let min \= arr\[0\];

---

## **Boolean**

let found \= false;

---

## **Position**

let index \= 0;

---

# **Choosing the Correct State**

| Question | State |
| ----- | ----- |
| How many? | `count` |
| Total? | `sum` |
| Largest? | `max` |
| Smallest? | `min` |
| Exists? | `found` |
| Where? | `index` |

Memorize the **relationship**, not the variables.

---

# **Common Beginner Mistakes**

❌ Using `sum` when the problem asks for a count.

❌ Using `count` when the problem asks for a sum.

❌ Storing the value when the problem wants the index.

❌ Forgetting that one problem can require multiple state variables.

---

# **Interview Recognition**

When reading a problem, ask:

What information must survive  
from this iteration  
to the next iteration?

The answer is your **state**.

For example:

> Find the largest number.

Need to remember:

Largest so far

So:

let max \= arr\[0\];

---

# **Mental Formula**

Every traversal problem now becomes:

Traversal

↓

Current Element

↓

What state do I have?

↓

Should it change?

↓

Update

↓

Repeat

↓

Final State \= Answer

This is one of the most powerful mental models in DSA.

---

# **Quick Concept Check**

### **Q1**

Which state type would you use to count vowels?

---

### **Q2**

Which state type would you use to calculate total marks?

---

### **Q3**

Which state type would you use to find the smallest number?

---

### **Q4**

Can one problem use multiple state variables?

---

### **Q5**

What is the first question you should ask after identifying traversal?

---

# **Progress Update**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 3 — State Pattern

✅ Chapter 1 → What is State?  
✅ Chapter 2 → Why State Exists  
✅ Chapter 3 → Types of State  
✅ Chapter 4 → Maintaining State  
✅ Chapter 5 → State in JavaScript  
⬜ Chapter 6 → Dry Run  
⬜ Chapter 7 → Common Beginner Mistakes  
⬜ Chapter 8 → Interview Recognition

---

## **🎯 Most Important Insight**

Notice how every problem you've solved so far fits the same pattern:

Traversal  
      │  
      ▼  
Choose State  
      │  
      ▼  
Initialize State  
      │  
      ▼  
Visit Current Element  
      │  
      ▼  
Update State (if needed)  
      │  
      ▼  
Repeat  
      │  
      ▼  
Final State \= Answer

This isn't just for arrays. You'll reuse this exact reasoning in **Strings, Linked Lists, Trees, Graphs, Sliding Window, Prefix Sum, Kadane's Algorithm, Greedy, and Dynamic Programming**. Learning this mental model now pays off throughout the rest of your DSA journey.

