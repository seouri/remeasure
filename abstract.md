# Structured Abstract

## Background

Pediatric height and weight measurements recorded in electronic health records are vulnerable to measurement, recording, and transcription error. Existing data-cleaning methods identify extreme biologically implausible values, but many suspicious measurements fall within population ranges while deviating from an individual child's trajectory. Once recorded, true error status is often unknowable because measurement error, biological variation, and clinically meaningful growth abnormalities can appear similar in retrospect.

## Objective

To develop and evaluate a prospective remeasurement alert method for newly entered pediatric growth measurements, reframing the task from retrospective error adjudication to real-time identification of values that warrant immediate repeat measurement.

## Methods

We developed a trajectory-aware alerting approach that evaluates each new height or weight measurement using only information available at entry. The method combines age- and sex-standardized growth-chart position, within-child change, growth velocity, and deviation from the child's expected trajectory into a single remeasurement score. We evaluated the method in simulated pediatric growth trajectories with injected measurement errors, including the Harrall simulation framework, by sequentially presenting measurements to mimic prospective use. Primary outcomes were injected-error capture, total alert rate, non-injected alert rate, and estimated additional remeasurements per clinic day across candidate thresholds.

## Results

Across [N] simulated children and [N] growth measurements, [N] injected errors were evaluated. At the prespecified threshold, the method captured [X%] of injected errors, generated alerts for [Y%] of all measurements, and flagged [Z%] of non-injected measurements. Threshold analyses showed that capturing [X%] to [X%] of injected errors required remeasurement of [Y%] to [Y%] of measurements, corresponding to [N] to [N] additional remeasurements per day in a clinic seeing [N] pediatric growth-measurement visits daily. Flagged examples included population-plausible but trajectory-discordant measurements missed by cross-sectional biologically implausible value rules.

## Conclusions

Ambiguous pediatric growth measurements should not be treated as retrospectively knowable errors when true values cannot be recovered. A prospective remeasurement alert system offers a clinically actionable use of longitudinal growth modeling by flagging suspicious measurements while the child can still be remeasured. Reporting threshold-dependent tradeoffs as remeasurement burden may help health systems choose settings appropriate to local workflow and tolerance for missed errors.

## Keywords

Pediatric growth; anthropometry; electronic health records; measurement error; data quality; longitudinal data; clinical decision support; remeasurement.
