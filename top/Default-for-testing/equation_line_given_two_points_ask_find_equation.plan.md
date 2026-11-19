GOAL (non-negotiable): Edit of the existing question. Given two points, the student finds the equation of the line through them and writes it as y=mx+c (task: calculate). The gradient is a non-integer rational with |m|<3; the y-intercept is a small non-integer rational. Assessment is built around what the answer shows (form, straight line, gradient, intercept, points it passes through), not around a list of anticipated wrong answers.

STRUCTURE (non-negotiable): Single part, one algebraic input pre-filled "y=", one grading tree. Wording unchanged: "Find the equation of the line, written in the form y=mx+c. Give any fractions as fractions." Decimals stay rejected, implicit multiplication (5x) allowed, validation shown.

RANDOMIZATION (negotiable): Constructive, no rejection sampling; question variables hold only the random data and the model answer.
- q in {2,3,4,5}; gradient m=p/q with p = ±k, k from 1..3q-1 coprime to q (built as a filtered list), so m is never a whole number and |m|<3.
- Point A: xa a non-multiple of q in -5..5 (so neither point is on the y-axis). ya = round(m*xa)+e, e in {-2..2}, so ya is an integer and the intercept stays small.
- Point B: xb = xa + q*k2, k2 in {-2,-1,1,2}; yb = ya + p*k2. Integer coordinates guaranteed; the points may be on the same or opposite sides of the y-axis, and xb differs from xa.
- c = ya - m*xa has denominator q, so it is never an integer, never 0, and |c|<=2.5 plus a fraction of at most 1/2 (small).
- Swap which point is called A/B at random so the order of x does not give away the sign of m.
- Same method in the worked solution for every variant.

ANSWER TESTS (negotiable): All assessment variables (the student's right-hand side, its gradient and intercept, the check against each point) are defined in the feedback variables, not the question variables. Checks in order:
1. Is it an equation? If not (bare expression such as mx+c, or 0): 0, "Your answer must be an equation starting y=."
2. Is it a straight line, i.e. y alone on the left, or an equation that is linear in x and y? A non-linear equation (x^2, 1/x terms) scores 0: "This is not a straight line."
3. Does it represent the correct line? If it is the correct line but y is not alone on the left (e.g. 4y=3x+2): 0.5, "This is the right line but not in the form y=mx+c; rearrange."
4. With y alone: right-hand side equivalent to m*x+c: 1 (any equivalent form, e.g. (p*x+q*c)/q).
5. Gradient correct, intercept wrong: 0.5.
6. Gradient wrong, but the line passes through A or through B (the intercept is consistent with a given point): 0.4, error carried forward.
7. Otherwise 0.
Check the gradient by the coefficient of x in the right-hand side; for the intercept, the constant term. Form alone never earns marks.

FEEDBACK (negotiable): Only evidence-based statements; no guessing of the student's method.
- Correct: "Correct."
- Not an equation / not straight / not y= : the hints in steps 1-3.
- Gradient right, intercept wrong: "Your gradient is correct, but your line does not pass through A and B. Substitute a point to check c."
- Gradient wrong, line through A (or B) only: "Your line passes through A (or B) but not the other point, so the gradient is not correct. Recheck rise over run." No claim of upside-down or sign error.
- Other: "Not correct. Find the gradient from the two points, then substitute a point to find c."
- No named wrong-answer branches (upside-down, sign-flip, m/c swap); these now land in the generic or point-based branches. Silent marks: none; every lost mark has a hint.
- Worked solution, structured and in the same method each time: (1) gradient m=(y2-y1)/(x2-x1) with the values shown in brackets for negatives, simplified to a displayed fraction; (2) substitute point A into y=mx+c, with brackets around negative values and the fraction coefficient shown as \frac; (3) rearrange to find c, showing the arithmetic; (4) final equation y=mx+c, then a check that B satisfies it. No sign clashes like "+ -3" or "--".
- Question note shows m, c and both points.
- Question description (saved with the question) documents: pedagogical objective, mathematical constraints (|m|<3, non-integer, c non-integer, integer coordinates), the randomisation strategy above, and the assessment decisions (partial credits and why unambiguous-only feedback).

PRT/QTEST SUGGESTIONS: Descriptive tests, no duplicates (old cases 1 and 2 merged):
- Model answer: 1. Equivalent forms: (p*x+q*c)/q, p*x/q+c, factored/expanded: 1.
- Correct line unrearranged, q*y=p*x+q*c: 0.5.
- Bare expression, 0: 0 (not an equation).
- Non-straight: y=x^2: 0.
- Right gradient, wrong intercept (y=m*x+c+1): 0.5.
- Wrong gradient through A: y=(q/p)*x + the intercept making it pass through A: 0.4 (check that it still passes through A on every seed).
- Wrong gradient through B: 0.4.
- Gradient wrong, intercept not tied to either point: 0.
- Constant line y=c: 0.

REFERENCE POINTERS (optional):
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Potential_response_trees.md
Authoring/Question_note.md
Authoring/Inputs/Input_options.md
CAS/Random.md

ADDITIONAL LANGUAGES (optional): (none)
