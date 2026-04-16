# NPTEL AI: KRR — EXTRA PREPARATION NOTES
# Worked Examples, Tricky Variations & Rapid-Fire Q&A

> **Purpose:** This file COMPLEMENTS the main guide. Focus here on **problem-solving walkthroughs**, tricky variations, and rapid-fire recall drills.  
> **Exam Date:** Tomorrow!

---

## PART 1: RAPID-FIRE FLASHCARDS (100+ Q&A)

### 🔹 Week 1 — Foundations

| # | Question | Answer |
|---|----------|--------|
| 1 | What is an intelligent agent? | An **autonomous persistent goal-directed program** |
| 2 | Three types of reasoning? | **Deduction** (general→specific), **Induction** (specific→general), **Abduction** (observation→explanation) |
| 3 | What does Winograd Schema test? | **Anaphora resolution** — what does "it" refer to? |
| 4 | Situational knowledge is represented by? | **Scripts** (Schank) + **Frames** (Minsky) |
| 5 | Domain in logic = ? | **Universe of discourse** = set of individuals a logic language can talk about |
| 6 | Image labeling uses? | **Pattern recognition** + **Neural networks** |
| 7 | Expectations involve what type of reasoning? | **Abductive reasoning** from domain knowledge |

### 🔹 Week 2 — Formal Logic & Proofs

| # | Question | Answer |
|---|----------|--------|
| 8 | "Logic is formal" means? | Conclusion acceptable based only on the **FORM** of the argument |
| 9 | KB = ? | Set of sentences accepted to be **TRUE** = set of **premises/axioms** |
| 10 | Entailment means? | α is **necessarily true** given KB (NOT "possibly true") |
| 11 | What is a proof? | **Syntactic** process using rules of inference — **devoid of truth values AND meaning** |
| 12 | Sound logic machine = ? | Derives **ONLY true** sentences, **cannot derive ANY false** sentence |
| 13 | Complete logic machine = ? | Can derive **ALL true** sentences |
| 14 | Valid rule of inference is based on? | **Tautological implication** + is a **sound** rule |
| 15 | Modus Ponens: p, p⊃q → ? | **q** |
| 16 | Modus Tollens: ¬q, p⊃q → ? | **¬p** |
| 17 | P⊃Q is FALSE only when? | **P is TRUE and Q is FALSE** |
| 18 | How many binary connectives between P and Q? | **16** (2^(2²) = 16) |
| 19 | Commutative connectives? | **∧** (AND) and **∨** (OR) — NOT ⊃! |
| 20 | P ≡ Q expanded? | **(P ⊃ Q) ∧ (Q ⊃ P)** |

### 🔹 Week 3 — Propositional Logic & Tableau

| # | Question | Answer |
|---|----------|--------|
| 21 | ∧ in Tableau → ? | **Linear** expansion (same branch) |
| 22 | ∨ in Tableau → ? | **Branching** (two new branches) |
| 23 | ⊃ in Tableau → ? | **Branching** into ¬α \| β |
| 24 | ¬∧ in Tableau → ? | **Branching** |
| 25 | ¬∨ in Tableau → ? | **Linear** |
| 26 | KB is satisfiable if? | At least **ONE** branch is open (gives a model) |
| 27 | KB is unsatisfiable if? | **ALL** branches are closed |
| 28 | Deduction Theorem? | If you can prove β given α → **(α ⊃ β)** is derivable |
| 29 | Model for set S = ? | Valuation making **ALL** sentences in S **true** |
| 30 | De Morgan's: ¬(A ∧ B) = ? | **¬A ∨ ¬B** |
| 31 | De Morgan's: ¬(A ∨ B) = ? | **¬A ∧ ¬B** |

### 🔹 Week 4 — First-Order Logic (HIGH YIELD!)

| # | Question | Answer |
|---|----------|--------|
| 32 | "All X are Y" in FOL? | **∀x(X(x) ⊃ Y(x))** — IMPLICATION! |
| 33 | "Some X are Y" in FOL? | **∃x(X(x) ∧ Y(x))** — CONJUNCTION! |
| 34 | "No X are Y" in FOL? | **∀x(X(x) ⊃ ¬Y(x))** |
| 35 | "Only X are Y" in FOL? | **∀x(Y(x) ⊃ X(x))** — REVERSED! |
| 36 | Why NOT ∀x(Apple(x) ∧ Red(x)) for "All apples are red"? | Says **EVERYTHING** is a red apple! |
| 37 | Why NOT ∃x(Apple(x) ⊃ Red(x)) for "Some apples are red"? | **Trivially true** — any non-apple satisfies it! |
| 38 | FOL sentence vs formula? | **Sentence** = no free variables (all bound by quantifiers) |
| 39 | Skolem constant when? | ∃x **NOT** inside any ∀ |
| 40 | Skolem function when? | ∃x **inside** ∀y → replace x with **f(y)** |
| 41 | Modified Modus Ponens = ? | **Modus Ponens + Universal Instantiation** |
| 42 | Skolem constant = ? | Like constant (fixed element) + like variable (unspecified mapping) |
| 43 | L(P, F, C) means? | **P**=predicates, **F**=functions, **C**=constants |
| 44 | Atomic formula = ? | Predicate applied to terms: **P(t₁, t₂, ..., tₙ)** |
| 45 | When is unification impossible? | **Constants clash** (a≠b) or **occurs check fails** (x = f(x)) |
| 46 | ¬∀x P(x) = ? | **∃x ¬P(x)** (NOT ∀x ¬P(x)!) |
| 47 | ¬∃x P(x) = ? | **∀x ¬P(x)** |

