Excellent. If you've solved all 10 problems correctly **and** manually evaluated them with dry runs, then you've completed the practical part of Lesson 2\.

Now we'll verify your understanding before moving on.

---

# **DSA in JavaScript**

# **Phase 1 — Arrays**

## **Module 1 — Foundations**

## **Lesson 2 — Traversal**

# **🟩 Lesson Quiz**

---

## **📍 Current Progress**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 2 — Traversal

✅ Theory  
✅ Guided Examples  
✅ Practice Problems  
🟩 Lesson Quiz  
⬜ Revision Notes

---

# **Instructions**

* No coding.  
* Answer using your own words.  
* This quiz tests your understanding, not your memory.

---

# **Section A — Fundamentals**

### **Q1**

What is traversal?

---

### **Q2**

Why do we need traversal?

---

### **Q3**

Is traversal itself an algorithm or a process? Explain.

---

### **Q4**

What is the difference between:

i

and

arr\[i\]

---

### **Q5**

Why do arrays start from index `0` instead of `1`?

---

# **Section B — JavaScript Traversal**

### **Q6**

Explain every part of this loop.

for (let i \= 0; i \< arr.length; i++)

What does each part do?

---

### **Q7**

Why do we use

i \< arr.length

instead of

i \<= arr.length

---

### **Q8**

What happens if we remove

i++

?

---

### **Q9**

What happens if we start with

let i \= 1;

?

---

### **Q10**

What is the purpose of a dry run?

---

# **Section C — Pattern Recognition**

For each problem, write **only the pattern**.

### **Q11**

Find the largest number.

---

### **Q12**

Count even numbers.

---

### **Q13**

Print the array in reverse.

---

### **Q14**

Find the maximum sum of a subarray of size `5`.

---

### **Q15**

Find an element in a sorted array.

---

# **Section D — State Recognition**

Which state variable would you use?

### **Q16**

Count odd numbers.

---

### **Q17**

Find total marks.

---

### **Q18**

Find largest number.

---

### **Q19**

Find smallest number.

---

### **Q20**

Search for `50`.

---

# **Section E — Dry Run**

Without writing code.

Array

\[8, 3, 15, 6\]

### **Q21**

Which element is visited first?

---

### **Q22**

Which element is visited last?

---

### **Q23**

How many iterations occur?

---

### **Q24**

After the second iteration, what is the current index?

---

### **Q25**

If finding the maximum, what is the maximum after visiting:

8

↓

3

↓

15

---

# **Passing Criteria**

23–25  → Excellent  
20–22  → Ready for Lesson 3  
17–19  → Review weak areas  
Below 17 → Revisit Lesson 2

---

# **🟩 Revision Notes**

Once you've completed the quiz, use these notes for quick revision before interviews.

---

## **Lesson 2 Mind Map**

Traversal  
│  
├── Visit every required element  
│  
├── Usually left → right  
│  
├── Can also be:  
│     ├── Right → Left  
│     ├── Two Ends  
│     ├── Circular  
│     └── Matrix  
│  
├── Mental Cycle  
│     │  
│     ├── Current Element  
│     ├── Observe  
│     ├── Process  
│     ├── Move  
│     └── Repeat  
│  
└── Foundation for:  
      ├── State Pattern  
      ├── Simulation  
      ├── Frequency Counting  
      ├── Sliding Window  
      ├── Prefix Sum  
      ├── Kadane  
      └── Two Pointers

---

## **Recognition Cheat Sheet**

If the problem says:

* Find maximum  
* Find minimum  
* Count  
* Sum  
* Print  
* Linear search  
* Check every element

⬇️

Think:

Traversal

---

## **Standard Traversal Template**

for (let i \= 0; i \< arr.length; i++) {  
    // Process arr\[i\]  
}

---

## **Reverse Traversal Template**

for (let i \= arr.length \- 1; i \>= 0; i--) {  
    // Process arr\[i\]  
}

---

## **Common State Variables**

| Problem | State Variable |
| ----- | ----- |
| Count | `count` |
| Sum | `sum` |
| Maximum | `max` |
| Minimum | `min` |
| Search | `found` (boolean) |

---

## **Common Mistakes**

❌ Confusing `i` with `arr[i]`

❌ Using `<= arr.length`

❌ Forgetting `i++`

❌ Starting from index `1` without reason

❌ Thinking about the whole array instead of the current element

❌ Skipping the dry run

---

## **Traversal Mental Formula**

Read Problem

↓

Need every element?

↓

YES

↓

Traversal

↓

What state do I need?

↓

Process current element

↓

Move to next

↓

Repeat

---

## **Complexity**

| Operation | Time | Space |
| ----- | ----- | ----- |
| Simple Traversal | O(n) | O(1) |

---

# **✅ Lesson 2 Completed**

Phase 1 — Arrays

Module 1 — Foundations

Lesson 1 — Array Basics           ✅  
Lesson 2 — Traversal              ✅  
Lesson 3 — State Pattern          ⬜  
Lesson 4 — Simulation             ⬜  
Lesson 5 — Frequency Counting     ⬜  
Lesson 6 — Pattern Recognition    ⬜  
Lesson 7 — Revision               ⬜  
Lesson 8 — Assessment             ⬜

## **🎯 Skills You Now Have**

By completing Lesson 2, you can now:

* Identify when a problem requires traversal.  
* Traverse arrays from left-to-right and right-to-left.  
* Perform dry runs confidently.  
* Maintain simple state (`count`, `sum`, `max`, `min`, `found`) during traversal.  
* Analyze traversal solutions with **O(n)** time and **O(1)** extra space.  
* Recognize traversal as the foundation for many advanced array patterns.

This prepares you well for **Lesson 3 — State Pattern**, where we'll take the idea of "remembering information while traversing" and turn it into a reusable interview pattern used across arrays, strings, linked lists, trees, graphs, sliding windows, and dynamic programming.

