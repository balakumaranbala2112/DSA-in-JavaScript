Excellent. This is where DSA actually begins.

Up to now, you've learned the theory of traversal.

Now we'll solve **only pure traversal problems**.

**Important Rule for Guided Examples**

We will **not** jump to LeetCode immediately.

We'll first solve simple problems that teach the traversal pattern.

Then we'll move to LeetCode.

---

# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **🔵 Guided Examples**

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
                  ✅ Chapter 5 → Traversal in JavaScript  
                  ✅ Chapter 6 → Dry Run  
                  ✅ Chapter 7 → Common Beginner Mistakes  
                  ✅ Chapter 8 → Interview Recognition  
                  │  
                  🔵 Guided Examples  
                  ⬜ Practice Problems  
                  ⬜ Lesson Quiz  
                  ⬜ Revision Notes

---

# **Guided Example Roadmap**

We'll solve these in order.

Example 1 → Print Every Element  
Example 2 → Print Reverse  
Example 3 → Count Elements  
Example 4 → Sum of Elements  
Example 5 → Find Maximum

Notice something.

The problems gradually become harder.

Each one adds **one new idea**.

---

# **Example 1 — Print Every Element**

This is the **purest traversal problem**.

---

## **Problem**

Given an array,

print every element.

Example

const arr \= \[10, 20, 30, 40\];

Output

10  
20  
30  
40

---

# **Step 1 — Pattern Recognition**

Before touching the keyboard...

Ask yourself:

### **Do I need every element?**

Yes.

---

### **Can I process one element at a time?**

Yes.

---

### **Which pattern?**

Traversal

Done.

---

# **Step 2 — Mental Model**

Imagine standing in front of the array.

Index

0      1      2      3  
┌────┬────┬────┬────┐  
│10  │20  │30  │40  │  
└────┴────┴────┴────┘

Your job is simply

Visit

↓

Print

↓

Move

↓

Repeat

No counting.

No comparing.

No remembering.

Just visit and print.

---

# **Step 3 — Algorithm (English)**

Never write code first.

Describe the process.

Start at the first element.

↓

Print it.

↓

Move to the next.

↓

Print it.

↓

Repeat until the array ends.

If you can explain it in English,

coding becomes much easier.

---

# **Step 4 — JavaScript Code**

const arr \= \[10, 20, 30, 40\];

for (let i \= 0; i \< arr.length; i++) {  
    console.log(arr\[i\]);  
}

Now let's understand **every line**.

---

## **Line 1**

const arr \= \[10, 20, 30, 40\];

We create an array.

Memory:

Index

0      1      2      3  
┌────┬────┬────┬────┐  
│10  │20  │30  │40  │  
└────┴────┴────┴────┘

---

## **Line 2**

for (let i \= 0; i \< arr.length; i++)

This controls the traversal.

### **`let i = 0`**

Start at the first index.

---

### **`i < arr.length`**

Continue while we're still inside the array.

---

### **`i++`**

Move to the next index after processing the current one.

---

## **Line 3**

console.log(arr\[i\]);

This is the actual work.

`i`

↓

Current index.

`arr[i]`

↓

Current value.

Print that value.

---

# **Step 5 — Dry Run**

Array

\[10,20,30,40\]

---

### **Iteration 1**

i \= 0

↓

arr\[0\]

↓

10

↓

Print 10

---

### **Iteration 2**

i \= 1

↓

arr\[1\]

↓

20

↓

Print 20

---

### **Iteration 3**

i \= 2

↓

arr\[2\]

↓

30

↓

Print 30

---

### **Iteration 4**

i \= 3

↓

arr\[3\]

↓

40

↓

Print 40

---

### **Next**

i \= 4

↓

4 \< 4

↓

False

↓

Stop

---

# **Dry Run Table**

| Iteration | `i` | `arr[i]` | Action |
| ----- | ----- | ----- | ----- |
| 1 | 0 | 10 | Print |
| 2 | 1 | 20 | Print |
| 3 | 2 | 30 | Print |
| 4 | 3 | 40 | Print |

---

# **Time Complexity**

We visit every element once.

O(n)

---

# **Space Complexity**

We don't create any extra data structures.

O(1)

---

