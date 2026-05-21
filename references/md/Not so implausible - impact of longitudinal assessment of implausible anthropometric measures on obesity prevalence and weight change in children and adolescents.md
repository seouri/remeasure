Annals of Epidemiology 31 (2019) 69e74

![image 1](<Not so implausible - impact of longitudinal assessment of implausible anthropometric measures on obesity prevalence and weight change in children and adolescents_images/imageFile1.png>)

![image 2](<Not so implausible - impact of longitudinal assessment of implausible anthropometric measures on obesity prevalence and weight change in children and adolescents_images/imageFile2.png>)

Contents lists available at ScienceDirect

# Annals of Epidemiology

Original article

Not so implausible: impact of longitudinal assessment of implausible anthropometric measures on obesity prevalence and weight change in children and adolescents

Janne Boone-Heinonen, PhD, MPH a, *, Carrie J. Tillotson, MPH b, Jean P. O'Malley, MPH c, Miguel Marino, PhD, MS a, c, Sarah B. Andrea, MPH a, Andrew Brickman, PhD d, Jennifer DeVoe, MD, DPhil c, Jon Puro, MPA-HA b

- a OHSU-PSU School of Public Health, Portland, OR
- b OCHIN, Portland, OR
- c OHSU Department of Family Medicine, Portland, OR
- d Health Choice Network, Miami, FL


![image 3](<Not so implausible - impact of longitudinal assessment of implausible anthropometric measures on obesity prevalence and weight change in children and adolescents_images/imageFile3.png>)

a r t i c l e i n f o

a b s t r a c t

Article history: Received 14 August 2018 Accepted 13 January 2019 Available online 5 February 2019

Purpose: Implausible anthropometric measures are typically identiﬁed using population outlier deﬁnitions, conﬂating implausible and extreme measures. We determined the impact of a longitudinal outlier approach on prevalence of body mass index (BMI) categories and mean change in anthropometric measures in pediatric electronic health record data.

Methods: We examined 996,131 observations from 147,375 children (10e18 years) in the ADVANCE Clinical Data Research Network, a national network of community health centers. Sex-stratiﬁed, mixed effects, linear spline regression modeled weight, height, and BMI as a function of age. Longitudinal outliers were deﬁned as observations with studentized residual greater than |6|; population outliers were deﬁned by Centers for Disease Control-deﬁned z-score thresholds.

Keywords: Longitudinal Youth Biologically implausible values Outliers Anthropometry Body mass index Obesity

Results: At least 99.7% of anthropometric measures were not extreme by longitudinal or population deﬁnitions (agreement 0.995). BMI category prevalence after excluding longitudinal or population outliers differed by less than 0.1%. Among children greater than 85th percentile at baseline, annual mean changes in anthropometric measures were larger in data that excluded longitudinal (girls: 1.24 inches, 12.39 pounds, 1.53 kg/m2; boys: 2.34, 14.08, 1.07) versus population outliers (girls: 0.61 inches, 8.22 pounds, 0.75 kg/m2; boys: 1.53, 11.61, 0.48).

Conclusions: Longitudinal outlier methods may reduce underestimation of anthropometric change in children with elevated baseline values.

© 2019 Elsevier Inc. All rights reserved.

Introduction

Electronic health record (EHR) data are increasingly used for pediatric obesity research, surveillance, and screening [1]. Weight and height measured in clinical settings may contain more error than in research settings, but there is no standard method for identifying implausible measures among pediatric anthropometric EHR data [2].

* Corresponding author. OHSU-PSU School of Public Health, Oregon Health & Science University, 3181 SW Sam Jackson Park Road, Mail Code FM, Portland, OR 97239-3098. Tel.: þ1 503-494-9055; fax: þ1 503-494-4981.

E-mail address: boonej@ohsu.edu (J. Boone-Heinonen).

https://doi.org/10.1016/j.annepidem.2019.01.006 1047-2797/© 2019 Elsevier Inc. All rights reserved.

A common approach for identifying implausible anthropometric measures in U.S. children identiﬁes biologically implausible values relative to the Centers for Disease Control and Prevention (CDC) growth curves [3]. This approach assumes that extreme measuresdthose that exceed predeﬁned z-score cutoffs based on a reference populationdare biologically implausible and erroneous; we refer to these measures as population outliers. This assumption has been challenged in the context of increasing prevalence and severity of pediatric obesity in the United States [4]. Evidence based on children aged 2e4 years with high body mass index (BMI) values at two measurement occasions suggests that population outliers include valid values, underestimating obesity prevalence by 1% [5]. Moreover, population outlier deﬁnitions do not consider

implausible change over time and may truncate estimates of anthropometric change among the heaviest children, as their weights increase beyond “biologically implausible” thresholds. Importantly, children who are racial or ethnic minorities or with low socioeconomic status have a higher burden of obesity relative to more afﬂuent white children [6, 7] and are thus particularly vulnerable to misclassiﬁcation when population outlier methods are applied.

Recent work has proposed longitudinal methods for identifying implausible values in pediatric anthropometric data. In contrast to population outlier methods, longitudinal outlier methods are child speciﬁc; they use repeated measures for each child to inform the validity of any given measure. However, these methods vary with regard to the requisite number of measures per child, the dependence on the validity of ﬁrst observation, and the extent to which data from the full study population are incorporated. Methods include a jackknife residual method for growth data from birth to 24 months of age [8], conditional growth percentiles for birth to 6.5 years of age [9], and a data cleaning method for EHR data based on deviation from the weighted moving average for each child aged 1e21 years [1]. Welch et al. used mixed-effects models to identify longitudinal outliers in clinical data on a predominately adult patient population [10], which accommodates the substantial variability in number and spacing of anthropometric measures, as well as in age of ﬁrst observation found in clinical data.

In this study, we extend Welch's approach to accommodate the nonlinear growth patterns typically observed in pediatric populations. We develop and test this method in 147,375 low-income children receiving care in community health centers in the 23 states participating in the ADVANCE Clinical Data Research Network. The extensive longitudinal measures and high burden of severe childhood obesity in our study population enabled examination of the extent to which exclusion of population outliers might bias the estimates of weight, height, and BMI change over time in the heaviest children, as their weights increase beyond the population outlier cutpoints. Our objectives were to (1) demonstrate a mixed-effects modelebased method for identifying longitudinal implausible anthropometric measures in pediatric EHR data, (2) compare classiﬁcation of and level of agreement between population outliers and longitudinal outliers, and (3) determine the impact of outlier identiﬁcation approach on the estimated values for prevalence of BMI categories and change in anthropometric measures.

Methods

Study population

