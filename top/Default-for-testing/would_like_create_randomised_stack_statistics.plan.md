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
