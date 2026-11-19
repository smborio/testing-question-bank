GOAL (non-negotiable): Given two points, find the equation of the line through them in the form y=mx+c (calculate: gradient from two points, then intercept).
STRUCTURE (non-negotiable): Single part. The student types one equation y=mx+c.
RANDOMIZATION (negotiable): Built in this order. (1) y-intercept c: integer in -9..9, not 0. (2) Gradient m=p/q in lowest terms, q in 2..5, |p| in 1..9, so m is never an integer; it may exceed 1 in size (e.g. 7/3) and may be negative. (3) Two points on the line with integer coordinates, one each side of the y-axis: x1=-q*a, x2=q*b with a,b in 1..2, so y values are integers. Points are never the intercept, and are shown in x order. Keep all |y| at most 20. The worked solution always follows the same steps.
ANSWER TESTS (negotiable): Accept any equation equivalent to the correct line, but only if it is written with y alone on the left (y=mx+c). Otherwise, e.g. 3y=2x+6, tell the student to rearrange into y=mx+c without giving marks (form is the point of the task). Full marks need the right line, not only the right form. Reject input that is not an equation in x and y.
FEEDBACK (negotiable): Right: short confirmation. Wrong: hint naming the likely slip, no answer given. Mistakes with their own branch, in the question's variables: y=(q/p)x+c (gradient upside down; hint: gradient is change in y over change in x); y=-(p/q)x+c (sign of gradient wrong; hint: check the order of subtraction is the same top and bottom); y=cx+p/q... i.e. y=c*x+m (gradient and intercept swapped; hint: m is the coefficient of x, c is where the line crosses the y-axis). Each scores 0 with its hint. Worked solution: gradient = (y2-y1)/(x2-x1), simplify; substitute a point to find c (or note c from the point on the y-axis); state y=mx+c. Silent marks: not allowed.
PRT/QTEST SUGGESTIONS: Also test an unsimplified equivalent form such as y=(2*p*x)/(2*q)+c, which must get full marks, and 2y=2mx+2c, which must be refused for form.
REFERENCE POINTERS (optional):
Authoring/Answer_Tests/Equivalence.md
Authoring/Answer_Tests/Form.md
Authoring/Inputs/Input_options.md
CAS/Random.md
ADDITIONAL LANGUAGES (optional): (none)
