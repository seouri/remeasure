IEA

International Journal of Epidemiology, 2025, 54(2), dyaf013 https://doi.org/10.1093/ije/dyaf013 Original article

International Epidemiological Association

Original article

# Protocol for improving equity in quantitative big data cleaning: lessons from longitudinal analysis of electronic health records from underrepresented and marginalized communities

## Zeruiah V. Buchanan1,2, , Scarlett E. Hopkins3,4, Bert B. Boyer3,4, Alison E. Fohner1,‡

1Department of Epidemiology, University of Washington, Seattle, WA, United States 2Robert Wood Johnson Health Policy Scholars Program, Johns Hopkins University, Baltimore, MD, United States 3Departments of Obstetrics and Gynaecology, Oregon Health & Science University , Portland, OR, United States 4Center for Alaska Native Health Research, University of Alaska Fairbanks, Fairbanks, AK, United States

Corresponding author. Department of Epidemiology, University of Washington, UW Box # 351619, Seattle, WA 98195, United States. E-mail: zbuchana@uw.edu ‡Senior author.

### Abstract

Background: Large biomedical datasets, including electronic health records (EHRs), are a significant source of epidemiologic data. To prepare an EHR for analysis, there are several data-cleaning approaches; here, we focus on data filtering. Common data-filtering methods employ rules that rely on data from socially constructed dominant populations but are inappropriate for marginalized populations, leading to the loss of valuable data and neglect of underrepresented communities. We propose a novel method based on a phenomenological framework that is more equitable and inclusive, leading to culturally responsive research and discoveries.

Methods: EHRs from the Yukon-Kuskokwim Health Corporation (YKHC) containing 1 262 035 records from 12 402 unique individuals from 2002 to 2012 were cleaned by using the proposed phenomenological (individual) and common (cohort) data-filtering approach. Within the phenomenological framework, we (i) excluded values that were undeniably biologically impossible for any population, (ii) excludes values that fell outside three standard deviations from the mean value for each individual person, and (iii) used two forms of imputation methods for stable quantitative and qualitative values at the individual level when data were missing.

Results: Compared with common data-filtering practices, the phenomenological approach retained more observations, participants, and a range of outcomes, allowing a truer representation of the priority population. In sensitivity analyses comparing the results of the raw data, the common approach implemented, and the phenomenological approach applied, we found that the phenomenological approach did not compromise the integrity of the results.

Conclusion: The phenomenological approach to filtering big data presents an opportunity to better advocate for marginalized communities even when using large datasets that require automated rules for data filtering. Our method may empower researchers who are partnering with communities to embrace large datasets without compromising their commitment to community benefit and respect.

Keywords: Yup’ik; Alaska Native; community-based participatory research; cardiometabolic; data filtering; data cleaning.

Key Messages This paper explores how we can humanize the quality control and data filtering of large biomedical datasets, including electronic health records, to increase participant inclusion and diversity in data analysis, and improve findings for marginalized communities. This novel approach to data filtering, called the phenomenology approach, allows the unique physiological experiences of each individual to remain in the dataset and enables more equitable and culturally responsive findings instead of relying on norms that are defined by the socially constructed dominant population. The phenomenological approach to data filtering prioritizes comparisons within a single individual, rather than across the study population, to identify and remove outliers and errors.

## Introduction

As the field of epidemiology moves toward equitable research, a culturally responsive approach to cleaning large biomedical datasets is essential to combat systems of oppression in public

health research, healthcare delivery, investment allocation, and policy development [1]. Data cleaning is implemented to ensure that data are accurate for analysis. Common cleaning methods are aggregation (consolidating), filtering (excluding),

Received: 20 January 2024; Editorial Decision: 9 January 2025; Accepted: 1 February 2025 © The Author(s) 2025; all rights reserved. Published by Oxford University Press on behalf of the International Epidemiological Association. For commercial re-use, please contact reprints@oup.com for reprints and translation rights for reprints. All other permissions can be obtained through our RightsLink service via the Permissions link on the article page on our site—for further information please contact journals.permissions@oup.com.

Downloadedfromhttps://academic.oup.com/ije/article/54/2/dyaf013/8051311bygueston02May2026

