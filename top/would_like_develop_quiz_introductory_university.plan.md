GOAL: Evaluate exactly the definite integral of 2x/((x^2+a)(x^2+b)) from 0 to 1. It tests the substitution u = x^2 combined with partial fractions (calculate). Exact answer: (1/(b-a))*ln(b(1+a)/(a(1+b))).

DESCRIPTION: The student sees one part: "Evaluate the definite integral ∫₀¹ 2x/((x²+a)(x²+b)) dx. Hint: consider the substitution u = x². Enter the exact value (not a decimal approximation)." There is one algebraic input that expects an exact expression, usually with a logarithm. Decimals are refused. The question is short and formative, for a Week 9 quiz.

STRUCTURE: A single part with one expression input and no intermediate steps.

RANDOMIZATION: Integers a and b with 1 <= a < b <= 6. This gives 15 variants of similar difficulty, with no repeated factors (a = b is excluded). The worked solution is the same for every variant.

ANSWER TESTS: The student's expression must be algebraically equivalent to (1/(b-a))*ln(b(1+a)/(a(1+b))). Any equivalent exact form keeps full marks, such as a single logarithm, a difference of logarithms, or fully expanded logarithms. Full marks need the correct value, and form alone is not enough. Floats are forbidden in the input. The words "int" and "diff" are also forbidden. The answer is checked after a validation step, and the student must confirm it.

FEEDBACK:
- Correct: scores 1 with no extra message.
- Mistake 1: the answer without the 1/(b-a) factor, ln(b(1+a)/(a(1+b))). Score 0. Hint: "You are missing the partial-fraction constant 1/(b-a)."
- Mistake 2: the inverted logarithm, (1/(b-a))*ln(a(1+b)/(b(1+a))). Score 0. Hint: "Check the order and signs inside the logarithm: the upper-limit value goes on top."
- Any other wrong answer: score 0. Generic hint: "Check the substitution u = x² and your partial fractions, then enter the exact value."
- Worked solution: with u = x² and du = 2x dx, the limits stay 0 and 1. The integral becomes ∫₀¹ du/((u+a)(u+b)). Partial fractions give (1/(b-a))(1/(u+a) − 1/(u+b)). Integrating and evaluating from 0 to 1 gives the exact value. It names the methods: substitution, then partial fractions.

IMPLEMENTATION NOTES:
- a is drawn as rand(5)+1 and b as a+1+rand(6-a), which keeps a < b <= 6.
- The wrong-answer values wrong1 and wrong2 are computed in the question variables from a and b.
- Both mistake checks use the same equivalence test as the correct answer.
- The "missing 1/(b-a)" branch (node 1) has no test case that reaches it. The build's test of wrong1 ended at node 2 on some variants and at node 1 on others, so it was not kept as a test case. This is expected when b-a = 1, because wrong1 then equals the correct answer. In that variant the correct answer is accepted first.
- The test cases cover the model answer, a difference of logarithms, fully expanded logarithms, the inverted answer, and zero.

ADDITIONAL LANGUAGES: (none)