GOAL (non-negotiable): Read a two-stage probability tree for sampling without replacement, find missing branch probabilities, and compute joint probabilities (both blue; same colour). Skills: recall/calculate.

STRUCTURE (non-negotiable): Non-interactive JSXGraph tree: 3 first-draw branches, each with 3 second-draw branches (12 branches), all fractions shown except a, b, c, which are labelled by letter. End-of-path (joint) probabilities are NOT shown. Three parts, five inputs, each worth 0.2:
(i) a, b, c (three fraction inputs): a = P(blue first); b = P(blue second | blue first); c = P(red second | blue first).
(ii) P(both blue).
(iii) P(both same colour).
Answers are fractions; need not be simplified.

RANDOMIZATION (negotiable): Counts of red, blue, green: integers each >= 2, sum 16, all three different. Colours assigned to counts randomly, so blue's count varies between variants. Blue is always the colour in a, b, c; red is the colour in c. Tree labels are shown as unsimplified fractions over 16 and 15 (e.g. 5/16, 4/15). The tree layout stays the same, only numbers change. Worked solution is the same method for every variant.

ANSWER TESTS (negotiable): Each input accepts only a fraction (decimals rejected, not simplified-required), graded by value (any equivalent fraction gets full marks). (i) a, b, c each checked against the correct value. (ii) correct value a*b = B(B-1)/240 gets 1. Otherwise, if the student's a and b are both genuine probabilities (strictly between 0 and 1) and the answer equals their a*b, award follow-through. (iii) correct value (R(R-1)+B(B-1)+G(G-1))/240 gets 1. Otherwise follow-through: the student's answer equals their a*b plus the red-red and green-green products read from the tree, provided their a and b are probabilities between 0 and 1. Follow-through score is 95% of the part mark (0.19 of 0.2). Follow-through is not given if a or b is outside [0,1] (or not a number). Form only: not allowed; full marks need the right value.

FEEDBACK (negotiable):
(i) a: wrong answer B/15 (wrong denominator): hint that there are 16 counters at the first draw. b: wrong answer B/15 (no counter removed): hint that one blue is already gone and only 15 remain. b = a (as if with replacement): hint that the counter was not replaced. c: wrong answer 1-b: hint that the bag also holds a third colour (green), so c is not 1-b. Right answers: short confirmation.
(ii) wrong answer a+b: hint to multiply along the branch, not add. Follow-through answer: tell the student the method is right but earlier values are wrong (score 0.19).
(iii) wrong answer: only blue-blue (a*b): hint that red-red and green-green also count. Wrong answer adding the branch probabilities instead of multiplying: same hint as (ii). Follow-through: method right, earlier values wrong.
Worked solution in General Feedback: find a=B/16, b=(B-1)/15, c=R/15 (name the method: counts remaining after the first draw); P(BB)=a*b; P(same colour)=sum of RR, BB, GG products along branches, with the numbers for the variant.
Silent marks: not allowed.

PRT/QTEST SUGGESTIONS: Test cases: all correct (full marks); wrong a with consistent follow-through in (ii) and (iii) (0.19); a = 3/2 (out of range) with follow-through value (no follow-through credit); decimal 0.25 entered (rejected).

REFERENCE POINTERS (optional):
Specialist_tools/JSXGraph/JSXGraph.md
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Potential_response_trees.md
Authoring/Inputs/Input_options.md
CAS/Random.md

ADDITIONAL LANGUAGES (optional): (none)
