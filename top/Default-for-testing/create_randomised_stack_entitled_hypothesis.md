# Metadata — Default-for-testing/create_randomised_stack_entitled_hypothesis.xml

Running record of every agent (and user) action on this question that
isn't the XML itself: the reasoning, findings, improvement notes, and
reference lookups behind each change. Entries are appended in order,
newest at the bottom. The XML changes themselves are recorded by git —
this file holds the substance and meaning behind them, not the diffs.

## Entry 1 — planner · plan locked (2026-11-27T10:13:40)

**Reference files fetched:**
- Authoring/Question_blocks/Conditional_blocks.md

**Reference files recommended by Planner:**
- Authoring/Question_blocks/Conditional_blocks.md
- Authoring/Inputs/Multiple_choice_input.md
- Authoring/Inputs/Numerical_input.md
- Authoring/Answer_Tests/Numerical.md
- Authoring/Answer_Tests/Grading_recipes.md
- Authoring/Potential_response_trees.md
- CAS/Random.md
- Authoring/Question_note.md
- CAS/Statistics.md

```text
GOAL (non-negotiable): Assess a one-sample z-test for a population mean with known population standard deviation, in a battery-lifetime context (manufacturer claims mean lifetime mu0 hours; researcher investigates whether it has decreased, increased or changed). Significance level 5%. Conditions for the test are assumed satisfied. Question title: "Hypothesis testing". Default question grade 1.

STRUCTURE (non-negotiable): Five equally weighted parts, in order:
1. Radio input: choose the alternative hypothesis H1 from three options (mu < mu0, mu > mu0, mu != mu0). H0 (mu = mu0) is given in the question text.
2. Numerical input: test statistic z, 2 decimal places.
3. Numerical input: p-value, 3 significant figures.
4. Radio input: decision (reject / do not reject H0).
5. Radio input: contextual conclusion (options in battery context, including the distractor "the data prove H0 is true / the mean lifetime is definitely mu0").
Parts 3, 4, 5 use follow-through (see ANSWER TESTS). The order of radio options is randomised in every radio input.

RANDOMIZATION (negotiable):
- Case drawn from six combinations: tail (left, right, two) x outcome (reject, not reject), balanced so that all six are reasonably represented (e.g. case index 1..6 chosen with rand, or equally by seed).
- Context values: mu0 from {40, 45, 50, 60, 75, 80, 100...} hours (sensible battery lifetimes, e.g. multiples of 5 between 40 and 120); sigma a value such as 4, 5, 6, 8, 10; n from {16, 25, 36, 49, 64}, so sigma/sqrt(n) is tidy.
- Sample mean built from a target z at a safe distance from the critical values (e.g. reject: |z| between 2.2 and 3.2 for one-tailed/ 2.3-3.3 two-tailed; not reject: |z| between 0.3 and 1.3), then the mean is rounded to 2 decimals and z recomputed from the rounded mean; require recomputed z to stay safely away from the critical values (1.645 one-tailed, 1.96 two-tailed; margin at least 0.2).
- For one-tailed non-rejecting cases, about half have the observed difference in the opposite direction to the alternative (e.g. sample mean above mu0 for a left-tailed test).
- Question Note records tail, outcome and direction of difference only, not option permutations.

ANSWER TESTS (negotiable):
- Part 1: correct option gets full marks.
- Part 2: numerical closeness to the teacher's z with tolerance consistent with 2 decimal places (e.g. 0.005 absolute); no trailing zeros required; z entered as a number.
- Part 3: full credit if equal to the correct p-value to 3 significant figures (relative tolerance consistent with 3 s.f., no trailing zeros required). Follow-through 95%: p-value consistent with the student's own z (using the correct tail from the true alternative), only if part 1 is correct, and only if the student's z is a valid input; a p-value outside [0,1] never gets follow-through.
- Part 4: full credit for the correct decision. Follow-through 95%: decision consistent with the student's own p-value (compare with 0.05), only if part 1 correct and the student's p-value is a valid probability in [0,1].
- Part 5: full credit for the correct conclusion. Follow-through 95%: conclusion consistent with the student's own decision, only if part 1 correct.
- Follow-through never applies if part 1 is wrong; a student who answered a part correctly independently gets full marks.

FEEDBACK (negotiable):
- Part 1: wrong tail gets a hint tying the tail to the researcher's claim (decreased -> <, increased -> >, changed -> !=).
- Part 2: no special branch beyond a general hint if far off; if sign wrong (-z), hint to check the direction of sample mean minus mu0 (score 0, hint).
- Part 3: two-tailed case, student gives half the p-value (single tail area): hint "remember to double for a two-tailed test" (95% follow-through not applied; score 0 with hint). Wrong tail for p-value (1-p or the other tail): hint to check which tail the alternative points to. Invalid probability (<0 or >1): note that a probability lies in [0,1].
- Part 4: decision inconsistent with p-value compared to 0.05: hint to compare p with 0.05.
- Part 5: the option "the data prove H0 is true" gets a specific hint: failing to reject H0 does not prove H0 true, only that there is insufficient evidence against it. Other wrong conclusions: hint matching conclusion to decision.
- Worked solution (General Feedback): three complete solutions, one per tail, in an outer native conditional block (if/elif/else), each with a nested conditional for reject vs not reject; conditions depend on Question Variables. Solutions name the method: state H0/H1, z = (xbar - mu0)/(sigma/sqrt n), p-value from the correct tail (doubled for two-tailed), compare with 0.05, state conclusion in context. Question Text uses native conditional blocks for the researcher's claim wording.
Silent marks: not allowed.

PRT/QTEST SUGGESTIONS: Tests covering every PRT termination point: all-correct answers; part 1 wrong with the rest otherwise consistent (no follow-through); wrong z with consistent p, decision, conclusion (95%); p outside [0,1] (no follow-through); two-tailed half p-value; "prove H0 true" option. Avoid duplicates.
```

