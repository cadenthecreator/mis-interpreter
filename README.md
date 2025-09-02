# Misinterpreter

*A multiplayer code-telephone game where meaning drifts through obfuscation and reinterpretation.*

---

## Overview

Misinterpreter is an online, multi-user game inspired by the mechanics of *Telestrations* and the *Telephone Game*.
Instead of drawings, players exchange short programs. Each round, code is obfuscated, interpreted in plain language, and re-implemented. By the end, the final program often diverges significantly from the original.

---

## How It Works

### 1. Prompt Stage

* Each player begins with a simple coding task (e.g., *“Write a function that reverses a string”*).
* They implement a short snippet in the chosen language.

### 2. Obfuscation & Pass

* The system automatically **obfuscates** the code before passing it along.

  * Variable renaming
  * Minification or unusual formatting
  * Redundant no-ops
  * Structural rewrites (e.g., loops → recursion)

### 3. Interpretation Stage

* The next player receives the obfuscated code.
* They provide a plain-language description of what they believe the code does.

### 4. Re-Implementation Stage

* Another player receives only the description.
* They re-implement the code from scratch, based on that description.

### 5. Repeat Cycle

* This sequence of **code → obfuscation → description → rewrite** continues until every player has contributed.

### 6. Reveal Stage

* At the end of the round, the entire chain is shown:

  1. The original prompt
  2. The original code
  3. Each obfuscated version
  4. Each interpretation and re-implementation

---

## Scoring Modes

### Casual Mode

* No points. The focus is on comparing the original with the final result.

### Competitive Mode

* Points for **accurate descriptions** (does the description match the code’s actual behavior?).
* Points for **faithful re-implementations** (does the new code behave the same as the last version?).
* Optional bonus points for creative or surprising outcomes (voted by players).

---

## Technical Features

* **Sandboxed execution** for safety.
* **Languages**: initial support for Python and JavaScript.
* **Obfuscation engine**: automated code transformations at each pass.
* **Multiplayer lobbies**: recommended 4–10 players.
* **Reveal timeline**: shows the progression step by step.

---

## Example Round

**Prompt:** “Write code that sums a list of numbers.”

1. Player A →

   ```python
   def sum_list(nums): return sum(nums)
   ```

2. Obfuscated →

   ```python
   def Q(q): R=0
       for i in q: R+=i
       return R
   ```

3. Player B (description) → “This adds up numbers in a list.”

4. Player C (rewrite) →

   ```javascript
   function addAll(arr) {
       let t=0;
       for (const a of arr) { t+=a; }
       return t;
   }
   ```

5. Obfuscated again →

   ```javascript
   function f(a){return a.reduce((x,y)=>x+y,0)}
   ```

6. Player D (description) → “This concatenates strings together.”

…and the cycle continues.

---

## Purpose

Misinterpreter explores how intent changes as code passes through transformations, interpretations, and rewrites. It combines programming practice with collaborative play and emphasizes how easily meaning can shift.

---

Would you like me to also produce a **short “Quick Rules” reference** (one section players can skim before starting), alongside this more detailed doc?
