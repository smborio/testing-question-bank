GOAL (non-negotiable): Test reading and completing a probability tree for two draws without replacement from a bag of 16 counters (red, blue, green): find missing branch probabilities (conditional probabilities), then multiply along branches and add paths to get joint probabilities.

STRUCTURE (non-negotiable): Three parts, five answers in total, each worth 0.2 of the question.
(i) Three inputs: a = P(blue on 1st draw), b = P(blue on 2nd | blue 1st), c = P(red on 2nd | blue 1st).
(ii) P(both counters blue).
(iii) P(both counters the same colour).
A non-interactive JSXGraph probability tree is shown: first draw 3 branches, then 3 branches from each (9 second-draw branches). All branch probabilities are displayed as fractions over 16 and 15, except the three labelled a, b, c (the blue-first branch, the blue-after-blue branch and the red-after-blue branch). End-of-path (joint) probabilities are NOT shown on the tree. The red-red and green-green branch fractions are shown, so students can use them in (iii). Students enter fractions, not necessarily simplified.

RANDOMIZATION (negotiable): Counts of red, blue and green sum to 16, each at least 2, and all three different. The colours are assigned randomly to the counts, so blue's count varies between variants (blue is always the colour labelled a, b, c). The tree and worked solution are generated from the counts. The tree must be drawn correctly for every variant.

ANSWER TESTS (negotiable): Five inputs (a, b, c, part ii, part iii), all accepting fractions only; decimals are rejected as invalid. Fractions need not be simplified, so any equivalent value of the correct fraction gets full marks. Check equivalence to the correct value, not only the form.
Follow-through: in (ii), the student's a times the student's b earns 95% of the part mark (0.19 of 0.2). In (iii), the student's a times the student's b, plus the correct red-red and green-green products, earns 95% of the part mark. Follow-through applies only if the student's earlier answers are admissible probabilities (between 0 and 1); otherwise no follow-through credit. Full marks need the correct value.

FEEDBACK (negotiable): Part (i): a wrong, e.g. B/15 for b (forgetting the first counter was removed): hint that the bag has one fewer counter after the first draw. b = a (treating the draws as with replacement): hint about the first counter not being replaced. c = 1−b (leaving out the green counters): hint that the third colour has been left out; the three second-draw branches after blue must sum to 1. Part (ii): adding a+b instead of multiplying: hint to multiply along the branches. Part (iii): only the blue-blue path, or leaving out one of the colours: hint that all three same-colour paths are needed. Follow-through answers get a note that the method is right but an earlier answer was wrong. Silent marks: not allowed. Worked solution in General Feedback: explains counts after the first draw, finds a, b and c, multiplies along branches for BB, then adds RR, BB, GG for same colour, using the variant's numbers.

PRT/QTEST SUGGESTIONS: Model answers for all five inputs; unsimplified equivalents; decimals rejected; follow-through case: a, b wrong but valid probabilities, with a*b in (ii) scoring 0.19; inadmissible a (e.g. 3/2) giving no follow-through.

REFERENCE POINTERS (optional):
Specialist_tools/JSXGraph/JSXGraph.md
Authoring/Potential_response_trees.md
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Inputs/Numerical_input.md
CAS/Random.md

ADDITIONAL LANGUAGES (optional): (none)