### 🔹 Week 5 — CNF & Resolution

| # | Question | Answer |
|---|----------|--------|
| 48 | Forward Chaining is sound? | **YES** |
| 49 | Forward Chaining is complete? | **Not guaranteed** in FOL |
| 50 | Backward Chaining is sound? | **YES** |
| 51 | CNF = ? | **Conjunction of disjunctions** of literals |
| 52 | Steps to CNF? | Eliminate ≡ → Eliminate ⊃ → Push ¬ inward → Distribute ∨ over ∧ |
| 53 | Resolution refutation step 1? | Convert KB to clause form |
| 54 | Resolution refutation step 2? | **NEGATE the goal** |
| 55 | Resolution refutation ends when? | **Empty clause □** is derived → PROVED! |
| 56 | Does resolution always terminate in FOL? | **NO!** FOL is **semi-decidable** |
| 57 | Semi-decidable means? | If true → will find proof. If false → **may loop forever** |
| 58 | Equality axioms in clause form? | **Reflexivity** (x=x), **Symmetry** (¬(x=y)∨(y=x)), **Transitivity** |

### 🔹 Week 6 — Prolog & Logic Programming

| # | Question | Answer |
|---|----------|--------|
| 59 | Horn clause = ? | Clause with **at most one positive literal** |
| 60 | Can ALL FOL formulas be Horn clauses? | **NO!** (A ∨ B has TWO positive literals) |
| 61 | SLD resolution always terminates? | **NO!** Can loop on recursive predicates |
| 62 | Prolog search strategy? | **Depth-first, left-to-right** |
| 63 | Prolog variable naming? | Start with **UPPERCASE** |
| 64 | Prolog atom naming? | Start with **lowercase** |
| 65 | `[H|T]` means? | H = **head** (first element), T = **tail** (rest of list) |
| 66 | Definite clause = ? | **Exactly one positive literal** (fact or rule) |
| 67 | Goal clause = ? | **Zero positive literals** (a query) |

### 🔹 Week 7 — Prolog Advanced & Rule-Based Systems

| # | Question | Answer |
|---|----------|--------|
| 68 | `\+X` in Prolog? | **Negation by failure** — succeeds when proving X **FAILS** |
| 69 | Cut (!) does what? | **Prevents backtracking** past the cut point |
| 70 | Green cut vs Red cut? | **Green** = no behavior change (optimization). **Red** = changes solutions |
| 71 | Tabling in Prolog? | **Memoization** — stores results, prevents infinite loops |
| 72 | PRIORITY conflict resolution? | Fire rule with **highest priority number** |
| 73 | RECENCY conflict resolution? | Fire rule matching **most recently added WM element** |
| 74 | SPECIFICITY conflict resolution? | Fire rule with **most conditions** |
| 75 | Working Memory contains? | Currently known **facts** |

### 🔹 Week 8 — Knowledge Representation, RDF

| # | Question | Answer |
|---|----------|--------|
| 76 | RDF triple = ? | **(Subject, Predicate, Object)** |
| 77 | RDF/RDFS elements? | **Entities, Properties, Resources, Statements** |
| 78 | Turtle format example? | `:subject :predicate :object .` |
| 79 | FOL is monotonic means? | Adding new info **NEVER** invalidates existing conclusions |
| 80 | Sibling relation properties? | **Binary, Transitive, Irreflexive** |
| 81 | Reification = ? | Treating an **event/statement as an object** with properties |
| 82 | `rdf:type` means? | Instance-of relationship (individual → class) |
| 83 | Grandfather FOL? | **∀x∀y(GF(x,y) ≡ ∃z(Father(x,z) ∧ Parent(z,y)))** |

### 🔹 Week 9 — Description Logic (HIGH YIELD!)

| # | Question | Answer |
|---|----------|--------|
| 84 | ALC stands for? | **Attributive Language with Complement** |
| 85 | ⊓ in DL = ? | **Intersection** (AND) |
| 86 | ⊔ in DL = ? | **Union** (OR) |
| 87 | ⊑ in DL = ? | **Subsumption** (is-a / all X are Y) |
| 88 | ∃R.C in DL = ? | **At least one** R-filler in C |
| 89 | ∀R.C in DL = ? | **All** R-fillers are in C |
| 90 | "All apples are red" in DL? | **Apple ⊑ Red** |
| 91 | "Some apples are red" in DL? | **Apple ⊓ Red ⊑ ⊤** (intersection is non-empty) |
| 92 | ¬∃R.C = ? | **∀R.¬C** |
| 93 | ¬∀R.C = ? | **∃R.¬C** |
| 94 | ¬(C ⊓ D) = ? | **¬C ⊔ ¬D** |
| 95 | ¬(C ⊔ D) = ? | **¬C ⊓ ¬D** |
| 96 | Is DL decidable? | **YES!** (unlike FOL) |