We used data from the ADVANCE Clinical Data Research Network, a national network of Federally Qualiﬁed Health Centers serving more than 4.3 million safety net patients across the United States [11]. ADVANCE is a multicenter collaborative led by OCHIN, Inc. (not an acronym) health information network in partnership with Health Choice Network (HCN) and Fenway Health. Together, these systems have outpatient clinical data from more than 130 community health centers with more than 1100 clinics. ADVANCE includes pediatric and adult patients with one or more ofﬁce visit on or after January 1, 2012, across OCHIN, HCN, and Fenway Health networks, and their historical records, dating back as far as 2005.

This study examines anthropometric data for children aged 10e18 years from OCHIN and HCN networks. Fenway data were excluded because the network does not include pediatric clinics. We focused on middle childhood through adolescence as critical life stages in which obesity often develops; however, the

proposed methodology could be adapted for other ages. EHR data were extracted from clinical encounters from January 1, 2012, through December 31, 2015 (354,614 children, 1,270,278 encounters). Initial data screening at the encounter-level excluded (1) 1455 encounters with height 25 inches or less, or 100 inches or longer and (2) 123 encounters with weight of 5 or less, or 1000 or greater pounds. This initial exclusion of biologically impossible values was required to achieve model convergence; selected cutpoints were well beyond the ﬁrst and 99th percentiles of the original distributions for weight (62 and 280 pounds) and height (51.7 and 73.3 inches), respectively. We then excluded 207,036 children with less than three remaining height, weight, and BMI measures. Our ﬁnal analytic sample included 147,375 children randomly assigned to training or test datasets. A total of 73,599 children were selected for the training dataset; the remaining 73,776 were retained for the test dataset. Mean weight, height, and BMI for included versus excluded children were generally within 0.1 z-scores (Appendix Table A1).

Study variables

Dependent variables included time-varying weight, height, and BMI. Weight and height were ascertained from clinical encounter records. BMI was calculated from weight and height measured on the same day. For descriptive analysis, BMI was converted to ageand sex-speciﬁc BMI z-scores and percentiles using the CDC 2000 growth curves [12], then classiﬁed into underweight (<5th percentile), normal weight ( 5th, <85th), overweight ( 85th, <95th), obesity ( 95th to <20% higher than the 95th percentile), and severe obesity ( 20% higher than the 95th percentile) [13].

Independent variables included time-varying age (continuous) and time-constant sex (male, female) and race or ethnicity (Asian, Native Hawaiian/Paciﬁc Islander, black/African, American Indian/ Alaska Native, white, multiple race, other/unknown, and Hispanic). Sex, date of birth, and race/ethnicity were recorded by clinical staff and are nonmissing for most patients because most community health centers are required to report these data to the US Health Resources and Services Administration.

Statistical analysis

Weight, height, and BMI trajectories were modeled using linear spline mixed-effects regression models. We built on previous work proposing similar methods to identify longitudinal outliers in clinical data on a predominately adult patient population, accounting for clustering of multiple observations per patient over time [10]. We extended this model to account for nonlinear growth in youth by incorporating piecewise regression over age [14]. Statistical analysis was conducted in SAS Version 9.4 (SAS Institute, Cary, NC). Each of the following steps was performed ﬁrst in the training dataset (n ¼ 73,599), then repeated in the test dataset (n ¼ 73,776).

First, mixed-effects regression modeled weight, height, and BMI as a function of age, specifying random intercept and slopes for subjects, and ﬁxed effects for race/ethnicity. Analyses were stratiﬁed by sex to accommodate sex-speciﬁc growth patterns. Piecewise trajectories were ﬁt by including spline terms for age; the number and placement of knots were determined by inﬂection points identiﬁed in loess plots, stratiﬁed by sex and race/ ethnicity to address potential racial/ethnic differences in growth trajectories. Graphically identiﬁed inﬂection points within the age range of the study (10e18 years) for weight, height, and BMI were 12.5 years for girls and 15 years for boys. Racial/ethnic groups had different intercepts, but similar inﬂection points;

therefore, ﬁnal models were stratiﬁed by sex and included race/ ethnicity as a covariate:

Girls : Yit ¼ b0 þ b1 Age þ b2Age after12:5 þ bxXi þ b0i þ b1tAge þ b2tAge after12:5 þ εit

Boys: Yit ¼ b0 þ b1 Age þ b2Age after15 þ bxXi þ b0i

þ b1tAge þ b2tAge after15 þ εit

where Yit denotes weight, height, or BMI for patient i at time t. Continuous Age was centered at 10 years, with a spline variable for years after age 12.5 and 15 years for girls (Age_after12.5) and boys (Age_after15), respectively. Xi was race/ethnicity. b0i enabled patient variability at age 10 years. b1t enabled different patient-level growth trajectories from age 10 to 12.5 years for girls and age 10 to 15 years for boys. b2t enabled different patient-level growth trajectories from age 12.5 to 18 years for girls and age 15 to 18 years for boys. Model coefﬁcients are presented in Appendix Tables A2 and 3.

Second, after ﬁtting the sex-stratiﬁed longitudinal models, we calculated studentized residuals for each measurement, representing the difference between the measurement at any given encounter relative to the expected value from the child's speciﬁc growth curve, standardized by their estimated standard error. Longitudinal encounter-level outliers were deﬁned as measurements with studentized residuals greater than j6j. Population outliers were deﬁned based on modiﬁed z-scores as described by the CDC: weight z-score less than 5 or greater than 8, height zscore less than 5 or greater than 4, BMI z-score less than 4 or greater than 8, relative to the CDC 2000 growth curves [15].

Third, we assessed agreement between population and longitudinal outliers by computing percent agreement and prevalenceadjusted bias-adjusted kappa (PABAK) statistics. PABAK was selected over Cohen's Kappa, which can yield paradoxical results when the prevalence of the outcome is not evenly distributed across categories of interest [16].

Fourth, we determined the impact of outlier identiﬁcation approach on prevalence of BMI categories and change in anthropometric measures. Within two analytic subsamplesdone excluding population outliers, the other excluding longitudinal outliersdwe calculated prevalence of BMI categories and mean change in weight, height, and BMI from the ﬁrst to the last observed

measurements Last Measurement

i First Measurementi

Yearsi .

Results

Study characteristics were similar in the training and test samples (Table 1). Both were composed of 57% females and a large proportion of Hispanic (43%) and non-Hispanic white (36%) children. Among the ﬁrst observed encounters for each child, mean age was 13.6 years; mean height, weight, and BMI z-scores were 0.1, 0.7, and 0.8, respectively. Among the last observed encounters for each child, mean age was 15.7 years, mean height z-score was smaller ( 0.08), and mean weight and BMI remained elevated (mean zscore 0.7 and 0.7, respectively). Children had a median of four height and BMI measures and ﬁve weight measures, although number of measurements per child varied; 10% had only three measures, 10% had 10 or more measures.

