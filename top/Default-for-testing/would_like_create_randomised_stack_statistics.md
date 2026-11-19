# Metadata — Default-for-testing/would_like_create_randomised_stack_statistics.xml

Running record of every agent (and user) action on this question that
isn't the XML itself: the reasoning, findings, improvement notes, and
reference lookups behind each change. Entries are appended in order,
newest at the bottom. The XML changes themselves are recorded by git —
this file holds the substance and meaning behind them, not the diffs.

## Entry 1 — planner · plan locked (2026-11-19T10:20:11)

**Reference files fetched:**
- Specialist_tools/JSXGraph/Binding.md

**Reference files recommended by Planner:**
- Specialist_tools/JSXGraph/JSXGraph.md
- Specialist_tools/JSXGraph/Binding.md
- Authoring/Answer_Tests/Grading_recipes.md
- CAS/Random.md
- CAS/Statistics.md

```text
Question name: "Place mean and median in stacked dot plot". Category: default-for-testing.

GOAL (non-negotiable): Students estimate by eye the mean and median of a right-skewed distribution and show they understand that the long right tail pulls the mean above the median. Context: August precipitation (mm) in Eastern African cities.

STRUCTURE (non-negotiable): One stacked dotplot on one JSXGraph board. The student drags two labelled vertical lines, "Mean" and "Median", along the mm axis. The lines start at neutral positions that give nothing away. Three independent scored parts, equal weight (1/3 each):
1. Accuracy of the mean estimate.
2. Accuracy of the median estimate.
3. Relative position: the mean line is to the right of the median line. Judged only from the two line positions, independent of accuracy. Equal positions score 0.

RANDOMIZATION (negotiable):
- Number of observations N: random integer 50 to 99.
- Bins 6 mm wide starting at 0, 8 to 12 bins, each dot at the bin centre.
- Constructive generation, NO while/loop-until-valid retries: build the counts directly from a right-skewed shape, e.g. a peak in one of the first 2-3 bins followed by a geometric-type decay with a random ratio (about 0.6-0.8) over the remaining bins, scaled and rounded to sum to N (put the rounding remainder in the peak bin). Choose the peak and decay ranges so that, by construction, the mean exceeds the median by at least about 3 mm for every variant. Verify this over the ranges and restrict the ranges if needed rather than retrying.
- City names in the context text are not randomised.

ANSWER TESTS (negotiable):
- True mean and true median are computed from the plotted binned dot positions (median of the dot positions), so the plot and the answer agree.
- Mean accuracy: full marks if within 10% of the true mean, half marks if outside 10% but within 20%, otherwise 0. The tolerances are intentional and must not change.
- Median accuracy: same bands against the true median.
- Relative position: 1 if student mean position > student median position, else 0. Scored even when both estimates are inaccurate.
- Line positions are read from the board and graded on the question side. A line never moved scores 0.

FEEDBACK (negotiable):
- Mean and median parts: feedback relates only to the accuracy band reached (within 10%, within 20%, or further off), with the true value and a short tip on visual estimation (the median splits the dots into two equal halves; the mean is the balance point). No separate branches for specific mistakes.
- Position part: simply states whether the mean is to the right of the median or not.
- A detailed general feedback / worked solution covers the details: true mean and median, number of dots on each side of the median, and why the extreme values in the long right tail pull the mean more than the median, so mean > median in right-skewed data.
- Silent marks: allowed (no mistake-specific hints beyond the accuracy bands).

PRT/QTEST SUGGESTIONS:
- Mean and median lines both at the exact true values: full marks on all three parts.
- Lines swapped (mean left of median): position part 0.
- Mean line at +15% of the true mean: mean part half marks.
```