substitution (imputing), and transformation (manipulating) of values; here we focus on data filtering [2]. We use examples from our experience in analysing the electronic health record (EHR) data from the Yukon-Kuskokwim Health Corporation (YKHC), which serves American Indian and Alaska Native people in south-western Alaska, to present a novel approach to filtering large, longitudinal datasets that prioritize cultural responsiveness and equity for underrepresented communities without compromising the integrity of results. Methods such as the one we propose are needed to counter structures of oppression in research and improve advocacy.

A critique of common data-filtering steps for equitable research

Although an exceptional resource for epidemiology research, EHRs are notoriously error-prone, with at least half of the records having errors [3–8]. A challenge to cleaning datasets is that EHR datasets are often enormous, requiring routinized protocols that process data automatically using data rules and predefined standards. Many of these methods use distributions of population-level data to establish ‘normalized’ ranges and to homogenize the data [9–13].

Cleaning the EHR dataset by using common data-filtering approaches often first applies truncation, in which values are excluded if they are outside a biologically ‘plausible’ or clinically normal range [9, 12, 13]. These ranges are determined by using literature searches for plausible or normal values. Common data-filtering practices then apply 3–5 standard deviation (SD) pruning, in which values that are smaller or greater than 3–5 SD from the mean of all entries in the dataset are excluded [2, 14–16]. The motivation for these steps in data filtering is that extreme values are likely errors.

We found this common approach to be inappropriate for health data from the YKHC and other marginalized communities because it sets artificial parameters on the data based on an unrepresentative reference population. These ‘normal ranges’ used that are to determine biological plausibility were based on populations that were not reflective of the people in our study, but were based instead on averages within large medical institutions in the contiguous USA that typically prioritize socially dominant narratives. Furthermore, we knew that individuals in our study had true physiology outside of those ‘normal’ ranges based on our firsthand experience in the communities. For example, in a subset of communities in the Yukon-Kuskokwim Delta (Y-K Delta) population, we (Boyer et al.) found Yup'ik people to have lower triglycerides, lower fasting glucose, and higher high-density lipoprotein cholesterol (HDL-C) levels than those of the average US adult population, as reported in the National Health and Nutrition Examination Survey (NHANES) database (Table 1) [17, 18].

Secondly, the common approach to exclude observations beyond 3–5 SD from the mean of the entire study population eliminates erroneous extreme values and excludes people whose physiological truths are at the margins of data. Missing values are often imputed or estimated according to common patterns in the data. These approaches assume that all people within the study population have similar physiological patterns and exclude participants whose physiology deviates from cohort norms. Physiological and psychological heterogeneity leads to diverse lived experiences that are valuable truths of people within communities that we advocate for as epidemiologists, and routinely eliminating these

Table 1. Summaries of population-level cardiovascular risk factors from the YKHC community-based research and NHANES III.

Cardiovascular outcome YukonKuskokwim Delta (mean ± SD) [18]

NHANES III (mean ± SD) [17]

Body mass index (kg/m2) 26.7±5.7 27.0±5.8 LDL cholesterol (mg/dL) 124.7±34.8 127.0 ±38.5 HDL cholesterol (mg/dL) 62.9±18.1 50.9±15.1 Triglycerides (mg/dL) 82.4±44.3 127.0 ±38.5 Fasting blood glucose (mg/dL) 90.8±9.8 101.5 ±31.6 Systolic blood

116.3±13.4 122.7 ±20.7 Diastolic blood

pressure (mmHg)

68.0±9.5 72.2±12.6

pressure (mmHg)

The data from the YKHC are derived from communities in the Y-K Delta, as reported in Boyer et al. [22], whereas the NHANES III data were collected in the Lower 48 states, as reported in Philip et al. [21]. HDL, high-density lipoprotein; LDL, low-density lipoprotein; SD, standard deviation.

observations from analysis invalidates participants and misrepresents communities.

Therefore, we developed a novel method that pulls from previous researchers’ within-person data considerations to clean large EHR datasets by using an interpretive phenomenology framework to validate all participants’ physiological experiences [19]. The novelty of this approach is rooted in the inclusion and equity framing of the data filtering. We describe our method and rationale, and then present a guide to implementing the data-filtering method that honours the individuals in our datasets and leads to data that better reflect a population’s true health status. We compare the strengths and challenges of this novel approach to common approaches to cleaning large biomedical datasets by using examples from the YKHC.

## Methods

