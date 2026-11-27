GOAL (non-negotiable): Assess a one-sample z-test for a population mean with known sigma at the 5% level, in a battery-lifetime context: choose the alternative hypothesis, compute z (2 d.p.) and the p-value (3 s.f.), decide on H0, and state the contextual conclusion. Title: "Hypothesis testing". Default question grade 1.

STRUCTURE (non-negotiable): Five equally weighted parts (0.2 each).
1. Radio: alternative hypothesis (mu < mu0, mu > mu0, mu ≠ mu0). H0: mu = mu0 is given. Options shuffled.
2. Numerical input: test statistic z, 2 d.p.
3. Numerical input: p-value, 3 s.f.
4. Radio: reject / do not reject H0 at 5%.
5. Radio: contextual conclusion (options shuffled). Distractors include "sufficient evidence" vs "insufficient evidence" for the right claim, the wrong direction, and "the data prove the mean is exactly mu0" (non-rejection read as proof of H0).
Question text states the manufacturer's claim, sigma, n, sample mean and alpha = 5%, and the researcher's claim through conditional blocks: "has decreased" / "has increased" / "has changed".

RANDOMIZATION (negotiable): Case = (tail: left/right/two) x (reject: yes/no), 6 cases drawn uniformly, so all are well represented. Context numbers: mu0 from 300 to 900 hours in steps of 50 (batteries); sigma from {15, 20, 25, 30, 40}; n from {25, 36, 49, 64, 81, 100}. The sample mean is built from a target z, rounded to 0.1 h, then z is recomputed from the rounded mean, so the values are real and the case is certain.
Target |z| away from the critical values (1.645 one-tailed, 1.96 two-tailed):
- Reject: one-tailed 2.1 to 3.0 in the direction of the alternative; two-tailed |z| 2.3 to 3.0, either sign.
- Non-reject, in the direction: one-tailed 0.3 to 1.2; two-tailed |z| 0.2 to 1.5, either sign.
- Non-reject, one-tailed, opposite direction to the alternative: z 0.3 to 2.5 the wrong way, about half of the one-tailed non-rejections. The p-value is then above 0.5.
Question Note names tail, decision, and direction of the difference (the mathematically distinct variants), without the option order. Comments in the variables explain the construction.

ANSWER TESTS (negotiable):
- Part 1: correct option gets full marks.
- Part 2: numerical closeness with tolerance 0.005 absolute (rounding to 2 d.p.); no trailing zeros required. Full credit for the correct value.
- Part 3: numerical closeness consistent with 3 s.f. (tolerance half a unit in the third significant figure of the correct p); no trailing zeros required. Full credit for the correct p. 95% follow-through if p matches the student's own z (their z with the right tail rule), only if part 1 was correct and the student's z is a valid number.
- Part 4: correct decision for the true p-value gets full marks. 95% follow-through if it matches the student's own p-value (reject iff p < 0.05), only if part 1 was correct and the student's p is a valid probability (0 to 1); an invalid p gets no follow-through.
- Part 5: correct conclusion for the true decision gets full marks. 95% follow-through if it matches the student's own decision, only if part 1 was correct.
- Follow-through on parts 3 to 5 needs part 1 correct. Follow-through is never offered when the answer is only equal to the model answer by accident (copied answers earn nothing beyond the normal route).

FEEDBACK (negotiable): Each wrong answer below gets its own hint.
- Part 1: a wrong tail is told which direction the researcher's claim points (decreased, increased, changed); no answer given.
- Part 3 (parts 3 to 5 depend on the tail): two-tailed p given as a one-tailed value (the p without the factor 2, p/2 of the correct value): "remember both tails". One-tailed case with the wrong tail (1 − p) is told to check which tail the alternative points to. Both score 0 for the p, with a hint.
- Part 5: choosing "H0 is true / the mean is exactly mu0" after non-rejection is told that failing to reject is not proof of H0, only lack of evidence.
- Part 2: z with sign reversed (-z) is told to check the order of x-bar and mu0; sigma used without dividing by sqrt(n), i.e. (xbar-mu0)/sigma, is told to use the standard error.
- Follow-through answers are told they are consistent with the earlier mistake and the first error is named, at 95%.
- Silent marks: not allowed.
- General Feedback: a full worked solution inside an outer [[if]]/[[elif]]/[[else]] on the test direction (left, right, two). Each contains a nested [[if]]/[[else]] on rejection vs non-rejection, giving hypotheses, z, p (with factor 2 for two-tailed), the comparison with 0.05, the decision and the contextual conclusion. Conditions use Boolean variables from the Question Variables (e.g. tail and reject flags tested with is(...)). Native conditional CASText only, not Maxima strings of HTML.

PRT/QTEST SUGGESTIONS:
- Full correct answer set.
- Correct part 1 and wrong z with a consistent p, decision and conclusion (follow-through at 95%).
- Wrong part 1 with otherwise correct answers (no follow-through marks on parts 3 to 5).
- Invalid p (e.g. 1.5) with decision "reject" (no follow-through).
- Two-tailed p without the factor 2.
- Non-rejection read as proof of H0 in part 5.
- Cover every end point of each answer check, and avoid duplicates.

Authoring conventions: Question grade 1; explanatory comments in Question Variables; short node descriptions; literal paragraph tags with an empty source line between paragraphs; no line-break tags; CDATA to keep the HTML readable; the Question Note as above; complete importable XML.

REFERENCE POINTERS (optional):
Authoring/Question_blocks/Conditional_blocks.md
Authoring/Inputs/Multiple_choice_input.md
Authoring/Inputs/Numerical_input.md
Authoring/Answer_Tests/Numerical.md
Authoring/Potential_response_trees.md
Authoring/Question_note.md
CAS/Random.md
CAS/Statistics.md

ADDITIONAL LANGUAGES (optional): (none)