### 🔹 Week 10 — Conceptual Dependency (HIGH YIELD!)

| # | Question | Answer |
|---|----------|--------|
| 97 | Give → ? | **ATRANS** (abstract transfer of possession) |
| 98 | Walk/Run → ? | **PTRANS** (physical transfer of location) |
| 99 | Tell/Read/See → ? | **MTRANS** (mental transfer of information) |
| 100 | Think/Decide → ? | **MBUILD** (building new mental info) |
| 101 | Eat/Drink → ? | **INGEST** (taking into body) |
| 102 | Push/Kick → ? | **PROPEL** (applying physical force) |
| 103 | Grab/Hold → ? | **GRASP** (physically grasping) |
| 104 | Say/Sing → ? | **SPEAK** (producing sounds) |
| 105 | Look/Listen → ? | **ATTEND** (focusing sensory attention) |
| 106 | Raise hand/Nod → ? | **MOVE** (moving a body part) |
| 107 | Cry/Spit → ? | **EXPEL** (expelling from body) |
| 108 | "Buy" uses what CDs? | **2× ATRANS** (money↔item) |
| 109 | Kill/Hate/Love in CD? | **States or state changes** + causal relations |
| 110 | Remember/Forget? | **MTRANS** between memory compartments |
| 111 | ELI module does? | Extracts **explicit** conceptual elements from story |
| 112 | PP-Memory does? | Memory of script roles + matches incoming tokens to script |
| 113 | Causal chain completion? | Inferring **intervening events** between two explicit events |

### 🔹 Week 11 — Frames & Inheritance

| # | Question | Answer |
|---|----------|--------|
| 114 | PAM = ? | **Plan Applier Mechanism** — understands stories via plans |
| 115 | Slot filler can be? | Value, pointer to frame, pointer to generic frame, **attached procedure** |
| 116 | Strict inheritance? | Entity **CANNOT** override inherited value |
| 117 | Defeasible inheritance? | Entity **CAN** override inherited value |
| 118 | Credulous extension? | Any ONE **consistent** subgraph (may have multiple) |
| 119 | Skeptical extension? | Only what **ALL** credulous extensions agree on |
| 120 | Admissible edge? | Not **preempted** by a more specific edge |
| 121 | Redundant edge? | Can be **derived** from other edges (transitivity) |
| 122 | Edge in inheritance hierarchy = ? | **Class-subclass (IS-A)** relation |

### 🔹 Week 12 — Default Reasoning & Event Calculus (HIGH YIELD!)

| # | Question | Answer |
|---|----------|--------|
| 123 | Frame Problem = ? | Which fluents **remain UNCHANGED** when action occurs |
| 124 | Circumscription key idea? | **Minimize abnormality** — assume normal unless stated |
| 125 | CWA key idea? | If **not provable**, assume **FALSE** |
| 126 | Default rule format? | **A : B₁,...,Bₙ / C** (prerequisite : justifications / consequent) |
| 127 | Extension in Default Logic? | **Maximal consistent** set of conclusions from defaults |
| 128 | Happens(a, t) means? | Action **a** occurs at time **t** |
| 129 | HoldsAt(f, t) means? | Fluent **f** is **true** at time **t** |
| 130 | Initiates(a, f, t) means? | Action **a** makes fluent **f TRUE** at time **t** |
| 131 | Terminates(a, f, t) means? | Action **a** makes fluent **f FALSE** at time **t** |
| 132 | Clipped(t1, f, t2) means? | Fluent **f** is terminated **between** t1 and t2 |
| 133 | K_a P means? | Agent **a** **knows** P |
| 134 | What does K_putin ¬K_biden P mean? | Putin knows that Biden **doesn't know** P |
| 135 | K_putin ¬K_biden ¬P means? | Putin knows Biden **considers P possible** |
| 136 | FOL is monotonic? | **YES** |
| 137 | Default Logic is monotonic? | **NO** — new defaults can retract conclusions |

---

## PART 2: WORKED EXAMPLES — STEP-BY-STEP SOLUTIONS

### EXAMPLE 1: FOL Translation (Most Common Exam Pattern!)

**Problem:** Translate "Every student who passes the exam is happy" to FOL.

**Step-by-step:**
1. Identify the pattern: "Every/All X (that) Y are Z"
2. "All" → ∀ with ⊃
3. Subject: student(x) ∧ passes(x)
4. Predicate: happy(x)
5. **Answer: ∀x((Student(x) ∧ Passes(x)) ⊃ Happy(x))**

> [!TIP]
> **Pattern recognition:** "All X that have property P are Y" = ∀x((X(x) ∧ P(x)) ⊃ Y(x))

---

**Problem:** Translate "Some dogs that are trained can do tricks" to FOL.

**Step-by-step:**
1. Pattern: "Some X that Y can Z"
2. "Some" → ∃ with ∧
3. **Answer: ∃x(Dog(x) ∧ Trained(x) ∧ CanDoTricks(x))**

---

**Problem:** Translate "No reptile is a mammal" to FOL.

