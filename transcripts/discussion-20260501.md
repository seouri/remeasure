# Discussion Summary: Labeling Longitudinal Growth Measurements

The group agreed that the main problem is not detecting extreme impossible values, but labeling borderline height deviations where it is impossible to know from the chart alone whether the point reflects measurement/data-entry error or real biological variation. Because of that, the label should not pretend to be objective "truth." It should be framed as a clinician consensus judgment under an explicit operational definition.

The most useful framing that emerged was:

> Given the full longitudinal growth chart, which height measurements deviate enough that they should have been remeasured?

This is more concrete than asking "is this an error?" or "would you take clinical action?" The "take action" threshold felt too high, because clinicians often would not act on a single odd growth point, even if they would still want the measurement repeated. "Remeasure" better captures the practical use case: identifying points suspicious enough that they may compromise downstream growth analysis or patient safety.

## Evaluation Framing

A key distinction was made between:

1. **Retrospective labeling with full chart visibility**

   Humans label using the entire growth trajectory, effectively a "God's-eye view." This is unfair compared with real-time clinical judgment, but it may be the right benchmark if the goal is to clean historical data or evaluate whether Lucy's prospective method approximates what humans could infer only after seeing future points.

2. **Prospective algorithm performance**

   If Lucy's algorithm can perform prospectively as well as clinicians can label retrospectively, that would be meaningful, because the algorithm would be approximating future-informed judgment without seeing the future.

There was also discussion of possibly separating evaluation into harder and softer cases:

- clearly abnormal points that humans agree should be flagged or remeasured;
- near-miss or ambiguous points where variation may be biological or measurement noise.

This would avoid making the whole paper depend on subjective borderline labels.

## Labeling Workflow Proposed

The next labeling process should be structured as:

1. Define the labeling question explicitly:

   "Which data points should have been remeasured because they are significantly off from the likely true growth trajectory?"

2. Show labelers the full longitudinal chart for each patient.

3. Hold a short calibration session with all labelers.

   Review one or two examples together so everyone interprets "remeasure-worthy" similarly.

4. Have labelers independently label cases.

5. Reconvene to reconcile disagreements and produce a consensus dataset.

6. Report inter-rater disagreement and emphasize that the final labels are consensus clinical judgments, not objective ground truth.

## Main Takeaway

The next step is to turn the subjective labeling problem into an explicit, reproducible clinical task: not "is this definitely an error?", but "is this point suspicious enough that it should have been remeasured?" That framing gives Lucy's algorithm and existing error detection rules a fairer, more clinically meaningful benchmark.
