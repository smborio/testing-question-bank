GOAL (non-negotiable): Read a probability tree for sampling without replacement. Find the unknown branch probabilities (a, b, c), then use the multiplication rule for "both blue" and add branch products for "same colour".

STRUCTURE (non-negotiable): One question, three parts, five inputs, each worth 1/5. A non-interactive JSXGraph tree (first draw R, B, G; second draw R, B, G; nine branches) sits above the parts. All branch fractions are shown except a, b, c.
(i) three inputs: a = P(blue first), b = P(blue second | blue first), c = P(red second | blue first).
(ii) P(both blue).
(iii) P(both same colour).

RANDOMIZATION (negotiable): Counts (r,b,g): three distinct integers each >=2 summing to 16, drawn from all such triples and randomly permuted so blue can be any size. Tree shows unsimplified fractions with denominators 16 and 15. Colours fixed as red, blue, green.

ANSWER TESTS (negotiable): Fractions; any equivalent fraction accepted, simplification not required. Decimals rejected with a message asking for a fraction.
(i) a = nb/16, b = (nb-1)/15, c = nr/15, each checked for equivalence.
(ii) Full marks for a*b with the correct values. Follow-through 0.8 of the mark for (student a)*(student b) if the student's a, b, c are admissible.
(iii) Full marks for the correct total. Follow-through 0.8 of the mark for (student's (ii)) + (red-red branch product) + (green-green branch product), the last two from the tree, provided the student's (ii) is between 0 and 1.
Admissible: each of a, b, c between 0 and 1, and b + c <= 1. Follow-through only when earlier answers are wrong; full marks only from the correct value.

FEEDBACK (negotiable): Correct answers get a short confirmation. Silent marks: not allowed.
(i) b = nb/16 (with-replacement error; the bag now holds 15); b = nb/15 (forgot a blue counter is gone); c = nr/16 (wrong denominator); c = 1-b (ignores the third colour). Each gets its own hint.
(ii) a+b (adds instead of multiplying; hint: both happen, multiply along the branch); a*a (with-replacement error).
(iii) only the blue-blue product (forgot other colours); the sum of three products using wrong second-draw probabilities. Each gets a hint.
Follow-through answers get a note: method right, but built on an earlier wrong value, marks reduced.
Worked solution in General Feedback: counts and total 16; a, b, c with the reason the denominator drops to 15; multiplication rule for P(BB); three same-colour branch products added, with numbers.

PRT/QTEST SUGGESTIONS: all five correct (expect 1); same answers as unsimplified fractions (expect 1); wrong b with consistent (ii) and (iii) (expect follow-through); inadmissible b (e.g. 2) giving no follow-through; a decimal refused.

REFERENCE POINTERS:
Specialist_tools/JSXGraph/JSXGraph.md
Authoring/Potential_response_trees.md
Authoring/Answer_Tests/Grading_recipes.md
Authoring/Inputs/Input_options.md
CAS/Random.md

ADDITIONAL LANGUAGES: (none)