**Step-by-step:**
1. Pattern: "No X are Y"
2. "No" → ∀ with ⊃ ¬
3. **Answer: ∀x(Reptile(x) ⊃ ¬Mammal(x))**
4. Equivalent: ¬∃x(Reptile(x) ∧ Mammal(x))

---

**Problem:** Translate "Only registered users can post comments" to FOL.

**Step-by-step:**
1. Pattern: "Only X can Y" = "All things that Y must be X"
2. REVERSE the direction!
3. **Answer: ∀x(CanPost(x) ⊃ Registered(x))**
4. NOT: ∀x(Registered(x) ⊃ CanPost(x)) — that says "All registered users CAN post" (different meaning)

> [!CAUTION]
> **"Only" reverses the implication!** "Only X are Y" ≡ ∀x(Y(x) ⊃ X(x)), NOT ∀x(X(x) ⊃ Y(x))

---

### EXAMPLE 2: Skolemization — Step-by-Step

**Problem:** Skolemize: ∀x ∃y ∀z ∃w P(x, y, z, w)

**Step-by-step:**
1. List existential variables and what ∀ they're under:
   - y is under ∀x → replace y with **f(x)**
   - w is under ∀x and ∀z → replace w with **g(x, z)**
2. Drop all quantifiers
3. **Answer: P(x, f(x), z, g(x, z))**

---

**Problem:** Skolemize: ∃x ∀y ∃z P(x, y, z)

**Step-by-step:**
1. x is NOT under any ∀ → replace x with **Skolem constant a**
2. z is under ∀y → replace z with **f(y)**
3. **Answer: P(a, y, f(y))**

---

**Problem:** Skolemize: ∀x ∃y (Loves(x, y))

**Step-by-step:**
1. y is under ∀x → replace y with **f(x)**
2. **Answer: Loves(x, f(x))**
3. **Meaning:** "Everyone loves someone" → "Everyone loves their special someone f(x)"

> [!NOTE]
> **Skolem functions capture dependencies.** f(x) means "the person that x loves" — different for each x!

---

### EXAMPLE 3: CNF Conversion — Complete Walkthrough

**Problem:** Convert (P ⊃ Q) ⊃ R to CNF.

**Step 1: Eliminate ⊃**
- P ⊃ Q = ¬P ∨ Q
- So: (¬P ∨ Q) ⊃ R = ¬(¬P ∨ Q) ∨ R