# **Why This Problem Matters**

It looks extremely easy.

But this problem teaches the **core structure** used in almost every array algorithm.

Later you'll replace:

console.log(arr\[i\]);

with:

* Compare  
* Count  
* Add  
* Update  
* Check  
* Store

The traversal loop itself usually stays the same.

---

# **Mini Exercise (No Code Yet)**

Given:

const arr \= \[5, 15, 25\];

Without writing code, tell me:

### **Q1**

Which value is printed first?

---

### **Q2**

Which value is printed last?

---

### **Q3**

How many times does the loop execute?

---

### **Q4**

What is the value of `i` during the last successful iteration?

---

### **Q5**

After the loop ends, what is the value of `i`?

---

# **Guided Example Progress**

Lesson 2 — Guided Examples

🟩 Example 1 → Print Every Element  
⬜ Example 2 → Print in Reverse  
⬜ Example 3 → Count Elements  
⬜ Example 4 → Sum of Elements  
⬜ Example 5 → Find Maximum

---

## **Why We Start With This**

You might think:

> "This problem is too easy."

That's intentional.

A beginner should **not** learn five concepts in one problem.

This example teaches **only one thing**:

> **How to correctly traverse an array.**

The next examples will keep the same traversal loop and gradually change only **what happens inside the loop**, helping you build pattern recognition one step at a time.

Perfect. Notice something before we begin.

**Example 2 changes only one thing.**

Example 1:

> Move **left → right**

Example 2:

> Move **right → left**

The traversal concept stays the same. Only the **direction** changes.

This is exactly how DSA should be learned—**change one concept at a time**.

---

# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **Guided Example 2 — Print Every Element in Reverse**

---

# **🎯 Goal**

Learn how to traverse an array from **right to left**.

---

# **Problem Statement**

Given an array, print every element in **reverse order**.

Example:

const arr \= \[10, 20, 30, 40\];

Output:

40  
30  
20  
10

---

# **Step 1 — Pattern Recognition**

Before writing code, ask yourself:

### **Do I need to visit every element?**

✅ Yes.

---

### **Am I still traversing?**

✅ Yes.

---

### **What's different?**

The **direction**.

Instead of:

10 → 20 → 30 → 40

we go

40 → 30 → 20 → 10

---

# **Step 2 — Mental Model**

Visualize the array.

Index

0      1      2      3  
┌────┬────┬────┬────┐  
│10  │20  │30  │40  │  
└────┴────┴────┴────┘

Instead of standing here

↑  
10

Start here

              ↑  
              40

Now walk backwards.

40

↑

30

↑

20

↑

10

---

# **Step 3 — Algorithm (Plain English)**

Don't think about JavaScript yet.

Think about the process.

Go to the last element.

↓

Print it.

↓

Move one position left.

↓

Print it.

↓

Repeat until the first element.

That's the entire algorithm.

---

# **Step 4 — How Do We Reach the Last Element?**

Earlier we learned:

arr.length

returns

Number of elements

But the **last index** is

arr.length \- 1

Example:

const arr \= \[10,20,30,40\];

Length \= 4

Last Index \= 3

So traversal starts at

Index 3

---

# **Step 5 — JavaScript Code**

const arr \= \[10, 20, 30, 40\];

for (let i \= arr.length \- 1; i \>= 0; i--) {  
    console.log(arr\[i\]);  
}

Let's understand every part.

---

## **Part 1**

let i \= arr.length \- 1;

Why?

Because we want to start from the **last element**.

If

arr.length

is

4

then

arr.length \- 1

becomes

3

So initially:

i \= 3

---

## **Part 2**

i \>= 0

Question:

Why not stop at `1`?

Because index `0` is also a valid element.

We want to visit

3

↓

2

↓

1

↓

0

When `i` becomes `-1`, the loop stops.

---

## **Part 3**

i--

Earlier we used

i++

because we were moving right.

Now we're moving left.

So after each iteration:

3

↓

2

↓

1

↓

0

---

## **Part 4**

console.log(arr\[i\]);

Exactly the same as Example 1\.

Only the value of `i` changes.

---

# **Step 6 — Dry Run**

Array:

Index

