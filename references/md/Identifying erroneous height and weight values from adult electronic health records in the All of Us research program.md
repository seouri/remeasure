Journal of Biomedical Informatics 155 (2024) 104660

Contents lists available at ScienceDirect

![image 1](<Identifying erroneous height and weight values from adult electronic health records in the All of Us research program_images/imageFile1.png>)

# Journal of Biomedical Informatics

journal homepage: www.elsevier.com/locate/yjbin

![image 2](<Identifying erroneous height and weight values from adult electronic health records in the All of Us research program_images/imageFile2.png>)

Original Research

## Identifying erroneous height and weight values from adult electronic health records in the All of Us research program

Andrew Guidea, Lina Suliemanb, Shawn Garbetta, Robert M Croninc, Matthew Spotnitzd, Karthik Natarajand, Robert J. Carrollb, Paul Harrisb, Qingxia Chena,b,*

- a Department of Biostatistics, Vanderbilt University Medical Center, Nashville, TN, United States
- b Department of Biomedical Informatics, Vanderbilt University Medical Center, Nashville, TN, United States
- c Department of Internal Medicine, The Ohio State University, Columbus, OH, United States
- d Department of Biomedical Informatics, Columbia University, New York, NY, United States


![image 3](<Identifying erroneous height and weight values from adult electronic health records in the All of Us research program_images/imageFile3.png>)

##### A R T I C L E I N F O

A B S T R A C T

Keywords: All of Us Research Program Data quality Electronic Health Records Measurement error

Introduction: Electronic Health Records (EHR) are a useful data source for research, but their usability is hindered by measurement errors. This study investigated an automatic error detection algorithm for adult height and weight measurements in EHR for the All of Us Research Program (All of Us).

Methods: We developed reference charts for adult heights and weights that were stratified on participant sex. Our analysis included 4,076,534 height and 5,207,328 wt measurements from ~ 150,000 participants. Errors were identified using modified standard deviation scores, differences from their expected values, and significant changes between consecutive measurements. We evaluated our method with chart-reviewed heights (8,092) and weights (9,039) from 250 randomly selected participants and compared it with the current cleaning algorithm in All of Us. Results: The proposed algorithm classified 1.4 % of height and 1.5 % of weight errors in the full cohort. Sensitivity was 90.4 % (95 % CI: 79.0–96.8 %) for heights and 65.9 % (95 % CI: 56.9–74.1 %) for weights. Precision was 73.4 % (95 % CI: 60.9–83.7 %) for heights and 62.9 (95 % CI: 54.0–71.1 %) for weights. In comparison, the current cleaning algorithm has inferior performance in sensitivity (55.8 %) and precision (16.5 %) for height errors while having higher precision (94.0 %) and lower sensitivity (61.9 %) for weight errors. Discussion: Our proposed algorithm outperformed in detecting height errors compared to weights. It can serve as a valuable addition to the current All of Us cleaning algorithm for identifying erroneous height values.

### 1. Introduction

Electronic Health Records (EHR) data are a valuable source for research, but they often contain errors that can compromise the reliability of clinical research.[1,2] Common physical measurements like height and weight are frequently used in research, but data accuracy is key. Erroneous data are a major issue in EHR databases.[3–6] Daymont et al. found incorrect values among 4.5 % of height measures and 3.8 % of weights in a study performed on 2 million pediatric patients.[7] A manual review by a clinician is a reliable error-checking method but can be costly and subject to errors itself.[5] Considering the massive amount of data in EHR repositories, manual detection of all errors is unfeasible.

Ideally, errors within height and weight measurements in EHRs would be identified automatically. Several such algorithms exist, with

their focus depending on error types and target populations. Previous research has flagged implausible height values using deviations from a preset cutoff and detected weight errors by calculating relative differences in measurements over time.[8–10] Khan’s approach considered unit correction across multiple sites, addressing inconsistent, missing, or incorrect unit usage.[11] However, identifying erroneous inliers—values plausible within the population but implausible within an individual trajectory—remains challenging. These inliers, often undetected by existing methods, can compromise data analysis.[12] Even after applying the World Health Organization (WHO)’s criteria for implausible values, Phan et al. found a persistent 3 % error rate.[13] Daymont et al. combined extreme outlier and adaptive inlier detection for error identification within pediatric growth charts.[7] This algorithm was recently extended to accommodate adult data.[14] However, due to the

* Corresponding author at: 2525 West End, Suite 11133A, Nashville, TN, 37203, United States. E-mail address: cindy.chen@vumc.org (Q. Chen).

https://doi.org/10.1016/j.jbi.2024.104660 Received 8 November 2023; Received in revised form 29 April 2024; Accepted 21 May 2024