Research setting: the YKHC

We use examples from our analysis of EHRs from the YKHC—a Tribal health organization and a fully integrated healthcare delivery system that provides comprehensive care to all American Indian and Alaska Native people in the Y-K Delta in south-western Alaska. The Y-K Delta is home to

23 000 people, 85% of whom are self-identified Alaska Native and live predominantly in 58 communities. Unless needing to travel for speciality care, most residents in the Y-K Delta receive all of their healthcare through the YKHC.

Our analysis included records of all healthcare visits within the YKHC system between 2002 and 2012 by people who were ≥18years of age at the time of the visit. Data were compiled as part of a study to determine the longitudinal change in cardiometabolic risk factors among residents of the Y-K Delta [20]. The dataset included records from 1 262 035 healthcare visits from 12 402 unique individuals, with age at visit ranging from 18 to 102 years. The records included observed values of cardiometabolic risk factors from the visit, including height, weight, systolic blood pressure (SBP), diastolic blood pressure (DBP), and high-density lipoproteins cholesterol (HDL-C) levels. In addition, records included age at visit, sex, tobacco use, and community of residence.

Our study team included researchers (S.E.H. and B.B.B.) who had been conducting community-based participatory research in the region for >20years [21–24]. They have

Downloadedfromhttps://academic.oup.com/ije/article/54/2/dyaf013/8051311bygueston02May2026

extensive knowledge of the communities, lifestyles, and health statuses of people in the area. Only de-identified data were used for analysis.

Analysis

We first applied a phenomenological framework to develop a novel data-filtering approach that honours the diverse identities in the population. Then, we compared the properties of the phenomenological data-filtering approach to common data-filtering approaches. To do so, we applied the phenomenological and common data-filtering protocols to the EHR dataset. We summarized the data and results from both approaches compared with the uncleaned data for cardiometabolic outcomes of interest, including body mass index (BMI), HDL-C, SBP, and DBP. We calculated BMI by using height and weight from the clinical visits in the dataset. To evaluate the performance of the data-filtering methods and their ability to eliminate erroneous data, we investigated the excluded observations in each approach to determine their plausibility as true health states of individuals rather than erroneous data. To illustrate the impact of these different data-filtering methods on the analysis and conclusions of epidemiology research, we performed linear mixed model analysis of whether the rate of change in BMI, HDL-C, SBP, and DBP significantly differed between males and females over the study period, adjusting for age at visit, community of residence, and tobacco use. All analyses were performed by using R software, version 4.2.1, including the lme4 package.

Where we present individual-level examples from our data, we added or subtracted a random number from one to three to protect privacy and prevent the identification of individuals.

Adopting a phenomenological framework to prioritize inclusivity in big data filtering

Heidegger’s interpretive phenomenological methodology inspired our approach to data filtering. Interpretive phenomenology challenges the notion that the summarized experience presented in research findings represents all participants’ experiences [25]. The phenomenological methodology aims to uplift unique lived experiences by honouring and validating the mean narrative and the narratives at the margins of data. This transdisciplinary lens of phenomenology integrates cultural humility and equitable practices into methods, interpretations, and results, which enables a more accurate comprehension of the population represented in a dataset.

The common practice of using external reference populations and ‘normal’ ranges to clean EHR datasets is inconsistent with a phenomenology approach [9–13]. These ranges are usually derived from socially constructed dominant populations that are not representative of marginalized populations. Even ‘normal’ ranges based on the majority experience within the same population violate the phenomenology principle that not all participants in a study population experience life and health in the same way.

The phenomenological approach humanizes data cleaning by honouring each individual’s unique experiences by comparing data only from the same individual. This method retains heterogeneity within a study population, allowing analysis and conclusions to be more inclusive of broad, true lived experiences. It also strives to meet the same goal as common big data-filtering methods: to implement an automated approach to clean data while upholding accuracy, credibility,

completeness, correctness, concordance, plausibility, and currency [16, 26, 27].

To do so, the phenomenological approach excludes only biologically ‘impossible’ values instead of excluding biologically implausible values, thereby eliminating the need for reference ranges from potentially unrepresentative populations. These parameters are purposely set conservatively. For example, a weight observed at 2 lbs would be considered biologically impossible. No human aged >18years would weight <2 lbs, so that observation would be removed from the analysis.

