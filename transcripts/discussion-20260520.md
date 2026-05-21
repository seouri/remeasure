# Discussion Summary: Reframing Growth Data Error Detection as Remeasurement Alerts

This meeting built on the May 1 discussion about the difficulty of labeling pediatric growth measurements as "errors" after the fact. The earlier discussion settled on a more clinically meaningful labeling question: which points are suspicious enough that they should have been remeasured? This meeting pushed that idea further into a revised paper framing: the project should not be presented as a retrospective data-cleaning algorithm, but as a prospective alert system for new height or weight measurements that may warrant immediate remeasurement.

## Core Problem: Signal and Noise Cannot Be Separated Retrospectively

The central argument is that once a height or weight measurement has been taken, entered, and saved in the EHR, the opportunity to know the true value is gone. A deviation from the expected growth trajectory may reflect pathological growth, measurement error, data-entry error, ordinary biological variation, or some mixture of these.

Extreme impossible values, such as biologically impossible heights, can still be filtered out. The harder and more important cases are values that fall within the possible population range but are implausible for that specific child's longitudinal trajectory. These "inlier" problems are difficult because the point is not obviously impossible in the population distribution, but it may be suspicious relative to the child's own growth history.

The group agreed that this makes retrospective ground truth very fragile. Even trained clinicians may not reliably distinguish pathological signal from data error when looking backward at borderline deviations. Inter-rater consistency is expected to be low, especially as the labeling task expands to more subtle points.

## Why Retrospective Ground Truth Is Hard

Several reasons were identified for avoiding a paper that depends heavily on retrospective error labels:

1. Once a measurement is recorded, it is impossible to remeasure the child at that prior age.

2. Pathological signal and measurement noise can look similar in longitudinal data.

3. True gold-standard data would require an impractical prospective study: many children, repeated measurements over years, deliberate inclusion of healthy and pathological cases, and repeat measurements triggered whenever a value appears suspicious.

4. Simulated or relabeled datasets can make an algorithm look better or worse depending on assumptions and label choices.

5. Measurement itself has variation from posture, age, time of day, measurer technique, biological fluctuation, and data-entry processes.

Because of this, the paper should be explicit that it is not trying to solve retrospective data cleaning or claim objective ground truth for ambiguous historical measurements.

## Proposed Paper Framing

The proposed framing is:

> Pediatric growth data contain unavoidable uncertainty once recorded in the EHR. Rather than trying to retrospectively declare ambiguous points true errors, this work proposes a prospective remeasurement alert method that flags newly entered measurements when they deviate substantially from the child's expected longitudinal trajectory.

This reframing separates the project from prior work that tries to clean historical growth data. The paper can still discuss prior data-cleaning methods, but mainly to motivate why the prospective alert setting is more defensible and clinically actionable.

The practical output should be a recommendation such as "remeasure" plus a score indicating how strongly the measurement deviates from expectation. The threshold for issuing an alert can then be chosen by the user or clinical setting based on tolerance for false positives and workflow burden.

## Algorithm and Output

The current approach uses longitudinal information to estimate whether a new measurement is plausible for a specific child, not merely whether it lies inside or outside the population growth-chart range. Relevant derived metrics may include population z-score, percentile, height or weight velocity, change over age, and trajectory-relative deviation.

The group discussed combining multiple component metrics into a single composite score. The exact method for combining scores should be kept simple and justifiable, ideally drawing on existing approaches for combining z-scores or anomaly metrics rather than inventing an unnecessarily complex method.

The paper should avoid making every internal metric threshold the central decision point. Instead, it should produce one final score, then show how different final-score thresholds affect alerting behavior.

## Evaluation Strategy

Harrall's simulated data can be used for evaluation because it already contains injected errors. However, the paper should be careful about terminology. The algorithm should not be described as proving which real-world points are true errors. In the simulated setting, it can report how many injected errors would have triggered a remeasurement alert at each threshold.

Suggested analyses include:

1. Run the algorithm prospectively by feeding data only up to each measurement point.

2. Compute a remeasurement confidence or anomaly score for each point.

3. Vary the alert threshold and report how many measurements are flagged.

4. In the simulated dataset, report how many injected errors are captured at each threshold.

5. Identify thresholds that capture all or most injected errors, then report the corresponding number of additional non-injected measurements that would also be remeasured.

This is essentially an ROC-style or threshold tradeoff analysis, but the interpretation should be centered on remeasurement burden and operational choice rather than an absolute claim about error truth.

## Clinical Workflow and Alert Burden

A key result should be how the threshold translates into clinical workload. A remeasurement alert is less consequential than a diagnostic clinical decision support alert, so a somewhat higher false-positive rate may be acceptable. Still, too many alerts could create alert fatigue or burden nurses and clinic staff.

The paper should therefore include a simple operational calculation: for a typical pediatric clinic seeing a certain number of patients per day, a chosen threshold would lead to approximately some number of additional remeasurements per day. This makes the method interpretable for deployment.

Future work could evaluate the system in live clinical practice by measuring alert rate, remeasurement rate, data quality improvement, and staff burden after deployment.

## LLM and Representation Experiments

There was a side discussion about possible future LLM-related projects. One idea is to test whether LLMs perform better when growth data are provided in different representations:

- raw age and height or weight values;
- age plus z-scores;
- age plus percentiles;
- age plus z-scores and percentiles;
- age plus velocity or delta features;
- image-based growth charts.

The expectation is that general-purpose LLMs probably do not reliably compute CDC/LMS z-scores from raw measurements unless they are using an explicit tool. They may approximate percentiles incorrectly, especially away from the 50th percentile. A future project could compare text-table inputs with image-based growth chart inputs, or even train an open-source model on a large corpus of growth-chart images.

This was treated as an interesting possible second paper, not the immediate priority.

## Immediate Next Steps

The near-term goal is to move quickly toward a paper draft before Lucy's graduation period reduces available momentum.

Proposed next steps:

1. Use the meeting transcript and prior discussion summary to draft an abstract and introduction around the prospective remeasurement-alert framing.

2. Produce a short list of expected figures and tables, likely no more than four or five.

3. Reintroduce or compute a final confidence/anomaly score if feasible within the timeline.

4. Run the method on Harrall's simulated dataset.

5. Report alert counts across thresholds and, for the simulated injected errors, the number captured at each threshold.

6. Add a clinic-workload interpretation, such as expected additional remeasurements per day at selected thresholds.

7. Use Joon's curated literature collection on pediatric growth data quality, measurement error, and cleaning algorithms to support the introduction and discussion.

## Main Takeaway

The paper should make a clear conceptual move: ambiguous historical growth measurements cannot be reliably labeled as pure error or pure clinical signal once they are recorded. The more defensible contribution is a prospective remeasurement alert system that acts while the child can still be remeasured. This avoids overclaiming retrospective ground truth and turns the method into a practical clinical workflow tool.
