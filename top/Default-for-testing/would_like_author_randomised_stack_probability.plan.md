GOAL (non-negotiable): Read a two-stage probability tree for sampling without replacement, find missing branch probabilities (a, b, c), then use the multiplication rule and addition of exclusive outcomes to get P(both blue) and P(same colour). Tests calculate/interpret at school probability level.

STRUCTURE (non-negotiable): A bag of 16 counters, red/blue/green; two drawn without replacement. A non-interactive JSXGraph tree shows both draws with all 3+9 branches. Branch probabilities are shown as fractions over 16 and 15, EXCEPT three labelled a, b, c (blue first; blue second given blue first; red second given blue first). The joint (end-of-path) probabilities are NOT shown on the diagram. Parts, five inputs, equal weight (0.2 of the total each):
(i) three inputs: a, b, c.
(ii) P(both blue).
(iii) P(both counters the same colour).
Answers are fractions, not necessarily simplified.

RANDOMIZATION (negotiable): Counts (red, blue, green) sum to 16, each at least 2, all three different. Possible sets: {2,3,11},{2,4,10},{2,5,9},{2,6,8},{3,4,9},{3,5,8},{3,6,7},{4,5,7}; assign them to colours in a random order so blue's count varies (my choice). Tree labels and text follow the variant; the tree is redrawn from the counts. The worked solution structure stays the same.

ANSWER TESTS (negotiable): Each input accepts a fraction or any equivalent value (not required to be simplified). Reject a non-numeric entry, and a decimal if easy (my choice: fractions only). Correct values: a=B/16, b=(B-1)/15, c=R/15 where B,R are blue/red counts. (ii) a*b. (iii) P(BB)+P(RR)+P(GG), using the RR and GG branch fractions shown on the tree.
Follow-through: (ii) is full marks if equal to the student's a times student's b, provided a and b are admissible probabilities (each between 0 and 1); then 80% of the part mark (the small deduction; my choice). (iii) is full marks if correct, 80% if equal to the student's (ii) answer plus the correct RR and GG products, provided the student's (ii) is between 0 and 1 and the total is not above 1. Follow-through is not given for inadmissible values (negative, above 1).
Form only: allowed (no simplification required).

FEEDBACK (negotiable):
(i) Right: confirm. Wrong mistakes with hints:
- b = B/15 (counter not removed after the first draw): "After a blue counter is taken, one fewer blue remains."
- b = a (with replacement): "The first counter is not put back; the bag now has 15 counters."
- c = 1-b (third colour left out): "Two colours are left besides blue's own branch; green must be counted as well: the three branches from blue add up to 1."
- a with denominator 15 or other bad denominator: hint that the bag holds 16 counters at the start.
(ii) a+b instead of a*b: "Along a path, multiply the branch probabilities." Follow-through message when earlier answers were wrong but method right: say marks are reduced because a or b was wrong.
(iii) Only P(BB) given (other colours forgotten): "Same colour includes red-red and green-green." Product of the three correct terms or a sum with one term missing: hint saying which colour is missing. Answer is a wrong total above 1: say a probability cannot exceed 1.
Worked solution (General Feedback): states a=B/16; after one blue is removed 15 left, b=(B-1)/15, c=R/15 (and the green branch G/15, total 1); P(BB)=a*b; P(same)=P(BB)+P(RR)+P(GG), each a product along the path; numeric values for the variant.
Silent marks: not allowed (each lost-mark route above has a hint).

PRT/QTEST SUGGESTIONS: Full correct answers; unsimplified correct fractions; wrong a with (ii)=a*b follow-through case (80%); inadmissible values (e.g. a=3/2) no follow-through; mistake b=a and c=1-b.

REFERENCE POINTERS (optional):
Specialist_tools/JSXGraph/JSXGraph.md
Authoring/Potential_response_trees.md
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Feedback.md
CAS/Random.md

ADDITIONAL LANGUAGES (optional): (none)