## Entry 2 — planner · plan locked (2026-11-27T10:18:44)

**Reference files fetched:**
- (none)

**Reference files recommended by Planner:**
- Authoring/Question_blocks/Conditional_blocks.md
- Authoring/Inputs/Multiple_choice_input.md
- Authoring/Inputs/Numerical_input.md
- Authoring/Answer_Tests/Numerical.md
- Authoring/Answer_Tests/Grading_recipes.md
- Authoring/Potential_response_trees.md
- CAS/Random.md
- Authoring/Question_note.md
- CAS/Statistics.md

```text
GOAL (non-negotiable): Assess a one-sample z-test for a population mean with known population standard deviation, in a battery-lifetime context (manufacturer claims mean lifetime mu0 hours; researcher investigates whether it has decreased, increased or changed). Significance level 5%. Conditions for the test are assumed satisfied. Question title: "Hypothesis testing". Default question grade 1.

STRUCTURE (non-negotiable): Five equally weighted parts, in order:
1. Radio input: choose the alternative hypothesis H1 from three options (mu < mu0, mu > mu0, mu != mu0). H0 (mu = mu0) is given in the question text.
2. Numerical input: test statistic z, 2 decimal places.
3. Numerical input: p-value, 3 significant figures.
4. Radio input: decision (reject / do not reject H0).
5. Radio input: contextual conclusion (options in battery context, including the distractor "the data prove H0 is true / the mean lifetime is definitely mu0").
Parts 3, 4, 5 use follow-through (see ANSWER TESTS). The order of radio options is randomised in every radio input.

RANDOMIZATION (negotiable):
- Case drawn from six combinations: tail (left, right, two) x outcome (reject, not reject), balanced so that all six are reasonably represented (e.g. case index 1..6 chosen with rand, or equally by seed).
- Context values: mu0 from {40, 45, 50, 60, 75, 80, 100...} hours (sensible battery lifetimes, e.g. multiples of 5 between 40 and 120); sigma a value such as 4, 5, 6, 8, 10; n from {16, 25, 36, 49, 64}, so sigma/sqrt(n) is tidy.
- Sample mean built from a target z at a safe distance from the critical values (e.g. reject: |z| between 2.2 and 3.2 for one-tailed/ 2.3-3.3 two-tailed; not reject: |z| between 0.3 and 1.3), then the mean is rounded to 2 decimals and z recomputed from the rounded mean; require recomputed z to stay safely away from the critical values (1.645 one-tailed, 1.96 two-tailed; margin at least 0.2).
- For one-tailed non-rejecting cases, about half have the observed difference in the opposite direction to the alternative (e.g. sample mean above mu0 for a left-tailed test).
- Question Note records tail, outcome and direction of difference only, not option permutations.

ANSWER TESTS (negotiable):
- Part 1: correct option gets full marks.
- Part 2: numerical closeness to the teacher's z with tolerance consistent with 2 decimal places (e.g. 0.005 absolute); no trailing zeros required; z entered as a number.
- Part 3: full credit if equal to the correct p-value to 3 significant figures (relative tolerance consistent with 3 s.f., no trailing zeros required). Follow-through 95%: p-value consistent with the student's own z (using the correct tail from the true alternative), only if part 1 is correct, and only if the student's z is a valid input; a p-value outside [0,1] never gets follow-through.
- Part 4: full credit for the correct decision. Follow-through 95%: decision consistent with the student's own p-value (compare with 0.05), only if part 1 correct and the student's p-value is a valid probability in [0,1].
- Part 5: full credit for the correct conclusion. Follow-through 95%: conclusion consistent with the student's own decision, only if part 1 correct.
- Follow-through never applies if part 1 is wrong; a student who answered a part correctly independently gets full marks.

FEEDBACK (negotiable):
- Part 1: wrong tail gets a hint tying the tail to the researcher's claim (decreased -> <, increased -> >, changed -> !=).
- Part 2: no special branch beyond a general hint if far off; if sign wrong (-z), hint to check the direction of sample mean minus mu0 (score 0, hint).
- Part 3: two-tailed case, student gives half the p-value (single tail area): hint "remember to double for a two-tailed test" (95% follow-through not applied; score 0 with hint). Wrong tail for p-value (1-p or the other tail): hint to check which tail the alternative points to. Invalid probability (<0 or >1): note that a probability lies in [0,1].
- Part 4: decision inconsistent with p-value compared to 0.05: hint to compare p with 0.05.
- Part 5: the option "the data prove H0 is true" gets a specific hint: failing to reject H0 does not prove H0 true, only that there is insufficient evidence against it. Other wrong conclusions: hint matching conclusion to decision.
- Worked solution (General Feedback): three complete solutions, one per tail, in an outer native conditional block (if/elif/else), each with a nested conditional for reject vs not reject; conditions depend on Question Variables. Solutions name the method: state H0/H1, z = (xbar - mu0)/(sigma/sqrt n), p-value from the correct tail (doubled for two-tailed), compare with 0.05, state conclusion in context. Question Text uses native conditional blocks for the researcher's claim wording.
Silent marks: not allowed.

PRT/QTEST SUGGESTIONS: Tests covering every PRT termination point: all-correct answers; part 1 wrong with the rest otherwise consistent (no follow-through); wrong z with consistent p, decision, conclusion (95%); p outside [0,1] (no follow-through); two-tailed half p-value; "prove H0 true" option. Avoid duplicates.
```