In mixed-effects models (Appendix Tables A2 and 3), weight, height, and BMI increased at faster rate before the ﬁrst inﬂection point (girls: 12.5 years; boys: 15 years), compared with after. Relative to white children, children of color were generally shorter

Table 1 Characteristics of children aged 10e18 y in the ADVANCE weight cohort*

Training dataset Test dataset

Total (n) 73,599 73,776 Sex, n (%)

Female 42,319 (57.5) 42,306 (57.3) Male 31,280 (42.5) 31,470 (42.7)

Race/ethnicity, n (%) American Indian or Alaskan Native 316 (0.4) 346 (0.5) Asian 1882 (2.3) 2103 (2.9) Black or African American 10,722 (14.6) 10,770 (14.6) Multiple race 939 (1.3) 940 (1.3) Native Hawaiian or Other Paciﬁc Islander 340 (0.5) 363 (0.5) White 26,699 (36.3) 26,587 (36.0) No information/unknown 1154 (1.6) 1157 (1.6) Hispanic 31,547 (42.9) 31,510 (42.7)

First observed visit, mean (SD)

Age (y) 13.58 (2.59) 13.57 (2.58) Height z-score 0.07 (1.17) 0.07 (1.17) Weight z-score 0.70 (1.38) 0.70 (1.39) BMI z-score 0.75 (1.50) 0.76 (1.46)

Last observed visit, mean (SD)

Age (y) 15.73 (2.47) 15.72 (2.48) Time since ﬁrst visit (y) 2.15 (1.57) 2.15 (1.57) Height z-score 0.08 (1.12) 0.08 (1.12) Weight z-score 0.69 (1.38) 0.69 (1.39) BMI z-score 0.74 (1.47) 0.74 (1.38)

Number of measures per child, median (10th, 90th percentile)

Height 4 (3, 10) 4 (3, 10) Weight 5 (3, 13) 5 (3, 13) BMI 4 (3, 10) 4 (3, 10)

* OCHIN and HCN patients who, between January 1, 2012, and December 31, 2015, had at least three height, weight, or BMI measures when they were aged 10e18 y, regardless of weight status.

and heavier at baseline, with the exception of Asian children who were shorter and lighter.

Overall, few outliers were identiﬁed using either longitudinal or populationdeﬁnitions in the test dataset; 99.7%or greaterofweight, height, and BMI measurements were not extreme by either deﬁnition in both girls and boys (agreement and PABAK 0.995; Table 2). Among population outliers, the proportion also classiﬁed as longitudinal outliers varied. For example, most low weight and height population outliers were also classiﬁed as longitudinal outliers in girls (weight: 89.3%; height: 67.1%) and boys (weight: 88.2%; height: 74.6%). For low BMI, agreement was lower: few of the population outliers were longitudinally deﬁned outliers (6.8% in girls, 17.3% in boys). High population outliers were typically also longitudinal outliersingirls(weight:100%;height:84.6%;BMI:83.7%),butlessso in boys (weight: 18.4%; height: 50.6%; BMI: 48.8%).

Exclusion of population or longitudinal BMI outliers had negligible impact on the prevalence of BMI categories; estimated prevalence were within 0.1 percentage point (Table 3). Prevalence estimates were also similar if height and weight outliers were omitted from calculated BMI values (as opposed to excluding BMI outliers).

Annualized mean change in height and BMI was similar upon removing longitudinal outliers, compared with removing population outliers (Table 4). However, among children who were greater than 85th percentile at baseline, mean changes in height, weight, and BMI were consistently and substantially higher in data screened for longitudinal outliers (girls: 1.24 inches, 12.39 pounds, 1.53 kg/m2; boys: 2.34 inches,14.08 pounds,1.07 kg/m2), compared with population outliers (girls: 0.61 inches, 8.22 pounds, 0.75 kg/ m2; boys: 1.53 inches, 11.61 pounds, 0.48 kg/m2).

The comparison of longitudinal and population outliers with regard to prevalence, agreement, BMI category prevalence and change over time were similar in the training and test datasets (Appendix Tables A4eA6).

- Table 2 Agreement between CDC population and proposed longitudinal outliers: test dataset*

Proposed longitudinal outliersy CDC population outliersz, n (column %) Percent agreement Prevalence-adjusted

bias-adjusted kappa Low Not extreme High

Girls

Weight Low 67 (89.3) 282 (0.1) 0 (0.0) 0.9983 0.9974 Not extreme 8 (10.7) 300,463 (99.8) 0 (0.0) High 0 (0.0) 235 (0.1) 33 (100)

Height Low 155 (67.1) 274 (0.1) 0 (0.0) 0.9971 0.9956 Not extreme 76 (32.9) 189,129 (99.8) 10 (15.4) High 0 (0.0) 199 (0.1) 55 (84.6)

BMI Low 6 (6.8) 123 (0.1) 0 (0.0) 0.9987 0.998 Not extreme 82 (93.2) 188,305 (99.9) 16 (16.3) High 0 (0.0) 27 (0.0) 82 (83.7)

Boys

Weight Low 45 (88.2) 194 (0.1) 0 (0.0) 0.998 0.9969 Not extreme 6 (11.8) 195,775 (99.8) 84 (81.6) High 0 (0.0) 117 (0.1) 19 (18.4)

Height Low 50 (74.6) 268 (0.2) 0 (0.0) 0.9969 0.9954 Not extreme 17 (25.4) 140,040 (99.7) 39 (49.4) High 0 (0.0) 110 (0.1) 40 (50.6)

BMI Low 18 (17.3) 56 (0.0) 1 (12.0) 0.9986 0.9979 Not extreme 86 (82.7) 139,534 (99.9) 41 (50.0) High 0 (0.0) 15 (0.0) 40 (48.8)

* Children aged 10e18 y in the ADVANCE weight cohort (n ¼ 73,776).

- y Standardized residual >j6j from sex-stratiﬁed, linear spline, mixed-effects regression.
- z Weight z-score < 5 or >8, height z-score < 5 or >4, BMI z-score < 4 or >8, relative to the CDC 2000 growth curves.


- Table 3 BMI category* prevalence (child-level): test datasety


Discussion

latter ﬁnding indicates that population-based outlier exclusion criteria may limit the accuracy of growth trajectory estimation for high-risk children, for whom growth tracking has high clinical relevance.

In this study, we demonstrated a longitudinal method for assessing weight, height, and BMI outliers in a large population of low-income children. Overall, outliers were uncommon, and agreement between population and longitudinal outlier deﬁnitions was high. The method used to identify outliers had negligible impact on the estimated prevalence of BMI categories. However, within children with elevated height, weight, or BMI at baseline (>85th percentile), exclusion of population outliers resulted in smaller estimates of mean change in weight, height, and BMI over time, compared with exclusion based on longitudinal outliers. This

