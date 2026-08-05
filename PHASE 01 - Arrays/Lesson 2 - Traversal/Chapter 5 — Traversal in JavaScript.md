# **DSA in JavaScript (Interview-Focused)**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **🔵 Chapter 5 — Traversal in JavaScript**

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
                  🔵 Chapter 5 → Traversal in JavaScript  
                  ⬜ Chapter 6 → Dry Run  
                  ⬜ Chapter 7 → Common Beginner Mistakes  
                  ⬜ Chapter 8 → Interview Recognition

                  ⬜ Guided Examples  
                  ⬜ Practice Problems  
                  ⬜ Lesson Quiz  
                  ⬜ Revision Notes

---

# **🎯 Goal**

After this chapter, you should be able to:

* Traverse an array using JavaScript.  
* Understand **every part** of a traversal loop.  
* Know why we usually use a `for` loop in DSA.  
* Understand the role of `i`.

---

# **First Question**

Suppose we have

const arr \= \[10, 20, 30, 40\];

Your brain wants to visit

10

↓

20

↓

30

↓

40

But JavaScript cannot read your mind.

It needs instructions.

---

# **How Do We Tell JavaScript?**

We need a loop.

The most common loop in DSA is

for (...)

Why?

Because arrays have indexes.

And `for` gives us complete control over indexes.

---

# **The Standard Traversal Template**

for (let i \= 0; i \< arr.length; i++) {

}

This is one of the most important pieces of code in DSA.

You will write it **thousands of times**.

Let's understand every part.

---

# **Part 1**

let i \= 0;

This is the **starting point**.

Remember:

Arrays start at index

0

So traversal begins at

Index 0

Visual:

Index

0   1   2   3

We start here.

↑

---

# **Why is the Variable Named `i`?**

`i` stands for **index**.

It stores the position of the current element.

For example:

i \= 2;

means

Current Index \= 2

It does **not** mean

Current Value \= 2

This is one of the biggest beginner mistakes.

Suppose

const arr \= \[50, 80, 20\];

If

i \= 1;

Then

Current Index \= 1

Current Value \= 80

`i` stores the position.

Not the element.

---

# **Part 2**

i \< arr.length

This is the **stopping condition**.

Suppose

const arr \= \[10,20,30\];

Length

3

Indexes

0

1

2

The loop continues while

i \< 3

Let's see.

| i | Condition | Continue? |
| ----- | ----- | ----- |
| 0 | 0 \< 3 | ✅ |
| 1 | 1 \< 3 | ✅ |
| 2 | 2 \< 3 | ✅ |
| 3 | 3 \< 3 | ❌ Stop |

Perfect.

---

# **Why NOT Write**

i \<= arr.length

Suppose

const arr \= \[10,20,30\];

Length

3

Indexes

0

1

2

Now

i \<= 3

means

0

1

2

3

Index `3` doesn't exist.

If you try

arr\[3\]

You'll get

undefined

This is a classic off-by-one error.

---

# **Part 3**

i++

Means

> Move to the next index.

Visual:

0

↓

1

↓

2

↓

3

Without

i++

The loop never moves.

It stays forever at

0

That creates an **infinite loop**.

---

# **Putting It Together**

for (let i \= 0; i \< arr.length; i++) {

}

Mentally read it like this:

> Start at index `0`.

↓

> Continue while the index is inside the array.

↓

> After finishing the current element, move to the next index.

That's exactly the traversal mental model you learned in Chapter 4\.

---

# **Getting the Current Element**

Inside the loop,

`i` tells us **where** we are.

To get the value, we write

arr\[i\]

Example

const arr \= \[10,20,30\];

Suppose

i \= 1;

Then

arr\[i\]

becomes

arr\[1\]

which returns

20

Notice the difference.

| Expression | Meaning |
| ----- | ----- |
| `i` | Current index |
| `arr[i]` | Current value |

Never confuse these.

---

# **Full Traversal**

const arr \= \[10,20,30\];

for (let i \= 0; i \< arr.length; i++) {  
    console.log(arr\[i\]);  
}

Let's trace it.

### **First iteration**

i \= 0

arr\[0\]

↓

10

---

### **Second iteration**

i \= 1

arr\[1\]

↓

20

---

### **Third iteration**

i \= 2

arr\[2\]

↓

30

---

Loop ends.

---

# **Dry Mental Animation**

Imagine a pointer moving.

Index

0   1   2   3

↓

10 20 30 40

Move.

0   1   2   3

    ↓

10 20 30 40

Move.

0   1   2   3

        ↓

10 20 30 40

Move.

0   1   2   3

            ↓

10 20 30 40

Traversal complete.

---

# **Why Don't We Use `for...of`?**

You already know `for...of`.

Example:

for (const value of arr) {

}

This works for simple traversal.

However, in DSA we usually need:

* Current index.  
* Previous index.  
* Next index.  
* Left pointer.  
* Right pointer.

`for` gives direct access to the index, so it becomes the standard choice.

You'll still see `for...of`, but `for` is used much more often in interview solutions.

---

# **Common Beginner Mistakes**

### **Mistake 1**

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

### **Mistake 2**

Using

i \<= arr.length

instead of

i \< arr.length

---

### **Mistake 3**

Starting at

i \= 1

The first element is at index `0`.

---

### **Mistake 4**

Forgetting

i++

Result:

Infinite loop.

---

# **JavaScript Traversal Template**

This is the template you'll use throughout the course.

for (let i \= 0; i \< arr.length; i++) {

    // Current Index  
    // i

    // Current Element  
    // arr\[i\]

    // Process the current element

}

Don't memorize it blindly.

Understand **why every part exists**.

---

# **Quick Check**

Given:

const arr \= \[5, 10, 15\];

### **Q1**

What is the value of `i` in the first iteration?

---

### **Q2**

What does `arr[i]` return in the second iteration?

---

### **Q3**

Why do we write:

i \< arr.length

instead of

i \<= arr.length

---

### **Q4**

What is the difference between:

i

and

arr\[i\]

---

### **Q5**

What happens if we remove:

i++

---

# **Progress Update**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 2 — Traversal

✅ Chapter 1 → What is Traversal?  
✅ Chapter 2 → Why Do We Need Traversal?  
✅ Chapter 3 → Types of Traversal  
✅ Chapter 4 → Traversal Mental Model  
🟩 Chapter 5 → Traversal in JavaScript (Completed)

Next:  
🔵 Chapter 6 → Dry Run

---

## **📌 One improvement to our course**

From **Chapter 5 onward**, every code example will follow this fixed explanation order:

1. **Read the problem.**  
2. **Explain the algorithm idea (without code).**  
3. **Show the code.**  
4. **Explain every line.**  
5. **Dry run the code.**  
6. **Analyze time and space complexity.**  
7. **Discuss common mistakes.**

This mirrors how senior engineers typically review solutions and keeps every lesson consistent.