# Literature Synthesis: Longitudinal Growth Measurement Error

Longitudinal height measurements are inherently limited in their capacity to distinguish genuine biological growth from measurement or data entry error. A recorded increase of 3 cm from a preceding measurement, for instance, cannot be unambiguously attributed to true somatic growth, because it may partially or wholly reflect systematic or random error introduced during measurement, recording, or transcription. At the same time, atypical growth trajectories may be clinically meaningful signals of underlying growth-related pathology. Indiscriminate removal of unusual values therefore risks discarding diagnostically valuable information.

The papers in `references/md` support framing the problem not as determining whether a height value is objectively erroneous, but as deciding whether a value is suspicious enough that it should have been remeasured. This aligns with the discussion in `transcripts/discussion-20260501.md`: clinician labels should be treated as consensus judgments under an operational definition, not as ground truth. The proposed labeling question, "Which data points should have been remeasured because they are significantly off from the likely true growth trajectory?", is consistent with the literature's treatment of anthropometric error, longitudinal outlier detection, and the risks of over-cleaning.

## Measurement Error and Reliability

The anthropometry reliability literature establishes that height and length are subject to nontrivial technical error even under standardized protocols. Foundational work on anthropometric measurement error distinguishes imprecision, bias, reliability, and accuracy, and emphasizes technical error of measurement (TEM) as a practical way to quantify repeated-measure variability. WHO Multicentre Growth Reference Study materials show that high-quality growth references required duplicate measurements, observer standardization, repeated training, remeasurement thresholds, and ongoing monitoring. Field studies in Ghana, Ethiopia, Indonesia, and South Africa similarly show that training improves measurement reliability, but length and height remain harder to measure reliably than weight, especially among infants, young children, and non-specialist fieldworkers.

These findings are directly relevant to Lucy's labeling task. If even trained observers can differ by clinically meaningful amounts, then a discordant longitudinal point should not automatically be treated as a false value. The more defensible interpretation is that the point may be unreliable enough to warrant repeat measurement or review.

## Longitudinal Cleaning Methods

Several papers evaluate methods that use within-person trajectories rather than only population-level cutoffs. Conditional growth percentiles, jackknife residuals, robust regression protocols, growthcleanr, PEANOF, and Harrall-style algorithms all attempt to identify values inconsistent with an individual's observed growth path. These methods are generally better suited to longitudinal EHR or cohort data than simple cross-sectional thresholds because they can detect impossible decreases, sudden implausible velocity changes, carried-forward values, duplicates, unit errors, and transcription errors that may still fall within broad population ranges.

However, these methods remain assumption-dependent. Pediatric height-cleaning algorithms often assume monotonic height increase, bounded growth velocity, and sufficient serial observations. Sparse data limit algorithmic certainty. Clinical populations add further complexity because true disease, treatment effects, nutritional change, endocrine disorders, pubertal timing, or severe obesity can create trajectories that appear unusual but are biologically real. The literature therefore supports using longitudinal algorithms as flagging tools rather than deletion rules.

## Risks of Cross-Sectional Cutoffs and Over-Removal

The strongest cautionary theme across the papers is that biologically implausible value rules can conflate true extremeness with error. Studies evaluating WHO or CDC-style BIV cutoffs in NHANES and very large pediatric datasets found that many high values flagged as implausible were likely real, corroborated by other anthropometric measures or repeated over time. Removing them can reduce estimated obesity prevalence and bias conclusions about high-risk groups.

Similarly, comparisons of BIV methods show wide variation in exclusion rates and poor standardization across studies. Some large epidemiologic studies do not report BIV handling at all, while others use incompatible or under-specified methods. A systematic review found that height has a higher frequency of implausible values than weight and concluded that anthropometric quality should be assessed using multiple indicators rather than a single cutoff. Equity-focused work further warns that cohort-level norms can disproportionately remove observations from underrepresented or marginalized populations, whereas individual-level or phenomenological filtering can better preserve real variation.

For Lucy, this argues against silent deletion. A flagged value should remain visible as a candidate for remeasurement, review, or sensitivity analysis, especially when the value might represent clinically meaningful atypical growth.

## Implications for Evaluation

The literature supports the evaluation framing developed in the discussion note:

1. Human labels should be based on full longitudinal chart review.
2. The label should be "remeasure-worthy" rather than "definitely erroneous."
3. Clearly abnormal points should be distinguished from borderline or ambiguous deviations.
4. Inter-rater disagreement should be reported because the task is inherently judgment-based.
5. Lucy's prospective performance should be compared against retrospective clinician consensus with the caveat that clinicians have future chart visibility.

If Lucy can prospectively identify points that clinicians retrospectively agree should have been remeasured, that would be meaningful. It would indicate that the algorithm approximates future-informed clinical judgment without seeing future measurements. But the output should preserve uncertainty: flag, explain, and prioritize review rather than removing data as if error status were known.

## Bottom Line

The papers collectively justify Lucy as a prospective remeasurement recommender, not an oracle for identifying erroneous growth values. Longitudinal context improves detection of suspicious measurements, but it cannot eliminate the ambiguity between true biological growth, measurement error, transcription error, and clinically meaningful pathology. The most defensible benchmark is therefore consensus clinician judgment about whether a point deviates enough from the likely true trajectory that it should have been remeasured.