Despite concerns about error in weight and height in clinical data, less than 0.3% of pediatric weight, height, and BMI measurements in our analytic sample were classiﬁed as outliers by either deﬁnition. This ﬁnding is consistent with a recent review, in which the prevalence of implausible height, weight, or BMI values ranged from 0.03% to 4.5% using variable, largely cross-sectional deﬁnitions in large study populations. Yang and Hutcheon's longitudinal outlier approach identiﬁed 0.3% of weight measures in young

Measures excluded Girls Boys

CDC population outlier approach

Proposed longitudinal outlier approach

CDC population outlier approach

Proposed longitudinal outlier approach

Height and weight outliers excluded n ¼ 33,259 n ¼ 33,155 n ¼ 25,860 n ¼ 25,782

Underweight 2.0 1.99 2.76 2.75 Normal BMI 51.6 51.67 52.36 52.43 Overweight 21.32 21.38 16.38 16.39 Obesity 15.3 15.29 16.76 16.73

- Severe obesity 9.78 9.67 11.73 11.7

BMI outliers excluded n ¼ 33,285 n ¼ 33,264 n ¼ 25,868 n ¼ 25,874

Underweight 2.01 2.03 2.74 2.79 Normal BMI 51.57 51.57 52.36 52.32 Overweight 21.33 21.34 16.38 16.37 Obesity 15.31 15.3 16.77 16.76

- Severe obesity 9.79 9.77 11.75 11.76


* BMI percentiles were classiﬁed according to CDC 2000 growth curves: underweight (<5th percentile), normal weight (5th to <85th), overweight (85th to <95th), obesity (95th to <20% higher than the 95th percentile), and severe obesity ( 20% higher than the 95th percentile).

y Children aged 10e18 y in the ADVANCE weight cohort (n ¼ 73,776). Children were classiﬁed based on last observed BMI measure, after omission of height and weight or BMI outliers, according to the population or longitudinal outlier approach.

Table 4 Annualized change in anthropometry (child level): test dataset*

Measures excluded Girls Boys

CDC population outlier approach

Proposed longitudinal outlier approach

CDC population outlier approach

Proposed longitudinal outlier approach

Height changey

Full sample n ¼ 33,429 n ¼ 33,391 n ¼ 26,021 n ¼ 25,996 Mean (SD) 0.78 (3.05) 0.73 (6.60) 1.76 (5.00) 1.74 (7.95) Median (10th, 90th percentile) 0.42 ( 0.34, 2.58) 0.40 ( 0.42, 2.64) 1.82 (0.00, 3.35) 1.79 (0.00, 3.43)

>85th percentile at baseline n ¼ 5802 n ¼ 4662 n ¼ 5518 n ¼ 4717 Mean (SD) 0.61 (2.93) 1.24 (7.51) 1.53 (2.92) 2.34 (5.45) Median (10th, 90th percentile) 0.52 ( 0.44, 2.46) 0.70 ( 0.14, 3.34) 1.67 (0.00, 3.25) 2.36 (0.00, 3.95)

Weight changey Full sample n ¼ 42,226 n ¼ 42,164 n ¼ 31,363 n ¼ 31,338 Mean (SD) 7.98 (28.20) 8.21 (32.00) 10.87 (22.46) 10.43 (42.57)

- Median (10th, 90th percentile) 6.81 ( 4.30, 21.56) 6.78 ( 5.57, 23.33) 10.59 ( 0.63, 23.66) 10.56 ( 2.12, 24.72)

>85th percentile at baseline n ¼ 17,068 n ¼ 17,434 n ¼ 13,620 n ¼ 13,067 Mean (SD) 8.22 (37.87) 12.39 (38.09) 11.61 (26.18) 14.08 (39.10)

- Median (10th, 90th percentile) 7.92 ( 7.06, 24.76) 10.73 ( 5.14, 30.23) 12.39 ( 4.09, 27.01) 15.08 ( 2.48, 30.09)


BMI changey

Full sample n ¼ 33,230 n ¼ 33,267 n ¼ 25,757 n ¼ 25,871 Mean (SD) 0.87 (5.64) 0.91 (8.74) 0.66 (5.69) 0.72 (7.94) Median (10th, 90th percentile) 0.73 ( 1.12, 3.02) 0.74 ( 1.43, 3.37) 0.67 ( 1.02, 2.53) 0.67 ( 1.28, 2.88)

>85th percentile at baseline n ¼ 15,153 n ¼ 15,475 n ¼ 12,115 n ¼ 11,661 Mean (SD) 0.75 (7.37) 1.53 (8.39) 0.48 (7.89) 1.07 (10.33) Median (10th, 90th percentile) 0.80 ( 1.71, 3.41) 1.27 ( 1.32, 4.56) 0.69 ( 1.78, 2.83) 1.11 ( 1.46, 3.71)

* Children aged 10e18 y in the ADVANCE weight cohort (n ¼ 73,776). y Annualized change calculated as (last measure ﬁrst measurement)/number of years, after omission of height and weight or BMI outliers, according to the population or

longitudinal outlier approach.

children as potential outliers in an intervention trial [9]. Among studies using EHR data, Daymont et al. reported that 3.8% of weight and 4.5% of height measures were implausible; or 0.3% of weights and 1% of heights implausible for reasons other than values “carried forward” [1], which were not explicitly identiﬁed in our study. In previous work using EHR data, BMI among children aged 2e17 years was highly reliable over time (intraclass correlation coefﬁcient 0.97) [17], and childhood obesity prevalence was consistent with NHANES [18]. In short, high-quality anthropometric measurements are available from EHR data, even in the lower resourced setting of safety net providers. This would be anticipated, given the clinical importance of accurate measurements for medication dosing and other clinical decisions.

Correspondingly, the outlier identiﬁcation method had negligible impact on the estimated prevalence of BMI categories. This result contrasts with ﬁndings from Freedman et al., who found that inclusion of valid, but extreme BMI measures resulted in a 1 percentage point difference in obesity prevalence in predominately low-income children aged 0e5 years [5]. The small impact of excluding potentially valid but extreme anthropometry measures on overall obesity prevalence in our EHR-based sample of older children is encouraging, particularly for studies that focus on overall obesity prevalence in cross-sectional populations.

Yet pediatric obesity research increasingly focuses on weight, and BMI changes over time, temporal growth patterning, or, as severe obesity becomes more common, children in the upper ranges of weight and BMI. Indeed, we found that the estimates of mean change in weight, height, and BMI over time were smaller in analyses that excluded population outliers in children who were greater than 85th percentile at baseline. These ﬁndings suggest that longitudinal outlier approaches are valuable in analyses that focus on weight change among the highest risk children.

Strengths and limitations

This study should be interpreted with several limitations in mind. Similar to most prior studies, classiﬁcation as a longitudinal or population outlier was not validated against a gold standard. Yet

