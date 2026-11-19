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

