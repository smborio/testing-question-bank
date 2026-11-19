GOAL (non-negotiable): Edit of the existing question "Equation line given two points ask find equation". Given two points, the student finds the equation of the line through them and writes it as y=mx+c. Task type: calculate. The gradient is a non-integer rational with |m|<3. The y-intercept is small (|c| about 6 or less) but not an integer. Pedagogical objective: gradient from two points, find the intercept by substituting a point, write the line in the requested form.

STRUCTURE (non-negotiable): Single part with one algebraic input (an equation, pre-filled "y="), one grading tree. Implicit multiplication allowed, decimals forbidden, fractions required (the question text says so).

RANDOMIZATION (negotiable): As built: m=p/q in lowest terms, q in {2,3,4,5}, p nonzero with random sign, |m|<3, never a whole number, from a filtered list per q. A=(xa,ya) integer, xa nonzero in -6..6 and not a multiple of q; ya within 5 of floor(m*xa) so |c|<6. B=A+(q*k,p*k), k in {-2,-1,1,2}. All assessment variables are in the feedback variables. Worked solution is the same method for every variant.

ANSWER TESTS (negotiable): Checked in order, using the student's equation.
1. Not an equation: 0, hint "Your answer must start with y=".
2. Not a straight line: 0, hint that the answer should be a straight line.
3. Line equivalent to the correct one: 1 only if y is alone on the left AND the right-hand side is in the form y=mx+c, i.e. a number times x plus a number (e.g. x/3-7/3, (1/3)x-7/3, -7/3+x/3). Otherwise 0.5 with the hint "Your line is right, but write it in the form y = mx + c: a number times x, plus a number." This covers y=(x-7)/3 and 3y=x-7.
4. Right gradient, wrong intercept: 0.5.
5. Wrong gradient, line passes through A or B: 0.4.
6. Anything else: 0.
Form alone never earns marks.

FEEDBACK (negotiable): Evidence-based hints only.
- Right gradient, wrong intercept: "Your gradient is correct, but the intercept is not. Substitute a point into y=mx+c and solve for c."
- Wrong gradient through exactly one point: "Your line passes through A (or B) but not the other point. Recheck the gradient using both points."
- Wrong gradient through neither: "Your line does not pass through either given point. Find the gradient from both points, then substitute a point to find c."
- Correct line not in the form y=mx+c: the hint in test 3.
- Worked solution in 4 steps as built (gradient, substitute A, solve for c, final line with fraction coefficient of x, no "+ -").
Silent marks: not allowed.

PRT/QTEST SUGGESTIONS: model answer (1); p*x/q+c (1); (p*x+q*c)/q (0.5); q*y=p*x+q*c (0.5); a single-fraction right side such as y=(x-7)/3 style (0.5); bare expression (0); y=x^2 (0); right gradient wrong intercept (0.5); wrong gradient through A (0.4); through B (0.4); neither (0); input 0.

REFERENCE POINTERS (optional):
Authoring/Potential_response_trees.md
Authoring/Feedback.md
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Answer_Tests/Form.md
Authoring/Variables.md
CAS/Random.md

ADDITIONAL LANGUAGES (optional): (none)
