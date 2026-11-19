GOAL: Edit of the existing question "Equation line given two points ask find equation". Given two points, the student finds the equation of the line through them and writes it as y=mx+c. Task type: calculate. The gradient is a non-integer rational with |m|<3. The y-intercept is not an integer and |c|<6. Pedagogical objective: find the gradient from two points, find the intercept by substituting a point, and write the line in the requested form.

DESCRIPTION: The student sees two integer points A and B. They are asked for the equation of the line through them in the form y=mx+c, with any fractions given as fractions. There is one part with one algebraic input, which opens pre-filled with "y=". The input must be validated before it is graded. Decimals are rejected as invalid input. Implicit multiplication such as 5x is accepted.

STRUCTURE: Single part with one algebraic input (an equation) and one grading tree.

RANDOMIZATION:
- m=p/q in lowest terms, with q in {2,3,4,5}.
- p is nonzero with a random sign, drawn from a filtered list for each q. This keeps |m|<3 and m never a whole number.
- A=(xa,ya) has integer coordinates. xa is in -6..6 and not a multiple of q. ya is drawn within 5 of floor(m*xa), which keeps |c|<6.
- B=A+(q*k,p*k), with k in {-2,-1,1,2}. Its coordinates are integers.
- The worked solution uses the same method for every variant.

ANSWER TESTS: The tests run in this order on the student's equation.
1. If it is not an equation, the score is 0.
2. If it is not a straight line, the score is 0.
3. If it is equivalent to the correct line, the score depends on its form.
   - It scores 1 only if y is alone on the left and the right side is a single x-term plus at most one constant. The x-term is a number times x, for example x/3-7/3, (1/3)x-7/3 or -7/3+x/3.
   - Otherwise it scores 0.5. This covers y=(x-7)/3, 3y=x-7 and y=m*(x+c/m).
4. If the gradient is right but the intercept is wrong, the score is 0.5.
5. If the gradient is wrong and the line passes through A, the score is 0.4.
6. If the gradient is wrong and the line passes through B, the score is 0.4.
7. Anything else scores 0.

Form alone never earns marks. A line that does not pass through A or B, with a wrong gradient, scores 0.

FEEDBACK: Silent marks are not allowed. Every route that scores below 1 gives a hint.
- Not an equation: "Your answer must start with y=."
- Not a straight line: "Your answer should be the equation of a straight line, y = mx + c."
- Correct line in the wrong form: "Your line is right, but write it in the form y = mx + c: a number times x, plus a number."
- Right gradient, wrong intercept: "Your gradient is correct, but the intercept is not. Substitute a point into y=mx+c and solve for c."
- Wrong gradient, line through A only: "Your line passes through A but not B. Recheck the gradient using both points."
- Wrong gradient, line through B only: "Your line passes through B but not A. Recheck the gradient using both points."
- Wrong gradient, line through neither point: "Your line does not pass through either given point. Find the gradient from both points, then substitute a point to find c."
- Correct and in form: "Correct."
- The worked solution has four steps:
  1. Compute the gradient from the two points.
  2. Substitute A into y=mx+c.
  3. Solve for c.
  4. Write the final line with a fraction coefficient of x and no "+ -".

IMPLEMENTATION NOTES:
- Every assessment variable (equation test, linearity, rearranged y, form check, gradient and point checks) is computed in the feedback variables, and the nodes only test those booleans.
- The "form" check splits the right side into additive terms. It requires exactly one x-term whose coefficient has no x, and at most one constant. This is why a single-fraction right side such as (x-7)/3 scores only 0.5.
- The Author could not change how STACK displays the model answer ta1 itself. The worked solution's step 4 therefore builds the line from m and c with a conditional sign.
- The plan's suggested tests are kept as qtests. In the last build, the model answer in factored or single-fraction form is expected to score 0.5 (qtests 13 and 14, answer note prt_ans1-4-F). An earlier build wrongly gave it full marks.

REFERENCE POINTERS: (none)

ADDITIONAL LANGUAGES: (none)