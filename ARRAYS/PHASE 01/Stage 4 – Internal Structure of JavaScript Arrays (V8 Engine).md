# **JavaScript Arrays Master Bootcamp**

# **Phase 1 – Foundations**

# **Stage 4 – Internal Structure of JavaScript Arrays (V8 Engine)**

> **Goal:** Understand how JavaScript engines (especially Google's **V8**, used by Chrome and Node.js) internally store arrays, optimize them for speed, and why certain coding patterns can make arrays much slower.

> **Important:** Everything in this stage is **engine implementation**, not part of the official ECMAScript specification. Different engines (V8, SpiderMonkey, JavaScriptCore) may implement arrays differently, but the core ideas are similar.

---

# **Why This Stage Matters**

If you only know:

arr.push(10);  
arr.pop();

you're writing JavaScript.

If you understand:

* Packed Arrays  
* Holey Arrays  
* Fast Elements  
* Dictionary Mode  
* Engine Optimizations

you're writing **high-performance JavaScript**.

This knowledge helps in:

* DSA  
* Performance optimization  
* Large applications  
* Interviews at companies like Google, Microsoft, Amazon

---

# **Learning Outcomes**

By the end of this stage you'll understand:

* How V8 stores arrays  
* Why some arrays are extremely fast  
* Why others become slow  
* Dense vs Sparse arrays  
* Packed vs Holey arrays  
* Fast Elements  
* Dictionary Mode  
* Hidden optimizations  
* Why `delete` is dangerous  
* Why assigning `arr[1000000]` is expensive  
* Best practices for writing engine-friendly arrays

---

# **Roadmap**

1. JavaScript Specification vs Engine  
2. V8 Overview  
3. How V8 Stores Arrays  
4. Dense Arrays  
5. Sparse Arrays  
6. Packed Arrays  
7. Holey Arrays  
8. Fast Elements  
9. Dictionary Mode  
10. Engine Optimizations  
11. Why `delete` Slows Arrays  
12. Best Practices  
13. Interview Questions  
14. Exercises

---

# **Part 1 — JavaScript Specification vs Engine**

This is one of the biggest misunderstandings beginners have.

When you write:

const arr \= \[10, 20, 30\];

The ECMAScript specification says:

> "This creates an Array object."

It **does not** say:

* how memory should be allocated  
* how elements should be stored  
* how resizing should happen

Those decisions are left to the JavaScript engine.

Think of it like this:

ECMAScript  
      │  
      ▼  
Rules

      │  
      ▼

V8  
SpiderMonkey  
JavaScriptCore

      │  
      ▼

Actual Implementation

---

# **Part 2 — What Is V8?**

V8 is Google's JavaScript engine.

Used by:

* Chrome  
* Node.js  
* Deno (initially used V8 as well)

Its job is to convert JavaScript into machine code and execute it efficiently.

One of its biggest responsibilities is:

> Store arrays as efficiently as possible.

---

# **Part 3 — How Does V8 Store Arrays?**

Suppose:

const numbers \= \[10,20,30\];

Conceptually:

numbers

↓

Array Object

↓

Elements Storage

\+----+----+----+  
|10  |20  |30  |  
\+----+----+----+

The array variable points to an **Array object**.

The Array object keeps metadata such as:

* length  
* pointer to element storage  
* internal flags (such as what kind of elements it contains)

The element storage is where the values live.

---

# **Part 4 — Dense Arrays**

A **dense array** means:

Every index contains a value.

Example:

const arr \= \[10,20,30,40\];

Indexes

0 → 10

1 → 20

2 → 30

3 → 40

No gaps.

Memory conceptually:

\+----+----+----+----+  
|10  |20  |30  |40  |  
\+----+----+----+----+

These are the easiest arrays for the engine to optimize.

---

# **Characteristics**

✅ Every index exists

✅ Sequential

✅ Cache friendly

✅ Very fast

---

# **Part 5 — Sparse Arrays**

Now look at this.

const arr \= \[\];

arr\[100\] \= 50;

Indexes

0

1

2

...

99

100

Only

100

contains a value.

Everything else is empty.

This is called a

**Sparse Array**

---

Conceptually

0  → empty

1  → empty

2  → empty

...

99 → empty

100 → 50

Huge gaps.

---

# **Why Is This Bad?**

The engine can no longer treat it like a simple packed list.

It now has to keep track of missing indexes.

That adds overhead.

---

# **Part 6 — Packed Arrays**

This is V8 terminology.

Packed means:

> Every index between `0` and `length - 1` has a valid element.

Example

const arr \= \[10,20,30\];

Packed.

0

1

2

All filled.

Fastest type.

---

V8 loves packed arrays because:

* no missing values  
* simple indexing  
* predictable memory access  
* optimized machine code

---

# **Part 7 — Holey Arrays**

Now

const arr \= \[10,,30\];

Notice

Index

0 → 10

1 → ?

2 → 30

There is a

Hole

Not

undefined

There is a difference.

A hole means:

> No property exists at that index.

The engine must check:

"Does an element exist here?"

Every access becomes more complicated.

---

Another example

const arr \= \[10,20,30\];

delete arr\[1\];

Result

0 → 10

1 → Hole

2 → 30

Not

10

undefined

30

The slot itself has been removed.

---

# **Hole vs Undefined**

These look similar but are different.

const a \= \[10, undefined, 30\];

Index 1 exists.

It stores the value:

undefined

---

Now

const b \= \[10,,30\];

Index 1

doesn't exist.

Huge difference.

Example

1 in a

Output

true

Example

1 in b

Output

false

This distinction affects iteration methods and engine optimizations.

---

# **Part 8 — Fast Elements**

When arrays remain:

* packed  
* sequential  
* predictable

V8 stores them using **Fast Elements**.

Think of it as:

Optimized Storage

Operations become extremely fast.

Examples:

arr.push()

arr.pop()

arr\[i\]

The engine can generate highly optimized machine code.

---

# **Part 9 — What Breaks Fast Elements?**

Many operations can force the engine to use a slower representation.

Examples:

delete arr\[2\]

arr\[100000\] \= 5

arr\["hello"\] \= 10

arr.length \= 100000

These patterns make the array less predictable.

---

# **Part 10 — Dictionary Mode**

Suppose

const arr \= \[\];

arr\[1000000\] \= 50;

Imagine storing

one million empty slots.

Wasteful.

Instead,

V8 may switch to something conceptually similar to:

Key

↓

Value

1000000

↓

50

Like an object.

Internally this is often referred to as **Dictionary Mode**.

Instead of storing every position,

it stores only existing indexes.

This saves memory.

But

access becomes slower than fast packed arrays.

---

# **Part 11 — Engine Optimization**

Suppose

const arr \= \[10,20,30\];

V8 knows

* integers  
* packed  
* sequential

Great.

Machine code can be heavily optimized.

---

Now

arr.push(40);

Still packed.

Still optimized.

---

Now

delete arr\[1\];

Everything changes.

The engine must now consider missing elements.

Optimization opportunities decrease.

---

# **Part 12 — Why Does `delete` Slow Arrays?**

Consider:

const arr \= \[10,20,30\];

Memory:

10

20

30

Now

delete arr\[1\];

Result:

10

Hole

30

The engine now needs extra checks whenever it accesses elements because some indexes may be missing.

This can move the array from a packed representation to a holey representation, reducing optimization opportunities.

---

# **Should We Use `delete`?**

Almost never.

Instead

Use

arr.splice(index,1);

We'll study `splice()` later.

Unlike `delete`, `splice()` removes the element and shifts later elements left, preserving a packed structure.

Example

const arr \= \[10,20,30\];

arr.splice(1,1);

console.log(arr);

Output

\[10,30\]

No hole.

---

# **Part 13 — Engine-Friendly Arrays**

Prefer

const arr \= \[\];

arr.push(10);

arr.push(20);

arr.push(30);

Avoid

arr\[1000\]=10;

Avoid

delete arr\[2\];

Avoid unnecessary gaps.

Keep indexes continuous.

---

# **Part 14 — Array Evolution Inside V8**

Ideal journey

Packed Array

↓

Fast Elements

↓

Optimized Machine Code

Bad journey

Packed

↓

Holey

↓

Sparse

↓

Dictionary Mode

↓

Slower Access

Not every hole or gap immediately forces the slowest representation, but this progression is a useful mental model.

---

# **Part 15 — Common Misconceptions**

### **Misconception 1**

`delete` removes an array element completely.

Not exactly.

It removes the property at that index and leaves a **hole**.

---

### **Misconception 2**

A hole and `undefined` are the same.

False.

\[undefined\]

has an element.

\[,\]

contains a hole.

---

### **Misconception 3**

Arrays always stay fast.

False.

Certain operations reduce optimization opportunities.

---

### **Misconception 4**

Assigning

arr\[1000000\]

creates one million actual values.

False.

Modern engines use specialized representations for sparse arrays rather than allocating every missing slot.

---

# **Best Practices**

✅ Use `push()` to append.

✅ Keep indexes sequential.

✅ Avoid huge gaps.

✅ Avoid `delete`.

✅ Use `splice()` when removing elements.

✅ Prefer packed arrays for performance-critical code.

---

# **Interview Questions**

1. What is the difference between a dense array and a sparse array?  
2. What is a packed array?  
3. What is a holey array?  
4. What is the difference between a hole and `undefined`?  
5. Why does `delete` slow arrays?  
6. What is Dictionary Mode?  
7. Why does V8 optimize packed arrays better?  
8. Why is `splice()` generally preferred over `delete` for arrays?  
9. Does the ECMAScript specification define how arrays are stored internally?  
10. What kinds of operations can reduce array optimization opportunities?

---

# **Practice Exercises**

### **Exercise 1**

Predict the output:

const arr \= \[10, 20, 30\];

delete arr\[1\];

console.log(arr);  
console.log(arr.length);  
console.log(1 in arr);

Explain **why** each output occurs.

---

### **Exercise 2**

Compare:

const a \= \[10, undefined, 30\];  
const b \= \[10, , 30\];

For each array:

* What is `length`?  
* Does index `1` exist?  
* What does `1 in array` return?  
* Is it packed or holey?

---

### **Exercise 3**

Which of these are engine-friendly?

const a \= \[1, 2, 3\];

const b \= \[\];  
b\[1000\] \= 5;

const c \= \[1, 2, 3\];  
delete c\[1\];

const d \= \[\];  
d.push(1);  
d.push(2);  
d.push(3);

Explain your reasoning.

---

# **Stage 4 Summary**

After completing this stage, you should understand:

* JavaScript engines choose **how** arrays are stored; the ECMAScript specification does not prescribe the internal representation.  
* V8 prefers **packed, dense arrays** because they are easy to optimize and provide fast element access.  
* A **sparse array** contains large gaps, while a **holey array** contains missing indexes between existing elements.  
* A **hole** is different from the value `undefined`; a hole means the property does not exist at that index.  
* Operations like `delete`, assigning to very large indexes, or creating gaps can reduce optimization opportunities and may cause the engine to switch to slower internal representations such as dictionary-style storage.  
* For performance-critical code, keep arrays **packed**, append with `push()`, and use `splice()` instead of `delete` when removing elements. These practices help the engine maintain its fastest array optimizations.

