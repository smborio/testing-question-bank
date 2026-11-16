GOAL (non-negotiable): Evaluate exactly a definite integral that needs substitution followed by partial fractions (calculate). Week 9 quiz of an introductory university calculus course; formative.

STRUCTURE (non-negotiable): Single part, one expression input. Question text: "Evaluate the definite integral ∫_0^1 2x/((x^2+a)(x^2+b)) dx" with the randomised a and b, then the hint "Consider the substitution u = x^2." Then: "Enter the exact value." No intermediate answers, no further scaffolding. The hint must not mention partial fractions.

RANDOMIZATION (negotiable): Integers a, b with 1 ≤ a < b ≤ 6, which gives 15 variants (a<b avoids repeated factors and swapped duplicates). The worked solution has the same structure for every variant.

ANSWER TESTS (negotiable): Compare the student's expression with the model answer (1/(b-a))*ln(b*(1+a)/(a*(1+b))), accepting any mathematically equivalent exact form (a single logarithm, a difference of logarithms, etc.). Decimal answers are refused by an input restriction (no floats) so the student is told to give an exact value. Full marks only for a correct value. Form only: not allowed (value matters).

FEEDBACK (negotiable): Correct: brief confirmation. Wrong answers:
- ln(b*(1+a)/(a*(1+b))) without the factor 1/(b-a): 0 marks, hint about the constant from partial fractions, 1/((u+a)(u+b)) = (1/(b-a))(1/(u+a) - 1/(u+b)).
- -(1/(b-a))*ln(b*(1+a)/(a*(1+b))) (inverted logarithm): 0 marks, hint to check the order of the terms/signs when evaluating at the limits.
Any other wrong answer: generic hint to check the substitution (limits stay 0 and 1) and the partial fractions. Worked solution: substitute u = x^2, du = 2x dx, limits 0 to 1; integral of du/((u+a)(u+b)); partial fractions with 1/(b-a); integrate to logs; evaluate and combine into the final answer.

PRT/QTEST SUGGESTIONS: Accept the difference-of-logarithms form (1/(b-a))*(ln((1+a)/(1+b)) - ln(a/b)).

REFERENCE POINTERS (optional):
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Inputs/Input_options.md
Authoring/Random.md

ADDITIONAL LANGUAGES (optional): (none)
