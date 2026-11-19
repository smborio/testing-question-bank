GOAL (non-negotiable): Given two points, the student finds the equation of the line through them and writes it as y=mx+c (calculate).
STRUCTURE (non-negotiable): Single part. One input where the student types a full equation y=mx+c.
RANDOMIZATION (negotiable): Build in this order. (1) c: non-zero integer in -9..9. (2) m=p/q in lowest terms, q in 2..5, |p| in 1..9, p/q never a whole number; may be >1 or negative. (3) Points: A=(-q*a, y_A) and B=(q*b, y_B) with a,b each 1 or 2, both on the line y=mx+c, so one point is left and one right of the y-axis and all coordinates are integers. Neither point is the y-intercept.
ANSWER TESTS (negotiable): The answer must be an equation with y alone on the left. Accept any equivalent right-hand side (e.g. y=2/4x+3 style forms, y=3+2x/3) for full marks. Unrearranged forms such as 3y=2x+6 get no marks and a hint to rearrange to y=mx+c. If the student types only an expression (mx+c with no "y="), no marks and a specific hint that the answer must be an equation starting y=. Form only: not allowed beyond this; the line must be the correct one.
FEEDBACK (negotiable): Right: short confirmation. Wrong mistakes with own hint, no marks: y=-(q/p)x+c (gradient upside down), y=-(p/q)x+c (gradient sign flipped), y=cx+p/q (gradient and intercept swapped). Any other wrong answer: generic hint to compute the gradient as change in y over change in x and then use a point to find c. Worked solution: gradient = (y_B-y_A)/(x_B-x_A) simplified, substitute a point to get c, write y=mx+c.
PRT/QTEST SUGGESTIONS: Include test of the bare expression mx+c (no "y=") expecting the "start with y=" hint and 0 marks; and 3y=... unrearranged form expecting 0 and the rearrange hint.
REFERENCE POINTERS (optional):
Authoring/Inputs/Input_options.md
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Potential_response_trees.md
Authoring/Error_trapping.md
CAS/Random.md
ADDITIONAL LANGUAGES (optional): (none)