Furthermore, the phenomenological approach applies the 3-SD pruning at an intrapersonal level rather than at the cohort level. In other words, observations outside 3 SD from the mean of an individual’s observations are excluded. Longitudinal data, such as in EHRs, in which each participant has repeat measures from repeat healthcare visits, allow an individual to be compared with themselves, thereby validating each person’s unique truths and eliminating the need to compare population averages. Finally, we used routine imputation methods to address missing data by imputing within-person means for height and the next or last observation for qualitative confounders (e.g. tobacco use) included in the analysis [28–30].

In contrast to common data-filtering approaches, the novel phenomenological data-filtering approach prioritizes responsiveness to participants by retaining heterogeneity and not forcing their conformity to preconceived parameters or population averages. Steps of the phenomenological data-filtering approach and examples of their application are presented in Table 2.

Simulation and spot-checking outliers

Due to the limitations of the phenomenological approach, when there are few observations per person, we performed a simulation study to model how many observations are needed for each individual to identify an outlier. From a normal distribution, we selected a random number of points, starting with 2 points, through 20 points along that distribution. Then, for standard deviations 3–7, we modelled an outlier that was far outside of the standard deviations of the normally distributed observations. We then calculated the Zscore of that outlier with respect to it and its companion normally distributed observations. We performed each simulation 100 times based on a random selection of the normally distributed observations.

We also performed spot-checking to identify how many observations within our dataset were needed to detect an outlier. We created cohort datasets that included participants with more than three observations per person and identified participants with plausible errors as compared with their clustered observations. We repeated this process until we found consistent detection of errors within a cohort dataset.

## Results

A comparison of common versus phenomenological methods to clean data in the YKHC

We excluded impossible biological values in the first step of data filtering with a phenomenological approach. To determine these impossible ranges, we first reviewed the literature

Downloadedfromhttps://academic.oup.com/ije/article/54/2/dyaf013/8051311bygueston02May2026

Table 2. Steps to clean EHRs or other large, longitudinal biomedical datasets by using a phenomenological approach.

##### Step Details Example

- (i) Truncate extreme outliers Exclude values that are undeniably biologically impossible for any population

Any weight of ‘2’ for a study population aged ≥18years

- (ii) Normalize intrapersonal distributions

Exclude values that fall outside of 3 standard deviations from the mean value for each individual person

A single participant had 20 healthcare visits with weight values over the 10years. The weight values were between 150 and 175 lbs, with one entry of 375 lbs. The range based on 3 standard deviations from the mean is 32–318 lbs. Thus, we exclude the 375 lbs observation as implausible for that individual

- (iii) Use individual average or data proximity to estimate missing values


When data on stable quantitative variables are missing, use the average value from all visits for that same person. For stable qualitative variables, use the data from the closest available time point

Height is stable across adulthood but is often missing in EHR records. The average height for an individual was used to replace all missing height values. Therefore, BMI could be calculated at any visit with weight data rather than only visits with weight and height data

BMI, body mass index; EHR, electronic health record.

specific to the Yup’ik community and consulted experts who were interacting with the community continually. Based on this search, we excluded all weight measurements of <50 or >500 lbs and all height measurements of <48 and >84 inches. Thus, we excluded 910 weight and 260 height observations in the dataset, though no more than five observations were excluded for a single individual. All the other cardiovascular outcomes of interest had less clear biological limits. Based on our experience in the communities, we determined that the ranges of all other outcomes were within possibility for humans. Therefore, we did not exclude values from the other outcomes as being impossible. Using the phenomenological method to replace missing height values with the average height values for the same person, we calculated BMI for >200 000 healthcare visits at which weight was recorded but not height.

We focus here on comparing values excluded using 3-SD pruning with the common versus phenomenological approach to data filtering. Table 3 presents the mean, SD, and range for HDL-C, height, and weight from the YKHC dataset with no data filtering (original data), pruning of values outside of 3 SD of the cohort mean (common data filtering), and pruning of values outside of 3 SD of the individual mean (phenomenological data filtering). Based on the phenomenological approach, 1 observation of HDL-C, 92 observations of height, and 4294 observations of weight were excluded. Based on the common approach, 91 observations of HDL-C, 266 of height, and 3049 of weight were excluded.

