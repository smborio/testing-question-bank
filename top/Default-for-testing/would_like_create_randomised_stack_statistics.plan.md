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