Available online 23 May 2024 1532-0464/© 2025 The Authors. Published by Elsevier Inc. This is an open access article under the CC BY-NC license (http://creativecommons.org/licenses/bync/4.0/).

lack of a reference chart for adults, the extension was based on raw measurement values despite the demonstrated benefit of using reference charts in Daymont et al. [7].

The All of Us Research Program (All of Us) collects raw EHR physical measurements, including height and weight.[15] While a rule-based cleaning algorithm was applied to the raw values to remove errors, it did not utilize individual profiles to identify potential inlier errors.[11] This paper extended Daymont et. al.’s algorithm to detect erroneous inliers within individual trajectories for an adult population in All of Us. Our contributions are multifold: (1) Unlike Daymont et al. who used existing growth charts for pediatrics, we leveraged unbalanced longitudinal EHRs to establish the reference chart for adults. This expands the method’s applicability, enabling possible methods of error detection for other vital measurements within EHRs such as body mass index (BMI) and waist-to-hip ratio. (2) To better fit the statistical nature of our data, we extended the standard deviation score to accommodate the additional kurtosis parameter observed in the data. This is a significant statistical enhancement that allows for better handling of extreme values or outliers, thus improving the reliability of our model’s results.[16].

Problem Electronic Health Record usage in research is hindered by

measurement errors. What is Already

Several algorithms exist to automatically identify errors in weights and heights with the focus depending on error types and target populations. However, identifying erroneous inliers—values plausible within the population but implausible within an individual trajectory—remains challenging.

Known

What this Paper Adds

We developed a statistical model to create reference charts for adult heights and weights and assigned errors based on extreme measures, changes based on individual trajectory curves, and excessive changes in consecutive measurements. It provides additional cleaning methods for All of Us.

### 2. Methods

- 2.1. Population

The All of Us is a national initiative to gather and study biomedical data for research from one million or more U.S. diverse residents, including EHR data from healthcare visits.[15] To extract measurements, we used LOINC codes from the Observational Medical Outcomes Partnership (OMOP) common data model: 8302–2, 3137–7, and 3138–5 for heights, and 29463–7, 3141–9, and 3142–7 for weights.[17] We included All of Us participants aged 18 or older at the time of measurement, considering their non-null height and weight values after performing the unit conversion procedure outlined by Khan and Carroll. [11] We included participants with at least one non-null measurement of height or weight.

- 3. Reference chart for adult population


The Centers for Disease Control and Prevention (CDC) growth charts, used by Daymont et. al. to detect erroneous weight and height records, are the reference for children’s growth in the United States. These charts were developed with the lambda, mu, sigma (LMS) model using data from a large cross-sectional pediatric cohort, with a single record per child.[18,19] However, applying the LMS models directly to adult EHR data presents limitations: (a) Unlike the one observation per person used in LMS, EHRs have varying numbers of measurements per individual; (b) LMS estimates parameters at age interval, requiring a large sample size at each interval, without using the information from other age interval ranges; (c) LMS does not account for kurtosis, found to be useful for creating accurate growth charts.[20] Kurtosis measures data in the distribution tails, aiding in model creation.[21].

To create trajectory charts using adults’ longitudinal EHR height and weight measurements, we used a weighted extension of the generalized

additive models for location, scale, and shape (GAMLSS) parameters. [22] The GAMLSS models incorporate a Box-Cox transformation to model the mean, standard deviation, skewness, and kurtosis of the BoxCox t-family. Each of the four parameters was modeled by stratifying on sex at birth. In All of Us, participants provided their sex-at-birth (Male, Female, Another sex) in surveys. Further details on the GAMLSS model are provided in the supplemental material.

These models also had to consider the significantly varying and skewed number of records per individual. To account for this, each measurement was assigned a modeling weight, the reciprocal of an individual’s total records count, addressing the imbalance in measurements numbers between participants. This led to weighted GAMLSS (wGAMLSS) models. Through wGAMLSS, height and weight quantiles could be established for sex groups.

3.1. Proposed algorithm

It is important to note that the likelihood of observing the same unit change varies across different subjects. For instance, a 10 kg reduction in weight within one month is more common among overweight individuals than among underweight individuals.[23] Therefore, it is necessary to normalize the measurements to a more comparable quantity. The z-score is a common statistic implemented to achieve this goal. However, researchers at the CDC found that z-score was not sensitive in identifying errors at the extremes and suggested standard deviation scores, an extension of z-score at the tail, to better identify errors at the extremes for the LMS model.[18] We further extended this score with wGAMLSS to incorporate kurtosis and computed modified standard deviation scores (MSDS) for each measurement (details in supplemental material).[24] MSDS quantified the relative position of measurement on the population distribution. We considered the measurement extreme or implausible if the absolute value of MSDS exceeded a predetermined threshold of 25.[7].

Since a possibility for variation exists within MSDS during certain age intervals, MSDSs were normalized by subtracting each participant’s median MSDS from their individual MSDS.[7] We used this conservative cutoff for MSDS to ensure that the heights and weights being removed were indeed biologically implausible.[7].

Next, we calculated the expected MSDS, called exponentially weighted moving average (EWMA), to leverage the correlated measurements from the same individual. EWMA of each measurement was calculated using the remaining measurements from the same participant [7,25] and was defined as:

∑

k∈Ni jMSDSik×(5 + |ageik ageij|) 1.5 ∑

EWMAij = MSDŜ ij =

(1)

k∈Ni j(5 + |ageik ageij|) 1.5

Where EWMAij is the expected MSDS for participant i at ageij and ℕi j is the collection of indices for participant i with the measurement at ageij removed.

To improve the robustness, in addition to the overall EWMA as described, we also calculated the EWMA in two additional ways for each measurement: EWMA values after excluding the preceding value and EWMA value excluding the following value. A measurement was determined to have extreme EWMA values if there was a large difference between the observed MSDS value and EWMA.

EWMA was then used to detect moderate inliers which would be more challenging for a human reviewer to detect. A total of eight different EWMA classifications were made depending on the location of the value within an individual trajectory (first, middle, last). For all EWMA exclusions, measures were marked iteratively; the algorithm excluded one measure at a time and looped through all remaining measurements until no more exclusions were assigned. An individual needed to have at least three measurements to qualify for EWMA classifications.

Large changes between consecutive measurements were also considered as an exclusionary criterion. Heights do not often change once a person reaches adulthood, and while some growth continues into a person’s early twenties, growth typically ceases around this age. Thus, we would not expect to see drastic changes in an adult’s height over time, but small variations in recorded height are inevitable. To determine how much change in height was acceptable, we used sensitivity curves to determine the optimal threshold to maximize the precision while controlling the negative predictive value (NPV) at an acceptable value. The potential height cutoffs ranged from 3 to 12 cm, and the resulting curves are displayed in Fig. 1. Based on these curves, we chose a value of 8 cm to be the cutoff used in the evaluation, as this was the height value which was deemed to maximize precision and recall while also minimizing NPV. Additionally, a study on young Polish adults suggested that the most extreme change in heights compared to their adolescent measurements was 7 cm, indicating that our cutoff would be conservative to minimize the risk of marking true values as errors.[26].

A similar method was used to determine an appropriate cutoff for weights, with the weight cutoffs varying from 5 to 50 kg in multiple of 5; the results are shown in Fig. 2. We determined that 15 kg was the appropriate cutoff between consecutive weights. Since weight fluctuates

more for adults than heights and can be impacted by lifestyle or clinical events such as pregnancy, we only marked consecutive measurements if they were no more than 180 days apart. The algorithm marked the measure with the highest impact on EWMA as an error and iteratively marked these errors with the dataset until no more were discovered.

In addition to the error classifications, we marked measurements with a warning flag if they were repeated measures (differing measurements on the same day) or carried forward (identical values repeated over subsequent days). Daymont et al. marked values carried forward as errors because height and weight increase steadily as children age. This pattern, however, does not hold for an adult population. Adult heights tend to be stable over time while weights can fluctuate for reasons unrelated to age. Since heights are expected to be stable, this leads to a large proportion of heights being carried forward. Unlike in Daymont et. al., we did not exclude these values but merely flagged them to track their presence within the data.[7] Measures were marked as potential carried forward and repeated values at the beginning of the algorithm, and all measurements given these warning flags could still be marked as errors using any of the exclusion criteria considered within the automated method.

![image 4](<Identifying erroneous height and weight values from adult electronic health records in the All of Us research program_images/imageFile4.png>)

- Fig. 1. Sensitivity curves used to determine the optimal height cutoff for consecutive records, with the potential cutoff varying from 3 to 12 cm increasing in 1-centimeter intervals. The optimal cutoff was chosen by maximizing the precision while controlling the false positive rate at an acceptable value.


![image 5](<Identifying erroneous height and weight values from adult electronic health records in the All of Us research program_images/imageFile5.png>)

- Fig. 2. Sensitivity curves used to determine the optimal weight cutoff for consecutive records, with the potential cutoff varying from 5 to 50 kg increasing in 5-kilogram intervals. The optimal cutoff was chosen by maximizing the precision while controlling the false positive rate at an acceptable value.


- 3.2. Algorithm evaluation


To assess the performance of our algorithm, two random selections each with 250 participants were generated for a manual chart review for height and weight. Two manual reviewers (LS and SG) blindly annotated whether each sampled participant’s measures (n = 8092 heights, n = 9039 weights) were plausible or implausible. When the two reviewers disagreed, a third reviewer (RMC) made a final decision on all measures with differing annotations. At evaluation, reviewers were presented with sex, age at measurement, and measurement values. We then calculated the sensitivity, specificity, precision, NPV, accuracy, and F1score of the algorithm using the annotated values and constructed their confidence intervals using exact binomial confidence limits. We reported the evaluation metrics when warnings were considered as errors to compare with Daymont et al. as well as when excluding measurements with warnings.[7] Additionally, we calculated Cohen’s kappa to judge the agreement between the two reviewers.

Finally, we wanted to determine if our method would be a useful data error detector in addition to the cleaning method currently utilized by the curation team in All of Us.[11] The base version of the EHR dataset contains the raw measures collected by All of Us prior to applying the

program’s cleaning algorithm and is the dataset on which we ran our cleaning algorithm. The cleaned version contains the measures after being run through the curation team’s algorithm. To test our method, we considered all measures that appeared in the base version but not in the cleaned version to be errors identified by the current method implemented by All of Us and ran performance metrics using the aforementioned chart review to compare the error detection results of our method against the current cleaning procedure. We also conducted a comparison with Daymont’s “cleanadult” function to evaluate the impact of employing MSDS versus raw measurements in the algorithm.[14].

All analysis and error detection methods were done using R version 4.2.2 in the All of Us Researcher Workbench. The percentile models using wGAMLSS used the gamlss package in R.

### 4. Results

4.1. Automated error classification

From the Fifth Release of the All of Us EHR Registered Tier (https:// workbench.researchallofus.org/login), we used a total of 4,076,534 height measurements from 149,244 participants and 5,207,328 wt

measurements from 150,372 participants recorded in EHRs.[15] Among all eligible height and weight measurements evaluated by the automated error detection method, approximately 1.4 % of heights and 1.5 % of weights were classified as errors. Table 1 shows the full error breakdown from the algorithmic detection. The most common error classification was an erroneous inlier, defined as a violation of the maximum permitted change between consecutive measurements. This is likely due to the nature of adult data, as substantial deviations in height measures are likely to be implausible, and extreme changes in weight over a short time period are problematic. Approximately 1.2 % of heights and 0.96 % of weights were determined to have violated the consecutive measurement rule; this error classification made up 83.0 % and 64.1 % of errors for heights and weights, respectively.

Errors related to EWMA change within a participant’s trajectory were also common compared to other error classifications, constituting 13.3 % of height errors and 34.8 % of weight errors. Errors based on extreme values were less common; 171 (<0.01 %) heights were excluded for extreme MSDS, and more heights than weights were marked as having extreme EWMA (1,873 vs. 828). As shown in Table 1, approximately 66.2 % of heights were carried forward, and 7.9 % were repeated measures, whereas 10.8 % and 17.7 % of weights were carried forward and repeated measurements, respectively.

Examples of individual trajectory curves against height and weight percentile curves can be found in Fig. 3 (true positives) and 4 (false positives). We shifted heights, weights, and ages by a value randomly sampled from 10 to 10 to protect participant confidentiality but preserve the pattern. In Fig. 3, we can see that although the marked errors are not extreme values by themselves, they stand out as erroneous inliers when compared to the other measurements in the trajectory. In Fig. 4, despite large changes between consecutive measures for these values, the measurements are closely clustered with the remainder of the data, making them likely to be correct values.

- 4.2. Algorithm evaluation


The inter-rater agreement, as measured by Cohen’s kappa, was moderate between the two reviewers, with a value of 65 % for heights and a higher value of 78 % for weights.[27] To reconcile any disagreements, we incorporated annotations from a third reviewer in our evaluation process. The kappa values being less than perfect highlight the intricate nature of the problem at hand.

The results of the manual review can be seen in Table 2, which is

Table 1 Classification breakdown by the automated method on height and weight EHR record data.

- A: Exclusions Exclusion Height (n ¼ 4,076,534) Weight (n ¼ 5,207,328)

EWMA^ 7,557 27,022 EWMA-Extreme% 1,873 828 EWMA-Pair$ 57 10 Consecutive Record

Change

47,160 49,824

SD-Cutoff 171 0 Include 4,019,716 5,129,644

- B: Warning Flags Carried Forward 2,697,815 563,031 Repeated Measure 321,699 924,149 None 1,057,020 3,720,148


- A: Breakdown of exclusionary errors made by the automated method.
- B: Breakdown of warning flags (not excluded) assigned by the automated method. ^: Exponentially weighted moving averages, based on the influence of an individual measurement’s impact on the moving average for the person %: Assigned if the measurement has an extreme change in EWMA (>3). $: Assigned if a participant has two measurements on the same day, and one is classified as having an extreme change in EWMA.


divided into two settings depending on the error classifications used. Setting A includes metrics while marking repeated measures and values carried forward as erroneous as in Daymont et al., while setting B considers them as warnings only but not as errors. In setting A, all metrics exceeded 98 % for both height and weight; additionally, sensitivity, specificity, and precision were all greater than 99.5 % among heights. For weights, the precision was slightly lower than height precision (98.3 %), while all other metrics exceeded 99 %. The accuracy of the algorithm was greater than 99 % for both height and weight.

In setting B, the reviewers identified 52 errors in height and 126 among weights out of 8092 and 9039 reviewed heights and weights, respectively. While specificity and accuracy were high (>99 %) for both heights and weights, sensitivity was high for the heights (47/52 = 90.4 %) but significantly lower among weights (83/126 = 65.9 %). Similarly, precision was 73.4 % for heights and 62.9 % for weights. Overall, the algorithm performed better in detecting errors for heights than for weights. This is because weight tends to fluctuate more than height, making it more challenging to identify inaccurate weight values.

Additionally, we compared the method’s performance metrics after stratifying by sex at birth and age groups. We limited the sex stratification to male and female participants since those who identified as neither had too few measurements, and split age by the 33rd and 67th percentiles. For heights, males outperformed females with a precision of 90.5 % compared to 65.1 % for females. This trend was reversed for the weights, as females had a precision of 87.5 % compared to 54.8 % for the male cohort. Within the age categories, those aged 49–62 had the highest precision of 92.9 % while maintaining an acceptable sensitivity of 86.7 %. Among weights, the oldest group had the greatest performance with a precision and sensitivity of 81.1 % and 88.2 %, respectively.

Comparing our method’s performance to that of the existing cleaning process employed in All of Us, the sensitivity (55.8 %) and precision (16.5 %) for the heights were significantly lower in the existing cleaning process. Among weights, the sensitivity was slightly lower (61.9 %), but precision was much higher (94.0 %) in the existing cleaning process. A complete summary of the performance of the current cleaning method is shown in Table 3.

Finally, for the cleanadult function in Daymont [14], sensitivity (7.7 %) was considerably lower in this algorithm for the heights, with majority of height errors being missed by this method. For the weights, the sensitivity (61.1 %) was slightly lower than our method, with the tradeoff of a slightly improved precision (70.0 %).

### 5. Discussion

This study assessed an error detection algorithm’s performance on longitudinal EHR height and weight values among adult All of Us participants. We found 98.6 % of heights and 98.5 % of weights plausible, aligning closely with prior literature on adult error detection algorithms. [13,6,7].

The All of Us Data and Research Center has transformed, harmonized, and anonymized a comprehensive dataset, including EHR data; this process includes conformance checks and the application of a stringent privacy methodology.[28] The final product is the Curated Data Repository (CDR) base. This dataset, released approximately twice a year, is what the proposed algorithm was developed upon.[29] It is worth noting that some values from earlier versions may have been corrected or omitted during EHR updates. Consequently, the latest release is likely a more refined version of the same records. The unit conversion process might also have reduced the error rate by correcting mis-recorded units. Unit conversion allowed some issues existing in the database to be repaired prior to our error detection.

The error detection algorithm’s development and chart review were conducted on the 5th release of the All of Us registered tier dataset, which was the most up-to-date version at the time. However, after various alterations to the method and rounds of reviews, the 7th release

![image 6](<Identifying erroneous height and weight values from adult electronic health records in the All of Us research program_images/imageFile6.png>)

- Fig. 3. Two randomly shifted individual trajectories with true positive classifications for height (Panel A) and weight (Panel B). The percentile curves were constructed by wGAMLSS. In each plot, the points are measurements with correct error classifications based on manual review (red: error, black: plausible value). Heights, weights, and ages are randomly shifted to further de-identify participant IDs but preserve patterns in the data. (For interpretation of the references to colour in this figure legend, the reader is referred to the web version of this article.)


became available to researchers. To check the method’s generalizability, we ran the error detection algorithm on the heights and weights of this current version and presented the results in Table D1 in the Appendix. The results for heights remain similar between the two versions (1.4 % out of 4,076,534 records in the 5th release vs 1.5 % out of 5,912,029 records in the 7th release). However, the algorithm detected a higher error rate in the 7th release for weight (1.5 % out of 5,207,328 records in the 5th release vs 3.44 % out of 8,625,468 records in the 7th release), with a heavier emphasis on EWMA errors among weights. This highlights the dynamic nature of the All of Us dataset and the need to continually execute the algorithm to identify potential height and weight errors.

By extending Daymont et al.’s methodology to the adult All of Us cohort, we expanded its scope, capturing the heterogeneity inherent in a more diverse population. We also developed an updatable algorithm to ensure our reference charts remain relevant, adjusting to health trends in the adult population.

The ’carried forward’ warning was the most common classification for height records, accounting for approximately two-thirds. Given the relative stability of adult heights, this is not surprising. Healthcare

providers often forgo re-measuring heights during clinic visits, instead reporting a prior record. This automation method was initially designed for pediatric populations, where heights are expected to consistently increase, thus no identical heights would be expected in sequential visits. Hence, we removed ’carried forward’ and ’same-day repeated measures’ from the error list, granting them distinct non-error designations. Weights had fewer ’carried forward’ values due to their variable and non-linear progression in adults.

The automated method performed better in detecting height errors than weight. The original method used a 3 cm cutoff for heights, slightly adjusted to account for variations such as wearing shoes in adults. However, setting a plausible cutoff for weights was more challenging due to factors like diet, lifestyle changes, hydration, pregnancy, and medication effects, which can cause significant weight fluctuations. We used a 15 kg cutoff based on two sensitivity curves, but this is not universal and proved to be a conservative decision. The binary 180-day cutoff for marking weight errors was also limited. The height cutoff was robust, maintaining high sensitivity, but the weight cutoff failed to align with manual review values. The sensitivity for weight was lower than ideal, indicating difficulty in distinguishing genuine fluctuations

![image 7](<Identifying erroneous height and weight values from adult electronic health records in the All of Us research program_images/imageFile7.png>)

- Fig. 4. Two synthetic individual trajectories with false positive classifications for height (Panel A) and weight (Panel B). The percentile curves were algorithmic error classifications constructed by wGAMLSS percentile curves. In each plot, the points are measurements with red dots indicating records that were marked as errors by the automated method while being deemed plausible values from a manual review. Heights, weights, and ages are randomly shifted to further de-identify participants but preserve patterns. (For interpretation of the references to colour in this figure legend, the reader is referred to the web version of this article.)


from errors due to volatility. Additional checks or alternative approaches may be necessary for accurate weight measurements.

By developing this error detection algorithm, we established adultspecific thresholds, rather than adopting those designed for pediatric patients. This approach ensures more accurate and relevant healthrelated decisions for adults. Several discrepancies between the automated method and manual review were borderline cases (i.e. a manual review identified an error in a measurement that was 13 kg different from the next, whereas the algorithm did not detect this). Examples of this incorrect error classification, often occurring when measurements just exceeded the cutoff threshold, can be found in Fig. 4.

In comparison to the current cleaning algorithm, the evidence suggested that the proposed method can serve as a valuable addition for identifying erroneous height values. However, its effectiveness for weights may be less pronounced. For heights, our method increased the sensitivity from 55 % to 90 %, capturing implausible values overlooked by the current algorithm. For weights, sensitivity was similar to the current method, indicating our method’s error detection capabilities were roughly equivalent. The prevalence of borderline cases could have led to lower precision in our method than anticipated.

The wGAMLSS algorithm allowed us to extend the reference charts to adjust for conditions that might affect a person’s height and weight in addition to demographic variables. Results of this attempt were included in the supplementary material with, however, little difference from the results adjusting for demographic variables only. This is likely due to inability to distinguish between acute and chronic conditions and lack of evidence to establish the end of the disease as many conditions stored in EHRs did not have ending dates. In the current data release, diet and nutrition information is not available within the All of Us workbench. However, All of Us is actively working to collect diet information from participants, which may become available in subsequent data releases. If this data becomes available in a later release, future error detection methods will work to incorporate this information to improve error classifications.

### 6. Limitations

Despite the promising results, our error detection method has limitations. Primarily, the algorithm’s evaluation was confined to the All of Us data, making its performance on other EHR datasets uncertain.

The performance of the automated error detection algorithm on the annotated dataset.

Group Category Sensitivity (95 % CI) Specificity (95 % CI) Precision (95 % CI)

NPV (95 % CI)

Accuracy (95 % CI)

F1 Score

Setting A* Height All All 99.9

99.5 (99.1–99.8)

99.8 (99.7–99.9)

99.8 (99.5–99.9)

99.8 (99.7–99.9)

0.999

(99.8–99.9)

Sex at Birth Male (N = 2298)

99.9 (99.7–100)

100 (99.3–100)

100 (99.8–100)

99.8 (99.0–100)

100 (99.8–100)

0.999

Female (N = 5757)

99.9 (99.8–100)

99.3 (98.8–99.7)

99.8 (99.6–99.9)

99.8 (99.4–100)

99.8 (99.6–99.9)

0.998

Age 18–49 (N = 2624)

99.9 (99.6–100)

99.1 (98.1–99.7)

99.7 (99.3–99.9)

99.7 (98.9–100)

99.7 (99.4–99.9)

0.998

49–62 (N = 2784)

99.9 (99.7–100)

100 (99.7–100)

100 (99.7–100)

100 (99.7–100)

99.9 (99.8–100)

0.999

62+ (N = 2684)

100 (99.8–100)

99.6 (98.8–99.9)

99.8 (99.6–100)

100 (99.5–100)

99.9 (99.7–100)

0.999

Setting A* Weight All All 99.3

99.4 (99.2–99.6)

98.3 (97.7–98.8)

99.8 (99.6–99.9)

99.3 (99.2–99.5)

0.988

(99.0–99.7)

Sex at Birth Male (N = 3376)

98.3 (97.1–99.1)

98.6 (98.1–99.0)

95.8 (94.2–97.1)

99.4 (99.1–99.7)

98.5 (98.1–98.9)

0.970

Female (N = 5419)

99.7 (99.3–99.9)

99.9 (99.7–100)

99.7 (99.3–99.9)

99.9 (99.7–100)

99.9 (99.7–99.9)

0.997

Age 18–49 (N = 2964)

98.8 (97.9–99.4)

98.8 (98.2–99.2)

97.6 (96.5–98.5)

99.4 (98.9–99.7)

98.8 (98.3–99.1)

0.982

49–62 (N = 2933)

99.4 (98.5–99.8)

99.6 (99.2–99.8)

98.5 (97.3–99.3)

99.8 (99.5–100)

99.5 (99.2–99.7)

0.989

62+ (N = 3142)

99.7 (99.1–100)

99.8 (99.5–99.9)

99.4 (98.5–99.8)

99.9 (99.7–100)

99.8 (99.5–99.9)

0.995

Setting B^Height All All 90.4

99.8 (99.7–99.9)

73.4 (60.9–83.7)

99.9 (99.9–99.9)

99.7 (99.6–99.8)

0.810

(79.0–96.8)

Sex at Birth Male (N = 2298)

95.0 (75.1–99.9)

99.9 (99.7–100)

90.5 (69.6–98.8)

100 (99.8–100)

99.9 (99.6–100)

0.927

Female (N = 5757)

87.5 (71.0–96.5)

99.7 (99.6–99.9)

65.1 (49.1–79.0)

99.9 (99.8–100)

99.7 (99.5–99.8)

0.747

Age 18–49 (N = 2624)

88.0 (68.8–97.5)

99.7 (99.4–99.9)

73.3 (54.1–87.7)

99.9 (99.7–100)

99.6 (99.3–99.8)

0.800

49–62 (N = 2784)

86.7 (59.5–98.3)

100 (99.8–100)

92.9 (66.1–99.8)

99.9 (99.7–100)

99.9 (99.7–100)

0.897

62+ (N = 2684)

100 (73.5–100)

99.7 (99.4–99.9)

60.0 (36.1–80.9)

100 (99.9–100)

99.7 (99.4–99.9)

0.750

Setting B^Weight All All 65.9

99.5 (99.3–99.6)

62.9 (54.0–71.1)

99.5 (99.4–99.7)

99.0 (98.7–99.2)

0.643

(56.9–74.1)

Sex at Birth Male (N = 3376)

52.3 (41.4–63.0)

98.8 (98.4–99.2)

54.8 (43.5–65.7)

98.7 (98.3–99.1)

97.6 (97.1–98.1)

0.535

Female (N = 5419)

83.3 (68.6–93.0)

99.9 (99.8–100)

87.5 (73.2–95.8)

99.9 (99.7–99.9)

99.8 (99.6–99.9)

0.854

Age 18–49 (N = 2964)

56.3 (44.0–68.1)

99.0 (98.5–99.3)

57.1 (44.7–68.9)

98.9 (98.5–99.3)

97.9 (97.4–98.4)

0.567

49–62 (N = 2933)

61.9 (38.4–81.9)

99.6 (99.3–99.8)

52.0 (31.3–72.2)

99.7 (99.5–99.9)

99.3 (98.9–99.6)

0.565

62+ (N = 3142)

88.2 (72.5–96.7)

99.8 (99.5–99.9)

81.1 (64.8–92.0)

99.9 (99.7–100)

99.6 (99.4–99.8)

0.845

CI: Confidence Interval. A*: classified records labeled as repeated measurements and carried forward as errors. B^: records labeled as repeated measurements and carried forward are not considered to be errors, but are subject to other error types.

Despite this, thresholds used in the algorithm were not trained in All of Us manual review data. Instead, many of the thresholds were either adopted or modified from the original Daymont et al. algorithm, which used pediatric data from a Philadelphia children’s hospital. No thresholds were determined by the content of All of Us EHR data and were determined separately.

The algorithm’s error detection performance could also be influenced by the varying quantity and timing of each participant’s measurements. Participants with more frequent measurements, and shorter intervals between them, had clearer indicators of plausibility. For instance, a participant whose weight increased from 70 to 90 kg within three months with only two measurements would be flagged as an error. However, another participant with the same weight upward trend over three months but with multiple evenly spaced measurements showing

2–3 kg increments would be classified as plausible. Without additional data, the automated method struggles to discern whether a significant weight increase is genuine or a data error, a distinction more easily made by a manual reviewer. This method’s inability to account for measurement frequency is a key limitation, particularly since adult weights fluctuate more than pediatric weights.

Finally, our error detection method encountered challenges when assigning errors in cases where measurements were nearly evenly divided between two groups that exceeded the cutoff thresholds for heights and weights. In such cases, the algorithm’s decision to exclude one group over the other could differ from a manual reviewer’s judgment. As a result, the algorithm might exclude values that a human reviewer would not, leading to reduced precision. This problem is further amplified by the absence of an absolute truth or standard for

The performance of the current algorithm implemented by All of Us, cleanadult function in Daymont [14], and the proposed algorithm.

Measurement Sensitivity (95 % CI) Specificity (95 % CI) Precision (95 % CI)

NPV (95 % CI)

Accuracy (95 % CI)

F1 Score

Current Algorithm Implemented by All of Us Height 55.8

98.2 (97.9–98.5)

16.7 (11.5–23.1)

99.7 (99.6–99.8)

97.9 (97.6–98.2)

0.257

(41.3–69.5)

Weight 61.9 (52.8–70.4)

99.9 (99.9–99.9)

94.0 (86.5–98.0)

99.5 (99.3–99.6)

99.4 (99.2–99.6)

0.746

cleanadult Function in Daymont [14] Height 7.7

100 (100–100)

100 (39.8–100)

99.4 (99.2–99.6)

99.4 (99.2–99.6)

0.143

(2.1–18.5)

Weight 61.1 (52.0–69.7)

99.6 (99.5–99.7)

70.0 (60.5–78.4)

99.5 (99.3–99.6)

99.1 (98.9–99.3)

0.653

Proposed Algorithm Height 90.4

99.8 (99.7–99.9)

73.4 (60.9–83.7)

99.9 (99.9–99.9)

99.7 (99.6–99.8)

0.810

(79.0–96.8)

Weight 65.9 (56.9–74.1)

99.5 (99.3–99.6)

62.9 (54.0–71.1)

99.5 (99.4–99.7)

99.0 (98.7–99.2)

0.643

Evaluated under Setting B^: records labeled as repeated measurements and carried forward are not considered to be errors but are subject to other error types. Errors are values that appear in the raw dataset but not in the cleaned version. CI: Confidence Interval.

![image 8](<Identifying erroneous height and weight values from adult electronic health records in the All of Us research program_images/imageFile8.png>)

- Fig. 5. This individual trajectory represents a virtual participant’s height measurements, with age and height shifted and additional pseudo points to protect participant’s privacy. Here the algorithm did not perform as expected due to the presence of two groups of measurements with a fairly even split. Both groups exceed the 8 cm threshold for error detection, but the algorithm has more difficulty determining the group to mark as errors due to the split.


- comparisons. An illustration of this scenario is depicted in Fig. 5. Additionally, this decision-making structure occasionally made it difficult for human reviewers to make clear determinations, as evidenced by the lower kappa values.
- 6.1. Practical applications to research

The explored models and error detection methods offer significant applications to ongoing research in clinical environments that make use of EHR data. Data entry errors are a common issue, given the ease with which they can occur during data entry. Such errors can have a negative impact on research that relies on precise values. The proposed error detection model can help identify potentially implausible values prior to performing data analysis, thus enabling more rigorous and credible results. While the method was used to retrospectively identify erroneous values, it can also be used prospectively, and can allow researchers to find data errors before they can occur and interfere with research. Researchers could also opt to include flagged values in their analyses to assess the potential impact of these implausible entries. Given that our error detection method deemed over 98 % of the values in the All of Us dataset as plausible, the risk of discarding valid data is minimized. Ideally, this approach can supplement existing data cleaning procedures, enhancing the accuracy and reliability of EHR datasets. Future research will involve testing our developed method on external datasets to demonstrate its versatility.

- 7. Conclusion

Inaccuracies in measurement values can potentially undermine the integrity of data-driven research. Height and weight are some of the most reported measures, and it is vital to ensure their accuracy. The automated method developed for identifying errors in height and weight records within the All of Us EHR data represents a promising tool that, when used alongside existing data cleaning methods, can help uncover errors in the voluminous data. The algorithm demonstrated more optimal performance among heights than weights, likely due to heights being far less volatile than weight within-subject trajectories. The automated method was also able to detect the majority of reviewerlabeled errors for height measures and was slightly more likely to classify a measure as implausible than a manual review. Further research is necessary to improve the error detection method by fine-tuning the parameters used to classify values as implausible and balance sensitivity and specificity.

This work was supported by the National Institutes of Health Office of the Director: Data and Research Center under grant 5 U2C OD023196 (AG, LS, SG, RMC, KN, RJC, PH, QC), the National Library of Medicine under T15LM007079 (MS), the National Institute on Minority Health and Health Disparities under R21MD019103 (LS, RMC, QC), and the National Cancer Institute under U24 CA194215 (QC).

- 8. Contributorship statement


AG refined the algorithm, calculated all performance metrics, and drafted the manuscript. AG and QC both developed the code necessary for the algorithm to run. QC contributed to the design of the error detection algorithm, and revised the manuscript. LS, SG, and RMC provided manual chart review and revised the manuscript. MS provided the list of conditions that could affect weights. RJC provided additional knowledge on the All of Us EHR structure and revised the manuscript. KN and PH provided additional edits to the manuscript. All the authors contributed to writing and reviewing the manuscript.

### CRediT authorship contribution statement

Andrew Guide: Writing – review & editing, Writing – original draft, Software, Methodology, Formal analysis, Data curation. Lina Sulieman:

Writing – review & editing, Writing – original draft, Formal analysis, Data curation, Conceptualization. Shawn Garbett: Writing – review & editing, Data curation. Robert M Cronin: Writing – review & editing, Funding acquisition, Data curation. Matthew Spotnitz: Writing – review & editing, Data curation. Karthik Natarajan: Writing – review & editing, Data curation. Robert J. Carroll: Writing – review & editing, Methodology, Data curation, Conceptualization. Paul Harris: Writing – review & editing, Funding acquisition, Conceptualization. Qingxia Chen: Writing – review & editing, Writing – original draft, Supervision, Project administration, Methodology, Investigation, Funding acquisition, Conceptualization.

### Declaration of competing interest

The authors declare that they have no known competing financial interests or personal relationships that could have appeared to influence the work reported in this paper.

### Acknowledgements

The authors would like to thank the participants of the All of Us Research Program who made this research possible. We thank the countless co-investigators and staff across all awardees and partners enrollment sites, without which All of Us would not have achieved our current goals. “Precision Medicine Initiative”, “PMI”, “All of Us”, the “All of Us” logo, and “The Future of Health Begins with You” are service marks of the U.S. Department of Health and Human Services.

### Appendix A. Supplementary data

Supplementary data to this article can be found online at https://doi. org/10.1016/j.jbi.2024.104660.

### References

- [1] E.P. Ambinder, Electronic Health Records, J. Oncol. Pract. 1 (2005) 57–63.
- [2] N.G. Weiskopf, C. Weng, Methods and dimensions of electronic health record data quality assessment: enabling reuse for clinical research, J. Am. Med. Inform. Assoc. 20 (2013) 144–151.
- [3] S.K. Bell, T. Delbanco, J.G. Elmore, et al., Frequency and Types of Patient-Reported Errors in Electronic Health Record Ambulatory Care Notes, JAMA Netw. Open 3

(2020).

- [4] T. Botsis, G. Hartvigsen, F. Chen, et al., Secondary Use of EHR: Data Quality Issues and Informatics Opportunities, Summit Translat Bioinforma (2010) 1–5.
- [5] J.C. Young, M.M. Conover, M.J. Funk, Measurement error and misclassification in electronic medical records: methods to mitigate bias, Curr Epidemiol Rep 5 (2018) 343–356.
- [6] Lin P-ID, Rifas-Shiman SL, Aris IM, et al. Cleaning of anthropometric data from PCORnet electronic health records using automated algorithms. JAMIA Open 2022; 5.
- [7] C. Daymont, M.E. Ross, A. Russell Localio, et al., Automated identification of implausible values in growth data from pediatric electronic health records, J. Am. Med. Inform. Assoc. 24 (2017) 1080–1087.
- [8] A. Muthalagu, J.A. Pacheco, S. Aufox, et al., A Rigorous Algorithm To Detect And Clean Inaccurate Adult Height Records Within EHR Systems, Appl Clin Inform 5

(2014) 118–126.

- [9] S.I. Goldberg, M. Shubina, A. Niemierko, et al., A Weighty Problem: Identification, Characteristics and Risk Factors for Errors in EMR Data, AMIA Annu. Symp. Proc. 2010 (2010) 251–255.
- [10] S. Chen, W.A. Banks, M. Sheffrin, et al., Identifying and categorizing spurious weight data in electronic medical records, Am J Clin Nutrit 107 (2018) 420–426.
- [11] M.S. Khan, R.J. Carroll, Inference-based correction of multi-site height and weight measurement data in the All of Us research program, J. Am. Med. Inform. Assoc. 29

(2022) 626–630.

- [12] Winkler W. Problems with Inliers. Census Bur Res Rep Ser RR9805. 1998. https:// www.census.gov/content/dam/Census/library/working-papers/1998/adrm/ rr9805.pdf. Accessed September 2, 2022.
- [13] H.T. Phan, F. Borca, D. Cable, et al., Automated data cleaning of paediatric anthropometric data from longitudinal electronic health records: protocol and application to a large patient cohort, Sci. Rep. 10 (2020).
- [14] Daymont C. growthcleanr: Adult Algorithm. Secondary Growthcleanr: Adult Algorithm 2024. https://carriedaymont.github.io/growthcleanr/articles/adultalgorithm.html. Accessed March 8, 2024.
- [15] J.C. Denny, J.L. Rutter, D.B. Goldstein, et al., The “All of Us” Research Program, N. Engl. J. Med. 7 (2019) 668–676.


- [16] WHO Multicentre Growth Reference Study Group, WHO Child Growth Standards based on length/height, weight and age, Acta Paediatr. Suppl. 450 (2006) 76–85.
- [17] OMOP Common Data Model – OHDSI. https://www.ohdsi.org/datastandardization/the-common-data-model. Accessed September 2, 2022.
- [18] Modified z-scores in the CDC growth charts. Atlanta, GA: National Center for Chronic Disease Prevention and Health Promotion, Centers for Disease Control and Prevention; 2022 https://www.cdc.gov/nccdphp/dnpa/growthcharts/resources/ biv-cutoffs.pdf. Accessed September 2, 2022.
- [19] R.J. Kuczmarski, C.L. Ogden, S.S. Guo, et al., 2000 CDC Growth Charts for the United States: methods and development, Vital Health Stat. 11 (2002) 1–190.
- [20] R.A. Rigby, D.M. Stasinopoulos, Smooth centile curves for skew and kurtotic data modelled using the Box-Cox power exponential distribution, Statist Med 23 (2004) 3053–3076.
- [21] P. Mishra, C.M. Pandey, U. Singh, et al., Descriptive Statistics and Normality Tests for Statistical Data, Ann. Card. Anaesth. 22 (2019) 67–72.
- [22] R.A. Rigby, D.M. Stasinopoulos, Generalized additive models for location, scale and shape, J Royal Statistical Soc C 54 (2005) 507–554.
- [23] E. Finkler, S.B. Heymsfield, M.-P. St-Onge, Rate of weight loss can be predicted by patient characteristics and intervention strategies, J. Acad. Nutr. Diet. 112 (2012) 75–80.


- [24] Cut-Offs to Define Outliers in the 2000 CDC Growth Charts. Atlanta, GA: National Center for Chronic Disease Prevention and Health Promotion, Centers for Disease Control and Prevention; 2022 https://www.cdc.gov/nccdphp/dnpa/growthcharts/ 00binaries/BIV-cutoffs.pdf. Accessed September 2, 2022.
- [25] S. Sukparungsee, Y. Areepong, R. Taboran, Exponentially weighted moving average—Moving average charts for monitoring the process mean, PLoS One 15

(2020).

- [26] B. Hulanicka, K. Kotlarz, The final phase of growth in height, Ann. Hum. Biol. 10

(1983) 429–433.

- [27] M.L. McHugh, Interrater reliability: the kappa statistic, Biochem Med (zagreb) 22

(2012) 276–282.

- [28] Data Curation Process for the All of Us Data https://support.researchallofus.org/ hc/en-us/articles/4554267110804-Data-curation-process-for-the-All-of-Us-data. Accessed August 14, 2023.
- [29] NIH’s All of Us Research Program Releases New COVID-19 Data. All of Us Research Program | NIH. 2021.https://allofus.nih.gov/news-events/announcements/nihsall-us-research-program-releases-new-covid-19-data. Accessed August 14, 2023.