0      1      2      3  
┌────┬────┬────┬────┐  
│10  │20  │30  │40  │  
└────┴────┴────┴────┘

---

### **Iteration 1**

i \= 3

↓

arr\[3\]

↓

40

↓

Print 40

---

### **Iteration 2**

i \= 2

↓

arr\[2\]

↓

30

↓

Print 30

---

### **Iteration 3**

i \= 1

↓

arr\[1\]

↓

20

↓

Print 20

---

### **Iteration 4**

i \= 0

↓

arr\[0\]

↓

10

↓

Print 10

---

### **Next**

i \= \-1

↓

\-1 \>= 0

↓

False

↓

Stop

---

# **Dry Run Table**

| Iteration | `i` | `arr[i]` | Action |
| ----- | ----- | ----- | ----- |
| 1 | 3 | 40 | Print |
| 2 | 2 | 30 | Print |
| 3 | 1 | 20 | Print |
| 4 | 0 | 10 | Print |

---

# **Compare Example 1 vs Example 2**

| Left → Right | Right → Left |
| ----- | ----- |
| Start at `0` | Start at `arr.length - 1` |
| Stop when `i < arr.length` is false | Stop when `i >= 0` is false |
| Move with `i++` | Move with `i--` |

Notice something.

The **pattern is still traversal**.

Only the **starting point**, **stopping condition**, and **movement direction** changed.

---

# **Time Complexity**

Every element is visited once.

O(n)

---

# **Space Complexity**

No extra memory is used.

O(1)

---

# **Real Interview Note**

Printing in reverse order is **not** the same as **reversing an array**.

Example:

Array:

\[10,20,30,40\]

Printing in reverse produces:

40  
30  
20  
10

But the original array is still:

\[10,20,30,40\]

Nothing changed in memory.

Reversing an array means modifying it to become:

\[40,30,20,10\]

That is a different problem, which we'll solve later using the **Two Pointers** pattern.

---

# **Mini Exercise (No Code)**

Given:

const arr \= \[5, 15, 25, 35\];

Answer these:

### **Q1**

Which value is printed first?

---

### **Q2**

Which value is printed last?

---

### **Q3**

What is the starting value of `i`?

---

### **Q4**

What is the last valid value of `i` before the loop stops?

---

### **Q5**

After the loop finishes, what is the value of `i`?

---

# **Guided Example Progress**

Lesson 2 — Guided Examples

✅ Example 1 → Print Every Element  
🟩 Example 2 → Print Every Element in Reverse  
⬜ Example 3 → Count Elements  
⬜ Example 4 → Sum of Elements  
⬜ Example 5 → Find Maximum

---

## **What You Learned**

Example 1 taught you:

> **How to traverse an array.**

Example 2 taught you:

> **Traversal direction can change without changing the underlying pattern.**

From **Example 3 onward**, we'll keep the traversal the same but start changing **what we do with each element**, which is the bridge to the **State Pattern** you'll study in the next lesson.

Excellent. This is the **first guided example** where we introduce a very important DSA idea.

Examples 1 and 2 only **visited** elements.

From this example onward, we start **doing useful work while traversing**.

This is the beginning of the **State Pattern**, but we'll keep it simple. We won't formally study the State Pattern until Lesson 3\.

---

# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **Guided Example 3 — Count Elements**

---

# **🎯 Goal**

Learn how to:

* Traverse an array.  
* Keep track of information while traversing.  
* Understand why we need an extra variable (`count`).

---

# **Problem Statement**

Given an array, count how many elements it contains.

Example:

const arr \= \[10, 20, 30, 40\];

Output

4

---

# **Step 1 — Pattern Recognition**

Ask yourself:

### **Do I need to visit every element?**

✅ Yes.

---

### **Can I process one element at a time?**

✅ Yes.

---

### **Pattern?**

✅ Traversal

---

# **Step 2 — Before Writing Code**

Let's solve it like humans.

Imagine four books on a table.

📕 📗 📘 📙

How would you count them?

You don't magically know there are four.

You start with:

Count \= 0

Then

Book 1

↓

Count \= 1

Next

Book 2

↓

Count \= 2

Next

Book 3

↓

Count \= 3

Next

Book 4

↓

Count \= 4

Finished.

Notice something.

