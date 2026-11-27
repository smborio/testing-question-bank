GOAL: Assess a one-sample z-test for a population mean with known population standard deviation, in a battery-lifetime context. A manufacturer claims a mean lifetime mu0 hours, and a researcher investigates whether it has decreased, increased or changed. The significance level is 5%. The conditions for the test are assumed to hold. Title: "Hypothesis testing". Default grade 1.

DESCRIPTION: The student sees the scenario (mu0, sigma, n, sample mean) and H0: mu = mu0. There are five equally weighted parts:
1. Radio: choose H1 from mu < mu0, mu > mu0 and mu != mu0.
2. Numerical: the test statistic z, to 2 decimal places.
3. Numerical: the p-value, to 3 significant figures.
4. Radio: the decision, either "Reject H0" or "Do not reject H0".
5. Radio: the conclusion in context. There are three options: sufficient evidence, insufficient evidence, and the distractor "The data prove H0 is true: the mean lifetime is definitely mu0 hours".

STRUCTURE: Five parts in order, as above. Parts 3, 4 and 5 use follow-through from the student's own earlier answers. The option order is randomised in every radio input.

RANDOMIZATION:
- A case index from 1 to 6 gives tail (left, right, two-tailed) × outcome (reject for cases 1-2, not reject for 3-5 and 0). The tail is mod(case, 3) and the outcome is reject when case < 3. The wording of the researcher's claim ("decreased", "increased", "changed") follows the tail.
- mu0 is a multiple of 5 between 40 and 120.
- sigma is one of 4, 5, 6, 8 or 10.
- n is one of 16, 25, 36, 49 or 64.
- The target |z| is 2.2 to 3.2 for a rejecting one-tailed case and 2.3 to 3.3 for a rejecting two-tailed case. It is 0.3 to 1.3 for a non-rejecting case.
- The direction follows the alternative in rejecting one-tailed cases. Otherwise it is random.
- The sample mean is rounded to 2 decimals. z is then recomputed from that rounded mean and rounded to 2 decimals.
- The Question Note records tail, reject and direction only.

ANSWER TESTS:
- Part 1: the correct option.
- Part 2: z within 0.005 of the model z.
- Part 3: full marks if the p-value is within 0.5% relative of EITHER the p-value from the rounded z (the model answer) OR the p-value from the unrounded z. Both are accepted so correct working is not penalised for intermediate rounding. Follow-through is worth 95%. It applies when part 1 is correct, part 2 is wrong (outside tolerance), and the p-value is a valid probability consistent with the student's own z and the true tail.
- Part 4: full marks for the correct decision. Follow-through is worth 95% when part 1 is correct and the p-value is in [0,1] and the decision is consistent with comparing that p-value with 0.05.
- Part 5: full marks for the correct conclusion. Follow-through is worth 95% when part 1 is correct and the conclusion matches the student's own decision.
- Follow-through never applies if part 1 is wrong.

FEEDBACK:
- Part 1: a wrong option gets a hint linking the tail to the researcher's claim (decreased -> <, increased -> >, changed -> !=).
- Part 2: a sign-flipped z scores 0 with a hint to compute sample mean minus mu0. Any other wrong value gets a general hint to recheck z.
- Part 3:
  - A p-value outside [0,1] scores 0 with a note that a probability lies between 0 and 1.
  - In the two-tailed case, half the p-value scores 0 with a hint to double the tail area.
  - 1-p scores 0 with a hint to check which tail H1 points to.
  - Any other wrong value gets a general hint.
- Part 4: a decision inconsistent with the p-value gets a hint to compare p with 0.05.
- Part 5: the "prove H0 true" option gets a hint that not rejecting does not prove H0. Other wrong options get a hint to match the conclusion to the decision.
- Worked solution: one block per tail, each split into reject and not reject. It states H0 and H1, z = (xbar - mu0)/(sigma/sqrt n), the p-value from the correct tail (doubled for two-tailed), the comparison with 0.05, and the conclusion in context. z is shown to 2 decimal places and p to 3 significant figures.
- Silent marks: not allowed.

IMPLEMENTATION NOTES:
- Part 3 accepts both the rounded-z and unrounded-z p-values. This was added after students found that a correct p-value from the unrounded z (for example 0.0106 against the key 0.0107) was marked wrong. The worked solution still shows the p-value from the rounded z.
- The part 3 follow-through requires that z is outside tolerance. This stops the "error in part 2" message appearing when part 2 was marked correct.
- The case index and the tail and outcome variables use the first two 3-way splits. The "prove H0" distractor is option 3 in part 5, and the correct option is 1 (reject) or 2 (not reject).
- Qtests for "half p-value" and the "prove H0" option on the not-rejecting route depend on the variant. The "prove H0" qtest with a wrong decision does pass on every variant. The two-tailed half-p route is only reached on some variants.

ADDITIONAL LANGUAGES: (none)