In the case of HDL-C and height, the phenomenological approach excluded fewer observations than the common approach, while fewer observations were excluded for weight when using the common method. However, the observations removed in the phenomenological approach were not always those on the edges of the overall range, but instead were on the edges of an individual’s range. Importantly, no individual was completely removed from the analysis when using the phenomenological approach.

We spot-checked the data after applying each method to compare the types of excluded observations. The cohort ranges of all outcomes were wider when using the phenomenological approach, but the common approach removed people with trustworthy values that the phenomenological approach retained. For example, one individual had many consistent height measurements of 50 inches. Common data-filtering methods would have excluded every height

observation for that individual based on the cohort distribution, thereby completely excluding that individual from analysis. However, by calculating individual distribution, this person was included in analysis. Our (S.E.H. and B.B.B.) anecdotal experience in the community validated the plausibility of this height value.

The phenomenological approach also excluded outliers for individuals who would have been retained when using the common approach but that appear faulty. For example, one individual had 155 observations for weight ranging from 115 to 145 lbs and one observation was 185 lbs. This outlier was within 3 SD of the overall mean of the dataset when using the common method for data filtering but was outside of 3 SD of the individual mean when using the phenomenological method. Excluding this observation for the individual seems most consistent with the physiological state revealed in the other 155 observations, especially for an analysis concerning chronic health states.

Observation considerations when using the phenomenological approach

The phenomenological approach outperformed the common approach when individuals had many healthcare visits. However, the common approach was better when individuals had only a few visits. For example, in our study population, we identified a participant with only four values for HDL-C. One observation was 185mg/dL, which was considerably higher than the other three observations (all 150mg/dL) and relatively high for general human physiology. This observation of 185mg/dL was excluded when using the common datafiltering approach because it was outside of 3 SD from the cohort mean but was not excluded when using the phenomenological approach of excluding values outside of 3 SD from the individual mean. We performed a simulation based on outliers from normally distributed data to determine the number of observations needed to detect an outlier. How closely clustered the other observations are and how far away the outlier is from that cluster determine how many observations are needed overall to detect the outlier. For example, an outlier that is 5 SD from 15 randomly selected normally distributed observations would be identified with a Z-score of >3. This is a conservative estimate, as the points are normally distributed, and often biomedical data are more consistent. Figure 1 shows the number of observations needed to detect an outlier based on a normal distribution simulation. Additionally, when spot-

Downloadedfromhttps://academic.oup.com/ije/article/54/2/dyaf013/8051311bygueston02May2026

- Table 3. Comparison of mean, SD, range, and number of observations for HDL-C, height, and weight when using different data-filtering approaches. HDL-C (mg/dL) Height (in) Weight (lbs)


Comparator Original Common Phenomenological

Original Common Phenomenological

Original Common Phenomenological

Mean 62.99 62.36 63.00 62.86 62.91 62.87 161.14 159.49 161.38 SD 20.57 19.35 20.57 3.89 3.67 3.86 40.66 37.29 39.29 Range 5.00–193.00 5.00–

5.00– 193.00

48.00–83.00 51.25– 74.41

48.00– 83.00

50.00– 500.00

50.00– 283.07

50.00–

500.00 Total observations 11 376 11 285 11 375 27 225 26 956 27 133 297 022 293 973 292 728 Unique individuals 3589 3576 3589 7178 7143 7178 11 327 11 276 11 327

124.00

All datasets exclude biologically impossible values for height and weight. The original approach includes no additional data filtering. The common approach then excludes values outside of 3 SD from the overall mean of the data. The phenomenological approach excludes values outside of 3 SD from the mean of each individual. HDL-C, high-density lipoprotein cholesterol; SD, standard deviation.

![image 1](<Protocol for improving equity in quantitative big data cleaning - lessons from longitudinal analysis of electronic health records from underrepresented and marginalized communities_images/imageFile1.png>)

