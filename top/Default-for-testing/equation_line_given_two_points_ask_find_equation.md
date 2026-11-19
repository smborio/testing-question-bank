# Metadata — Default-for-testing/equation_line_given_two_points_ask_find_equation.xml

Running record of every agent (and user) action on this question that
isn't the XML itself: the reasoning, findings, improvement notes, and
reference lookups behind each change. Entries are appended in order,
newest at the bottom. The XML changes themselves are recorded by git —
this file holds the substance and meaning behind them, not the diffs.

## Entry 1 — planner · plan locked (2026-11-19T11:16:45)

**Reference files fetched:**
- (none)

**Reference files recommended by Planner:**
- CAS/Equations.md
- Authoring/Answer_Tests/Equivalence.md
- Authoring/Answer_Tests/Grading_recipes.md
- Authoring/Inputs/Input_syntax.md

```text
GOAL (non-negotiable): Given two points, the student finds the equation of the line through them and writes it in the form y=mx+c. Task type: calculate. The gradient is a non-integer fraction and the y-intercept is a nice non-zero integer.

STRUCTURE (non-negotiable): Single part. The student types one equation of the form y = mx + c.

RANDOMIZATION (negotiable): Construct in this order.
1. c: non-zero integer from -9 to 9.
2. m = p/q in lowest terms, q from 2 to 5, p a non-zero integer with |p| up to 9, gcd(p,q)=1, so m is never a whole number. It may be above 1 or negative.
3. Points: A at x = -q*a and B at x = q*b, with a and b each 1 or 2. One point is on each side of the y-axis and all coordinates are whole numbers. y-values are m*x + c.
The worked solution method stays the same: gradient from the two points, then substitute to find c (or check against the construction).

ANSWER TESTS (negotiable): One input, an equation.
- Full marks: an equation with y alone on the left whose right-hand side is equivalent to (p/q)x + c. Any equivalent right-hand side is accepted, e.g. y=(p x+q c)/q.
- Form required: an equation not with y alone on the left (e.g. 3y=2x+12) earns no marks and a hint to rearrange to y = mx + c.
- Bare expression (mx+c with no "y="): no marks and a specific hint that the answer must start with y=.
- Form only: not allowed. A right form with a wrong line gets no marks.

FEEDBACK (negotiable):
- Right answer: confirmed.
- Wrong answers with their own hint, score 0:
  - y=(q/p)x+c: gradient upside down, hint to recheck rise over run.
  - y=-(p/q)x+c: gradient sign flipped, hint to check the sign of the change in y and in x.
  - y=c x+p/q: gradient and intercept swapped, hint that m is the coefficient of x and c is where the line crosses the y-axis.
- Worked solution: gradient m = (y2-y1)/(x2-x1), then substitute one point to find c, then write y=mx+c.

PRT/QTEST SUGGESTIONS: 
- A bare mx+c with no "y=" (e.g. (p/q)x+c): expect no marks and the "start with y=" hint.
- An unrearranged equivalent, such as q*y=p*x+q*c: expect no marks and the rearrange hint.
```

## Entry 2 — author · build round 1 (2026-11-19T11:22:37)

**Reference files fetched:**
- (none)

```text
STACK API check: did NOT pass (api_unreachable) after 2 attempt(s).
Retriever gave the Author: Authoring/Answer_Tests/Grading_recipes.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Inputs/Input_syntax.md, AI_authors/stack_essentials.md, Authoring/Variables.md, CAS/Random.md, Authoring/Errors.md, Authoring/Potential_response_trees.md, STACK_question_admin/Testing.md
```

## Entry 3 — planner · review (2026-11-19T12:01:19)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=False)
Feedback to Author: Retry keeping the draft. Fixes: (1) algebraic_equivalence is not a STACK function: use a real check such as ATAlgEquiv(...) in feedback variables, or make the nodes use AlgEquiv directly on sans/tans expressions. (2) Guard against non-equations: only call lhs/rhs after equationp(ans1) is true (use if-then-else so nothing is evaluated on a bare expression). (3) Replace the dummy nodes that test true against true (nodes 6, 7, 8) with real checks, or give each terminal branch an explicit true/false score. Every false branch that ends the tree must state its FALSESCORE (0 for wrong answers). Keep the plan's scores: only the correct line scores 1, all mistake branches 0 with the planned hints, bare expression gets the 'start with y=' hint, unrearranged equation gets the rearrange hint.
```

## Entry 4 — author · build round 2 (2026-11-19T12:02:38)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: Authoring/Answer_Tests/Grading_recipes.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Inputs/Input_syntax.md
```