**Step 2: Push ¬ inward (De Morgan's)**
- ¬(¬P ∨ Q) = ¬¬P ∧ ¬Q = P ∧ ¬Q
- So: (P ∧ ¬Q) ∨ R

**Step 3: Distribute ∨ over ∧**
- (P ∨ R) ∧ (¬Q ∨ R)

**Answer: (P ∨ R) ∧ (¬Q ∨ R)**

---

**Problem:** Convert ¬(P ⊃ (Q ∧ R)) to CNF.

**Step 1:** P ⊃ (Q ∧ R) = ¬P ∨ (Q ∧ R)
**Step 2:** ¬(¬P ∨ (Q ∧ R)) = P ∧ ¬(Q ∧ R) = P ∧ (¬Q ∨ ¬R)

**Answer: P ∧ (¬Q ∨ ¬R)** — already in CNF!

---

### EXAMPLE 4: Resolution Refutation — Complete Walkthrough

**Problem:** Given KB = {P ⊃ Q, Q ⊃ R}, prove R assuming P.

**Step 1: Convert to clauses**
- P ⊃ Q → {¬P ∨ Q}
- Q ⊃ R → {¬Q ∨ R}
- Assumption: {P}

**Step 2: Negate the goal**
- Goal: R
- Negated goal: {¬R}

**Step 3: Add all clauses**
1. ¬P ∨ Q
2. ¬Q ∨ R
3. P
4. ¬R (negated goal)

**Step 4: Resolve**
- Resolve (1) with (3) on P: → **Q** (clause 5)
- Resolve (2) with (5) on Q: → **R** (clause 6)
- Resolve (6) with (4) on R: → **□** (empty clause!)

**Answer: □ derived → R is PROVED!** ✅

---

### EXAMPLE 5: Prolog Execution Trace

**Problem:** Given the Prolog program:
```prolog
parent(tom, bob).
parent(tom, liz).
parent(bob, ann).
parent(bob, pat).

grandparent(X, Z) :- parent(X, Y), parent(Y, Z).
```

**Query:** `?- grandparent(tom, X).`

**Trace:**
1. Goal: `grandparent(tom, X)`
2. Match rule head: `grandparent(X1, Z)` with `{X1=tom}`
3. New goals: `parent(tom, Y), parent(Y, Z)`
4. Try `parent(tom, Y)`:
   - First match: `parent(tom, bob)` → `{Y=bob}`
   - Goal becomes: `parent(bob, Z)`
   - Match: `parent(bob, ann)` → `{Z=ann}` → **X = ann** ✅
   - Backtrack: `parent(bob, pat)` → `{Z=pat}` → **X = pat** ✅
5. Backtrack to `parent(tom, Y)`:
   - Next match: `parent(tom, liz)` → `{Y=liz}`
   - Goal becomes: `parent(liz, Z)`
   - No match → **FAIL** (liz has no children)
6. No more matches → end

**Answer: X = ann ; X = pat** (two solutions)

> [!TIP]
> **Prolog tracing strategy:** Always go TOP-DOWN through rules, LEFT-TO-RIGHT through body goals, and BACKTRACK on failure.

---

### EXAMPLE 6: DL to FOL Translation

**Problem:** Translate (Person ⊓ ∀hasChild.Doctor) ⊑ Proud to FOL.

**Step-by-step:**
1. Person ⊓ ∀hasChild.Doctor = Person(x) ∧ ∀y(hasChild(x,y) ⊃ Doctor(y))
2. ⊑ Proud = ⊃ Proud(x)
3. Wrap in ∀x
4. **Answer: ∀x((Person(x) ∧ ∀y(hasChild(x,y) ⊃ Doctor(y))) ⊃ Proud(x))**

**English:** "Every person whose all children are doctors is proud"

---

**Problem:** Check if KB ⊨ (∃hasChild.Doctor)(Ada) given:
```
KB = { Doctor(Ada), Doctor(Bob), Doctor(Eve), 
       hasChild(Ada, Bob), hasChild(Ada, Eve) }
```

**Step-by-step:**
1. (∃hasChild.Doctor)(Ada) means: "Ada has at least one child who is a Doctor"
2. Ada hasChild Bob ✅, and Doctor(Bob) ✅
3. So Ada has at **least one** child (Bob) who is a Doctor
4. **Answer: YES, KB ⊨ (∃hasChild.Doctor)(Ada)** ✅

---

### EXAMPLE 7: CD Theory — Verb Mapping

**Problem:** Map "John gave Mary a book" to CD primitives.

**Analysis:**
- "gave" = transfer of possession
- Object transferred: book
- From: John → To: Mary
- **Answer: ATRANS(book, John, Mary)**

---

**Problem:** Map "Sneha bought an icecream and ate it" to CD primitives.

**Analysis:**
1. "bought" = two ATRANS:
   - ATRANS(money, Sneha, seller) — money goes to seller
   - ATRANS(icecream, seller, Sneha) — icecream comes to Sneha
2. Icecream needs to reach Sneha's hands:
   - PTRANS(icecream, store, Sneha) — physical movement
3. "ate" = taking into body:
   - INGEST(icecream, Sneha, mouth) — eating

**Answer: 2× ATRANS + PTRANS + INGEST**

---

**Problem:** Map "The teacher told the students about the exam" to CD.

**Analysis:**
- "told" = mental information transfer from speaker to listener
- SPEAK (producing the words) + MTRANS (information transfer)
- **Answer: SPEAK + MTRANS(exam-info, teacher, students)**

---

### EXAMPLE 8: Event Calculus Timeline

**Problem:** Given:
- Initially(alive)
- Happens(shoot, 5)
- Terminates(shoot, alive, 5)

**Question:** Does HoldsAt(alive, 3)? Does HoldsAt(alive, 7)?

**Timeline:**
```
Time:  0----1----2----3----4----5----6----7
alive: T    T    T    T    T    X    F    F
                                ↑
                           shoot happens
                           (terminates alive)
```

**At time 3:**
- Initially(alive) → alive true at t=0
- No action happens between 0 and 3
- ¬Clipped(0, alive, 3) → alive persists
- **HoldsAt(alive, 3) = TRUE** ✅

**At time 7:**
- Terminates(shoot, alive, 5) → alive becomes false after t=5
- ¬HoldsAt(alive, 7) unless alive is re-initiated
- **HoldsAt(alive, 7) = FALSE** ✅

> [!TIP]
> **Event Calculus strategy:** Draw a TIMELINE. Mark when each action happens. Draw arrows for Initiates/Terminates. Check Clipped between time points.

---

### EXAMPLE 9: Default Logic Extension

**Problem:** Given Default Theory:
- Facts W = {Bird(tweety)}
- Defaults: D = { Bird(x) : Flies(x) / Flies(x) }
  - Translation: "If x is a bird, and it's consistent that x flies, then conclude x flies"

**Computing the extension:**
1. W = {Bird(tweety)}
2. Check default: Bird(tweety) ✅ (prerequisite met)
3. Is Flies(tweety) consistent with what we know? YES (nothing contradicts it)
4. Add Flies(tweety)
5. **Extension E = {Bird(tweety), Flies(tweety)}**

---

**Problem:** Now add Penguin(tweety) and default: Penguin(x) : ¬Flies(x) / ¬Flies(x)

**Computing:**
1. W = {Bird(tweety), Penguin(tweety)}
2. Try default 1: Bird(tweety) → consistent that Flies(tweety)? → If we applied this, we'd get Flies(tweety)
3. Try default 2: Penguin(tweety) → consistent that ¬Flies(tweety)? → If we applied this, we'd get ¬Flies(tweety)
4. **CONFLICT!** Can't have both Flies and ¬Flies
5. Two possible extensions (credulous), but with priority (specificity/penguin overrides bird), typically: **¬Flies(tweety)**

---

### EXAMPLE 10: Inheritance Network — Admissible Paths

**Problem:** Given the network:
```
    a
   / \
  B   ¬B
  |    |
  C   ¬C
  |
  D
  |
  E
```

**Finding admissible edges w.r.t. node 'a':**
1. a → B: admissible (no more specific edge preempts it)
2. a → ¬B: admissible (direct edge from a)
3. B → C: admissible (not preempted)
4. B → ¬C: admissible (not preempted)
... and so on

**Finding admissible paths from 'a':**
- a, B, C, D, E ✅
- a, B, ¬C ✅
- a, ¬B, ¬C, D, E ✅ (if edges exist)

**Finding beliefs (skeptical):**
- Look at what ALL credulous extensions agree on
- If all extensions include a→E, then a→E is a skeptical belief

---

## PART 3: TRICKY EXAM VARIATIONS

### Variation Type 1: "Which is NOT true?"

Be extra careful when the question asks for what's FALSE. Common traps:

| Statement | TRUE or FALSE? |
|-----------|---------------|
| "Resolution always terminates in FOL" | **FALSE** |
| "All FOL formulas can be expressed as Horn Clauses" | **FALSE** |
| "SLD resolution always terminates" | **FALSE** |
| "FOL is decidable" | **FALSE** (semi-decidable) |
| "PL is decidable" | **TRUE** |
| "Forward chaining is sound" | **TRUE** |
| "Backward chaining is complete" | **FALSE** (in general) |
| "Sound implies complete" | **FALSE** |
| "Complete implies sound" | **FALSE** |
| "FOL is monotonic" | **TRUE** |
| "DL (ALC) is decidable" | **TRUE** |

### Variation Type 2: Subtle FOL Differences

> [!WARNING]
> **Watch for these trick options:**

| Option | What it ACTUALLY means | Correct for? |
|--------|----------------------|--------------|
| ∀x(P(x) ∧ Q(x)) | EVERYTHING is P AND Q | Almost never correct |
| ∀x(P(x) ⊃ Q(x)) | Every P is Q | "All P are Q" ✅ |
| ∃x(P(x) ⊃ Q(x)) | There exists something where if P then Q | Almost always trivially true! |
| ∃x(P(x) ∧ Q(x)) | There's a P that is also Q | "Some P are Q" ✅ |
| ∀x(Q(x) ⊃ P(x)) | Every Q is P | "Only P are Q" ✅ |

### Variation Type 3: DL Trap Questions

| DL Expression | Meaning | Trap |
|--------------|---------|------|
| Apple ⊑ Red | All apples are red | Correct for "all" |
| Apple ⊓ Red ⊑ ⊤ | Some apples are red | ⊤ means non-empty intersection |
| Apple ⊓ Red ⊑ ⊥ | NO apples are red | ⊥ means EMPTY intersection |
| Apple ⊑ ⊥ | NO apples exist | Different from "no apples are red" |
| ⊤ ⊑ Apple | EVERYTHING is an apple | Almost always wrong |

### Variation Type 4: CD Theory Traps

| Verb | WRONG primitive | RIGHT primitive | Why |
|------|-----------------|-----------------|-----|
| "See" | ATTEND only | **ATTEND + MTRANS** | Seeing = attending + info transfer to brain |
| "Kill" | PROPEL | **State change (alive→dead)** | Kill isn't an action — it's a caused state |
| "Buy" | 1× ATRANS | **2× ATRANS** | Money AND item both transfer |
| "Read" | ATTEND | **MTRANS** (+ ATTEND) | Reading = transferring info to mind |
| "Remember" | MBUILD | **MTRANS** | Info moves between memory compartments |

### Variation Type 5: Event Calculus Traps

| Question Pattern | Trap | Correct Answer |
|-----------------|------|----------------|
| "Does f hold at time t?" | Forgetting to check Clipped | Must verify ¬Clipped(t₁, f, t) |
| "Frame Problem is about?" | "What changes" | **What STAYS THE SAME** |
| "Initially(f) and no actions" | Assuming f might be false | f holds at ALL future times (if never terminated) |

---

## PART 4: CONCEPT DEEP-DIVES (Hardest Topics)

### Deep-Dive 1: Why FOL is Semi-Decidable (Not Decidable)

**The key insight:**
- **Decidable** = there's an algorithm that ALWAYS terminates and gives correct answer
- **Semi-decidable** = if the answer is YES, algorithm terminates. If NO, it may run forever.
- FOL is semi-decidable because:
  - If KB ⊨ α (it's true), resolution WILL find a proof (eventually)
  - If KB ⊭ α (it's false), resolution may keep generating new clauses forever
  - This is related to the **Halting Problem** — you can't always know if you'll halt

**For exam:** Resolution refutation = semi-decidable. It does NOT always terminate. It does NOT always produce a unique proof.

---

### Deep-Dive 2: Monotonic vs Non-Monotonic Reasoning

**Monotonic (FOL):**
```
KB = {Bird(tweety)}
KB ⊨ "Tweety might fly" (via default reasoning? NO — FOL can't do this!)
```
FOL can only derive what's LOGICALLY entailed. Adding new facts (Penguin(tweety)) can ADD new conclusions but NEVER remove old ones.

**Non-Monotonic (Default Logic / Circumscription):**
```
KB = {Bird(tweety)}  +  Default: "Birds normally fly"
→ Conclude: Flies(tweety)

Now add: Penguin(tweety)  +  "Penguins don't fly"
→ RETRACT: Flies(tweety)
→ Conclude: ¬Flies(tweety)
```

**Key difference:** In non-monotonic reasoning, new information CAN RETRACT old conclusions!

---

### Deep-Dive 3: The Frame Problem Explained Simply

**Scenario:** You have a robot in a room. The room has:
- Light is ON
- Door is CLOSED
- Robot is at position (1,1)

**Action:** Robot moves to position (2,3).

**Frame Problem:** After the move, what's still true?
- Light is still ON? (YES — moving doesn't affect lights)
- Door is still CLOSED? (YES — moving doesn't affect doors)
- Robot is at (1,1)? (NO — this changed!)

**The problem:** You have to EXPLICITLY state that "everything NOT mentioned as changed STAYS THE SAME." In a complex domain with thousands of fluents and dozens of actions, this requires a HUGE number of "frame axioms."

**Event Calculus solution:** Use **Clipped** predicate. A fluent persists UNLESS it's clipped (terminated by some action). This avoids listing all the things that DON'T change.

---

### Deep-Dive 4: Negation Normal Form (NNF) in DL — Full Algorithm

**Rule set for converting to NNF:**
1. ¬¬C → C (double negation)
2. ¬(C ⊓ D) → ¬C ⊔ ¬D (De Morgan)
3. ¬(C ⊔ D) → ¬C ⊓ ¬D (De Morgan)
4. ¬∀R.C → ∃R.¬C (push ¬ past ∀)
5. ¬∃R.C → ∀R.¬C (push ¬ past ∃)

**Example:** Convert ¬((Teens ⊓ ∃owns.Apple) ⊔ Happy) to NNF

Step 1: ¬(A ⊔ B) → ¬A ⊓ ¬B
= ¬(Teens ⊓ ∃owns.Apple) ⊓ ¬Happy

Step 2: ¬(C ⊓ D) → ¬C ⊔ ¬D
= (¬Teens ⊔ ¬∃owns.Apple) ⊓ ¬Happy

Step 3: ¬∃R.C → ∀R.¬C
= (¬Teens ⊔ ∀owns.¬Apple) ⊓ ¬Happy ← **DONE (NNF)**

---

### Deep-Dive 5: Understanding ALC Entailments

**KB reasoning in ALC:**

Given: Parent ≡ ∃hasChild.⊤  (Being a parent = having at least one child)

If hasChild(Max, Amy) is in KB:
- Max has child Amy → ∃hasChild.⊤ satisfied → **Parent(Max)** ✅

Given: OCC ≡ ∀hasChild.Doctor  (OCC = all children are doctors)

If OCC(Max) and hasChild(Max, Amy):
- All Max's children are doctors + Amy is Max's child → **Doctor(Amy)** ✅

Given: POCC ⊑ Parent ⊓ OCC  (POCC people are both parents and OCC)

If Parent(Max) and OCC(Max):
- Max satisfies Parent ⊓ OCC → **POCC(Max)** ✅

---

### Deep-Dive 6: Epistemic Logic — K and B Operators

**Notation:**
- K_a P = "Agent a KNOWS P" (factual, justified, true belief)
- B_a P = "Agent a BELIEVES P" (may or may not be true)
- K_a K_b P = "a knows that b knows P"
- K_a ¬K_b P = "a knows that b does NOT know P"
- K_a ¬K_b ¬P = "a knows that b doesn't know ¬P" = "a knows b considers P possible"

**Exam Question Pattern:**
"Putin is going to attack Ukraine. K_putin, K_biden, ¬K_biden represent?"

Parse: K_putin(¬K_biden(¬P))
= Putin KNOWS that Biden does NOT KNOW that P is false
= Putin knows that Biden considers P possible
= **Putin knows that Biden considers it possible that P**

---

## PART 5: PATTERN-BASED EXAM SHORTCUTS

### Shortcut 1: Instant FOL Translation

When you see "All/Every/Each" → write **∀x(...⊃...)**
When you see "Some/A few/There exists" → write **∃x(...∧...)**
When you see "No/None/Never" → write **∀x(...⊃ ¬...)**
When you see "Only/Just" → **REVERSE** → write ∀x(conclusion ⊃ condition)

### Shortcut 2: DL ↔ FOL Instant Mapping

See ⊑ → think ⊃ (implication)
See ⊓ → think ∧ (and)
See ⊔ → think ∨ (or)
See ∃R.C → think "at least one R-neighbor in C"
See ∀R.C → think "all R-neighbors in C"

### Shortcut 3: CD Theory Instant Mapping

Ask yourself:
- Does ownership change? → **ATRANS**
- Does location change? → **PTRANS**
- Does someone learn something? → **MTRANS**
- Does someone decide/think? → **MBUILD**
- Does someone eat/drink? → **INGEST**
- Does someone push/hit? → **PROPEL**
- Does someone grab? → **GRASP**

### Shortcut 4: Resolution Questions

1. Convert everything to clauses (disjunctions of literals)
2. NEGATE the goal and add as a clause
3. Find complementary literals (P in one clause, ¬P in another)
4. Resolve them (combine, remove the complementary pair)
5. If you get □ → proved. If you can't get □ → not provable.

### Shortcut 5: Tableau Questions

- **To prove validity:** Negate the formula. If all branches close → valid.
- **α-rules (linear):** ∧, ¬∨, ¬⊃ → keep on same branch
- **β-rules (branch):** ∨, ⊃, ¬∧ → split into two branches
- **Close when:** Both P and ¬P appear on same branch

---

## PART 6: 15-MINUTE RAPID REVISION

> [!IMPORTANT]
> **Read this section 15 minutes before the exam. These are the TOP 20 facts that cover 80% of questions:**

1. **All→⊃, Some→∧** (FOL quantifier patterns)
2. **Resolution does NOT always terminate** in FOL (semi-decidable)
3. **SLD resolution does NOT always terminate** (can loop)
4. **NOT all FOL formulas** can be Horn clauses
5. **Sound** = only true derivations. **Complete** = all truths derivable.
6. **Skolem constant** (∃ not under ∀) vs **Skolem function** (∃ under ∀)
7. **Modus Ponens:** p, p⊃q → q. **Modus Tollens:** ¬q, p⊃q → ¬p
8. **P⊃Q is FALSE** only when P=T, Q=F
9. **ALC** = Attributive Language with Complement
10. **Apple ⊑ Red** = "All apples red". **Apple ⊓ Red ⊑ ⊤** = "Some apples red"
11. **ATRANS** = give/buy/sell. **PTRANS** = go/walk. **MTRANS** = tell/see/hear. **INGEST** = eat/drink
12. **Kill/Hate/Love** = states + causal relations (NOT action primitives)
13. **Frame Problem** = what stays the SAME (not what changes!)
14. **HoldsAt(f,t)** = fluent f true at time t. **Clipped** = interrupted
15. **Monotonic** = new info can't retract old. **Non-monotonic** = CAN retract
16. **Default rule:** A : B / C (prerequisite : justification / consequent)
17. **Circumscription** = minimize abnormality
18. **CWA** = not provable → assume false
19. **PAM** = Plan Applier Mechanism (understands stories)
20. **Credulous** = any ONE consistent extension. **Skeptical** = intersection of ALL

---

## PART 7: COMMON WRONG ANSWER PATTERNS

### Pattern 1: "All of the above" / "None of the above"
- These are often correct in NPTEL exams — don't dismiss them!
- Especially "None of the above" when asking about FOL termination

### Pattern 2: Multiple Select Questions
- Read EVERY option carefully
- Don't stop after finding one correct answer
- Common trap: 3 out of 4 options are correct

### Pattern 3: "Which is FALSE?"
- Your brain is trained to look for TRUE
- Explicitly write "F" or "T" next to each option
- The FALSE one is your answer

### Pattern 4: Subtle Wording Changes
- "necessarily true" ≠ "possibly true" (entailment vs satisfiability)
- "terminates" ≠ "is sound" (process property vs correctness property)
- "derives only true" (soundness) ≠ "derives all true" (completeness)
- "can override" (defeasible) ≠ "cannot override" (strict)

---

## BONUS: KEY FORMULAS AT A GLANCE

### Logic Equivalences
```
P ⊃ Q  ≡  ¬P ∨ Q
P ≡ Q  ≡  (P ⊃ Q) ∧ (Q ⊃ P)
¬(P ∧ Q) ≡  ¬P ∨ ¬Q          (De Morgan)
¬(P ∨ Q) ≡  ¬P ∧ ¬Q          (De Morgan)
¬∀x P(x) ≡  ∃x ¬P(x)
¬∃x P(x) ≡  ∀x ¬P(x)
P ∨ (Q ∧ R) ≡ (P∨Q) ∧ (P∨R)  (Distribution)
P ∧ (Q ∨ R) ≡ (P∧Q) ∨ (P∧R)  (Distribution)
```

### DL NNF Rules
```
¬¬C       = C
¬(C ⊓ D)  = ¬C ⊔ ¬D
¬(C ⊔ D)  = ¬C ⊓ ¬D
¬∀R.C     = ∃R.¬C
¬∃R.C     = ∀R.¬C
```

### Skolemization Quick Rules
```
∃x (no ∀ above)         → Skolem CONSTANT: sk
∃x under ∀y             → Skolem FUNCTION: f(y)
∃x under ∀y, ∀z         → Skolem FUNCTION: f(y, z)
```

### CNF Conversion Pipeline
```
1. A ≡ B  →  (A ⊃ B) ∧ (B ⊃ A)
2. A ⊃ B  →  ¬A ∨ B
3. ¬(A ∧ B) → ¬A ∨ ¬B    (push ¬ in)
4. ¬(A ∨ B) → ¬A ∧ ¬B    (push ¬ in)
5. A ∨ (B ∧ C) → (A∨B) ∧ (A∨C)  (distribute ∨ over ∧)
```

---

> **You've reviewed EVERYTHING. Trust your preparation. Focus on the patterns — most exam questions are direct variations of assignment questions. Read each question carefully, identify the pattern, apply the rule, and you'll crush it!** 🎯