You had to **remember** the current count.

That remembered information is called **state**.

---

# **Step 3 — Algorithm (Plain English)**

Start the count at 0\.

↓

Visit the first element.

↓

Increase the count.

↓

Move to the next element.

↓

Repeat until the array ends.

↓

Return the count.

---

# **Step 4 — JavaScript Code**

const arr \= \[10, 20, 30, 40\];

let count \= 0;

for (let i \= 0; i \< arr.length; i++) {  
    count++;  
}

console.log(count);

Now let's understand every single line.

---

## **Line 1**

const arr \= \[10, 20, 30, 40\];

The array we are traversing.

---

## **Line 2**

let count \= 0;

This is the most important line.

### **Why do we create `count`?**

Because JavaScript doesn't automatically remember how many elements we've visited.

We need our own variable.

Initially:

Visited Elements \= 0

Count \= 0

---

## **Line 3**

for (let i \= 0; i \< arr.length; i++)

This traverses the array from left to right.

---

## **Line 4**

count++;

This means:

count \= count \+ 1

Every time we visit an element, we increase the count by one.

Notice something important.

We are **not using the value**.

Whether the current element is:

10

or

1000

or

\-5

doesn't matter.

We're counting **visits**, not values.

---

## **Line 5**

console.log(count);

After the traversal finishes,

print the final count.

---

# **Step 5 — Dry Run**

Array

\[10,20,30,40\]

Initially

count \= 0

---

### **Iteration 1**

i \= 0

Current Element \= 10

count++

↓

count \= 1

---

### **Iteration 2**

i \= 1

Current Element \= 20

count++

↓

count \= 2

---

### **Iteration 3**

i \= 2

Current Element \= 30

count++

↓

count \= 3

---

### **Iteration 4**

i \= 3

Current Element \= 40

count++

↓

count \= 4

Loop ends.

Output:

4

---

# **Dry Run Table**

| Iteration | `i` | `arr[i]` | `count` Before | `count` After |
| ----- | ----- | ----- | ----- | ----- |
| 1 | 0 | 10 | 0 | 1 |
| 2 | 1 | 20 | 1 | 2 |
| 3 | 2 | 30 | 2 | 3 |
| 4 | 3 | 40 | 3 | 4 |

---

# **Wait...**

You might have noticed something.

JavaScript already gives us:

arr.length

which is also `4`.

So why write this algorithm?

Excellent question.

For this specific problem, you should **not** traverse.

The best solution is simply:

const arr \= \[10, 20, 30, 40\];

console.log(arr.length);

This is **O(1)** because JavaScript already stores the array's length.

So why did we still study traversal?

Because this example teaches the **idea of maintaining a counter**.

Later you'll solve problems like:

* Count even numbers.  
* Count odd numbers.  
* Count negative numbers.  
* Count vowels.  
* Count elements greater than `50`.

In those problems, `arr.length` is useless because you only want to count **some** elements, not all.

---

# **Interview Insight**

If an interviewer asks:

> Count the number of **even** numbers.

Your thinking becomes:

Traversal

↓

Visit current element

↓

Is it even?

↓

YES

↓

Increase count

↓

Move to next

Notice that we only increment `count` **sometimes**.

That's exactly why we practiced this example.

---

# **Time Complexity**

Traversal visits every element once.

O(n)

If you simply use `arr.length`:

O(1)

---

# **Space Complexity**

Only one extra variable is used.

O(1)

---

# **Common Beginner Mistakes**

### **Mistake 1**

Starting with

let count \= 1;

Wrong.

Before visiting anything,

the count should be:

0

---

### **Mistake 2**

Incrementing twice.

count++;

count++;

Now every element is counted twice.

---

### **Mistake 3**

Thinking `count` stores values.

It doesn't.

It stores **how many times a condition has been satisfied**.

---

# **Mini Exercise (No Code)**

Given:

const arr \= \[8, 12, 25, 30, 45\];

Answer these:

### **Q1**

What is the initial value of `count`?

---

### **Q2**

After visiting the first element, what is `count`?

---

### **Q3**

After visiting the third element, what is `count`?

---

### **Q4**

After the loop finishes, what is `count`?

---

### **Q5**