## Entry 5 — planner · review (2026-11-19T12:04:41)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=False)
Feedback to Author: Keep the draft and the grading as they are. Two changes: (1) Make the input accept implicit multiplication, so y=-5x+5 and y=-x/5+5 are read as valid (insert the missing * automatically, for example with the input's insertStars option) and then graded normally. (2) Keep floats forbidden, since only fractions are accepted. Add a line to the question text: "Give the gradient as a fraction, not a decimal." A decimal like y=-0.2x+5 should still be rejected as invalid. Add qtests: y=-5x+5-style input without * (written for the variant, e.g. y=p*x/q+c with the stars left out) should score 1 for the correct line. Also add qtests for the sign-flipped answer -m*x+c and the swapped answer c*x+p/q, so those routes are exercised.
```

## Entry 6 — students · confirmed findings (2026-11-19T12:04:45)

**Reference files fetched:**
- (none)

```text
{"student": "student", "variant": 1, "answers": {"ans1": "y=-5x+5"}, "what_happened": "Not marked. The answer was rejected as invalid and the message said to add * (y = -5*x+5).", "why_wrong": "Implicit multiplication such as 5x is normal student notation. Rejecting it is unfriendly, and the student gets no marking feedback on a wrong-gradient answer."}
{"student": "student", "variant": 1, "answers": {"ans1": "y=-0.2x+5"}, "what_happened": "Not marked. The answer was rejected for containing a floating-point number and for missing *.", "why_wrong": "A correct answer in decimal form is refused, and the question doesn't say fractions are required. A student has no warning before the attempt."}
```

## Entry 7 — author · build round 3 (2026-11-19T12:05:38)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: Authoring/Answer_Tests/Grading_recipes.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Inputs/Input_syntax.md
```

## Entry 8 — planner · review (2026-11-19T12:08:15)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=False)
Feedback to Author: Keep the draft and the grading. Changes: (1) Replace the question-text sentence "Give the gradient as a fraction, not a decimal." with "Give any fractions in your answer as fractions." Do not mention decimals anywhere in the text. Keep forbidfloat on and insertstars on, so a decimal answer is still rejected as invalid. (2) The input box opens pre-filled with "y=...", so the student has to delete the dots. Change it so the box opens with "y=" only, or empty. (3) Add a qtest for the route no test reaches: a wrong equation with y alone on the left that matches no named mistake, e.g. y = x + 1 (use y = (p+1)*x + c + 1 so it is wrong on every variant). Expect 0 and the note prt_ans1-6-F.
```

## Entry 9 — author · build round 4 (2026-11-19T12:09:11)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: Authoring/Answer_Tests/Grading_recipes.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Inputs/Input_syntax.md
```

## Entry 10 — planner · review (2026-11-19T12:15:15)

**Reference files fetched:**
- (none)

```text
Review decision: APPROVE (keep_draft=True, plan_changed=False)
```

## Entry 11 — planner (2026-11-19T12:15:29)

**Reference files fetched:**
- (none)

```text
Wrote the current-state plan description for the approved, merged question.
```

## Entry 12 — concierge (2026-11-19T12:26:54)

**Issue:**
- #6

**Closes on merge:**
- yes

**Reference files fetched:**
- (none)

```text
Reserved as part of issue #6.
```

## Entry 13 — planner · plan locked (2026-11-19T12:32:35)

**Reference files fetched:**
- (none)

**Reference files recommended by Planner:**
- Authoring/Potential_response_trees.md
- Authoring/Feedback.md
- Authoring/Answer_Tests/Grading_recipes.md
- Authoring/Variables.md
- CAS/Random.md

```text
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
```

## Entry 14 — author · build round 1 (2026-11-19T12:35:11)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 2 attempt(s).
Retriever gave the Author: Authoring/Answer_Tests/Grading_recipes.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Potential_response_trees.md, Authoring/Feedback.md, Authoring/Variables.md, CAS/Random.md, Authoring/Inputs/Input_syntax.md, Authoring/CASText.md, CAS/Simplification.md
```

## Entry 15 — planner · review (2026-11-19T12:37:58)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=False)
Feedback to Author: Two changes, keep the rest of the draft. (1) Keep the intercept small: |c| should be at most about 6 (variants currently give c=23/3 and 25/2). For example narrow the ranges of xa and ya, or draw c first as a non-integer fraction with denominator q and build A from it; A and B must still have integer coordinates, xa and xb must not be 0, and xa must not be a multiple of q. (2) Display the model answer and the worked solution's step 4 with the gradient as a fraction coefficient of x, e.g. \frac{5}{2}x+\frac{25}{2} and \frac{x}{3} written as \frac{1}{3}x, with no visible multiplication dot (not \frac{5\cdot x}{2}), in every variant. Keep grading, hints and scores unchanged.
```

## Entry 16 — author · build round 2 (2026-11-19T12:39:10)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: Authoring/Answer_Tests/Grading_recipes.md, Authoring/Answer_Tests/Equivalence.md, Authoring/Potential_response_trees.md, Authoring/Feedback.md, Authoring/Variables.md, CAS/Random.md, Authoring/Inputs/Input_syntax.md
Deviations reported: RANDOMIZATION (negotiable): ya is now drawn within 5 of floor(m*xa), not from -8..8. This keeps |c|<6, and A and B keep integer coordinates. Only step 4 of the worked solution is changed, so it shows the fraction coefficient of x. I did not change how STACK displays the model answer ta1 itself, because I couldn't see a way to change that from these fields.
```

## Entry 17 — planner · review (2026-11-19T12:42:18)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=True)
Feedback to Author: One change, keep the rest of the draft. Full marks (1) now require the form y=mx+c: y alone on the left and the right-hand side written as (number)*x plus a number, so x/3-7/3, (1/3)x-7/3 and -7/3+x/3 get 1. A correct line with y alone on the left but the right side not split into mx+c, such as y=(x-7)/3 or y=(p*x+q*c)/q, gets 0.5 with the hint "Your line is right, but write it in the form y = mx + c: a number times x, plus a number." Same 0.5 and hint for an unrearranged correct line such as 3y=x-7. Update qtests: the (p*x+q*c)/q case now expects 0.5; add y=(x-7)/3-style case at 0.5; p*x/q+c stays 1. Grading of wrong lines, hints and other scores unchanged.
Revised plan:
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
```

## Entry 18 — students · confirmed findings (2026-11-19T12:42:22)

**Reference files fetched:**
- (none)

```text
{"student": "student", "variant": 1, "answers": {"ans1": "y=(x-7)/3"}, "what_happened": "Full marks, while 3y=x-7 got 0.5 for 'not in the form y=mx+c'.", "why_wrong": "y=(x-7)/3 is also not in the form y=mx+c, so the form check is inconsistent. It also accepts a wrong form that the question says should be avoided."}
```

