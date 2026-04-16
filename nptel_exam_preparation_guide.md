# 🎯 NPTEL AI: Knowledge Representation and Reasoning — EXAM PREPARATION GUIDE

> **Course:** Artificial Intelligence: Knowledge Representation And Reasoning  
> **Exam:** Tomorrow  
> **Strategy:** Most questions come from assignment questions — this guide covers ALL of them!

---

## 📋 TABLE OF CONTENTS

1. [Week 1-3: Propositional Logic Foundations](#week-1-3)
2. [Week 4: First-Order Logic (FOL)](#week-4)
3. [Week 5: Clause Form, CNF, Resolution](#week-5)
4. [Week 6: Logic Programming & Prolog](#week-6)
5. [Week 7: Prolog Programming & Execution](#week-7)
6. [Week 8: Knowledge Representation, RDF, Semantic Web](#week-8)
7. [Week 9: Description Logic (DL) & ALC](#week-9)
8. [Week 10: Conceptual Dependency (CD) Theory & Scripts](#week-10)
9. [Week 11: Planning (PAM), Frames & Inheritance Networks](#week-11)
10. [Week 12: Default Reasoning, Event Calculus, Epistemic Logic](#week-12)
11. [MASTER CHEAT SHEET](#cheat-sheet)

---

<a name="week-1-3"></a>
## 📘 WEEKS 1-3: PROPOSITIONAL LOGIC FOUNDATIONS

### Week 1 — Key Concepts

**Propositional Logic Basics:**
- A **proposition** is a declarative sentence that is either TRUE or FALSE
- Propositional variables: p, q, r... represent propositions
- **Connectives:** ¬ (NOT), ∧ (AND), ∨ (OR), ⊃ (IMPLIES), ≡ (BICONDITIONAL)

**Truth Tables — MEMORIZE THESE:**

| p | q | ¬p | p∧q | p∨q | p⊃q | p≡q |
|---|---|-----|------|------|------|------|
| T | T | F   | T    | T    | T    | T    |
| T | F | F   | F    | T    | F    | F    |
| F | T | T   | F    | T    | T    | F    |
| F | F | T   | F    | F    | T    | T    |

> [!IMPORTANT]
> **p ⊃ q is FALSE ONLY when p is TRUE and q is FALSE!** This is the most tested concept!

**Key Equivalences:**
- p ⊃ q ≡ ¬p ∨ q
- p ≡ q ≡ (p ⊃ q) ∧ (q ⊃ p)
- De Morgan's: ¬(p ∧ q) ≡ ¬p ∨ ¬q; ¬(p ∨ q) ≡ ¬p ∧ ¬q
- Contrapositive: p ⊃ q ≡ ¬q ⊃ ¬p

### Week 1 Assignment Q&A

**Q: Well-formed formulas (WFFs)?**
- Every propositional variable is a WFF
- If A is a WFF, then ¬A is a WFF
- If A, B are WFFs, then (A ∧ B), (A ∨ B), (A ⊃ B), (A ≡ B) are WFFs

**Q: Tautology vs Contradiction vs Contingency?**
- **Tautology:** TRUE for ALL interpretations (e.g., p ∨ ¬p)
- **Contradiction:** FALSE for ALL interpretations (e.g., p ∧ ¬p)
- **Contingency:** TRUE for some, FALSE for others

### Week 2 — Logical Reasoning & Inference

**Inference Rules — CRITICAL FOR EXAM:**
- **Modus Ponens:** From p and p ⊃ q, derive q
- **Modus Tollens:** From ¬q and p ⊃ q, derive ¬p
- **Hypothetical Syllogism:** From p ⊃ q and q ⊃ r, derive p ⊃ r
- **Disjunctive Syllogism:** From p ∨ q and ¬p, derive q
- **Resolution:** From p ∨ q and ¬p ∨ r, derive q ∨ r

> [!TIP]
> **Resolution is the most important inference rule for the exam** — it's used extensively in Weeks 5-6!

### Week 3 — Normal Forms

**CNF (Conjunctive Normal Form):**
- Conjunction of disjunctions: (l₁ ∨ l₂) ∧ (l₃ ∨ l₄)
- Each clause is a disjunction of literals

**DNF (Disjunctive Normal Form):**
- Disjunction of conjunctions: (l₁ ∧ l₂) ∨ (l₃ ∧ l₄)

**Conversion to CNF Steps:**
1. Eliminate biconditionals: A ≡ B → (A ⊃ B) ∧ (B ⊃ A)
2. Eliminate implications: A ⊃ B → ¬A ∨ B
3. Push negations inward (De Morgan's)
4. Distribute ∨ over ∧

---

<a name="week-4"></a>
## 📗 WEEK 4: FIRST-ORDER LOGIC (FOL)

### Assignment 4 Questions & Answers

**Q1: First-order logic refers to elements in a domain. We can refer to elements using:**
- ✅ using constant symbols in the language
- ✅ using variable symbols in the language
- ✅ using functions defined in the language

**Q2: When we define a predicate RichMan in our language L(P,F,C) and have a sentence RichMan(suresh) in the knowledge base, we are asserting that:**
- ✅ RichMan is some subset of a domain D

**Q3: An atomic formula in FOL:**
- ✅ is a well-formed formula
- ✅ is the smallest unit that can have a truth value assigned to it

**Q4: A variable x in an FOL formula ω:**
- ✅ must necessarily be in the scope of a quantifier if ω is a sentence of FOL
- ✅ can occur in the scope of more than one quantifier in a sentence of FOL

**Q5: Let father and coach be function symbols, Tall be a relation symbol, and Sneha be a constant symbol of L(P,F,C). Which are sentences of FOL?**
- ✅ Tall(father(x))
- ✅ Tall(father(Sneha))
- ✅ ∀y(Tall(father(Sneha)))
- ✅ ∃x(Tall(father(x)))
- ✅ ∀y(Tall(father(x)) ⊃ Tall(x))

**Q6: Which are sentences of FOL with equality?**
- ✅ father(Sneha) = coach(Sneha)
- ✅ ∃x(father(Sneha) = coach(x))
- ✅ ∃x(father(Sneha) = coach(Sneha))
- ✅ ∃x(father(x) = coach(x))
- ✅ ∀x(father(Sneha) = coach(x))
- ✅ ∀x(father(x) = coach(x))

**Q7: An interpretation I = ⟨D, {.}⟩ of L(P,F,C) unambiguously determines the truth value of:**
- ✅ formulas with terms only from the sets F and C
- ✅ formulas with terms made up of free variables and constants

**Q8: Which pairs of clauses are unifiable?**
- ✅ { *Likes(*Z₂, anisa) },  { Likes(*Z₂, anisa) }
- ✅ { *Likes(*Z₂, X₁) },  { Likes(*Z₂, mother(*Z₂)) }
- ✅ { *Likes(*Z₂, X₁) },  { Likes(*Z₂, mother(anisa)) }

**Q9: The Modified Modus Ponens rule combines which two rules of inference?**
- ✅ Modus Ponens and Universal Instantiation

**Q10: A Skolem constant:**
- ✅ is like a constant of L(P,F,C) because it maps to a fixed element in the domain D
- ✅ is like a variable of FOL since the mapping to an element of the domain is not specified
- ✅ is different from a variable as its value cannot be determined by making an inference

**Q11: If variable x is (substituted with) a Skolem function of variable y it means that:**
- ✅ x is existentially quantified in the scope of y which is universally quantified

### FOL Representation — KEY PATTERNS

> [!IMPORTANT]
> **"All X are Y"** → ∀x (X(x) ⊃ Y(x))  
> **"Some X are Y"** → ∃x (X(x) ∧ Y(x))  
> **"No X are Y"** → ∀x (X(x) ⊃ ¬Y(x))  
> **"Kings are rich"** → ∀x (King(x) ⊃ Rich(x))  
> **"Some kings are rich"** → ∃x (King(x) ∧ Rich(x))  
> **"Rich people are kings"** → ∀x (Rich(x) ⊃ King(x))

**FOL Language Components:**
- **Domain-independent (logical):** Punctuations, Constants T ⊥, Boolean connectives ¬∧∨⊃≡, Quantifiers ∀∃, Equals "="
- **Domain-dependent (non-logical):** Set of variable names, Set of function names, Set of predicate names, Set of constant names

**Terms in FOL:** Variable, Function with arguments, Constants
**Atomic Formula in FOL:** Predicate with arguments
**Where do terms occur?** Arguments to functions, arguments to arithmetic operations, arguments to predicates, arguments to relational operators

---

<a name="week-5"></a>
## 📙 WEEK 5: CLAUSE FORM, CNF & RESOLUTION

### Assignment 5 Questions & Answers

**Q1: Select the correct options:**
- ✅ Backward Chaining is sound
- ✅ Forward Chaining is sound

**Q2: Formulas that are in CNF:**
- ✅ A ∨ B ∨ C
- ✅ A ∧ B ∧ C
- ✅ (¬A ∨ B ∨ C) ∧ (¬C ∨ ¬D ∨ E)

**Q3: Formulas that are in Clause Form:**
- ✅ ∀x ∀y ( ¬Sees(x) ∨ ¬Owns(x,y) ∨ ¬Apple(y) ∨ Happy(y) )
- ✅ ¬Sees(¬x) ∨ ¬Owns(¬x,¬y) ∨ ¬Apple(¬x) ∨ Happy(¬x)

**Q4: The CNF of (A ∧ (B ⊃ C)) ∨ (A ∧ B ∧ D):**
- ✅ A ∧ (A ∨ B) ∧ (A ∨ D) ∧ (A ∨ B ∨ ¬C) ∧ (B ∨ C ∨ D)

**Q5: FOL formula and Skolemized formula — correct Skolem form (the prefix "sk" denotes Skolem):**
- ✅ ∃x∀y P(x,y),  P(sk1,¬y)
- ✅ ∀y∃x P(x,y),  P(sk1(¬y),¬y)
- ✅ ∀y (∃(R(P(x,y) ∧ Q(x)) ⊃ R(y))),   ¬R(¬x,¬y) ∨ ¬Q(¬x) ∨ R(¬y)

**Q6: Select the correct statement about KB consistency:**
- ✅ KB1 is inconsistent and KB2 is consistent

**Q7: Clauses corresponding to equality axioms:**
- ✅ (¬x = ¬y)
- ✅ ¬(¬x = ¬y) ∨ (¬y = ¬x)
- ✅ ¬(¬x = ¬y) ∨ ¬(¬y = ¬z) ∨ ¬x = ¬z

**Q8: Resolvent from unification of two clauses:**
- ✅ Likes(anisa, mother(anisa))
- ✅ Likes(*Z₂, mother(*Z₂)) ∨ ¬Likes(*Z₂, ¬x₁) ∨ ¬Likes(*x₁, ¬z₁)
- ✅ { Likes(*Z₂, anisa) ∨ ¬Likes(*Z₂, anisa) ∨ ¬Likes(mother(*Z₁, *Z₁) }  ≠ T
- ✅ Likes(*Z₂, mother(*Z₂)) ∨ ¬Likes(anisa, anisa) ∨ ¬Likes(anisa, *z₁)

**Q9: KB3 resolution (House, Owner, Taxpayer problem):**
- ✅ House(sk,Jack)
- ✅ Owner(sk,Jack), Jack)
- ✅ Taxpayer(Jack)
- ✅ ¬House(¬x) ∨ ¬Owner(¬x,¬x) ∨ Taxpayer(¬x)

**Q10: KB3 entailments:**
- ✅ KB3 entails Taxpayer(Jack)
- ✅ KB3 entails Landlord(Jack)

**Q11: Resolution refutation on any set of clauses in FOL:**
- ✅ None of the above (it does NOT always terminate!)

### Practice Week 5 — CNF & Resolution Details

**Literal in propositional logic:** a variable or negation of a variable  
**Clause in CNF formula:** disjunction of literals  
**CNF formula:** conjunction of clauses  
**Negation in CNF:** can occur only before a variable  

**Formulas in CNF:**
- ✅ (¬A ∨ ¬B) ∧ (¬A ∨ ¬C ∨ D) ∧ (¬B ∨ D)

**Skolem Form rules:**
- ∀x (P(x) ⊃ ∃y(Q(x,y) ⊃ ¬Q(y,y)))
- ∀x ∨ (¬P(x) ∨ ∀y(¬Q(x,y) ∨ ¬Q(y,y)))
- After Skolemization: ¬P(¬x) ∨ ¬Q(¬x,¬y) ∨ ¬Q(¬y,¬y)

> [!WARNING]
> **Resolution refutation does NOT always terminate in FOL** — this is a common trick question! It is **semi-decidable** only.

---

<a name="week-6"></a>
## 📕 WEEK 6: LOGIC PROGRAMMING & PROLOG

### Assignment 6 Questions & Answers

**Q1: Horn Clauses:**
- ✅ Disjunction of literals with at most one positive literal and zero or more negative literals
- ✅ Horn Clauses, when written as a logical implication, have a head and a body, where the head has almost one positive literal and the body is a conjunction of zero or more positive literals

**Q2: Converting to clause form (using the rule of substitution):**
- ✅ ∀x (¬Team(x) ∨ ∃y (Owns(x,y) ∧ Apple(y)) ⊃ Happy(x)) → ∀x (¬Team(x) ∨ ¬Owns(x,y) ∨ ¬Apple(y) ∨ Happy(x))

**Q3: SWI Prolog - predicates and unification:**
- Know how predicate definitions and list processing work
- Understand `member/2`, `append/3`, `length/2` predicates

**Q4: Natural numbers in Prolog (zero and successor function):**
- **insertHead** is the correct definition (review carefully)

**Q5: Predicate for length of a list (s() as a number):**
- ✅ s(l, rl)

**Q6: Predicate for sum of elements in a list:**
- ✅ sl, rl)

### Prolog Program Predicates (Common Data Q7-Q11):

Given predicates: `snakes/2`, `parrots/2`, `predOf/3`, `multiCol/4`, `mulList/4`, `sublist/4`, `subseq/4`

**Line 2 (snakes rule body):** `sameas(A, B)`  
**Line 4 (predOf rule body):** `—`  
**Line 5 (mulList rule):** `mulList(C, St, End)` → `suffix(Out, Sta, End)`  
**Line 9 (multiCol rule body):** `sameas(A, B)`  
**Line 7 (sublist rule body):** `prefix(1B, sl, B(p))`  
**Line 10 (subseq rule body):** `ordered(A, B)`  

**Q12: Total number of solutions using Prolog `findall`:**
- ✅ Answer: 8

**Q13: Correct statements:**
- ✅ All FOL formulas can be expressed as Horn Clauses — **FALSE!**
- ✅ SLD resolution always terminates — **FALSE!**
- ✅ None of the above — **CORRECT**

> [!IMPORTANT]
> **Key Prolog Concepts:**
> - **SLD Resolution** does NOT always terminate
> - **NOT all FOL formulas** can be expressed as Horn Clauses
> - Prolog uses **depth-first search** with **backtracking**
> - **Cut (!)** prevents backtracking
> - **Negation as failure:** `\+` (not provable)

---

<a name="week-7"></a>
## 📓 WEEK 7: PROLOG PROGRAMMING & EXECUTION

### Assignment 7 Questions & Answers

**Q1: Which of the following is a regular goal? (From Proof 1-4)**
- ✅ Both proofs use SLD resolution!
- ✅ Proof 1 uses SLD resolution but Proof 2 does not

**Q2: `\+X` denotes an atomic formula in PL, then negation by failure in Prolog:**
- ✅ returns true when all attempts to prove X fail
- ✅ returns false when at least one attempt to prove X succeeds

**Q3: Prolog program tracing — which statement is true:**
- ✅ Goal trace questions relate to finding paths and nodes in data structures

**Q4: SWI Prolog program with `consult` (two versions of predicates):**
- ✅ consult(1,1) contains red cut
- ✅ consult(1,2) contains green cut

**Q5: Study the Prolog program WITHOUT using tabling:**
- ✅ None of the above (query does NOT terminate without tabling)

**Q6: In top-level, independence refers to:**
- ✅ restarting the same code/rule pair from firing again and again
- ✅ reducing if content predicate that do not match rules
- ✅ blocking of the same code/rule pair from firing again and again

### Prolog Working Memory & Rule-Based Systems

**Q7-Q12: Working Memory and Conflict Resolution:**

Given a Production System with a Working Memory where knowledges are represented by sequence numbers:

**Q7: The best value of `new-default` is:** `4`  
**Q8: The best value of x:** `(Type, Number) 4`

**Regarding a Regular Fire rule:**
- ✅ It has equal footing
- ✅ Pointers: text is full
- ✅ Power is between 100 and 200 hp

**In the first round, which of the following will occur in the conflict set?**
- ✅ Greedycar: rule_194, 200, 1100
- ✅ MediumCar: rule_201, 201, 1390

**If PRIORITY is used as the conflict resolution strategy, then which rule will fire?**
- ✅ PRIORITY (rule_145, 210, 224)

**If RECENCY is used as the conflict resolution strategy, then which rule will fire?**
- ✅ GainerCar (rule_249, 201, 1310)

---

<a name="week-8"></a>
## 📒 WEEK 8: KNOWLEDGE REPRESENTATION, RDF & SEMANTIC WEB

### Assignment 8 Questions & Answers

**Q1: FOL representation of "All apples are red":**
- ✅ ∀x(Apple(x) ⊃ Red(x))

**Q2: FOL representation of "Some apples are red":**
- ✅ ∃x(Apple(x) ∧ Red(x))

> [!TIP]
> **CRITICAL PATTERN to remember:**
> - "All X are Y" → ∀x(X(x) **⊃** Y(x)) — uses IMPLICATION!
> - "Some X are Y" → ∃x(X(x) **∧** Y(x)) — uses CONJUNCTION!
> - NEVER mix these up!

**Q3: Properties of the sibling relation:**
- ✅ Binary relation
- ✅ Transitive relation
- ✅ Irreflexive relation

**Q4: FOL representation for grandfather relation (GF(x,y) defines x as grandfather of y):**
- ✅ ∀x∀y(GF(x,y) ≡ ∃z(Father(x,z) ∧ Parent(z,y)))
- ✅ ∀x∀y(GF(x,y) ≡ ∃z(Father(x,z) ∧ Parent(z,y)))

**Q5: FOL representation of "All students enroll for courses":**
- ✅ ∀x(Student(x) ⊃ ∃y(Enroll(x,y) ∧ Course(y)))

**Q6: FOL representation of "Squares are rectangles and rectangles are quadrilaterals":**
- ✅ ∀x(Square(x) ⊃ Rectangle(x)) ∧ ∀x(Rectangle(x) ⊃ Quadrilateral(x))
- ✅ ∀x(Square(x) ⊃ Rectangle(x) ∧ ∀x(Rectangle(x) ⊃ Quadrilateral(x)))

**Q7: Monotonic property of FOL domain:**
- ✅ This domain can be modeled in FOL
- ✅ This domain violates the monotonic property of FOL

**Q8: Given ∀XB {∀x∀y [P(x,y) ∧ Q(x,z) ⊃ R(x,y)] } and a set of individuals (a,b), which interpretations satisfy the KB?**
- ✅ { P(a,b), Q(a), R(a,b) }
- ✅ { P(a,b), Q(b), R(a,b) }
- ✅ { P(b,a), Q(b), R(b,a) }
- ✅ { R(a,b) }

**Q9: Semantic representation of chess match statement:**
- ✅ Match(WCM21) ∧ Player(WCM21, Nepo) ∧ Player(WCM21, Carlsen) ∧ Year(WCM21, 2021) ∧ City(WCM21, Dubai)

**Q10: Elements used by RDF/RDFS to model a domain:**
- ✅ Entities
- ✅ Properties
- ✅ Resources
- ✅ Statements

**Q11: What do you recall about `:thing :poet :laiz-dilwara` from the lecture?**
- ✅ It is a triple
- ✅ It is a statement
- ✅ It is an edge in a semantic graph
- ✅ It follows Turtle format

**Q12: RDF/RDFS document in Turtle format — what can be inferred?**
- ✅ :thing is an instance of :thing
- ✅ :laiz-dilwara is an instance of :poet
- ✅ :poet is a property
- ✅ :thing is an instance of rdfs:Resource

---

<a name="week-9"></a>
## 📔 WEEK 9: DESCRIPTION LOGIC (DL) & ALC

### Assignment 9 Questions & Answers

**Q1: In DL, ALC stands for:**
- ✅ Attributive Language with Complement

**Q2: In DL, which of the following formulas denote concepts?**
- ✅ ∀hasSibling.Rich
- ✅ Teens ⊓ Happy
- ✅ ¬Doctor

**Q3: The NNF of ((Teens ⊓ ∃owns.Apple) ⊔ Happy) is:**
- ✅ (¬Teens ⊔ (∀owns. ¬Apple) ⊔ Happy) ⊓ (¬Happy ⊔ (Teens ⊓ ∃owns.Apple))

**Q4: Select the correct DL representation of "Some apples are red":**
- ✅ Apple ⊓ Red ⊑ ⊤

**Q5: Select the correct DL representation of "All apples are red":**
- ✅ Apple ⊑ Red

> [!IMPORTANT]
> **DL Representation Patterns:**
> - **"All A are B"** → A ⊑ B (subsumption)
> - **"Some A are B"** → A ⊓ B ⊑ ⊤ (non-empty intersection)
> - **"No A are B"** → A ⊓ B ⊑ ⊥ (empty intersection)

**Q6: DL representation of "People whose all children are vaccinated are proactive":**
- ✅ (People ⊓ ∀hasChild.Vaccinated) ⊑ Proactive

**Q7: ALC knowledge base inference (KB with Doctor, hasChild, etc.):**
- ✅ KB ⊨ (∃hasChild.Doctor)(Ada)

**Q8: ALC knowledge base entailments (Parent, OCC, POCC, etc.):**
- ✅ KB ⊨ Parent(Max)
- ✅ KB ⊨ POCC(Max)
- ✅ KB ⊨ Doctor(Amy)

**Q9: Motivation for small set of predicates in Conceptual Dependency:**
- ✅ that one must define rules to operate on predicates, and one wants to keep the number of rules to a minimum

**Q10: Programs by Roger Schank's Yale group:**
- ✅ FRUMP
- ✅ MARGIE
- ✅ QUALM
- ✅ BORIS

**Q11: Conceptual Dependency (CD) theory is:**
- ✅ a representation scheme based on a small set of predicate names
- ✅ an attempt to identify a small set of actions for every day world
- ✅ an attempt to represent the meaning of natural language words

---

<a name="week-10"></a>
## 📗 WEEK 10: CONCEPTUAL DEPENDENCY (CD) THEORY & SCRIPTS

### Assignment 10 Questions & Answers

**Q1: A conceptualization in CD theory is:**
- ✅ the equivalent of a well formed formula in a formal logic
- ✅ a description of a basic event or action
- ✅ a description of a state in the domain

**Q2: Which of the following hold for the CD theory?**
- ✅ Nominals stand for objects and people
- ✅ Actions are acts done by nominals
- ✅ A Tamil sentence can be mapped to CD theory

**Q3: The program MARGIE processed a natural language sentence by:**
- ✅ constructing a syntactic parse tree of the input sentence
- ✅ identifying the concepts involved in the semantic representation
- ✅ making inferences commonly associated with the concepts involved

**Q4: A program constructing a conceptualization using ATRANS:**
- ✅ will infer that the object has a new owner
- ✅ identify the giver and the recipient

**Q5: The CD action MBUILD:**
- ✅ can be used to identify a causal build up in the story
- ✅ can be used to represent an actor making an inference

**Q6: "Sneha bought and icecream and ate it" — CD representation:**
- ✅ would involve the use of two instances of ATRANS
- ✅ would normally imply the use of PTRANS of the icecream
- ✅ would involve the use of INGEST by Sneha

**Q7: Verbs like kill, hate and love:**
- ✅ are represented by states or state changes in CD theory
- ✅ involve a causal relation in CD theory

**Q8: Verbs like remember and forget:**
- ✅ refer to movement of information in the between different compartments in memory models
- ✅ require the use of the CD action MTRANS

**Q9: "Causal chain completion" in story processing refers to:**
- ✅ Inferring intervening events that must have taken place between two events explicitly mentioned in the story

**Q10: Script Applier Mechanism — module ELI does the following:**
- ✅ extracts conceptual elements from the story that are explicit □

**Q11: The role of the module PP-Memory in SAM is:**
- ✅ serve as a memory of scriplat roles and props
- ✅ to match incoming tokens to the expected ones in the script

### CD Theory Primitives — MEMORIZE THESE

| Primitive | Meaning |
|-----------|---------|
| **ATRANS** | Transfer of an abstract relationship (give, buy, take) |
| **PTRANS** | Physical transfer of location of an object (go, move) |
| **MTRANS** | Transfer of mental information (tell, see, hear) |
| **MBUILD** | Building new information from old (decide, imagine, conclude) |
| **INGEST** | Taking something into the body (eat, drink, smoke, breathe) |
| **EXPEL** | Expelling from the body |
| **PROPEL** | Applying a physical force (push, pull, throw) |
| **MOVE** | Moving a body part |
| **GRASP** | Physically grasping an object |
| **SPEAK** | Producing a sound |
| **ATTEND** | Focusing attention (look, listen) |

---

<a name="week-11"></a>
## 📘 WEEK 11: PLANNING (PAM), FRAMES & INHERITANCE NETWORKS

### Assignment 11 Questions & Answers

**Q1: The program PAM was designed:**
- ✅ to understand natural language stories
- ✅ to work with relations between goals and plans of an actor
- ✅ to work with relations between goals and actions of an actor

**Q2: PAM may try to explain an action mentioned in the story:**
- ✅ by hypothesizing that it as a part of a plan the actor is assumed to have
- ✅ by matching it with an expectation generated by a known plan of the actor

**Q3: PAM may explain a plan that the actor is supposed to be using by:**
- ✅ its knowledge of which goals are achieved by the plan
- ✅ by recognizing that the plan can be used to resolve a goal conflict
- ✅ by recognizing that the plan is used to resolve goal competition with another actor

**Q4: The filler of a slot in an individual frame may be:**
- ✅ a value
- ✅ a pointer to another individual frame
- ✅ a pointer to a generic frame
- ✅ can be an attached procedure

**Q5: Inheritance is said to be strict if:**
- ✅ an entity cannot override an inherited value

**Q6: An entity cannot override an inherited value:**
- ✅ (This is the definition of strict inheritance)

**Q7: Edges in an inheritance hierarchy represent:**
- ✅ a class-subclass relation  
- ✅ a is-a/subset relation

**Q8: Inheritance hierarchy with conclusion node C and D, a node A:**
- ✅ can have the conclusion "A is a C"
- ✅ can have the conclusion "A is not C"
- ✅ can have both the conclusions "A is a C" and "A is not a C"

**Q9: A credulous extension of a (possibly ambiguous) inheritance hierarchy with respect to a node A:**
- ✅ is a subgraph of the inheritance hierarchy
- ✅ has a path from A to every node in the extension
- ✅ does not support both a conclusion C and the conclusion ¬C

**Q10: Admissible edges with respect to node 'a' in the graph:**
- ✅ a → B, a → ¬B, B → C, B → ¬C, D → E (see graph for specific edges)

**Q11: The redundant edges in the above graph with respect to 'a':**
- ✅ None of the above

**Q12: Admissible paths:**
- ✅ a, B, C, D, E
- ✅ a, B, ¬C
- ✅ a, B, ¬C, D
- ✅ a, ¬B, ¬C, D, E

**Q13: Which beliefs hold for 'a'?**
- ✅ a → E
- ✅ a → ¬C
- ✅ a → D

---

<a name="week-12"></a>
## 📙 WEEK 12: DEFAULT REASONING, EVENT CALCULUS & EPISTEMIC LOGIC

### Assignment 12 Questions & Answers

**Q1: Identify which of the following are definitely universally true statements:**
- ✅ Men are mortal
- ✅ Birds are two-legged, egg-laying creatures that have beaks

**Q2: Using Generalized Closed World Assumption (GCWA) for KB. The predicates p, q, r are atomic predicates. KB = {p ⊃ q ∨ r, q ∨ ¬r}. Which are entailed by KB under GCWA?**
- ✅ Neither p nor ¬q
- ✅ Both p and ¬q
- (Review specific entailments carefully)

**Q3: Set of statements that define a minimal/credulous model for circumscription on the given KB (K8 is a bird, Chilly is a penguin, Tweety is a canary):**
- ✅ Ab(¬x)
- ✅ Ab(¬chilly) ∧ ¬Ab(tweety)

**Q4: Which sets have models in the KB for the CB?**
- ✅ ¬Flies(¬chilly), Flies(tweety, ¬chilly)
- ✅ ¬Flies (¬chilly, ¬chilly), Flies (¬tweety)
- ✅ ¬Flies(¬chilly, tweety, ¬chilly), Flies(¬chilly)

**Q5: Given the KB (about birds, penguins, flying):**
- The problem: Circumscription form is ___
- ✅ It is unable to conclude that Peppy cannot fly

**Q6: Which of the following statements are true?**
- ✅ In Default logic, we provide a mechanism for specifying explicitly which statements should be added to the KB when it is consistent to do so
- ✅ In Circumscription, we minimize only the abnormal predicates

**Q7: Default theory Γ = ⟨D, W⟩ — What are the possible extensions?**
- ✅ { Egg-layer(tweety), Egg-layer(cot), ¬Bird(cot), Female(tweety), Female(cot), Bird(city) }

**Q8: What are the stable sets for the default theory in Q7?**
- ✅ F = { Bird(cot) }
- ✅ F = { Bird(cot), bird(tweety) }
- ✅ F = { Bird(tweety) }
- ✅ None of the above

**Q9: Initiate(x,f,t) — Discrete Event Calculus (DEC):**
- ✅ When action a Happens at time t1 = 1
- ✅ When action a Happens at time β1 = 5  and t is not Clipped between β1 = 5 and t1
- ✅ When f was true initially and t is not Clipped between 0 and t

**Q10: Narrative about Russian forces (Discrete Event Calculus):**
- ✅ Happens (Invasion(russia, ukraine, !!)
- ✅ Happens (Bomb(bomb,ukraine, maternity-Hospital, t2))
- ✅ Additional entailments per the narrative

**Q11: The Frame Problem in the context of Event Calculus:**
- ✅ The problem of deciding which fluents remain/become true at future time instances

**Q12: "Putin is going to attack Ukraine" — K_putin, K_biden:**
- ✅ Putin knows that Biden considers it possible that P

**Q13: 4 children (Aman, Bindu, Charu, Deep) — minimum questions to determine muddy:**
- ✅ 3

---

<a name="cheat-sheet"></a>
## 🏆 MASTER CHEAT SHEET — LAST MINUTE REVISION

### 1. FOL Quantifier Patterns (MOST TESTED!)

| English Statement | FOL Representation |
|---|---|
| All X are Y | ∀x (X(x) ⊃ Y(x)) |
| Some X are Y | ∃x (X(x) ∧ Y(x)) |
| No X are Y | ∀x (X(x) ⊃ ¬Y(x)) |
| Only X are Y | ∀x (Y(x) ⊃ X(x)) |
| Not all X are Y | ¬∀x (X(x) ⊃ Y(x)) ≡ ∃x (X(x) ∧ ¬Y(x)) |

> [!CAUTION]
> **"All" uses IMPLICATION (⊃), "Some" uses CONJUNCTION (∧)** — The #1 most common mistake!

### 2. Skolemization Steps
1. Eliminate biconditionals and implications
2. Move negations inward
3. Standardize variables apart
4. Move quantifiers to the left (prenex form)
5. **Skolemize:** Replace each ∃x with:
   - A new **Skolem constant** if NOT in the scope of any ∀
   - A new **Skolem function** of ALL universally quantified variables whose scope contains ∃x
6. Drop universal quantifiers

### 3. Resolution Refutation Method
1. Convert all KB sentences to clause form
2. Negate the query (what you want to prove)
3. Convert negated query to clause form
4. Add negated query clauses to KB
5. Apply resolution repeatedly
6. If you derive the **empty clause (□)**, the original query is **proved**!

### 4. Prolog Key Rules
- **Depth-first search** with left-to-right rule selection
- **Unification** without occurs check
- **Cut (!)** prevents backtracking past the cut point
- **Green cut** = doesn't change semantics
- **Red cut** = changes program behavior
- **Negation as failure** `\+` is NOT logical negation

### 5. DL (Description Logic) Quick Reference

| DL Symbol | Meaning |
|-----------|---------|
| ⊤ (top) | Universal concept (everything) |
| ⊥ (bottom) | Empty concept (nothing) |
| ⊓ | Intersection (AND) |
| ⊔ | Union (OR) |
| ¬ | Complement (NOT) |
| ∀R.C | Value restriction |
| ∃R.C | Existential restriction |
| ⊑ | Subsumption (is-a) |

### 6. Knowledge Representation Formalisms

| Formalism | Key Feature |
|-----------|-------------|
| Semantic Networks | Graph-based, IS-A relations |
| Frames | Slot-filler structures, inheritance |
| RDF/RDFS | Triple-based (subject-predicate-object) |
| Description Logic | Formal semantics, decidable reasoning |
| Conceptual Dependency | Primitive acts for NL understanding |
| Scripts | Stereotypical event sequences |

### 7. CD Theory Primitives (FREQUENTLY TESTED!)

| Action | Use |
|--------|-----|
| ATRANS | buy, give, sell, take |
| PTRANS | go, walk, move |
| MTRANS | tell, see, read, hear |
| MBUILD | decide, think, conclude |
| INGEST | eat, drink, breathe |
| PROPEL | push, kick, throw |
| SPEAK | say, scream |
| ATTEND | look, listen, smell |

### 8. Event Calculus Key Predicates

| Predicate | Meaning |
|-----------|---------|
| Happens(a, t) | Action a occurs at time t |
| HoldsAt(f, t) | Fluent f is true at time t |
| Initiates(a, f, t) | Action a starts fluent f at time t |
| Terminates(a, f, t) | Action a ends fluent f at time t |
| Clipped(t1, f, t2) | Fluent f terminated between t1 and t2 |
| Initially(f) | Fluent f is true at time 0 |

### 9. Frame Problem
- **What is it?** The problem of determining which fluents remain unchanged when an action occurs
- **Solution:** Frame axioms / Event Calculus handles this via `Clipped` predicate

### 10. Inheritance Networks
- **Strict inheritance:** Cannot override inherited values
- **Credulous extension:** Any consistent path through the network
- **Skeptical extension:** Only conclusions common to ALL credulous extensions
- **Admissible path:** Path with no "preempted" edges
- **Redundant edge:** Edge that can be derived from other edges

### 11. Default Logic
- Default rule: A : B / C (if A is known and B is consistent, conclude C)
- **Extension:** A maximal consistent set of conclusions
- Multiple extensions possible → **ambiguity**

### 12. Key "Trick Question" Answers

| Question Pattern | Answer |
|---|---|
| Does resolution always terminate in FOL? | **NO** (semi-decidable) |
| Can all FOL formulas be expressed as Horn Clauses? | **NO** |
| Does SLD resolution always terminate? | **NO** |
| Is Propositional Logic decidable? | **YES** |
| Is FOL decidable? | **NO** (semi-decidable) |
| Forward chaining is sound? | **YES** |
| Backward chaining is sound? | **YES** |
| Can FOL handle non-monotonic reasoning? | **NO** (FOL is monotonic!) |

---

## 🎯 EXAM STRATEGY

1. **Start with what you know** — answer confident questions first
2. **FOL representation questions** — use the "All→⊃, Some→∧" rule
3. **Resolution problems** — work systematically, show all steps
4. **DL questions** — convert to FOL mentally and then pick the DL equivalent
5. **CD theory** — memorize the 11 primitives, they're directly tested
6. **Prolog** — trace execution step by step, watch for cut and negation
7. **Week 12** — focus on Event Calculus predicates and Default Logic extensions

> [!TIP]
> **Last-minute priority:** Focus on Weeks 4, 5, 8, 9, and 12 — these contain the highest density of exam-worthy material!

---

*Good luck on your exam! You've got this! 💪*