Figure 1. Simulation results to determine how many observations are necessary among each participant to accurately detect an outlier using a Z-score of 3 as a cut-off point. From a normal distribution, we selected a random number of points, starting with 2 points, through 20 points along that distribution. Then, for standard deviations (SDs) of 3–7, we modelled an outlier that was far outside of the SD of the normally distributed observations. We then calculated the Z-score of that outlier with respect to it and its companion normally distributed observations. We performed each simulation 100 times based on a random selection of the normally distributed observations. This figure shows the Z-score for an outlier at the following SD from the others: 3, 4, 5, 6, and 7 to show where the Z-score crosses the threshold of 3, where we would detect it. For an observation at exactly 3 SD from the others, 20 observations are needed. However, for an observation that is 5 SD from the others, only 12 are needed. This figure is a conservative presentation based on values selected from a normal distribution; in reality, most of the values in the EHR are more tightly clustered and thus fewer observations would be needed to detect an outlier. For example, in our study, the average Zscore of the observations excluded was 3.60 above the mean and –3.48 below the mean. The average number of observations for an individual with excluded observations was 214.85 (range: 19–1488).

checking participant’s observations segmented by the number of observations included in the dataset, we found that 15 observations were needed to detect an error for an individual. Therefore, with only four observations in total in this example, the likely erroneous outlier was not statistically flagged when using intrapersonal 3-SD pruning.

Notably, the conclusions from the common and phenomenological approaches to data filtering were the same with respect to whether the rate of change in BMI, HDL-C, SBP, or DBP was significantly different between men and women throughout the study period after adjusting for age at visit, smoking, and community of residence (Table 4). In both approaches, men and women had significantly different rates of change in BMI, SBP, and DBP, but not in HDL-C. Thus, any potential loss of precision from retaining outliers when using the phenomenological approach did not seem to affect the analysis conclusions.

## Conclusion

We describe a phenomenological approach to cleaning large, longitudinal biomedical datasets that excludes only biologically impossible values and compares values only to others from the same individual. Rather than prioritizing the majority experience in a population, the phenomenological approach allows better representation of communities and individual participants without compromising analytic validity. Importantly, in contrast to common data-filtering approaches, the phenomenological approach did not exclude any participant from analysis. Thus, it leads to more culturally responsive and representative research and discoveries about the people who are represented in the data.

As epidemiology moves toward more inclusive research practices, a phenomenological data-filtering approach is one tool to consider. This approach requires familiarity with the population and intimate comprehension of how the data represent the true experience of the priority population. It may not be appropriate for all longitudinal biomedical datasets, especially those with few observations for each individual.

Although the phenomenological data-filtering approach may require more observations than are possible for some studies, researchers can still apply the essence of the phenomenological framework in their methods by prioritizing diverse and inclusive data to better serve the priority population. Depending on the researcher’s question and data type, researchers may consider integrating portions of the phenomenological approach with the common approach for their data-filtering methods. Equitably responsive research methods can be applied to data collection, cleaning, analysis, and interpretation. These methods improve the ultimate ability of results to benefit research participants and communities by informing effective and appropriate policies. Applying a phenomenological data-filtering approach to large biomedical datasets is a tool that researchers can use to advocate for and with structurally minoritized communities in epidemiology research.

## Ethics approval

Approval for research was received from the YKHC Human Studies Committee and Executive Board of Directors, the Alaska Area IRB, and the University of Alaska Fairbanks IRB.

#### Downloadedfromhttps://academic.oup.com/ije/article/54/2/dyaf013/8051311bygueston02May2026

- Table 4. Results from linear mixed models evaluating the difference in the rate of change in BMI, HDL-C, SBP, and DBP between men and women, adjusting for age at visit, tobacco use, and community of residence


Variable βInteraction Lower confidence interval

t-value (Int)

Upper confidence interval

Unique people

Observations per person [mean (SD)]

Total observations

BMI

Original (no pruning) 0.054 0.045 0.064 11.207 7175 36.60 (35.97) 262 597 Common 0.048 0.040 0.056 11.637 7128 36.38 (35.83) 259 300 Phenomenological 0.053 0.047 0.059 16.77 7175 36.04 (35.39) 258 586

HDL-C

Original –0.054 –0.209 0.102 –0.678 3589 3.17 (3.15) 11 376 Common –0.005 –0.152 0.143 –0.064 3576 3.16 (3.15) 11 285 Phenomenological –0.046 –0.201 0.109 –0.585 3589 3.17 (3.15) 11 375

SBP

Original –0.245 –0.281 –0.209 –13.392 11 587 33.62 (42.36) 389 535 Common –0.243 –0.277 –0.208 –13.879 11 586 33.34 (41.82) 386 285 Phenomenological –0.239 –0.274 –0.204 –13.411 11 587 33.46 (42.11) 387 750