we contributed evidence about agreement between approaches and their impact on estimates of BMI classiﬁcation prevalence and BMI change. Although we did not test alternative thresholds for the longitudinal residual values, we recommend this as an important next step in future research. Third, linear splines for age adequately captured the growth trajectory in our study population from 10 to 18 years of age while remaining feasible in our large, complex database, but other functional forms should be explored in studies using different age ranges. Fourth, determining the extent to which our ﬁndings are generalizable to children of higher socioeconomic status requires replication in middle and higher income study populations. Other study populations may exhibit different patterns of health care utilization and, therefore, timing of measures; however, measurements were consistent with the well-child visit schedule observed in most clinical populations. Balancing these limitations is our feasible and reproducible approach for identifying implausible values in a large, multistate study population of underrepresented and vulnerable low-income children.

Recommendations for identifying potentially invalid weight, height, and BMI values in pediatric EHR data

We offer several recommendations for deﬁning and excluding potentially implausible weight, height, and BMI values in pediatric EHR data. First, population-based deﬁnitions are well-deﬁned and easy to implement in any research context. They are the primary option for cross-sectional studies; and likely sufﬁcient for longitudinal studies that examine mean BMI or obesity prevalence at speciﬁc points in time and do not focus on children with weight or BMI above the 85th percentile.

Second, our ﬁndings suggest that longitudinal approaches are important for studies that examine changes in weight or BMI over time or among children with elevated weight or BMI. The development of longitudinal approaches is an evolving area, with several proposed approaches [1, 8, 9]. This article contributes a regressionbasedapproachforidentifying longitudinalanthropometric outliers in exceptionally large sample of older children with highly variable time points found in EHR data. Advancement of longitudinal

methods requires more validation against a gold standard, such as expert clinician review as described by Daymont et al. [1].

Third, our longitudinal approach can be applied to weight, height, and calculated BMI. We found that excluding extreme weight and heights from BMI calculations produced similar BMI category prevalence as excluding extreme calculated BMI. Yet, we recommend outlier assessment of weight and height because it aligns with the underlying data error mechanism. At a minimum, the approach should be explicitly reported to support research reproducibility.

Conclusion

We describe a longitudinal method for identifying weight, height, or BMI outliers that can be easily implemented and reproduced in EHR-based pediatric study populations. In our low-income clinical study population, less than 0.3% of anthropometry measures were potential outliers and prevalence of BMI classiﬁcations were robust to outlier identiﬁcation method. Yet our ﬁndings suggest that longitudinal outlier identiﬁcation methods are needed for unbiased estimation of weight, height, and BMI change in children with elevated values at baseline.

Acknowledgments

This publication was funded through a Patient-Centered Outcomes Research Institute Award (1306-04716; DeVoe and Puro) for the National Patient-Centered Clinical Research Network, known as PCORnet. The statements presented in this publication are solely the responsibility of the author(s) and do not necessarily represent the views of the Patient-Centered Outcomes Research Institute (PCORI), its Board of Governors or Methodology Committee or other participants in PCORnet. ADVANCE data are accessible to outside investigators through approval by the ADVANCE Research Leadership Committee and, subsequently, research collaboration and agreement with ADVANCE investigators. The project described was also supported by the National Institute of Digestive Disorders and Nutrition K01-DK102857 (J.B.H.).

References

[1] DaymontC,RossME,Russell LocalioA,Fiks AG, WassermanRC,GrundmeierRW. Automated identiﬁcation of implausible values in growth data from pediatric electronic health records. J Am Med Inform Assoc 2017;24:1080e7.

- [2] Lawman HG, Ogden CL, Hassink S, Mallya G, Vander Veur S, Foster GD. Comparing methods for identifying biologically implausible values in height, weight, and body mass index among youth. Am J Epidemiol 2015;182: 359e65.
- [3] Centers for Disease Control, Prevention. Modiﬁed z-scores in the CDC growth charts, https://www.cdc.gov/nccdphp/dnpa/growthcharts/resources/BIV-cutoffs. pdf. Accessed 2/19/2019.
- [4] Skinner AC, Ravanbakht SN, Skelton JA, Perrin EM, Armstrong SC. Prevalence of obesity and severe obesity in US Children, 1999-2016. Pediatrics 2018;141.
- [5] Freedman DS, Lawman HG, Pan L, Skinner AC, Allison DB, McGuire LC, et al. The prevalence and validity of high, biologically implausible values of weight, height, and BMI among 8.8 million children. Obesity (Silver Spring) 2016;24: 1132e9.
- [6] Isong IA, Richmond T, Avendano~ M, Kawachi I. Racial/ethnic disparities: a longitudinal study of growth trajectories among US kindergarten children. J Racial Ethn Health Disparities 2018;5:875e84.
- [7] Clarke P, O'Malley PM, Johnston LD, Schulenberg JE. Social disparities in BMI trajectories across adulthood by gender, race/ethnicity and lifetime socio-economic position: 1986e2004. Int J Epidemiol 2009;38: 499e509.
- [8] Shi J, Korsiak J, Roth DE. New approach for the identiﬁcation of implausible values and outliers in longitudinal childhood anthropometric data. Ann Epidemiol 2018;28:204e211.e3.
- [9] Yang S, Hutcheon JA. Identifying outliers and implausible values in growth trajectory data. Ann Epidemiol 2016;26:77e80.e2.
- [10] Welch C, Petersen I, Walters K, Morris RW, Nazareth I, Kalaitzaki E, et al. Twostage method to remove population- and individual-level outliers from longitudinal data in a primary care database. Pharmacoepidemiol Drug Saf 2012;21:725e32.
- [11] DeVoe JE, Gold R, Cottrell E, Bauer V, Brickman A, Puro J, et al. The advance network: accelerating data value across a national community health center network. J Am Med Inform Assoc 2014;21:591e5.
- [12] Kuczmarski RJ, Ogden CL, Guo SS, Grummer-Strawn LM, Flegal KM, Mei Z, et al. 2000 CDC Growth Charts for the United States: methods and development. Vital Health Stat 11 2002:1e190.
- [13] Division of Nutrition. Physical activity, and obesity, national center for chronic disease prevention and health promotion. Deﬁning Child Obes 2016.
- [14] Howe LD, Tilling K, Matijasevich A, Petherick ES, Santos AC, Fairley L, et al. Linear spline multilevel models for summarising childhood growth trajectories: a guide to their application using examples from ﬁve birth cohorts. Stat Methods Med Res 2016;25:1854e74.
- [15] Division of Nutrition. Physical activity, and obesity, National Center for Chronic Disease Prevention and Health Promotion. A SAS Program for the 2000 CDC Growth Charts (ages 0 to <20 years). Growth Chart Training; 2016. https:// www.cdc.gov/nccdphp/dnpao/growthcharts/resources/sas.htm. [Accessed 12 July 2018].
- [16] Byrt T, Bishop J, Carlin JB. Bias, prevalence and kappa. J Clin Epidemiol 1993;46:423e9.
- [17] Bailey LC, Milov DE, Kelleher K, Kahn MG, Beccaro MD, Yu F, et al. Multiinstitutional sharing of electronic health record data to assess childhood obesity. PLoS One 2013;8:e66192.
- [18] Flood TL, Zhao Y-Q, Tomayko EJ, Tandias A, Carrel AL, Hanrahan LP. Electronic health records and community health surveillance of childhood obesity. Am J Prev Med 2015;48:234e40.