## Entry 2 — author · build round 1 (2026-11-19T10:22:49)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: Specialist_tools/JSXGraph/JSXGraph.md, Specialist_tools/JSXGraph/Binding.md, Authoring/Answer_Tests/Grading_recipes.md, Authoring/Answer_Tests/Numerical.md, Authoring/Inputs/Numerical_input.md, CAS/Random.md
Deviations reported: RANDOMIZATION (negotiable): the peak is always in the first bin. Weights are r^i plus a constant tail of 1/10, with r from {3/5, 7/10, 4/5}. A peak in a later bin, or pure geometric decay, did not give a mean at least about 3 mm above the median for every variant. I checked this by hand on a few variants (the extremes of r and the number of bins), not on every variant.
Structure: the plan has three scored parts. They are built as one PRT with three additive-score node groups, because the position part needs both inputs.
```

## Entry 3 — planner · review (2026-11-19T10:31:11)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=True)
Feedback to Author: Keep the draft as the base and make these changes: (1) Distribution shape: the left side must be bell-shaped (counts rise to a mode around bin 3-4, then fall), not monotonically decreasing. (2) Only a few outliers on the right: 3-5 dots in total, singles spread over the last 2-3 bins; the rest of the dots form the bell. Build counts constructively (no retries) and check the mean exceeds the median by at least 3 mm over EVERY combination of the random parameters, restricting the ranges if needed. (3) The mean and median lines must be dragged by the line itself (horizontal movement only), not by a point/glider at the bottom; bind each line's x-position to its input. (4) Put the labels "Mean" and "Median" near the top of the lines, clear of the axis labels and of each other. (5) Draw the dots as crosses (face 'x'), not discs. (6) The two lines must start at different positions, away from the true values; the start order is random per variant so it gives nothing away. (7) A line that was never moved scores 0 for its accuracy part, and the position part scores 0 unless both lines have been moved. Keep the tolerances (10% full, 20% half) unchanged.
Revised plan:
Question name: "Place mean and median in stacked dot plot". Category: default-for-testing.

GOAL (non-negotiable): Students estimate by eye the mean and median of a right-skewed distribution and show they understand that a few large values in the right tail pull the mean above the median. Context: August precipitation (mm) in Eastern African cities.

STRUCTURE (non-negotiable): One stacked dotplot on one JSXGraph board. The dots are drawn as crosses. The student drags two labelled vertical lines, "Mean" and "Median", along the mm axis by grabbing the lines themselves (horizontal movement only, not a point at the bottom). The labels sit near the top of the lines, clear of the axis labels and of each other. The lines start at two different positions that give nothing away (start order random per variant). Three independent scored parts, equal weight (1/3 each):
1. Accuracy of the mean estimate.
2. Accuracy of the median estimate.
3. Relative position: the mean line is to the right of the median line. Judged only from the two line positions, independent of accuracy. Equal positions score 0.

RANDOMIZATION (negotiable):
- Number of observations N: random integer 50 to 99.
- Bins 6 mm wide starting at 0, 10 to 12 bins, each dot at the bin centre.
- Shape: a bell-shaped body on the left (counts rise to a mode in bin 3 or 4, then fall, e.g. Gaussian-type weights with a standard deviation of about 1 to 1.5 bins) holding almost all the dots, plus only 3 to 5 outlier dots in total on the right, as single dots spread over the last 2-3 bins. Build the counts constructively, NO while/loop-until-valid retries: scale and round the body to N minus the number of outliers, put the rounding remainder in the mode bin. Choose the ranges so that, by construction, the mean exceeds the median by at least about 3 mm for every variant, and verify this over ALL combinations of the random parameters, restricting the ranges if needed rather than retrying.
- Start positions of the two lines: two distinct fixed positions well away from the true values, in random order per variant.
- City names in the context text are not randomised.

ANSWER TESTS (negotiable):
- True mean and true median are computed from the plotted binned dot positions (median of the dot positions), so the plot and the answer agree.
- Mean accuracy: full marks if within 10% of the true mean, half marks if outside 10% but within 20%, otherwise 0. The tolerances are intentional and must not change.
- Median accuracy: same bands against the true median.
- Relative position: 1 if student mean position > student median position, else 0. Scored even when both estimates are inaccurate.
- Line positions are read from the board and graded on the question side. A line never moved scores 0 for its accuracy part; the position part scores 0 unless both lines have been moved.

FEEDBACK (negotiable):
- Mean and median parts: feedback relates only to the accuracy band reached (within 10%, within 20%, or further off), with the true value and a short tip on visual estimation (the median splits the dots into two equal halves; the mean is the balance point). No separate branches for specific mistakes.
- Position part: simply states whether the mean is to the right of the median or not.
- A detailed general feedback / worked solution covers the details: true mean and median, number of dots on each side of the median, and why the few extreme values in the right tail pull the mean more than the median, so mean > median in right-skewed data.
- Silent marks: allowed (no mistake-specific hints beyond the accuracy bands).

PRT/QTEST SUGGESTIONS:
- Mean and median lines both at the exact true values: full marks on all three parts.
- Lines swapped (mean left of median): position part 0.
- Mean line at +15% of the true mean: mean part half marks.
- Both lines left at their start positions: score 0.

REFERENCE POINTERS (optional):
Specialist_tools/JSXGraph/JSXGraph.md
Specialist_tools/JSXGraph/Binding.md
Authoring/Answer_Tests/Grading_recipes.md
CAS/Random.md
CAS/Statistics.md

ADDITIONAL LANGUAGES (optional): (none)
```

## Entry 4 — planner · plan locked (2026-11-19T10:31:16)

**Reference files fetched:**
- (none)

**Reference files recommended by Planner:**
- Specialist_tools/JSXGraph/JSXGraph.md
- Specialist_tools/JSXGraph/Binding.md
- Authoring/Answer_Tests/Grading_recipes.md
- CAS/Random.md
- CAS/Statistics.md

