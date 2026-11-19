GOAL: Given two points, the student finds the equation of the line through them and writes it as y=mx+c. Task type: calculate. The gradient is a non-integer fraction and the y-intercept is a non-zero integer.

DESCRIPTION: The student sees "A line passes through the points A(xa, ya) and B(xb, yb)". The question asks for the equation in the form y=mx+c and says to give any fractions as fractions. There is one part. It has one algebraic input, pre-filled with "y=", where the student types a full equation. Implicit multiplication such as 5x is accepted. Decimals are rejected as invalid.

STRUCTURE: Single part with one input (an equation) and one grading tree.

RANDOMIZATION:
- c is a non-zero integer from -9 to 9.
- m = p/q in lowest terms, with q in {2,3,4,5}. p has a random sign. Its absolute value is chosen from the values coprime to q, up to 9, so m is never a whole number.
- Point A is at x = -q*a and point B is at x = q*b, with a and b each 1 or 2. The points lie on opposite sides of the y-axis, and all coordinates are integers.
- y-values are m*x + c.
- The worked solution has the same method for every variant.

ANSWER TESTS: Marking runs in this order:
1. If the answer is not an equation, it scores 0 with the hint "Your answer must start with y=." This covers a bare expression such as mx+c.
2. If the left-hand side is not y alone (for example q*y = p*x+q*c), it scores 0 with the hint to rearrange to y = mx + c.
3. If the right-hand side is algebraically equivalent to m*x+c, it scores 1 and the feedback is "Correct." Any equivalent right-hand side is accepted, such as (p*x+q*c)/q or p*x/q+c.
4. A right form with a wrong line scores 0. Form alone never earns marks.
The input forbids decimals (floats). Implicit multiplication is allowed, and the validation message is shown to the student.

FEEDBACK: Every wrong answer scores 0. Each named mistake has its own hint:
- y=(q/p)x+c, gradient upside down: "Recheck rise over run."
- y=-m x+c, gradient sign flipped: "Check the sign of the change in y and in x."
- y=c x+p/q, m and c swapped: the hint says m is the coefficient of x and c is where the line crosses the y-axis.
- Any other wrong line: "Not correct. Find the gradient from the two points, then substitute a point to find c."
Worked solution: m = (y2-y1)/(x2-x1), then substitute point A to find c, then write y=mx+c.

IMPLEMENTATION NOTES:
- Round 1 failed. The Author's first tree had false-branch nodes with no score, and then the STACK API timed out. Round 2 rebuilt the tree.
- Students first found that "5x" and decimals were rejected as invalid. Implicit multiplication is now allowed (insertstars=4). Decimals are still forbidden, and the question text now says to give fractions as fractions.
- The mistake checks compare only the right-hand side, so they run only when y is alone on the left. Anything else leaves the tree earlier, with the form hints.
- Test case 13 covers the "other wrong line" route.
- Test cases 1 and 2 are identical.

PRT/QTEST SUGGESTIONS: The test cases cover the model answer and an equivalent right-hand side. They also cover a bare expression, an unrearranged equation, implicit multiplication, each named mistake, a generic wrong line, and the input 0.

REFERENCE POINTERS: (none)

ADDITIONAL LANGUAGES: (none)