Appendix A

Table A1 Characteristics of children aged 10e18 y in the ADVANCE weight cohort*

Characteristic Analytic sample Excluded Total (n) 147,375 207,242 Sex (%)

Female 57.42 51.60 Male 42.58 48.40

Race/ethnicity (%) American Indian or Alaskan Native 0.45 0.39 Asian 2.70 2.81 Black or African American 14.58 17.88 Multiple race 1.28 1.10 Native Hawaiian or Other Paciﬁc Islander 0.48 0.59 White 36.16 31.73 No information/unknown 1.57 3.30 Hispanic 42.79 42.19

First observed visit, median (10th, 90th percentile) Age (y) 13.39 (10.27, 17.25) 14.41 (10.56, 18.23) Height z-score 0.07 ( 1.30, 1.48) 0.03 ( 1.33, 1.45) Weight z-score 0.55 ( 0.95, 2.46) 0.45 ( 1.02, 2.26) BMI z-score 0.60 ( 0.82, 2.43) 0.47 ( 0.93, 2.21)

Last observed visit, median (10th, 90th percentile) Age (y) 16.16 (12.04, 18.73) 14.86 (11.08, 18.47) Time since ﬁrst visit (y) 1.85 (0.37, 4.37) 0.38 (0.04, 1.94) Height z-score 0.09 ( 1.44, 1.31) 0.01 ( 1.37, 1.41) Weight z-score 0.54 ( 0.97, 2.48) 0.48 ( 1.02, 2.33) BMI z-score 0.58 ( 0.85, 2.45) 0.50 ( 0.92, 2.28)

Number of measures per child, median (10th, 90th percentile)

Height 4 (3, 10) 1 (1, 2) Weight 5 (3, 13) 1 (1, 2) BMI 4 (3, 10) 1 (1, 2)

* OCHIN and HCN patients who, between January 1, 2012, and December 31, 2015, were aged 10e18 y.

Mixed model regression results: test dataset*

Variable Girls Boys Full Outliers removed Full Outliers removed b (95% conﬁdence interval)

Weight Intercept 88.32 (87.70, 88.93) 87.97 (87.36, 88.58) 84.04 (83.31, 84.76) 83.94 (83.23, 84.65) Age1y 14.85 (14.71, 15.00) 14.81 (14.67, 14.95) 14.11 (14.00, 14.22) 14.09 (13.99, 14.19) Age2z 9.58 ( 9.77, 9.39) 9.35 ( 9.54, 9.17) 7.84 ( 8.07, 7.60) 7.79 ( 8.00, 7.57) Asian 18.59 ( 20.71, 16.47) 18.29 ( 20.41, 16.17) 9.89 ( 12.39, 7.38) 9.56 ( 12.04, 7.07) NHPI 8.78 (3.91, 13.65) 8.28 (3.41, 13.14) 15.55 (9.79, 21.3) 15.21 (9.52, 20.89) Black 7.84 (6.80, 8.88) 7.43 (6.39, 8.47) 0.52 ( 0.79, 1.83) 0.86 ( 0.44, 2.16) AI/AN 5.57 (0.81, 10.33) 5.25 (0.48, 10.02) 2.18 ( 4.26, 8.62) 2.53 ( 3.85, 8.91) Multiple race 7.05 (4.15, 9.96) 6.55 (3.64, 9.46) 0.68 ( 3.41, 4.76) 0.73 ( 3.31, 4.76) Other race 0.58 ( 2.29, 3.45) 0.89 ( 1.98, 3.77) 1.62 ( 1.78, 5.01) 1.57 ( 1.79, 4.94)

- Hispanic 0.11 ( 0.65, 0.87) 0.01 ( 0.78, 0.75) 5.69 (4.77, 6.61) 5.95 (5.03, 6.86)

Height Intercept 56.39 (56.31, 56.46) 56.54 (56.47, 56.61) 55.44 (55.36, 55.52) 55.50 (55.43, 55.58) Age1y 2.50 (2.48, 2.52) 2.48 (2.46, 2.5) 2.49 (2.48, 2.500) 2.48 (2.47, 2.49) Age2z 2.18 ( 2.21, 2.16) 2.16 ( 2.18, 2.14) 2.02 ( 2.04, 2.00) 2.01 ( 2.03, 1.98) Asian 2.03 ( 2.22, 1.85) 2.05 ( 2.23, 1.87) 1.68 ( 1.91, 1.45) 1.66 ( 1.90, 1.43) NHPI 0.75 ( 1.16, 0.33) 0.78 ( 1.18, 0.37) 0.06 ( 0.60, 0.48) 0.00 ( 0.55, 0.54) Black 0.01 ( 0.09, 0.08) 0.01 ( 0.08, 0.09) 0.03 ( 0.15, 0.09) 0.01 ( 0.13, 0.11) AI/AN 0.11 ( 0.29, 0.51) 0.07 ( 0.32, 0.46) 0.18 ( 0.43, 0.78) 0.15 ( 0.46, 0.76) Multiple race 0.26 (0.01, 0.50) 0.23 ( 0.01, 0.47) 0.08 ( 0.45, 0.29) 0.10 ( 0.47, 0.28) Other race 0.19 ( 0.44, 0.06) 0.19 ( 0.44, 0.06) 0.45 ( 0.77, 0.13) 0.44 ( 0.76, 0.11)

- Hispanic 1.45 ( 1.52, 1.39) 1.47 ( 1.53, 1.40) 0.92 ( 1.00, 0.83) 0.89 ( 0.98, 0.81)