```text
Question name: "Place mean and median in stacked dot plot". Category: default-for-testing.

GOAL (non-negotiable): Students estimate by eye the mean and median of a right-skewed distribution and show they understand that a few large values in the right tail pull the mean above the median. Context: August precipitation (mm) in Eastern African cities.

STRUCTURE (non-negotiable): One stacked dotplot on one JSXGraph board. The dots are drawn as crosses. The student drags two labelled vertical lines, "Mean" and "Median", along the mm axis by grabbing the lines themselves (horizontal movement only, not a point at the bottom). The labels sit near the top of the lines, clear of the axis labels and of each other. The lines start at two different positions that give nothing away (start order random per variant). Three independent scored parts, equal weight (1/3 each):
1. Accuracy of the mean estimate.
2. Accuracy of the median estimate.
3. Relative position: the mean line is to the right of the median line. Judged only from the two line positions, independent of accuracy. Equal positions score 0.

RANDOMIZATION (negotiable):
- Number of observations N: random integer 50 to 99.
- Bins 6 mm wide starting at 0, 10 to 12 bins, each dot at the bin centre.
- Shape: a bell-shaped body on the left (counts rise to a mode in bin 3 or 4, then fall, e.g. Gaussian-type weights with a standard deviation of about 1 to 1.5 bins) holding almost all the dots, plus only 3 to 5 outlier dots in total on the right, as single dots spread over the last 2-3 bins. Build the counts constructively, NO while/loop-until-valid retries: scale and round the body to N minus the number of outliers, put the rounding remainder in the mode bin. Choose the ranges so that, by construction, the mean exceeds the median by at least about 3 mm for every variant, and verify this over ALL combinations of the random parameters, restricting the ranges if needed rather than retrying.
- Start positions of the two lines: two distinct fixed positions well away from the true values, in random order per variant.
- City names in the context text are not randomised.

ANSWER TESTS (negotiable):
- True mean and true median are computed from the plotted binned dot positions (median of the dot positions), so the plot and the answer agree.
- Mean accuracy: full marks if within 10% of the true mean, half marks if outside 10% but within 20%, otherwise 0. The tolerances are intentional and must not change.
- Median accuracy: same bands against the true median.
- Relative position: 1 if student mean position > student median position, else 0. Scored even when both estimates are inaccurate.
- Line positions are read from the board and graded on the question side. A line never moved scores 0 for its accuracy part; the position part scores 0 unless both lines have been moved.

FEEDBACK (negotiable):
- Mean and median parts: feedback relates only to the accuracy band reached (within 10%, within 20%, or further off), with the true value and a short tip on visual estimation (the median splits the dots into two equal halves; the mean is the balance point). No separate branches for specific mistakes.
- Position part: simply states whether the mean is to the right of the median or not.
- A detailed general feedback / worked solution covers the details: true mean and median, number of dots on each side of the median, and why the few extreme values in the right tail pull the mean more than the median, so mean > median in right-skewed data.
- Silent marks: allowed (no mistake-specific hints beyond the accuracy bands).

PRT/QTEST SUGGESTIONS:
- Mean and median lines both at the exact true values: full marks on all three parts.
- Lines swapped (mean left of median): position part 0.
- Mean line at +15% of the true mean: mean part half marks.
- Both lines left at their start positions: score 0.
```

## Entry 5 — author · build round 2 (2026-11-19T10:33:31)

**Reference files fetched:**
- (none)

```text
STACK API check: PASSED after 1 attempt(s).
Retriever gave the Author: Specialist_tools/JSXGraph/JSXGraph.md, Specialist_tools/JSXGraph/Binding.md, Authoring/Answer_Tests/Grading_recipes.md, Authoring/Answer_Tests/Numerical.md, CAS/Random.md
Deviations reported: - RANDOMIZATION (negotiable): the plan asks for mean − median ≥ about 3 mm for every variant. I could not reach that with 3–5 outlier dots and N up to 99. At most about 1.5 mm is possible, and in some variants less than 1 mm. I did not check mean > median over all combinations. The shape is a Gaussian body in bins 1 to nb−3, with its mode in bin 3 or 4 and sd 1, 1.25 or 1.5 bins. The outliers are the last three bins' counts, one of [1,1,1], [2,1,1], [1,2,1], [1,1,2] or [2,1,2], so 3 to 5 dots, a few bins holding 2.
- Line start positions: fixed at 4 mm and 6·nb−4 mm, in random order.
- Input handling: each input now holds a single number, the line's x-position, written by JavaScript on drag. "Never moved" is detected by comparing it with the start position.
```

## Entry 6 — planner · review (2026-11-19T10:38:49)

**Reference files fetched:**
- (none)