DBP

Original 0.074 0.050 0.097 6.107 11 587 33.62 (42.36) 389 535 Common 0.064 0.041 0.086 5.439 11 584 33.45 (42.15) 387 493 Phenomenological 0.076 0.053 0.099 6.501 11 587 33.45 (42.07) 387 534

The βinteraction term describes the difference in the annual rate of change between men and women. Output is compared by using the different methods for excluding outliers: the original data without any exclusions, the common approach excluding all values outside of 3 SD from the overall mean in the dataset, and the phenomenological approach that excludes values outside of 3 SD from the mean of each individual. All three methods use an intrapersonal mean for missing height values where weight was available and exclude biologically impossible values for height and weight. A t-value with an absolute value of >1.96 is considered significant. BMI, body mass index; DBP, diastolic blood pressure; HDL-C, high-density lipoprotein cholesterol; SBP, systolic blood pressure; SD, standard deviation.

## Acknowledgements

The authors sincerely thank the Yukon-Kuskokwim Delta community members for their input, guidance, and participation.

## Author contributions

S.E.H. and B.B.B. managed the CBPR study, collected data, and gave guidance on and reviewed this work. Z.V.B. and A. E.F. analysed the data and wrote all sections of this paper.

## Use of artificial intelligence (AI) tools

There was no use of AI in the preparation of this work.

## Conflict of interest

None declared

## Funding

This study was supported by funds from the University of Washington School of Public Health.

## Data availability

The Yukon-Kuskokwim Health Corporation owns the data underlying this article and proposals for data access can be directed to the Yukon-Kuskokwim Health Corporation Executive Board of Directors.

## References

- 01. Knight HE, Deeny SR, Dreyer K et al. Challenging racism in the use of health data. Lancet Digit Health 2021;3:e144–6.
- 02. Miao Z, Sealey MD, Sathyanarayanan S, Delen D, Zhu L, Shepherd S. A data preparation framework for cleaning electronic


- health records and assessing cleaning outcomes for secondary analysis. Inf Syst 2023;111:102130.
- 03. Graber ML, Byrne C, Johnston D. The impact of electronic health records on diagnosis. Diagnosis (Berl) 2017;4:211–23.
- 04. Kaboli PJ, McClimon BJ, Hoth AB, Barnett MJ. Assessing the accuracy of computerized medication histories. Am J Manag Care. 2004;10:872–7.
- 05. Staroselsky M, Volk LA, Tsurikova R et al. An effort to improve electronic health record medication list accuracy between visits: patients’ and physicians’ response. Int J Med Inform 2008; 77:153–60.
- 06. Suresh G. Don't believe everything you read in the patient's chart. Pediatr (Evanston) 2003;111:1108–9.
- 07. Weir CR, Hurdle JF, Felgar MA, Hoffman JM, Roth B, Nebeker JR. Direct text entry in electronic progress notes an evaluation of input errors. Methods Inf Med 2003;42:61–7.
- 08. Yadav S, Kazanji N, Narayan KC et al. Comparison of accuracy of physical examination findings in initial progress notes between paper charts and a newly implemented electronic health record. J Am Med Inform Assoc 2017;24:140–4.
- 09. Aguinis H, Gottfredson RK, Joo H. Best-practice recommendations for defining, identifying, and handling outliers. Organ Res Methods 2013;16:270–301.
- 10. Lawman HG, Ogden CL, Hassink S, Mallya G, Vander Veur S, Foster GD. Comparing methods for identifying biologically implausible values in height, weight, and body mass index among youth. Am J Epidemiol 2015;182:359–65.
- 11. Phan HTT, Borca F, Cable D, Batchelor J, Davies JH, Ennis S. Automated data cleaning of paediatric anthropometric data from longitudinal electronic health records: protocol and application to a large patient cohort. Sci Rep. 2020;10:10164.
- 12. Shi X, Prins C, Van Pottelbergh G, Mamouris P, Vaes B, De Moor B. An automated data cleaning method for Electronic Health Records by incorporating clinical knowledge. BMC Med Inform Decis Mak. 2021;21:267–
- 13. Van den Broeck J, Cunningham SA, Eeckels R, Herbst K. Data cleaning: detecting, diagnosing, and editing data abnormalities. PLoS Med 2005;2:e267-e.
- 14. Wood GC, Chu X, Manney C et al. An electronic health recordenabled obesity database. BMC Med Inform Decis Mak 2012; 12:45.