If the problem is **"Count only even numbers,"** would you increase `count` for every element?

---

# **Guided Example Progress**

Lesson 2 — Guided Examples

✅ Example 1 → Print Every Element  
✅ Example 2 → Print Every Element in Reverse  
🟩 Example 3 → Count Elements  
⬜ Example 4 → Sum of Elements  
⬜ Example 5 → Find Maximum

---

## **🔑 The Most Important Takeaway**

This example introduced your **first state variable**:

let count \= 0;

The traversal loop is still the same.

The only new idea is that you're **remembering information while visiting each element**.

That idea—maintaining information as you traverse—is the foundation of the **State Pattern**, which you'll formally master in **Lesson 3**. Every later pattern (Sliding Window, Kadane's Algorithm, Prefix Sum, etc.) also relies on maintaining some kind of state.

Excellent.

This example introduces one of the **most important ideas in DSA**.

In Example 3, the state variable stored a **count**.

Now the state variable will store a **running sum**.

The traversal is **exactly the same**.

Only the work done inside the loop changes.

This is why I said earlier:

> **Traversal is the road.**

> **The action inside the loop changes from problem to problem.**

---

# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **Guided Example 4 — Sum of Elements**

---

# **🎯 Goal**

After this example, you should understand:

* How to calculate the sum of all elements.  
* What a **running sum** is.  
* Why we create a `sum` variable.  
* How the value of `sum` changes during traversal.

---

# **Problem Statement**

Given an array of numbers, return the sum of all its elements.

Example

const arr \= \[10, 20, 30, 40\];

Output

100

Because

10 \+ 20 \+ 30 \+ 40 \= 100

---

# **Step 1 — Pattern Recognition**

Before writing code, ask yourself:

### **Do I need every element?**

✅ Yes.

---

### **Can I process one element at a time?**

✅ Yes.

---

### **Pattern?**

✅ Traversal

---

# **Step 2 — Solve It Like a Human**

Forget JavaScript.

Suppose I give you these numbers.

10

20

30

40

How do you add them?

You don't somehow know the answer is `100`.

You start with nothing.

Sum \= 0

Then

10

↓

Sum \= 10

Then

20

↓

10 \+ 20

↓

Sum \= 30

Then

30

↓

30 \+ 30

↓

Sum \= 60

Then

40

↓

60 \+ 40

↓

Sum \= 100

Finished.

Notice something.

You keep carrying the previous total with you.

That changing total is called the **running sum**.

---

# **What is a Running Sum?**

A running sum means:

> **The total accumulated so far while traversing the array.**

It is called "running" because it changes as you move through the array.

Visual:

Start

↓

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

# **Step 3 — Algorithm (Plain English)**

Don't write code yet.

Describe the process.

Start with sum \= 0\.

↓

Visit the first element.

↓

Add the current element to the sum.

↓

Move to the next element.

↓

Repeat until the array ends.

↓

Return the final sum.

If you can explain this in English, writing the code becomes straightforward.

---

# **Step 4 — JavaScript Code**

const arr \= \[10, 20, 30, 40\];

let sum \= 0;

for (let i \= 0; i \< arr.length; i++) {  
    sum \+= arr\[i\];  
}

console.log(sum);

---

# **Line-by-Line Explanation**

## **Line 1**

const arr \= \[10, 20, 30, 40\];

The input array.

---

## **Line 2**

let sum \= 0;

Why create `sum`?

Because JavaScript doesn't automatically remember the total.

We need a variable that stores the accumulated result.

Initially

Sum \= 0

No elements have been processed.

---

## **Line 3**

for (let i \= 0; i \< arr.length; i++)

Traverse the array from left to right.

Exactly the same traversal you've already learned.

---

## **Line 4**

sum \+= arr\[i\];

This is the only new line.

Let's expand it.

sum \= sum \+ arr\[i\];

Suppose

sum \= 30

arr\[i\] \= 40

Then

sum \= 30 \+ 40;

Now

sum \= 70

The old sum is updated with the current element.

---

## **Line 5**

console.log(sum);

After the loop finishes, print the final total.

---

# **Step 5 — Dry Run**

Array

\[10,20,30,40\]

Initially

sum \= 0

---

### **Iteration 1**

