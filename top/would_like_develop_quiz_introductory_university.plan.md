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

REFERENCE POINTERS (optional):
CAS/Random.md
Authoring/Inputs/Numerical_input.md
Authoring/Answer_Tests/Equivalence.md
Authoring/Feedback.md

ADDITIONAL LANGUAGES (optional): (none)