BMI Intercept 19.71 (19.56, 19.86) 19.68 (19.56, 19.8) 19.86 (19.73, 20.00) 19.85 (19.72, 19.97) Age1y 1.22 (1.16, 1.27) 1.16 (1.13, 1.18) 0.80 (0.78, 0.82) 0.80 (0.79, 0.82) Age2z 0.60 ( 0.67, 0.53) 0.47 ( 0.51, 0.43) 0.27 ( 0.32, 0.21) 0.22 ( 0.26, 0.19) Asian 2.16 ( 2.59, 1.72) 2.08 ( 2.48, 1.68) 0.88 ( 1.32, 0.44) 0.95 ( 1.38, 0.52) NHPI 1.50 (0.52, 2.48) 1.33 (0.43, 2.23) 2.81 (1.80, 3.82) 2.83 (1.86, 3.81) Black 1.49 (1.29, 1.7) 1.26 (1.07, 1.45) 0.09 ( 0.31, 0.13) 0.1 ( 0.32, 0.11) AI/AN 0.99 (0.04, 1.94) 1.01 (0.13, 1.89) 0.10 ( 1.01, 1.21) 0.12 ( 0.97, 1.22) Multiple race 1.22 (0.64, 1.81) 1.27 (0.73, 1.81) 0.32 ( 0.37, 1.01) 0.24 ( 0.44, 0.91) Other race 0.08 ( 0.68, 0.52) 0.07 ( 0.48, 0.62) 0.29 ( 0.32, 0.90) 0.31 ( 0.28, 0.90) Hispanic 0.90 (0.74, 1.05) 0.82 (0.68, 0.97) 1.48 (1.32, 1.64) 1.43 (1.28, 1.58)

AI/AN ¼ American Indian/Alaskan native; NHPI ¼ native Hawaiian or Paciﬁc islander.

* Children aged 10e18 y in the ADVANCE weight cohort (n ¼ 73,776).

- y Age1 corresponds to age in years from age 10 to 12.5 for girls and from age 10 to 15 in boys.
- z Age2 corresponds to age in years from age 12.5 to 18 for girls and from age 15 to 18 in boys.


Mixed model regression results: training dataset*

Variable Girls Boys Full Outliers removed Full Outliers removed b (95% conﬁdence interval)

Weight Intercept 88.04 (87.43, 88.65) 87.85 (87.24, 88.46) 84.34 (83.62, 85.07) 83.96 (83.26, 84.67) Age1y 14.73 (14.59, 14.87) 14.62 (14.49, 14.76) 14.03 (13.92, 14.14) 14.03 (13.93, 14.13) Age2z 9.33 ( 9.51, 9.14) 9.03 ( 9.21, 8.84) 7.58 ( 7.81, 7.35) 7.54 ( 7.75, 7.32) Asian 15.93 ( 18.17, 13.68) 15.85 ( 18.11, 13.58) 12.26 ( 14.86, 9.67) 11.66 ( 14.21, 9.1) NHPI 10.16 (5.15, 15.17) 10.27 (5.24, 15.3) 11.88 (5.66, 18.1) 11.5 (5.38, 17.62) Black 7.99 (6.95, 9.03) 7.64 (6.6, 8.68) 0.49 ( 0.83, 1.81) 0.74 ( 0.56, 2.04) AI/AN 7.62 (2.74, 12.5) 7.42 (2.51, 12.33) 8.54 (1.28, 15.8) 8.66 (1.53, 15.8) Multiple race 7.58 (4.65, 10.51) 7.37 (4.43, 10.32) 3.08 ( 0.88, 7.04) 2.54 ( 1.36, 6.44) Other race 1.78 ( 4.63, 1.07) 1.87 ( 4.74, 1) 0.42 ( 2.95, 3.79) 0.56 ( 3.89, 2.76) Hispanic 0.02 ( 0.74, 0.78) 0.17 ( 0.93, 0.6) 5.36 (4.44, 6.29) 5.94 (5.03, 6.85)

Height Intercept 56.42 (56.35, 56.49) 56.54 (56.47, 56.61) 55.47 (55.4, 55.55) 55.55 (55.47, 55.63) Age1y 2.5 (2.48, 2.53) 2.49 (2.47, 2.52) 2.49 (2.48, 2.5) 2.48 (2.47, 2.49) Age2z 2.19 ( 2.21, 2.16) 2.17 ( 2.2, 2.15) 2.02 ( 2.05, 2) 2 ( 2.02, 1.98) Asian 1.98 ( 2.18, 1.79) 2.03 ( 2.21, 1.84) 1.92 ( 2.16, 1.68) 1.88 ( 2.12, 1.64) NHPI 0.63 ( 1.05, 0.21) 0.68 ( 1.1, 0.27) 0.61 ( 1.19, 0.03) 0.47 ( 1.06, 0.11) Black 0.05 ( 0.13, 0.04) 0 ( 0.09, 0.08) 0.07 ( 0.19, 0.05) 0.06 ( 0.18, 0.06) AI/AN 0.07 ( 0.34, 0.48) 0.06 ( 0.35, 0.46) 0.11 ( 0.77, 0.55) 0.15 ( 0.81, 0.52) Multiple race 0.04 ( 0.21, 0.29) 0.02 ( 0.23, 0.26) 0.12 ( 0.48, 0.24) 0.13 ( 0.5, 0.23) Other race 0.29 ( 0.55, 0.04) 0.34 ( 0.59, 0.09) 0.31 ( 0.63, 0.01) 0.28 ( 0.6, 0.05) Hispanic 1.51 ( 1.57, 1.44) 1.52 ( 1.58, 1.46) 0.99 ( 1.07, 0.9) 0.98 ( 1.06, 0.89)

BMI Intercept 19.53 (19.38, 19.67) 19.56 (19.45, 19.68) 19.9 (19.77, 20.03) 19.88 (19.75, 20) Age1y 1.23 (1.18, 1.28) 1.16 (1.13, 1.19) 0.77 (0.75, 0.8) 0.78 (0.76, 0.79) Age2z 0.59 ( 0.65, 0.53) 0.46 ( 0.5, 0.42) 0.15 ( 0.21, 0.1) 0.16 ( 0.19, 0.12) Asian 1.78 ( 2.24, 1.33) 1.74 ( 2.15, 1.32) 1.15 ( 1.59, 0.7) 1.19 ( 1.63, 0.75) NHPI 2.13 (1.15, 3.12) 2.12 (1.21, 3.02) 2.6 (1.55, 3.65) 2.31 (1.26, 3.36) Black 1.52 (1.32, 1.73) 1.22 (1.03, 1.4) 0.06 ( 0.28, 0.16) 0.08 ( 0.3, 0.13) AI/AN 1.14 (0.16, 2.12) 1.2 (0.3, 2.1) 1.23 (0.01, 2.45) 1.31 (0.1, 2.51) Multiple race 1.37 (0.78, 1.96) 1.29 (0.74, 1.83) 0.77 (0.11, 1.43) 0.81 (0.16, 1.47) Other race 0.18 ( 0.78, 0.42) 0.16 ( 0.71, 0.4) 0.24 ( 0.35, 0.82) 0.3 ( 0.28, 0.88) Hispanic 0.96 (0.81, 1.12) 0.88 (0.74, 1.02) 1.45 (1.3, 1.6) 1.43 (1.28, 1.59)

AI/AN ¼ American Indian/Alaskan native; NHPI ¼ native Hawaiian or Paciﬁc islander.

* Children 10e18 y of age in the ADVANCE weight cohort (n ¼ 73,599).