i \= 0

Current Element \= 10

sum \= 0 \+ 10

↓

sum \= 10

---

### **Iteration 2**

i \= 1

Current Element \= 20

sum \= 10 \+ 20

↓

sum \= 30

---

### **Iteration 3**

i \= 2

Current Element \= 30

sum \= 30 \+ 30

↓

sum \= 60

---

### **Iteration 4**

i \= 3

Current Element \= 40

sum \= 60 \+ 40

↓

sum \= 100

Loop ends.

Output

100

---

# **Dry Run Table**

| Iteration | `i` | `arr[i]` | `sum` Before | `sum` After |
| ----- | ----- | ----- | ----- | ----- |
| 1 | 0 | 10 | 0 | 10 |
| 2 | 1 | 20 | 10 | 30 |
| 3 | 2 | 30 | 30 | 60 |
| 4 | 3 | 40 | 60 | 100 |

---

# **Visual Running Sum**

Current Element

10

↓

Running Sum

10

↓

Current Element

20

↓

Running Sum

30

↓

Current Element

30

↓

Running Sum

60

↓

Current Element

40

↓

Running Sum

100

Think of `sum` as a piggy bank.

Each time you visit an element, you put its value into the piggy bank.

By the end, the piggy bank contains the total.

---

# **Time Complexity**

Every element is visited once.

O(n)

---

# **Space Complexity**

Only one extra variable (`sum`) is used.

O(1)

---

# **Common Beginner Mistakes**

### **Mistake 1**

Starting with

let sum \= arr\[0\];

For this lesson, always start with

let sum \= 0;

We'll discuss when other initializations are appropriate in later lessons.

---

### **Mistake 2**

Writing

sum \= arr\[i\];

instead of

sum \+= arr\[i\];

Example:

Array

10 20 30

Wrong behavior:

sum \= 10

↓

sum \= 20

↓

sum \= 30

You keep replacing the previous total.

The final answer becomes `30`, not `60`.

---

### **Mistake 3**

Updating `sum` outside the loop.

Then only one element is added instead of all elements.

---

# **Compare Example 3 vs Example 4**

| Count Elements | Sum Elements |
| ----- | ----- |
| State Variable: `count` | State Variable: `sum` |
| Starts at `0` | Starts at `0` |
| `count++` | `sum += arr[i]` |
| Counts visits | Adds values |

Notice something.

The traversal loop didn't change.

Only the **state variable** and the **processing step** changed.

---

# **Interview Thinking**

Suppose the interviewer asks:

> Find the total marks of all students.

Your thinking should be:

Need every element?

↓

Yes

↓

Traversal

↓

Need to remember something?

↓

Yes

↓

Running Sum

↓

Answer

You're now thinking in **patterns**, not just writing loops.

---

# **Mini Exercise (No Code)**

Given:

const arr \= \[5, 15, 25, 35\];

Answer these:

### **Q1**

What is the initial value of `sum`?

---

### **Q2**

After visiting the first element, what is `sum`?

---

### **Q3**

After visiting the third element, what is `sum`?

---

### **Q4**

What is the final value of `sum`?

---

### **Q5**

What happens if you write:

sum \= arr\[i\];

instead of

sum \+= arr\[i\];

---

# **Guided Example Progress**

Lesson 2 — Guided Examples

✅ Example 1 → Print Every Element  
✅ Example 2 → Print Every Element in Reverse  
✅ Example 3 → Count Elements  
🟩 Example 4 → Sum of Elements  
⬜ Example 5 → Find Maximum

---

## **🔑 Most Important Takeaway**

This example introduced the idea of a **running sum**, which is one of the most frequently used state variables in DSA.

You'll see this idea again in:

* Prefix Sum  
* Sliding Window  
* Kadane's Algorithm  
* Dynamic Programming

The only difference is **how** the running sum is updated. The fundamental idea—**maintaining a value while traversing**—remains the same.

Excellent. This is the **most important guided example** in Lesson 2\.

Why?

Because finding the **maximum** introduces the idea of **comparison**, which is one of the most common operations in DSA.

Unlike the previous examples:

* Example 3 → State was **count**.  
* Example 4 → State was **sum**.  
* Example 5 → State becomes **maximum value found so far**.

