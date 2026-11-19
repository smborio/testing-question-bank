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