y Age1 corresponds to age in years from age 10 to 12.5 for girls and from age 10 to 15 in boys. z Age2 corresponds to age in years from age 12.5 to 18 for girls and from age 15 to 18 in boys.

Agreement between population and longitudinal outliers: training dataset* Longitudinal outliersy Population outliers,z n (column %) Percent agreement Prevalence-adjusted

bias-adjusted kappa Low Not extreme High

Girls

Weight d d d 0.9982 0.9974 Low 55 (87.3) 313 (0.1) 0 (0.0) d d Not extreme 8 (12.7) 301,602 (99.8) 3 (7.3) High 0 (0.0) 205 (0.1) 38 (92.7)

Height d d d 0.997 0.9955 Low 150 (79.8) 288 (0.2) 0 (0.0) d d Not extreme 38 (20.2) 189,824 (99.7) 47 (47.5) High 0 (0.0) 198 (0.1) 52 (52.5)

BMI d d d 0.9988 0.9983 Low 3 (4.2) 112 (0.1) 0 (0.0) d d Not extreme 68 (95.8) 189,166 (99.9) 10 (9.4) High 0 (0.0) 28 (0.0) 96 (90.6)

Boys

Weight d d d 0.9975 0.9963 Low 34 (56.7) 208 (0.1) 0 (0.0) d d Not extreme 26 (43.3) 192,484 (99.8) 96 (86.5) High 0 (0.0) 151 (0.1) 15 (13.5)

Height d d d 0.9968 0.9951 Low 64 (57.1) 228 (0.2) 0 (0.0) d d Not extreme 48 (42.9) 137,612 (99.8) 57 (57.6) High 0 (0.0) 116 (0.1) 42 (42.4)

BMI d d d 0.9985 0.9977 Low 15 (17.9) 74 (0.1) 0 (0.0) d d Not extreme 69 (82.1) 137,251 (99.9) 38 (46.9) High 0 (0.0) 26 (0.0) 43 (53.1)

* Children aged 10e18 y in the ADVANCE weight cohort (n ¼ 73,599).

- y Studentized residual >j6j from sex-stratiﬁed, linear spline, mixed-effects regression.
- z Weight z-score < 5 or >8, height z-score < 5 or >4, BMI z-score < 4 or >8, relative to the CDC 2000 growth curves.


Table A5 BMI category* prevalence (child-level): training datasety

Measures excluded Girls Boys

Population outlier approach Longitudinal outlier approach Population outlier approach Longitudinal outlier approach Height and weight outliers excluded n ¼ 33,345 n ¼ 33,214 n ¼ 25,666 n ¼ 25,585

Underweight 1.99 1.98 2.91 2.89 Normal BMI 51.82 51.90 52.21 52.26 Overweight 21.39 21.45 16.91 16.93 Obese 15.41 15.38 16.70 16.65

- Severe obesity 9.40 9.30 11.28 11.27

BMI outliers excluded n ¼ 33,364 n ¼ 33,342 n ¼ 25,686 n ¼ 25,683

Underweight 1.98 2.00 2.90 2.92 Normal BMI 51.80 51.80 52.19 52.16 Overweight 21.39 21.39 16.90 16.91 Obese 15.41 15.41 16.70 16.68

- Severe obesity 9.41 9.40 11.31 11.32


* BMI percentiles were classiﬁed according to CDC 2000 growth curves: underweight (<5th percentile), normal weight (5th to <85th), overweight (85th to <95th), obese (95th to <20% higher than the 95th percentile), and severe obese ( 20% higher than the 95th percentile).

y Children aged 10e18 y in the ADVANCE weight cohort. Children were classiﬁed based on last observed BMI measure, after omission of height and weight or BMI outliers, according to the population or longitudinal outlier approach.

Table A6 Annualized change in anthropometry (child level): training dataset*

Change measure Girls Boys

Population outlier approach Longitudinal outlier approach Population outlier approach Longitudinal outlier approach Height changey

Full sample n ¼ 33,492 n ¼ 33,439 n ¼ 25,798 n ¼ 25,769 Mean (SD) 0.78 (3.79) 0.71 (10.07) 1.71 (5.77) 1.65 (5.78) Median (10th, 90th percentile) 0.43 ( 0.34,2.57) 0.41 ( 0.42,2.65) 1.80 (0.00,3.34) 1.77 (0.00,3.42)

>85th percentile at baseline n ¼ 5839 n ¼ 4545 n ¼ 5383 n ¼ 4606 Mean (SD) 0.53 (5.92) 1.28 (6.74) 1.45 (5.66) 2.36 (7.32) Median (10th,90th percentile) 0.53 ( 0.44, 2.38) 0.73 ( 0.13, 3.26) 1.65 (0.00, 3.25) 2.39 (0.00, 4.04)

Weight changey Full sample n ¼ 42,254 n ¼ 42,194 n ¼ 31,195 n ¼ 31,166 Mean (SD) 8.07 (22.78) 8.34 (37.82) 10.71 (21.60) 10.93 (40.46)

- Median (10th, 90th percentile) 6.91 ( 4.27, 21.47) 6.89 ( 5.75, 23.48) 10.50 ( 0.22, 23.18) 10.46 ( 1.64, 24.33)

>85th percentile at baseline n ¼ 16,873 n ¼ 17,398 n ¼ 13,385 n ¼ 12,961 Mean (SD) 8.07 (27.95) 12.45 (44.52) 11.25 (24.09) 14.65 (50.88)

- Median (10th, 90th percentile) 7.89 ( 7.12, 24.35) 10.63 ( 4.91, 30.42) 12.12 ( 3.64, 26.61) 14.80 ( 1.60, 29.87)


BMI changey

Full sample n ¼ 33,310 n ¼ 33,345 n ¼ 25,558 n ¼ 25,682 Mean (SD) 0.89 (4.48) 0.90 (8.27) 0.68 (5.27) 0.63 (15.11) Median (10th, 90th percentile) 0.72 ( 1.06, 2.99) 0.72 ( 1.41, 3.37) 0.66 ( 1.01, 2.50) 0.66 ( 1.26, 2.79)

>85th percentile at baseline n ¼ 14,973 n ¼ 15,389 n ¼ 11,938 n ¼ 11,565 Mean (SD) 0.76 (4.97) 1.55 (10.51) 0.44 (6.58) 1.07 (10.25) Median (10th, 90th percentile) 0.80 ( 1.64, 3.33) 1.24 ( 1.40, 4.46) 0.64 ( 1.66, 2.82) 1.09 ( 1.44, 3.67)

* Children aged 10e18 y of age in the ADVANCE weight cohort. y Annualized change calculated as (last measure ﬁrst measurement)/number of years, after omission of height and weight or BMI outliers, according to the population or

longitudinal outlier approach.