This is your first real introduction to maintaining **state** during traversal.

---

# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **Guided Example 5 — Find Maximum Element**

---

# **🎯 Goal**

After this example, you should understand:

* How to find the largest element in an array.  
* Why we need a `max` variable.  
* How comparison works during traversal.  
* What "current maximum" means.

---

# **Problem Statement**

Given an array of numbers, return the largest element.

Example

const arr \= \[12, 5, 18, 9, 25\];

Output

25

---

# **Step 1 — Pattern Recognition**

Before writing code, ask yourself:

### **Do I need every element?**

✅ Yes.

---

### **Can I process one element at a time?**

✅ Yes.

---

### **Pattern?**

✅ Traversal

---

# **Step 2 — Solve It Like a Human**

Imagine someone writes these numbers on a whiteboard.

12

5

18

9

25

I ask:

> "Which number is the largest?"

You don't know immediately.

You look one number at a time.

---

## **First Number**

12

At this moment,

what is the largest number you've seen?

12

Because you've only seen one number.

So you remember

Current Maximum \= 12

---

## **Second Number**

Current number

5

Ask yourself:

Is 5 \> 12 ?

Answer

No

So

Current Maximum

remains

12

---

## **Third Number**

Current number

18

Question

Is 18 \> 12 ?

Yes.

Now update.

Current Maximum

↓

18

---

## **Fourth Number**

9

Question

9 \> 18 ?

No.

Keep

18

---

## **Fifth Number**

25

Question

25 \> 18 ?

Yes.

Update.

Current Maximum

↓

25

Finished.

Answer

25

---

# **The Important Observation**

Notice something.

You never compared every number with every other number.

You only compared:

Current Number

↓

Current Maximum

This makes the algorithm efficient.

---

# **Step 3 — Algorithm (Plain English)**

Before writing code:

Assume the first element is the maximum.

↓

Visit the next element.

↓

If the current element is larger,

update the maximum.

↓

Move to the next element.

↓

Repeat until the array ends.

↓

Return the maximum.

---

# **Why Do We Assume the First Element?**

Many beginners ask:

> "Why don't we start with 0?"

Suppose the array is

\[-8, \-3, \-15\]

If you write

let max \= 0;

What happens?

Compare:

\-8 \> 0 ?

No

\-3 \> 0 ?

No

\-15 \> 0 ?

No

Final answer becomes

0

But

0

isn't even inside the array.

Wrong answer.

That's why we initialize with:

arr\[0\]

because the maximum **must be one of the elements in the array**.

---

# **Step 4 — JavaScript Code**

const arr \= \[12, 5, 18, 9, 25\];

let max \= arr\[0\];

for (let i \= 1; i \< arr.length; i++) {

    if (arr\[i\] \> max) {  
        max \= arr\[i\];  
    }

}

console.log(max);

Now let's understand every line.

---

## **Line 1**

const arr \= \[12, 5, 18, 9, 25\];

Input array.

---

## **Line 2**

let max \= arr\[0\];

This is the most important line.

Initially

Current Maximum \= 12

Why?

Because it's the only element we've seen.

---

## **Line 3**

for (let i \= 1; i \< arr.length; i++)

Notice something.

Earlier we started at

i \= 0

Now we start at

i \= 1

Why?

Because

12

has already been stored in `max`.

There's no need to compare it with itself.

So the first comparison starts with the second element.

This is an optimization, not a different pattern.

---

## **Line 4**

if (arr\[i\] \> max)

This asks:

> "Is the current element larger than the best answer so far?"

If yes,

update.

Otherwise,

ignore it.

---

## **Line 5**

max \= arr\[i\];

This means:

> "I've found a new largest number."

Update the remembered answer.

---

# **Step 5 — Dry Run**

Array

\[12,5,18,9,25\]

Initially

max \= 12

---

### **Iteration 1**

i \= 1

Current Element \= 5

5 \> 12 ?

No

↓

max \= 12

---

### **Iteration 2**

i \= 2

Current Element \= 18

18 \> 12 ?

Yes

↓

max \= 18

---

### **Iteration 3**

i \= 3

Current Element \= 9

9 \> 18 ?

No

↓

max \= 18

---