```text
Review decision: REJECT (keep_draft=True, plan_changed=True)
Feedback to Author: Keep the draft (lines, crosses, grading, feedback all fine). Fix only the distribution: the mean exceeds the median by under 1.5 mm, and sometimes under 1 mm, so the position part is unreasonable by eye and the skew lesson is lost. Make the right tail heavier and further out: use 12-14 bins, a bell body with its mode in bin 3 or 4 holding about 90% of the dots, and a thin tail of single dots, about 8-10% of N (5 to 9 dots), spread over the last 4-5 bins. The tail count may scale with N. Build counts constructively with no retries. Check that mean - median >= 3 mm over EVERY combination of N, nb, mo, sg and tail, and narrow the ranges until it holds. State the minimum gap you found. If the engine times out, retry. Keep the line start positions away from the true values for every variant. Tolerances stay at 10% and 20%.
Revised plan:
Question name: "Place mean and median in stacked dot plot". Category: default-for-testing.

GOAL (non-negotiable): Students estimate by eye the mean and median of a right-skewed distribution and show they understand that a few large values in the right tail pull the mean above the median. Context: August precipitation (mm) in Eastern African cities.

STRUCTURE (non-negotiable): One stacked dotplot on one JSXGraph board. The dots are drawn as crosses. The student drags two labelled vertical lines, "Mean" and "Median", along the mm axis by grabbing the lines themselves (horizontal movement only). The labels sit near the top of the lines, clear of the axis labels and of each other. The lines start at two different positions that give nothing away (start order random per variant). Three independent scored parts, equal weight (1/3 each):
1. Accuracy of the mean estimate.
2. Accuracy of the median estimate.
3. Relative position: the mean line is to the right of the median line. Judged only from the two line positions, independent of accuracy. Equal positions score 0.

RANDOMIZATION (negotiable):
- Number of observations N: random integer 50 to 99.
- Bins 6 mm wide starting at 0, 12 to 14 bins, each dot at the bin centre.
- Shape: a bell-shaped body on the left (mode in bin 3 or 4, sd about 1 to 1.5 bins) holding about 90% of the dots, plus a thin right tail of single dots, about 8-10% of N (5 to 9 dots), spread over the last 4-5 bins. Build the counts constructively, with no retries. Choose the ranges so that mean - median is at least 3 mm for every variant, verified over ALL combinations of the random parameters, narrowing the ranges if needed.
- Start positions of the two lines: two distinct fixed positions well away from the true values, in random order per variant.
- City names are not randomised.

ANSWER TESTS (negotiable):
- True mean and median are computed from the plotted binned dot positions.
- Mean accuracy: full marks within 10% of the true mean, half marks within 20%, otherwise 0. Tolerances must not change.
- Median accuracy: same bands.
- Relative position: 1 if student mean position > student median position, else 0, scored even when estimates are inaccurate.
- A line never moved scores 0 for its accuracy part; the position part scores 0 unless both lines have been moved.

FEEDBACK (negotiable):
- Mean and median parts: feedback by accuracy band only, with the true value and a tip (median splits the dots into equal halves; mean is the balance point).
- Position part: states whether the mean is to the right of the median.
- Worked solution: true mean and median, dots each side of the median, why the tail pulls the mean more than the median.
- Silent marks: allowed.

PRT/QTEST SUGGESTIONS:
- Both lines at the true values: full marks.
- Lines swapped: position part 0.
- Mean line at +15% of the true mean: mean part half marks.
- Both lines at their start positions: score 0.

REFERENCE POINTERS (optional):
Specialist_tools/JSXGraph/JSXGraph.md
Specialist_tools/JSXGraph/Binding.md
Authoring/Answer_Tests/Grading_recipes.md
CAS/Random.md
CAS/Statistics.md

ADDITIONAL LANGUAGES (optional): (none)
```

## Entry 7 — students · confirmed findings (2026-11-19T10:38:53)

**Reference files fetched:**
- (none)

```text
{"student": "breaker", "variant": 1, "answers": {}, "what_happened": "Variant 1 could not be shown: 'STACK could not show the question: An Error occured while processing the question'. Submitting answers gave the same error, so nothing could be marked.", "why_wrong": "The question does not load, so a student cannot see the dot plot or answer it."}
{"student": "student", "variant": 1, "answers": {"ans1": "20", "ans2": "20"}, "what_happened": "No mark or feedback. I got the error: 'STACK could not mark it: An Error occured while processing the question'.", "why_wrong": "The question could not mark a plain numeric answer. This may be a fault in the question, but I could not tell that from the error."}
{"student": "student", "variant": 1, "answers": {"ans1": "30", "ans2": "20"}, "what_happened": "No mark or feedback. The STACK API request timed out after 30 seconds.", "why_wrong": "I could not check whether this answer was marked fairly. The timeout may come from the server rather than the question, so it is weak evidence."}
```

