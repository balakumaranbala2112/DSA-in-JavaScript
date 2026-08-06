# DSA in JavaScript — Lesson 2: Traversal

> **Phase 1 — Arrays › Module 1 — Foundations**

---

## 📍 Where You Are

```
DSA in JavaScript
│
└── Phase 1 — Arrays
      │
      └── Module 1 — Foundations
            │
            ├── ✅ Lesson 1 — Array Basics
            ├── 🔵 Lesson 2 — Traversal          ← You are here
            ├── ⬜ Lesson 3 — State Pattern
            ├── ⬜ Lesson 4 — Simulation
            ├── ⬜ Lesson 5 — Frequency Counting
            ├── ⬜ Lesson 6 — Pattern Recognition
            ├── ⬜ Lesson 7 — Revision
            └── ⬜ Lesson 8 — Assessment
```

---

## 🎯 Lesson Objectives

By the end of this lesson you will be able to answer:

- What is traversal?
- Why do we traverse an array?
- When should we use traversal?
- How do I recognise a traversal problem in an interview?
- What information should I maintain while traversing?
- Which interview questions are **pure traversal** questions?

---

## 📦 Prerequisites

| Requirement | Why It Matters |
|---|---|
| ✅ Lesson 1 — Array Basics | You must know what arrays are, how indexes work, and how JavaScript stores them in memory |
| Basic JavaScript syntax | `let`, `const`, `if`, comparison operators |

---

## 🗂️ Lesson Structure (5 Chapters)

This lesson is reorganised from 8 theory chapters + guided examples + practice + quiz + revision into **5 focused chapters**.

```
Lesson 2 — Traversal
│
├── Chapter 1 — Understanding Traversal
│     ├── What is Traversal?
│     └── Why Do We Need Traversal?
│
├── Chapter 2 — Types of Traversal and Mental Model
│     ├── Types of Traversal
│     └── The Traversal Mental Model
│
├── Chapter 3 — Traversal in JavaScript and Dry Run
│     ├── The Standard Traversal Template
│     └── How to Dry Run Code
│
├── Chapter 4 — Common Mistakes and Interview Recognition
│     ├── 10 Common Beginner Mistakes
│     └── How to Recognise Traversal in Interviews
│
└── Chapter 5 — Guided Examples, Practice and Assessment
      ├── 5 Guided Examples
      ├── 10 Practice Problems
      ├── Lesson Quiz
      └── Revision Notes
```

---

## 🔗 Quick Navigation

| Chapter | File | Focus |
|---|---|---|
| Chapter 1 | [`chapter-1-understanding-traversal.md`](./chapter-1-understanding-traversal.md) | Concept and motivation |
| Chapter 2 | [`chapter-2-types-and-mental-model.md`](./chapter-2-types-and-mental-model.md) | Types, mental cycle |
| Chapter 3 | [`chapter-3-javascript-and-dry-run.md`](./chapter-3-javascript-and-dry-run.md) | Code + tracing |
| Chapter 4 | [`chapter-4-mistakes-and-recognition.md`](./chapter-4-mistakes-and-recognition.md) | Pitfalls + interview skills |
| Chapter 5 | [`chapter-5-practice-and-assessment.md`](./chapter-5-practice-and-assessment.md) | Examples, problems, quiz, revision |

---

## 📊 Complexity Summary

| Operation | Time Complexity | Space Complexity |
|---|---|---|
| Simple Traversal (left → right) | O(n) | O(1) |
| Reverse Traversal (right → left) | O(n) | O(1) |
| Traversal with a state variable | O(n) | O(1) |

> `n` = number of elements in the array.

---

## 🧠 Core Insight

> Traversal is **not** an algorithm. It is a **process** — the foundation on which almost every array algorithm is built.

Every major pattern you will learn later still uses traversal:

```
Traversal (foundation)
      │
      ├── State Pattern       (Lesson 3)
      ├── Simulation          (Lesson 4)
      ├── Frequency Counting  (Lesson 5)
      ├── Sliding Window      (Module 3)
      ├── Prefix Sum          (Module 4)
      ├── Two Pointers        (Module 2)
      └── Kadane's Algorithm  (Module 5)
```

---

## ✅ Lesson Progress Tracker

Copy and use this as your personal checklist:

```
Lesson 2 — Traversal

Theory
  [ ] Chapter 1 — Understanding Traversal
  [ ] Chapter 2 — Types of Traversal and Mental Model
  [ ] Chapter 3 — Traversal in JavaScript and Dry Run
  [ ] Chapter 4 — Common Mistakes and Interview Recognition

Practice
  [ ] Chapter 5 — Guided Examples (5/5)
  [ ] Chapter 5 — Practice Problems (10/10)
  [ ] Chapter 5 — Lesson Quiz
  [ ] Chapter 5 — Revision Notes reviewed
```

---

## 📋 Golden Rules (Memorise These)

```
1. Traversal is a PROCESS, not an algorithm.
2. The for loop is just JavaScript — the PATTERN is what matters.
3. NEVER think about the whole array at once. Think about ONE element.
4. i   → the current INDEX (position)
   arr[i] → the current VALUE (element)
5. Always dry-run your code before executing it.
6. Recognise the pattern FIRST, then write the code.
```

---

*Lesson 2 of 8 in Module 1 — Foundations*
