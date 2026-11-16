# Metadata — would_like_develop_quiz_introductory_university.xml

Running record of every agent (and user) action on this question that
isn't the XML itself: the reasoning, findings, improvement notes, and
reference lookups behind each change. Entries are appended in order,
newest at the bottom. The XML changes themselves are recorded by git —
this file holds the substance and meaning behind them, not the diffs.

## Entry 1 — planner · plan locked (2026-11-16T16:16:36)

**Reference files fetched:**
- (none)

**Reference files recommended by Planner:**
- CAS/Random.md
- Authoring/Inputs/Numerical_input.md
- Authoring/Answer_Tests/Equivalence.md
- Authoring/Feedback.md

```text
GOAL (non-negotiable): Evaluate exactly the definite integral of 2x/((x^2+a)(x^2+b)) from 0 to 1. Tests combining the substitution u = x^2 with partial fractions (calculate). Exact answer: (1/(b-a))*ln(b(1+a)/(a(1+b))).

STRUCTURE (non-negotiable): A single part with one expression input and no intermediate steps. The question text says: "Evaluate the definite integral ∫₀¹ 2x/((x²+a)(x²+b)) dx. Hint: Consider the substitution u = x². Enter the exact value." Short, formative, part of a Week 9 quiz.

RANDOMIZATION (negotiable): integers a and b with 1 <= a < b <= 6, so a is less than b (no repeated factors, no swapped duplicates). This gives 15 variants of similar difficulty. The worked solution is the same for every variant.

ANSWER TESTS (negotiable): Check that the student's expression is mathematically equivalent to the exact value, accepting any equivalent exact logarithmic form (a single logarithm, a difference of logarithms, a rearranged constant). Full marks need the correct value. Decimal approximations are rejected: the input must refuse floats, with a message asking for an exact value. Form only: not allowed.

FEEDBACK (negotiable):
- Correct: confirm briefly.
- Mistake 1: the answer without the 1/(b-a) factor, ln(b(1+a)/(a(1+b))). Score 0, hint about the partial-fraction constant 1/(b-a).
- Mistake 2: the inverted logarithm, (1/(b-a))*ln(a(1+b)/(b(1+a))). Score 0, hint about the signs/order inside the logarithm.
- Any other wrong answer: a generic hint to check the substitution and the partial fractions.
- Worked solution: with u = x^2 and du = 2x dx the limits stay 0 and 1, so the integral is ∫₀¹ du/((u+a)(u+b)). Partial fractions give (1/(b-a))(1/(u+a) - 1/(u+b)). Integrating and evaluating gives the exact value above. It names the methods: substitution, then partial fractions.

PRT/QTEST SUGGESTIONS: (none)
```

## Entry 2 — author · build round 1 (2026-11-16T16:17:31)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: CAS/Random.md, Authoring/Inputs/Input_options.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Answer_Tests/Grading_recipes.md, Authoring/Potential_response_trees.md, Authoring/Feedback.md, STACK_question_admin/Testing.md
```

## Entry 3 — planner · review (2026-11-16T16:22:01)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=False)
Feedback to Author: Make four changes and keep everything else as is. 1) Make the validation message on input ans1 compact. 2) Rename the question to "Definite integral: substitution + partial fractions". 3) Remove the duplicate qtest 2 ("Correct"), which repeats qtest 1. 4) Add a qtest "Fully expanded logs (four terms)". It enters (ln(b)+ln(1+a)-ln(a)-ln(1+b))/(b-a), written with the question variables so it holds on every variant. It expects score 1 and answer note prt_ans1-1-T.
```

## Entry 4 — author · build round 2 (2026-11-16T16:22:38)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: CAS/Random.md, Authoring/Inputs/Input_options.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Answer_Tests/Grading_recipes.md, Authoring/Potential_response_trees.md, Authoring/Feedback.md, STACK_question_admin/Testing.md
Deviations reported: There is no field for the question name, so I could not rename it to "Definite integral: substitution + partial fractions". Please set that name outside these fields. I set SHOWVALIDATION to 3, which I believe is STACK's compact option without the variable list. The old value 1 may already have been compact, so please check that 3 is what you meant. The new qtest is numbered 6 and placed before qtest 4, and I did not renumber the others. I wrote its expected branch as NODE0-T, the root node's true branch. STACK records that branch as prt_ans1-1-T because answer notes count nodes from 1.
```

## Entry 5 — planner · plan locked (2026-11-16T16:28:18)

**Reference files fetched:**
- (none)

**Reference files recommended by Planner:**
- CAS/Random.md
- Authoring/Inputs/Numerical_input.md
- Authoring/Answer_Tests/Equivalence.md
- Authoring/Feedback.md

```text
GOAL (non-negotiable): Evaluate exactly the definite integral of 2x/((x^2+a)(x^2+b)) from 0 to 1. Tests combining the substitution u = x^2 with partial fractions (calculate). Exact answer: (1/(b-a))*ln(b(1+a)/(a(1+b))).

STRUCTURE (non-negotiable): A single part with one expression input and no intermediate steps. The question text says: "Evaluate the definite integral ∫₀¹ 2x/((x²+a)(x²+b)) dx. Hint: Consider the substitution u = x². Enter the exact value." Short, formative, part of a Week 9 quiz.

RANDOMIZATION (negotiable): integers a and b with 1 <= a < b <= 6, so a is less than b (no repeated factors, no swapped duplicates). This gives 15 variants of similar difficulty. The worked solution is the same for every variant.

ANSWER TESTS (negotiable): Check that the student's expression is mathematically equivalent to the exact value, accepting any equivalent exact logarithmic form (a single logarithm, a difference of logarithms, a rearranged constant). Full marks need the correct value. Decimal approximations are rejected: the input must refuse floats, with a message asking for an exact value. Form only: not allowed.

FEEDBACK (negotiable):
- Correct: confirm briefly.
- Mistake 1: the answer without the 1/(b-a) factor, ln(b(1+a)/(a(1+b))). Score 0, hint about the partial-fraction constant 1/(b-a).
- Mistake 2: the inverted logarithm, (1/(b-a))*ln(a(1+b)/(b(1+a))). Score 0, hint about the signs/order inside the logarithm.
- Any other wrong answer: a generic hint to check the substitution and the partial fractions.
- Worked solution: with u = x^2 and du = 2x dx the limits stay 0 and 1, so the integral is ∫₀¹ du/((u+a)(u+b)). Partial fractions give (1/(b-a))(1/(u+a) - 1/(u+b)). Integrating and evaluating gives the exact value above. It names the methods: substitution, then partial fractions.

PRT/QTEST SUGGESTIONS: (none)
```

## Entry 6 — author · build round 1 (2026-11-16T16:29:06)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: CAS/Random.md, Authoring/Inputs/Input_options.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Potential_response_trees.md, Authoring/Answer_Tests/Grading_recipes.md, Authoring/Feedback.md
```

