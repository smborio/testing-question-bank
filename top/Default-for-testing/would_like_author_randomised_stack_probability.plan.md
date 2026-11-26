GOAL: Test reading and completing a probability tree for two draws without replacement from a bag of 16 counters (red, blue, green). Students find missing conditional branch probabilities, then multiply along branches and add paths to get joint probabilities.

DESCRIPTION: The student sees a non-interactive JSXGraph probability tree. It has 3 first-draw branches and 3 second-draw branches from each, so 9 in all. Every branch is labelled with a fraction over 16 or 15, except three branches labelled a, b and c. End-of-path (joint) probabilities are not shown. The question has five numerical inputs, each worth 0.2 of the question:
- (i) a = P(blue 1st), b = P(blue 2nd | blue 1st), c = P(red 2nd | blue 1st). Three inputs: ans1, ans2, ans3.
- (ii) P(both counters blue). One input: ans4.
- (iii) P(both counters the same colour). One input: ans5.
Students enter fractions. These need not be in lowest terms, and decimals are rejected.

STRUCTURE: Three parts with five answers. Part (i) has three independent inputs. Parts (ii) and (iii) may follow through from the student's a and b in part (i).

RANDOMIZATION: The counts of red, blue and green are drawn from the triples (2,3,11), (2,4,10), (2,5,9), (2,6,8), (3,4,9), (3,5,8), (3,6,7), (4,5,7). They sum to 16, are all at least 2 and are all different. They are randomly permuted among the colours, so blue's count varies. Blue is always the colour labelled a, b and c. The tree labels and the worked solution are generated from the counts.

ANSWER TESTS:
- All five inputs are numerical inputs. Floats are forbidden, so decimals are invalid, and the lowest-terms requirement is off. Each is graded by algebraic equivalence to the model value: a = nb/16, b = (nb-1)/15, c = nr/15, (ii) nb(nb-1)/240, (iii) (nr(nr-1)+nb(nb-1)+ng(ng-1))/240.
- Follow-through in (ii): the student's a times the student's b scores 0.95.
- Follow-through in (iii): the student's a times the student's b, plus the correct red-red and green-green products, scores 0.95.
- Follow-through applies only if the student's a and b are strictly between 0 and 1. Otherwise there is no follow-through credit.
- Full marks need the correct value.

FEEDBACK:
- a wrong: a hint to divide the blue count by the 16 counters.
- b wrong:
  - nb/15 gets a hint that the bag has one fewer counter and one fewer blue.
  - b equal to a gets a hint that the first counter is not replaced.
  - Anything else gets a generic hint.
- c wrong:
  - 1-b gets a hint that green was left out and the three branches must sum to 1.
  - Anything else gets a generic hint.
- (ii) wrong:
  - a+b gets a hint to multiply along the branches.
  - Anything else gets a generic hint.
  - The follow-through answer gets "method right, earlier answer wrong".
- (iii) wrong:
  - Blue-blue only gets a hint that all three same-colour paths are needed.
  - One colour missing (RR+BB, GG+BB or RR+GG) gets a hint that a path is missing.
  - Anything else gets a generic hint.
  - The follow-through answer gets "method right, earlier answer wrong".
- No marks are silent.
- General feedback is a worked solution with the variant's numbers. It covers the counts after the first draw, a, b and c, BB by multiplying, and RR+BB+GG added for the same-colour case.

IMPLEMENTATION NOTES:
- The follow-through score of 0.95 was set by the plan. Students found it confusing, because the engine labels it "partially correct" and the mark looks nearly full. It was kept as the plan intended.
- The admissibility check uses strict bounds (0 < a < 1, 0 < b < 1), so a = 0 gets no follow-through. This is deliberate, and the Author changed it from the earlier non-strict bounds.
- Follow-through in (iii) only credits a student's own a·b plus the correct RR and GG terms. A student who wrongly multiplies the other terms too gets 0. This is by design, not an inconsistency.
- The tree is drawn in JSXGraph from the generated label lists l1 and l2. The labels are plain strings, e.g. "5/16".
- The question text includes the keywords for inputs and validation. `mustverify` is on.

PRT/QTEST: The built test cases cover the model answers, unsimplified equivalents, follow-through, inadmissible a, zeros, and each named mistake route. Decimals are rejected as invalid.

REFERENCE POINTERS: (none)

ADDITIONAL LANGUAGES: (none)