# JAMIA Manuscript Improvement Plan

## Recommended Target

Aim first for **JAMIA Research and Applications** if the paper is positioned as an informatics method plus formative evaluation. JAMIA fits clinical care, clinical research, implementation science, and biomedical informatics systems, but expects a structured abstract with `Objective`, `Materials and Methods`, `Results`, `Discussion`, `Conclusion`, main text with `Background and Significance`, and tight length limits: 4000 words, 250-word abstract, 4 tables, 6 figures.

Use **Journal of Biomedical Informatics** as the second target if you emphasize generalizable methodology. JBI describes itself as a methodology journal and allows a structured abstract up to 300 words, body up to 6000 words, and up to 8 total figures/tables.

## Step-By-Step Plan

1. **Choose the submission frame before rewriting.**
   Pick one: `JAMIA Research and Applications` as the default, `JBI Original Research` as fallback, or `npj Digital Medicine` only if you can strengthen clinical validation, data/code transparency, and implementation relevance. The current manuscript is closest to JAMIA/JBI.

2. ~~**Sharpen the central claim.**~~
   ~~Current language around "epistemological," "definitionally correct," "only task formulation," and "catastrophically low specificity" is memorable but reviewer-risky. Recast as: retrospective labels are limited; prospective remeasurement creates a practical path to recoverable reference measurements; the present study is a preclinical/retrospective streaming evaluation plus operational burden analysis.~~

3. ~~**Reduce overclaiming in the abstract and conclusion.**~~
   ~~Replace "outperforms" with more exact claims: "achieved higher sensitivity than streaming comparator implementations, with lower specificity than Daymont and much higher specificity than the EPIC 10% rule." Also remove or soften "EHR-agnostic and amenable to FHIR-based deployment" unless implementation details are added.~~

4. **Add a contribution box or significance statement.**
   Include 3 bullets: prospective task formulation; streaming multi-detector alert algorithm; evaluation on Harrall simulations plus large EHR alert-burden analysis. For JBI, explicitly explain why the method generalizes beyond pediatric height.

5. **Restructure for target journal compliance.**
   For JAMIA, rename `Background` to `Background and Significance`; make abstract headings match JAMIA exactly; add `Discussion` to the abstract; keep the main paper near 4000 words. For JBI, add a clearer `Related Work` section and keep the body under 6000 words.

6. **Add a reproducibility subsection.**
   State the code repository, simulation dataset source, exact software versions, threshold settings, growth-chart tables, and whether PPOC data can be shared. JAMIA requires a Data Availability Statement, and Nature/npj-style journals require transparent data/material/code availability for original research.

7. **Add ethics, governance, and privacy statements.**
   The PPOC EHR extract needs IRB status, waiver/consent status, de-identification details, data-use constraints, and whether authors had access to identifiable data. This is currently missing.

8. **Strengthen validation reporting.**
   Add confidence intervals for sensitivity, specificity, PPV/NPV where calculable, and alert burden. Add subgroup alert-burden analyses by age band, sex, visit type, and number of prior measurements. Reviewers will ask whether the method overalerts infants, adolescents, sparse-history patients, or specific demographic groups.

9. **Add ablation and calibration analyses.**
   Report detector-level ablations: hard rules only, velocity only, no LOWESS, no soft HAZ, no carry-forward rule, and full ensemble. Add calibration/reliability plots for fused confidence if possible. This turns the algorithm from a plausible construction into an interpretable informatics method.

10. **Clarify comparator implementation.**
    The streaming Daymont and Harrall reimplementations are central to the paper. Add enough detail that a reviewer can reproduce them, and put pseudocode in a supplement. Explicitly separate "original retrospective algorithm performance" from "our streaming adaptation."

11. **Make the real-world EHR analysis less vulnerable.**
    The PPOC section currently reports only alert volume. Add denominator details: number of height measurements actually eligible, missingness exclusions, duplicate visits, implausible ages, sex missingness, visit spacing distribution, and number of patients with sufficient history.

12. **Use AI/CDS reporting guidelines as a checklist, not as branding.**
    Because this is a decision-support alert rather than a deployed live study, borrow from DECIDE-AI for workflow, human factors, safety, and implementation reporting, while being clear that this manuscript is not yet a live clinical evaluation. DECIDE-AI is designed for early-stage live clinical evaluation of AI-based decision support systems.

13. **Add a limitations table.**
    Include: simulation ground truth only; no prospective remeasurement; height only; hand-set weights; single real-world network for burden; possible unmeasured workflow impact; no race/ethnicity fairness evaluation yet; proprietary EPIC rule details approximated by 10% rule.

14. **Improve figures for reviewer comprehension.**
    Add one workflow schematic: EHR entry -> prior-history retrieval -> hard rules -> soft detectors -> noisy-OR -> remeasure alert -> clinician action. Keep current performance figures, but make captions self-contained and add exact denominators.

15. **Prepare a supplement.**
    Include algorithm pseudocode, detector thresholds, growth-reference derivation, comparator details, full threshold table by dataset, ablations, subgroup burden tables, and reproducibility instructions.

16. **Rewrite discussion around three claims.**
    Claim 1: retrospective growth-error adjudication has intrinsic limits. Claim 2: prospective alerting makes remeasurement possible. Claim 3: this preclinical streaming evaluation shows sufficient performance and operational feasibility to justify prospective study. Drop repeated philosophical framing.

17. **Final submission package.**
    Add title page, author affiliations, corresponding author, CRediT roles, funding, competing interests, acknowledgments, data availability, code availability, ethics statement, figure alt text, and journal-specific formatting. JAMIA also requires figure alt text in the manuscript.

## Highest-Leverage Change

The highest-leverage change is not more rhetoric; it is turning this into a rigorously reported, reproducible, claims-disciplined informatics evaluation. The paper has a strong idea, but top-tier reviewers will need transparent implementation details, uncertainty intervals, ablations, ethics/data statements, and carefully bounded conclusions.