### **Iteration 4**

i \= 4

Current Element \= 25

25 \> 18 ?

Yes

↓

max \= 25

Loop ends.

Answer

25

---

# **Dry Run Table**

| Iteration | `i` | `arr[i]` | `max` Before | Comparison | `max` After |
| ----- | ----- | ----- | ----- | ----- | ----- |
| Initial | \- | 12 | \- | \- | 12 |
| 1 | 1 | 5 | 12 | 5 \> 12 ❌ | 12 |
| 2 | 2 | 18 | 12 | 18 \> 12 ✅ | 18 |
| 3 | 3 | 9 | 18 | 9 \> 18 ❌ | 18 |
| 4 | 4 | 25 | 18 | 25 \> 18 ✅ | 25 |

---

# **Visual Mental Model**

Current Maximum

12

↓

Compare 5

↓

12

↓

Compare 18

↓

18

↓

Compare 9

↓

18

↓

Compare 25

↓

25

Imagine carrying a trophy.

Whenever you find someone stronger,

you hand them the trophy.

At the end,

the strongest person is holding it.

That's exactly how `max` works.

---

# **Time Complexity**

Every element is visited once.

O(n)

---

# **Space Complexity**

Only one extra variable is used.

O(1)

---

# **Common Beginner Mistakes**

### **Mistake 1**

Initializing with

let max \= 0;

Fails for arrays containing only negative numbers.

---

### **Mistake 2**

Starting the loop at

i \= 0

This still works, but compares the first element with itself once.

Not wrong, just unnecessary.

---

### **Mistake 3**

Updating `max` every iteration.

Wrong:

max \= arr\[i\];

This simply stores the last element.

You should update **only when the current element is larger**.

---

### **Mistake 4**

Confusing the maximum **value** with the maximum **index**.

Remember:

max

stores the value.

Not the position.

Finding the index of the maximum is a different problem.

---

# **Compare Previous Examples**

| Problem | State Variable | Operation |
| ----- | ----- | ----- |
| Count Elements | `count` | Increment |
| Sum Elements | `sum` | Add |
| Find Maximum | `max` | Compare & Update |

Notice something incredible.

The traversal loop **never changed**.

Only the state variable and the action inside the loop changed.

This is why traversal is the foundation of DSA.

---

# **Interview Thinking**

When an interviewer asks:

> Find the largest number.

Your brain should work like this:

Need every element?

↓

Yes

↓

Traversal

↓

Need to remember something?

↓

Current Maximum

↓

Compare

↓

Update if needed

↓

Answer

---

# **Mini Exercise (No Code)**

Given:

const arr \= \[7, 15, 4, 21, 9\];

Answer these:

### **Q1**

What is the initial value of `max`?

---

### **Q2**

After comparing `15`, what is `max`?

---

### **Q3**

After comparing `4`, what is `max`?

---

### **Q4**

After comparing `21`, what is `max`?

---

### **Q5**

Why do we initialize `max` with `arr[0]` instead of `0`?

---

# **Guided Example Progress**

Lesson 2 — Guided Examples

✅ Example 1 → Print Every Element  
✅ Example 2 → Print Every Element in Reverse  
✅ Example 3 → Count Elements  
✅ Example 4 → Sum of Elements  
🟩 Example 5 → Find Maximum

---

# **🎯 Lesson 2 Guided Examples Completed**

You have now solved five progressively harder traversal problems:

1. **Print** → Visit each element.  
2. **Reverse Print** → Change traversal direction.  
3. **Count** → Maintain a counter.  
4. **Sum** → Maintain a running total.  
5. **Maximum** → Maintain the best value seen so far.

Notice the progression:

Traversal  
      │  
      ├── Print  
      ├── Count  
      ├── Sum  
      └── Compare

This wasn't accidental. Each example added **exactly one new idea** while keeping the traversal pattern the same.

The next stage in our fixed roadmap is:

Lesson 2  
│  
├── ✅ Theory  
├── ✅ Guided Examples  
├── 🔵 Practice Problems  
├── ⬜ Lesson Quiz  
└── ⬜ Revision Notes

From here, you'll start solving problems on your own with hints instead of full solutions. This is where pattern recognition begins to become automatic.

