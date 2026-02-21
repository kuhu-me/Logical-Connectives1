# 🧠 Knights and Knaves – Logical Reasoning Engine

## 📌 Overview

This project solves classic **Knights and Knaves** logic puzzles using propositional logic and model checking.

In these puzzles:

- 🛡️ Knights always tell the truth.
- 😈 Knaves always lie.
- Every character is either a knight or a knave, but not both.

The program determines each character’s identity by formally encoding their statements into a logical knowledge base and evaluating all possible truth assignments.

---

## 🎯 Objective

The purpose of this project is to:

- Convert natural language statements into propositional logic
- Build a logically consistent knowledge base
- Apply logical inference using model checking
- Automatically determine valid solutions

---

## 🏗️ Implementation Approach

### 1️⃣ Symbol Definitions

Each character is represented using propositional symbols:

- AKnight, AKnave
- BKnight, BKnave
- CKnight, CKnave

Additional symbols are introduced when required (for example, to represent what someone said, such as ASaidKnight and ASaidKnave).

---

### 2️⃣ Universal Constraints

For every character:

They must be either a knight or a knave:

    Or(PersonKnight, PersonKnave)

They cannot be both:

    Not(And(PersonKnight, PersonKnave))

---

### 3️⃣ Statement Encoding Rule

For any character:

- If the person is a knight → their statement must be true.
- If the person is a knave → their statement must be false.

This is encoded using logical implications:

    Implication(PersonKnight, Statement)
    Implication(PersonKnave, Not(Statement))

This rule is applied consistently across all puzzles.

---

## 🧩 Example Scenario (Puzzle 3)

In one of the puzzles:

- A says either "I am a knight." or "I am a knave."
- B says:
  - "A said 'I am a knave.'"
  - "C is a knave."
- C says:
  - "A is a knight."

After encoding all constraints correctly and running model checking, the logically consistent solution is:

    A = Knight
    B = Knave
    C = Knight

---

## 🧠 Key Concepts Used

- Propositional Logic
- Logical Connectives (And, Or, Not, Implication)
- Knowledge Representation
- Model Checking
- Logical Consistency Verification

---

## ⚠️ Challenges Addressed

- Modeling statements about statements (meta-reasoning)
- Maintaining correct implication direction
- Avoiding logical contradictions
- Enforcing exclusivity constraints

---

## 🚀 How to Run

1. Ensure Python is installed.
2. Run the main script:

    python puzzle.py

3. The program outputs which logical symbols are entailed by the knowledge base.

---

## ✨ What This Project Demonstrates

- Strong logical modeling skills
- Ability to translate natural language into formal logic
- Structured reasoning and debugging of logical systems
- Foundational understanding of symbolic reasoning systems