Downloadedfromhttps://academic.oup.com/ije/article/54/2/dyaf013/8051311bygueston02May2026

- 15. Woolley C, Handel I, Bronsvoort B, Schoenebeck J, Clements D. Is it time to stop sweeping data cleaning under the carpet? A novel algorithm for outlier management in growth data. PLoS One 2020; 15:e0228154.
- 16. Feder SL. Data quality in electronic health records research. Telemed Week 2017;3602. NewsRx.
- 17. Boyer BB, Mohatt GV, Plaetke R et al.; CANHR Project Team. Metabolic syndrome in Yup'ik Eskimos: the Center for Alaska Native Health Research (CANHR) study. Obesity (Silver Spring) 2007;15:2535–40.
- 18. Philip J, Ryman TK, Hopkins SE et al. Bi-cultural dynamics for risk and protective factors for cardiometabolic health in an Alaska Native (Yup'ik) population. PLoS One 2017;12:e0183451-e.
- 19. Tran DT, Havard A, Jorm LR. Data cleaning and management protocols for linked perinatal research data: a good practice example from the Smoking MUMS (Maternal Use of Medications and Safety) Study. BMC Med Res Methodol 2017;17:97.
- 20. Buchanan Z, Hopkins SE, Ryman TK et al. Electronic health record reveals community-level cardiometabolic health benefits associated with 10 years of community-based participatory research. Public Health 2024;232:38–44.
- 21. Boyer BB, Mohatt GV, Lardon C et al. Building a communitybased participatory research center to investigate obesity and diabetes in Alaska Natives. Int J Circumpolar Health 2005; 64:281–90.
- 22. Boyer BB, Wiener HW, Hopkins SE et al. Obesity-associated dyslipidemia is moderated by habitual intake of marine-derived n-3 polyunsaturated fatty acids in Yup'ik Alaska Native people: a


- cross-sectional mediation-moderation analysis. J Nutr. 2023; 153:279–92.
- 23. Fohner AE, Wang Z, Yracheta J et al. Genetics, diet, and season are associated with serum 25-hydroxycholecalciferol concentration in a Yup'ik Study population from Southwestern Alaska. J Nutr 2016;146:318–25.
- 24. O'Brien DM, Kristal AR, Nash SH et al. A stable isotope biomarker of marine food intake captures associations between n-3 fatty acid intake and chronic disease risk in a Yup'ik study population, and detects new associations with blood pressure and adiponectin. J Nutr. 2014;144:706–13.
- 25. Lopez KA, Willis DG. Descriptive versus interpretive phenomenology: their contributions to nursing knowledge. Qual Health Res 2004;14:726–35.
- 26. Terry AL, Stewart M, Cejic S et al. A basic model for assessing primary health care electronic medical record data quality. BMC Med Inform Decis Mak 2019;19:30.
- 27. Weiskopf NG, Weng C. Methods and dimensions of electronic health record data quality assessment: enabling reuse for clinical research. J Am Med Inform Assoc. 2013;20:144–51.
- 28. Engels JM, Diehr P. Imputation of missing longitudinal data: a comparison of methods. J Clin Epidemiol. 2003;56:968–76.
- 29. Ribeiro C, Freitas AA. A data-driven missing value imputation approach for longitudinal datasets. Artif Intell Rev 2021; 54:6277–307.
- 30. Rosato R, Pagano E, Testa S, Zola P, di Cuonzo D. Missing data in longitudinal studies: Comparison of multiple imputation methods in a real clinical setting. J Eval Clin Pract. 2021;27:34–41.


Downloadedfromhttps://academic.oup.com/ije/article/54/2/dyaf013/8051311bygueston02May2026

© The Author(s) 2025; all rights reserved. Published by Oxford University Press on behalf of the International Epidemiological Association. For commercial re-use, please contact reprints@oup.com for reprints and translation rights for reprints. All other permissions can be obtained through our RightsLink service via the Permissions link on the article page on our site—for further information please contact journals.permissions@oup.com. International Journal of Epidemiology, 2025, 54, 1–7 https://doi.org/10.1093/ije/dyaf013 Original article

