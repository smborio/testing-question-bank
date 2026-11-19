GOAL (non-negotiable): Edit of the existing question "Equation line given two points ask find equation". Given two points, the student finds the equation of the line through them and writes it as y=mx+c. Task type: calculate. The gradient is a non-integer rational with |m|<3. The y-intercept is small but not restricted to integers. Pedagogical objective: gradient from two points, find the intercept by substituting a point, write the line in the requested form.

STRUCTURE (non-negotiable): Single part with one algebraic input (an equation, pre-filled "y="), one grading tree. Implicit multiplication allowed, decimals forbidden, fractions required (the question text already says so).

RANDOMIZATION (negotiable):
- m = p/q in lowest terms, q in {2,3,4,5}, p a nonzero integer with random sign, coprime to q, |p/q|<3 and never a whole number. Build p from a filtered list per q (no rejection sampling), for example q=2: |p| in {1,3,5}; q=3: {1,2,4,5,7,8}; q=4: {1,3,5,7,9,11}; q=5: {1,2,3,4,6,7,8,9,11,12,13,14}, all with |p|<3q.
- Point A has integer coordinates xa, ya, with xa a random nonzero integer in -6..6. ya is a random integer in -8..8.
- Point B = A + (q*k, p*k) with k a random nonzero integer in -2..2 (k=±1 or ±2). Coordinates are always integers.
- The intercept c = ya - m*xa is then a fraction with denominator q, never an integer, so it is small but not an integer. Choose xa so that c is not a whole number, that is, xa is not a multiple of q.
- Points may lie on the same or opposite sides of the y-axis. Keep both points off the y-axis (xa≠0, xb≠0), so no point gives c away. Points must be distinct (k≠0).
- Constructive choices only; the worked solution is the same method for every variant.
- All assessment variables (the wrong-gradient lines, point checks) are defined in the feedback variables, not the question variables. The question variables hold only the generation of the points and the model answer.

ANSWER TESTS (negotiable): Checked in order, using the student's equation.
1. Not an equation: 0, hint "Your answer must start with y=" (this covers a bare expression).
2. Not a straight line (not linear in x and y): 0, hint that the answer should be a straight line.
3. y not alone on the left: if the equation is equivalent to the correct line, 0.5 with the hint to rearrange to y = mx + c; otherwise continue to the checks below, with no form hint.
4. y alone on the left: right-hand side equivalent to the correct line gets 1, "Correct." Any equivalent form is accepted (e.g. (p*x+q*c)/q).
5. Right gradient (coefficient of x equals m) with a wrong intercept: 0.5.
6. Wrong gradient, but the line passes through A or B (error carried forward): 0.4.
7. Anything else: 0.
Partial credits 0.5, 0.5, 0.4 were agreed with the user. Form alone never earns marks.

FEEDBACK (negotiable): Only evidence-based hints, no assumptions about the student's method.
- Right gradient, wrong intercept: "Your gradient is correct, but the intercept is not. Substitute a point into y=mx+c and solve for c."
- Wrong gradient but line passes through exactly one point: "Your line passes through A (or B) but not the other point. Recheck the gradient using both points."
- Wrong gradient, passes through neither: "Your line does not pass through either given point. Find the gradient from both points, then substitute a point to find c."
- Any other wrong line: 0 with the generic hint to find the gradient and then c.
- The old branches (upside-down gradient, sign flipped, m and c swapped) are dropped, since they assumed the process.
- Worked solution, structured in steps: (1) the gradient m=(y2-y1)/(x2-x1) with the values substituted, negatives in brackets, and the result as a fraction; (2) substitute point A into y=mx+c, written as ya = m(xa) + c with the gradient shown as a fraction coefficient; (3) rearrange to c = ya - m*xa and evaluate; (4) the final equation y=mx+c, with fractions displayed naturally (e.g. y = -\frac{3}{2}x + \frac{1}{2}, no "+ -" and no "1*").
Silent marks: not allowed (every partial score has a hint).

PRT/QTEST SUGGESTIONS: Remove the duplicate tests. Descriptive tests: model answer (1); equivalent forms, such as (p*x+q*c)/q and p*x/q+c (1); an unrearranged correct equation q*y=p*x+q*c (0.5); a bare expression (0); a non-linear equation such as y=x^2 (0); right gradient with wrong intercept (0.5); wrong gradient through A (0.4); wrong gradient through B (0.4); wrong line through neither point (0); the input 0.

REFERENCE POINTERS (optional):
Authoring/Potential_response_trees.md
Authoring/Feedback.md
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Variables.md
CAS/Random.md

QUESTION DESCRIPTION: The saved description must document the pedagogical objectives, mathematical constraints, randomisation strategy and assessment decisions (partial credits, error carried forward, evidence-only feedback).

ADDITIONAL LANGUAGES (optional): (none)
