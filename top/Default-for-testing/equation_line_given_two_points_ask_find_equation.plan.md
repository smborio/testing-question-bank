GOAL (non-negotiable): Edit of the existing question. Given two points, the student finds the equation of the line through them and writes it as y=mx+c (calculate). The gradient is a non-integer rational with |m|<3; the intercept is a small non-integer rational.

STRUCTURE (non-negotiable): Single part, one algebraic input (equation, pre-filled "y=", decimals forbidden, implicit multiplication allowed, validation shown), one grading tree. Fractions are requested as fractions.

RANDOMIZATION (negotiable): Constructive, no rejection sampling beyond filtered lists.
- q in {2,3,4,5}; p = sign * a value from a filtered list of integers coprime to q with 1<=|p|<3q, so m=p/q is in lowest terms, never whole, |m|<3.
- Point A: integer xa from -6..6, excluding 0. Step k: nonzero integer from -3..3, giving B = (xa+q*k, ya+p*k). Coordinates are integers. xb must not be 0 (choose k from the values that avoid it); points may lie on the same or opposite sides of the y-axis.
- Intercept: c = n/q with n a nonzero integer, -9..9, coprime to q, so c is never an integer and small. ya = m*xa + c is then a fraction with denominator q. To keep the points as integers, choose ya from integers and derive c: ya integer in -9..9, c = ya - m*xa. Since xa is not a multiple of q, c is non-integer. Pick xa from values not divisible by q, and k so xb stays off 0; the Author fixes the exact construction so all coordinates are integers, c is a non-integer with small size (|c|<=5), and both points are off the y-axis.
- Assessment variables live in the feedback variables, not the question variables. Question variables hold only the randomisation and the model answer.

ANSWER TESTS (negotiable): Checks in order:
1. Is the answer an equation? If not, 0, "Your answer must be an equation starting y=."
2. Is it a straight line (linear in x and y)? If not, 0, say so.
3. If it is the correct line but y is not alone on the left: 0.5, "right line, now write it as y=mx+c."
4. If y is alone and the right side equals mx+c: full marks 1. Any equivalent right side is accepted. Form alone never earns marks.
5. y alone, gradient correct, intercept wrong: 0.5.
6. y alone, gradient wrong, the line passes through A or B (error carried forward): 0.4, whichever point it passes through.
7. Anything else: 0.
Comparisons are made on the evidence in the answer, not on a guessed process.

FEEDBACK (negotiable): Only what the evidence supports.
- Not an equation / not a line: say what is expected.
- Right line, wrong form: say it is right and ask for y=mx+c.
- Right gradient, wrong intercept: "Your gradient is correct; check c by substituting a point."
- Wrong gradient but passes through a point: "Your line passes through A (or B) but not the other point, so recheck the gradient." Never claim how the student got it.
- Otherwise: "Not correct. Find the gradient from the two points, then substitute a point to find c."
- Old branches for upside-down gradient, flipped sign and m/c swap are dropped; those answers fall into the generic route or the pass-through-a-point route if they apply.
- Worked solution, structured in steps: (1) gradient m=(y2-y1)/(x2-x1) with the values substituted, negative numbers in brackets, simplified fraction; (2) substitute point A into y=mx+c; (3) rearrange to c = ya - m*xa and compute it; (4) final equation y=mx+c. Fractional coefficients are shown as proper fractions, and signs are displayed naturally (e.g. y = -\frac{3}{2}x+\frac{1}{2}, not +-).
Silent marks: none. Every partial mark has a hint.

QUESTION DESCRIPTION: The saved description records the pedagogical objectives (finding a line from two points, gradient then intercept), the mathematical constraints (|m|<3, m non-integer, c non-integer, integer coordinates, points off the y-axis), the constructive randomisation, and the assessment decisions (partial credit values and why, error carried forward, no guessing of process).

PRT/QTEST SUGGESTIONS: Remove the duplicate test 1/2. Descriptive tests: model answer; equivalent forms (fraction combined, implicit multiplication); right line with y not alone (0.5); bare expression (0); non-linear equation (0); right gradient wrong c (0.5); wrong gradient through A (0.4); wrong gradient through B (0.4); unrelated wrong line (0); 0 as input. Update the expected answer notes to the new tree.

REFERENCE POINTERS (optional):
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Potential_response_trees.md
CAS/Random.md
Authoring/Variables.md

ADDITIONAL LANGUAGES (optional): (none)
