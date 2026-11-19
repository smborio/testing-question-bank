GOAL (non-negotiable): Students estimate the mean and median of a right-skewed distribution by eye and show they understand the long right tail pulls the mean above the median. Context: August precipitation (mm) in Eastern African cities.

STRUCTURE (non-negotiable): One stacked dotplot, one JSXGraph board. Student drags two labelled vertical lines "Mean" and "Median" along the mm axis; lines start at neutral positions giving nothing away. Three independent parts, each worth 1/3: (1) accuracy of mean; (2) accuracy of median; (3) relative position: mean line strictly right of median line, judged only from line positions, independent of accuracy.

RANDOMIZATION (negotiable): N = 50..99 observations. Bins 6 mm wide from 0, about 8-12 bins, each dot at bin centre. Data built constructively, NO while loops and no regenerate-and-test: draw mode bin (low), tail decay rate and N; bin counts from a fixed right-skewed shape (rise to mode then slow geometric decay) scaled to N; fix rounding so counts sum exactly to N by adding the remainder to the mode bin. Parameter ranges chosen so mean exceeds median by at least ~3 mm for every combination; Author checks across the whole parameter grid. City names not randomised.

ANSWER TESTS (negotiable): True mean and median computed from the plotted binned dots. Accuracy is percentage of true value (intentional, do not change): full marks within 10%, half marks within 20%, else 0. Position: full marks if mean line strictly right of median line, else 0; scored even if both estimates inaccurate. Line positions read from the board and graded on the question side; a line never moved scores 0.

FEEDBACK (negotiable): Mean and median parts: feedback depends only on accuracy band (within 10%, within 20%, further off) and gives the true value; no mistake-specific branches. Position part: says only whether the mean is right of the median or not. General feedback after the parts covers: tips for estimating by eye (median halves the dots, mean is the balance point), common slips (mean at tallest stack, median right of mean), and why a long right tail pulls the mean above the median. Worked solution: true mean and median, number of dots on each side of the median. Silent marks: allowed (mistake-specific hints deliberately left out).

PRT/QTEST SUGGESTIONS: Both lines at exact true values: full marks. Lines swapped: position part 0. Mean estimate at +15% of true value: half marks.

REFERENCE POINTERS:
Specialist_tools/JSXGraph/JSXGraph.md
Specialist_tools/JSXGraph/Binding.md
Authoring/Answer_Tests/Grading_recipes.md
CAS/Random.md
CAS/Statistics.md

ADDITIONAL LANGUAGES: (none)
