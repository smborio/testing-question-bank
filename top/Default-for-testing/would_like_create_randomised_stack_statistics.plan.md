Question name: "Place mean and median in stacked dot plot". Category: default-for-testing.

GOAL (non-negotiable): Students estimate by eye the mean and median of a right-skewed distribution and show they understand that the long right tail pulls the mean above the median. Context: August precipitation (mm) in Eastern African cities.

STRUCTURE (non-negotiable): One stacked dotplot on one JSXGraph board. The dots are drawn as crosses. The student drags two labelled vertical lines, "Mean" and "Median", along the mm axis by grabbing the lines themselves (horizontal movement only). The labels sit near the top of the lines, clear of the axis labels and of each other. The lines start at two different positions that give nothing away (start order random per variant). Three independent scored parts, equal weight (1/3 each):
1. Accuracy of the mean estimate.
2. Accuracy of the median estimate.
3. Relative position: the mean line is to the right of the median line. Judged only from the two line positions, independent of accuracy. Equal positions score 0.

RANDOMIZATION (negotiable):
- Number of observations N: random integer 50 to 99.
- Data: N gamma quantiles quantile_gamma((i-0.5)/N, k, theta), i = 1..N, with shape k from 2 to 3 and scale theta from 9 to 12 mm. Each value goes into a 6 mm bin starting at 0 and is plotted at the bin centre. There are 12 to 14 bins, and the last bin takes anything beyond it. If quantile_gamma is too slow, count per bin from cdf_gamma at the bin edges (rounded to sum to N, remainder in the mode bin).
- Generation must be fast and simple: no loops with retries, no lambda, no heavy nested lists.
- Mean minus median is about theta/3, at least 3 mm. Verify it over ALL combinations of N, k, theta and nb, and state the minimum gap found. Narrow the ranges if needed.
- Start positions of the two lines: two distinct fixed positions (4 and 6*nb-4) well away from the true values, in random order per variant.
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