## Entry 3 — author · build round 1 (2026-11-27T10:24:56)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 2 attempt(s).
Retriever gave the Author: Authoring/Question_blocks/Conditional_blocks.md, Authoring/Inputs/Multiple_choice_input.md, Authoring/Inputs/Numerical_input.md, Authoring/Answer_Tests/Numerical.md, Authoring/Answer_Tests/Grading_recipes.md, Authoring/Potential_response_trees.md, CAS/Random.md, Authoring/Question_note.md, Authoring/Variables.md, STACK_question_admin/Testing.md, AI_authors/stack_essentials.md
```

## Entry 4 — planner · review (2026-11-27T10:30:00)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=False)
Feedback to Author: Fix these, keeping the draft and the plan unchanged (no change for F4: no follow-through on p after a wrong part 1).
1. Part 3: give full marks (1) to a p-value correct to 3 s.f. from either the rounded z (z2) or the unrounded z ((xbar-mu0)/se), using the correct tail. Accept either with the same relative tolerance.
2. Part 3 follow-through (0.95): apply it only if the student's z in part 2 is outside the part 2 tolerance (0.005 of z2). If the z is accepted, the follow-through message must not appear. A p-value that matches neither correct value then gets 0 and the normal tail hint.
3. Worked solution: print z to 2 decimal places (e.g. 2.30, not 2.3) wherever z is shown, using a formatted string such as printf or decimalplaces, in all three tail branches. Show the p-value with 3 s.f.
4. Keep the qtests passing. The half-p and "prove H0" routes are unreached on some variants, so add qtests that reach them on every variant: make them independent of the shuffled option order and of the tail.
```

## Entry 5 — students · confirmed findings (2026-11-27T10:30:04)

**Reference files fetched:**
- (none)

```text
{"student": "breaker", "variant": 1, "answers": {"ans1": "3", "ans2": "2.30", "ans3": "0.0106", "ans4": "2", "ans5": "1"}, "what_happened": "p-value 0.0106 was marked incorrect (0/1), with generic feedback about tail area. 0.0107 was accepted.", "why_wrong": "The unrounded z is 2.3033 and gives p=0.01064, which is 0.0106 to 3 s.f. The question accepts only the p-value computed from the rounded z=2.30. A correct answer is therefore marked wrong, and the feedback does not explain why."}
{"student": "breaker", "variant": 1, "answers": {"ans1": "3", "ans2": "2.303", "ans3": "0.01064", "ans4": "2", "ans5": "1"}, "what_happened": "z=2.303 got full marks for part 2. The p-value 0.01064 got 0.95 with the message 'the error was in part 2, so it is counted there only (95%)'.", "why_wrong": "The feedback says part 2 had an error, but part 2 was marked fully correct. It also penalises a more accurate p-value. The message contradicts the marks."}
{"student": "student", "variant": 1, "answers": {"ans1": "3", "ans2": "2.30", "ans3": "0.0106", "ans4": "2", "ans5": "1"}, "what_happened": "The p-value 0.0106 got 0 of 1 and the generic 'find the area in the tail' feedback. The worked solution gives 0.0107, which comes from rounding z to 2.3.", "why_wrong": "z = 3.29/(10/7) = 2.3029, so the exact p = 0.01066 → 0.0107?? Checked more carefully: the exact p is about 0.0106, and the key's 0.0107 comes from the rounded z. A correct answer is marked wrong because of intermediate rounding, and the student is told to redo a calculation they did correctly. The tolerance is too tight."}
```

