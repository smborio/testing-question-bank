GOAL (non-negotiable): Evaluate exactly a definite integral that needs a substitution followed by partial fractions (calculate). The substitution is given as a hint; the student must then see that partial fractions are needed.
STRUCTURE (non-negotiable): Single part. Question: evaluate ∫₀¹ 2x/((x²+a)(x²+b)) dx. Hint shown: "Consider the substitution u = x²." One expression input, no intermediate steps. Part of a Week 9 quiz, short, formative.
RANDOMIZATION (negotiable): integers a, b with 1 ≤ a < b ≤ 6 (15 variants), so no repeated factor and no swapped duplicates. Difficulty stays the same; the worked solution is the same for all. Agreed with the user.
ANSWER TESTS (negotiable): Check that the answer equals (1/(b−a))·ln(b(1+a)/(a(1+b))) mathematically, accepting any equivalent exact form (single logarithm, difference of logarithms, logs of products, etc.). Decimal approximations are rejected (my choice, to be confirmed). The answer must be the exact value, not only its form. Form only: not allowed.
FEEDBACK (negotiable): Right answer: confirmation. Worked solution: u = x², du = 2x dx, limits stay 0 and 1; ∫₀¹ du/((u+a)(u+b)); partial fractions 1/((u+a)(u+b)) = (1/(b−a))(1/(u+a) − 1/(u+b)); evaluate to (1/(b−a))·ln(b(1+a)/(a(1+b))). Likely mistakes, each score 0 with a hint:
- missing factor: ln(b(1+a)/(a(1+b))) → hint: check the constant in the partial fractions, 1/(b−a).
- inverted logarithm (sign error): (1/(b−a))·ln(a(1+b)/(b(1+a))) → hint: check the signs of the two partial-fraction terms and which log is subtracted.
Silent marks: not allowed.
PRT/QTEST SUGGESTIONS: (none)
REFERENCE POINTERS (optional):
Authoring/Answer_Tests/Equivalence.md
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Feedback.md
CAS/Random.md
ADDITIONAL LANGUAGES (optional): (none)
