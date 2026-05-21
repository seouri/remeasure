Published by Oxford University Press on behalf of the International Epidemiological Association The Author 2013; all rights reserved. Advance Access publication 14 September 2013

International Journal of Epidemiology 2013;42:1327–1339 doi:10.1093/ije/dyt157

DEVELOPMENTAL ORIGINS OF HEALTH AND DISEASE HYPOTHESES

# A critical evaluation of statistical approaches to examining the role of growth trajectories in the developmental origins of health and disease

Yu-Kang Tu,1* Kate Tilling,2 Jonathan AC Sterne2 and Mark S Gilthorpe3

1Graduate Institute of Epidemiology & Preventive Medicine, College of Public Health, National Taiwan University, Taipei, Taiwan, 2School of Social and Community Medicine, University of Bristol, Bristol, UK and 3Division of Biostatistics, School of Medicine, University of Leeds, Leeds, UK

*Corresponding author. Graduate Institute of Epidemiology & Preventive Medicine, College of Public Health, National Taiwan University, 17 Xu-Zhou Road, 110, Taipei, Taiwan. E-mail: yukangtu@ntu.edu.tw

Accepted 15 July 2013

The developmental origins of health and disease hypothesis suggests that small birth size in conjunction with rapid compensatory childhood growth might yield a greater risk of developing chronic diseases in later life. For example, there is evidence that people who developed coronary heart disease and diabetes experienced different growth trajectories from those who did not develop these diseases. However, some of the methods used in these articles may have been flawed. We critically evaluate proposed approaches for identifying the growth trajectories distinctive to those developing later disease and identifying critical phases of growth during the early lifecourse. Among the approaches we examined (tracing the z-scores, lifecourse plots and models, lifecourse path analysis, conditional body size analysis, multilevel analysis, latent growth curve models and growth mixture models) conditional body size analysis, multilevel analysis, latent growth curve models and growth mixture models are least prone to collinearity problems caused by repeated measures. Multilevel analysis is more flexible when body size is not measured at the same age for all cohort members. Strengths and weaknesses of each approach are illustrated using real data. Demonstrating the influence of growth trajectories on later disease is complex and challenging; therefore, it is likely that a combination of approaches will be required to unravel the complexity in lifecourse research.

Keywords Developmental origins of health and disease, birthweight, body weight, growth, cohort studies

Introduction

The foetal origins of adult disease hypothesis (FOAD)1 has attracted considerable attention among medical and epidemiological researchers over the past three decades. It has been shown that birth sizes (usually

birthweight) have an inverse relationship with health outcomes in later life, such as cardiovascular diseases,2 hypertension,3 diabetes4 and obesity.5 An elaboration of the FOAD hypothesis suggests that small birth size in conjunction with compensatory rapid growth in childhood (rather than small birth size

1327

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

per se) leads to a greater risk of developing chronic adult diseases. As a result, the FOAD hypothesis has been rephrased as ‘the developmental origins of health and disease hypothesis’ (DOHaD hypothesis).6

The DOHaD hypothesis proposes that the risk of chronic disease in adult life is initially induced through predictive adaptive responses that the foetus or infant develops in response to environmental signals from their mothers.6–8 These responses, including changes in metabolism, hormone production and tissue sensitivity to hormones, may have negative impacts on later health if the postnatal environment experiences substantial changes, leading to a mismatch between prenatal physiological adaption in foetal development and postnatal environment.9 Furthermore, the predictive adaptive responses are likely to continue into early life and childhood. Consequently, those people with a mismatch may show distinctive growth patterns, and if we can distinguish those patterns, we may be able to use growth data throughout the early lifecourse to identify people at higher risk of developing adverse health outcomes in later life.

Many approaches have been proposed to identify distinctive growth trajectories or critical growth phases in early childhood that may be related to higher risk of chronic diseases in later life. Some aim to model individual growth trajectories, whereas others take a population-average approach.9–12 The aim of this article is to review the strengths and weaknesses of several proposed strategies and to use real data to compare the results of these approaches.

## The illustrative dataset

Throughout this article we use data from a prospective cohort study whose participants were recruited from Metropolitan Cebu, an area of the central Philippines.13 Data were obtained from the website of the University of North Carolina Population Centre (www.cpc.unc.edu/projects/cebu/datasets); a detailed description of the study can be found on their website and in articles published by Adair and her colleagues.13,14 In summary, all pregnant residents of 33 randomly selected Metro Cebu communities were invited to participate, and index-child participants include 3080 singletons born during a 1-year period beginning in April 1983. Prenatal data were collected during the 6th to 7th months of pregnancy. We use postnatal data of offspring body weights measured immediately after birth and at ages 1 year, 2 years, 8 years, 15 years and 19 years. The later-life health outcome is systolic blood pressure (SBP) measured at age 19 years. We use data from 960 boys with no missing measurements of body weight or blood pressure. Raw body weights are transformed to obtain z-scores by subtracting sample average weights from individual weights and dividing by sample standard deviations at each age. Figure 1 shows observed growth trajectories for raw body

weights and for weight z-scores weights from birth to 19 years in 30 randomly selected Cebu boys. Table 1 summarizes means of and correlations between the body size measurements and SBP. Note that the first three measurements (at birth, age 1 and age 2 years) were at the same ages for all cohort members, but subsequent body weights (at ages 8, 15 and 19 years) were measured at only roughly the same ages, with 1–2 year differences.13,14

## Tracing the average z-scores

Following the statistical approach of tracking z-scores over the lifecourse,7–12 Figure 2a shows average weight z-scores between birth and age 19 years for men who had normal (dashed line) and high (solid line) blood pressure (defined as 4115mmHg) at age 19 years. The mean birthweight z-score of men with high blood pressure was negative: this group achieved above-average body weight at age 1 year. After age 1 year, they gained more weight than those with normal blood pressure. When the mean weight z-score of one subgroup is less than zero, the mean weight z-score of the other group must be greater than zero, as the average weight z-score of the whole group at each age is zero by definition. If the two groups (of men with normal and with high blood pressure) had the same number of subjects, and all subjects were measured at identical ages, the two growth trajectories would be mirror images about zero.

Figure 2a seems to suggest that compensatory growth in body weight during the 1st year of life is associated with an increased risk of developing hypertension in later life.7–12 However, the correct interpretation is that birthweight has an inverse association with high blood pressure at age 19 years. When the two patterns of growth cross, between birth and 1 year, the average z-score in each group equals zero; so the association of body weight at this age with high blood pressure at age 19 years is zero. After the age of 1 year, the association between body weight and high blood pressure at age 19 years becomes positive, and is greatest at the age of 19 years. The greater the association (positive or negative) between body weight at a particular age and the adult health outcome, the more separation occurs between the mean z-score in the two groups. The correct interpretation is apparent when we compare Figure 2a with Figure 2b, which shows the natural log of the odds ratios for the association of body weight at each age with high blood pressure at age 19 years. Since the difference between the mean zscores in the two groups at each age reflects the strength of the association at that age, the growth pattern of men with high blood pressure is similar to the trend in the values of the log odds ratio.

Based on tracking z-scores, several studies have concluded that people who develop adult chronic diseases tend to have had a distinctive growth trajectory.7–12 Figure 2 shows that these patterns are better

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

![image 1](<A critical evaluation of statistical approaches to examining the role of growth trajectories in the developmental origins of health and disease_images/imageFile1.png>)

Figure 1 Observed individual weight trajectories of 30 randomly selected Cebu boys during birth to age 19 years

- Table 1 Summary statistics of body weight measurements (in kg) and blood pressure (in mmHg) for 960 boys in Cebu cohort


Pearson correlations Variable Mean SD Weight0 Weight1 Weight2 Weight8 Weight15 Weight19 SBP

- Weight0 3.04 0.44 1.00
- Weight1 8.27 1.00 0.40 1.00
- Weight2 10.10 1.15 0.36 0.84 1.00 Weight8 20.67 3.21 0.26 0.61 0.67 1.00 Weight15 46.79 8.40 0.22 0.49 0.54 0.82 1.00 Weight19 53.37 8.58 0.21 0.47 0.53 0.78 0.87 1.00 SBP 106.37 10.57 0.00 0.08 0.11 0.22 0.27 0.33 1.00 Weightn: n is the age at which body weight is measured; SD, standard deviation.


understood as a connected series of cross-sectional associations of body weight at successive ages with health outcomes in later life. Substantial upward or downward slopes reflect ages during which the magnitude of the association of body size with health outcomes in adulthood is changing rapidly, rather than average growth trajectories.15 Figure 2 thus confirms, as is well known, that adult body sizes have a positive relationship with later-life adverse health outcomes, but that body sizes at birth or during early childhood have weaker, inverse relationships.

## Approaches based on conditioning

In this section, we discuss statistical approaches that estimate the relation between body weight measured

at a given age with adjustment for body weights at other ages, i.e. the estimated association is conditional on other body sizes in the same model. For instance, Figure 3 shows a directed acyclic graph, where each body weight may have a direct effect on blood pressure at age 19 years (i.e. the arrow from each weight to blood pressure) but each body weight may also have an indirect impact through its influence on later body weights (i.e. the arrow from each weight to the subsequent weight).

The lifecourse plot

In the lifecourse plot approach,16,17 the outcome variable is regressed on the body size (or its z-score) measured during the early lifecourse using multiple regression. Suppose that body weight was measured

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

![image 2](<A critical evaluation of statistical approaches to examining the role of growth trajectories in the developmental origins of health and disease_images/imageFile2.png>)

- Figure 2 (a) Mean z-scores for body weight from birth to the age of 19 years for men with normal (Normal) or higher blood pressure (Hypertensive) by the age of 19 years; (b) the natural log of Odds Ratio of developing higher blood pressure for 1-unit increase in body weight z-score at each age

![image 3](<A critical evaluation of statistical approaches to examining the role of growth trajectories in the developmental origins of health and disease_images/imageFile3.png>)

- Figure 3 Directed acyclic graph for the relationships among body weights measured at different ages (Weighti) and blood pressure at age 19 years. U1 represents unmeasured background variables affecting body weights, and U2 represents background variables affecting blood pressure. This figure


blood pressure are used instead, the intercept b0 will be zero. The partial regression coefficients bj are typically plotted as a connected line against the ages at which they were measured. A change in the direction of the multiple regression coefficients is interpreted as indicating a critical phase of the relationship between growth and risk of later chronic disease.

Table 2 summarizes results from the multiple linear regression analysis using the Cebu data, and Figure 4 is the lifecourse plot for SBP regressed on the six body size z-scores (zwt0, zwt1, zwt2, zwt8, zwt15, and zwt19) between birth and age 19 years. Regression coefficients in early life and childhood are all small and most of them are negative, whereas the coefficient at age 19 years is large and positive. Each coefficient represents the association between a 1-SD change in weight at that age and later blood pressure, conditional on all other weights. For example, for two individuals with identical weights at birth and all ages after 1 year, a 1-SD higher weight at 1 year would be associated with a difference in SBP in later life of

shows a simplified scenario, where U1 and U2 are not confounders for the relation between body weights and blood pressure

0.76 (95% CI: 1.95 to þ0.44) mmHg. The suggested interpretation of the entire plot is that weight gain from 15 to 19 years of age (i.e. into and through puberty) is associated with high SBP at 19 years.

Potential difficulty in the interpretation of the lifecourse plot arises due to collinearity among the series of body size measurements. As growth is a continuous process, successive body size measurements are generally correlated, and the shorter the age interval between two measurements the greater the correlation (Table 1). In Figure 4, when all six body size measurements are included in the multiple regression, zwt0, zwt1 and zwt8 have negative associations with SBP, but, zwt2 and zwt19 have positive correlations

p times at different ages. The lifecourse plot is obtained by regressing the outcome y on these measurements:

y ¼ b0 þ Xp j¼1

bjweightj þ e

where b0 is the intercept, bj the regression coefficient for weightj and e the residual error term. If sample z-scores for body weight and sample z-scores for

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

- Table 2 Results from multiple linear regression for (1) Model for the Lifecourse Plot: SBP regressed on birthweight z-scores and five z-score weights at ages 1, 2, 8, 15 and 19 years; (2) Conditional model: SBP regressed on birthweight z-scores and five conditional z-score weights at ages 1, 2, 8, 15 and 19 years; (3) Change Score Model 1: SBP regressed on birthweight z-scores and changes in consecutive weight z-scores; (4) Change Score Model 2: SBP regressed on changes in consecutive changes in weight z-scores and z-score weight at age 19 years


Model for Lifecourse Plot Conditional Model Change Scores Model 1 Change Scores Model 2 Coef 95% CI Coef 95% CI Coef 95% CI Coef 95% CI

- zwt0 0.54 1.23, 0.15 zwt0 0.026 ( 0.70, 0.64) zwt0 2.58 1.73, 3.43 zwt1–0 0.54 0.15, 1.23
- zwt1 0.76 1.95, 0.44 Cond. zwt1 1.01 (0.28, 1.74) zwt1–0 3.12 2.31, 3.92 zwt2–1 1.3 0.04, 2.56
- zwt2 0.18 1.08, 1.45 Cond. zwt2 1.76 (0.53, 2.99) zwt2–1 3.87 2.62, 5.13 zwt8–2 1.11 0.13, 2.09 zwt8 0.55 1.83, 0.73 Cond. zwt8 2.79 (1.90, 3.68) zwt8–2 3.69 2.80, 4.58 zwt15–8 1.66 0.42, 2.91 zwt15 0.01 1.41, 1.42 Cond. zwt15 2.9 (1.78, 4.01) zwt15–8 4.24 3.07, 5.41 zwt19–15 1.66 0.19, 3.12 zwt19 4.24 2.91, 5.56 Cond. zwt19 4.24 (2.91, 5.56) zwt19–15 4.24 2.91, 5.56 zwt19 2.58 1.73, 3.43


zwt 0: z-scores weight at birth; zwt1–0: change in z-scores between age 1 year and birth; zwt2–1: change in z-scores between ages 2 and 1 year; zwt8–2: change in z-scores between ages 8 and 2 years; zwt15–8: change in z-scores between ages 15 and 8 years; zwt19–15: change in z-scores between ages 19 and age 15 years; zwt19: z-scores weight at age 19 years.

![image 4](<A critical evaluation of statistical approaches to examining the role of growth trajectories in the developmental origins of health and disease_images/imageFile4.png>)

- Figure 4 Lifecourse plot for SBP on weight z-scores during birth to age 19 years in 960 Cebu boys


with SBP(Table 2). Whereas these negative associations in the lifecourse plot can be viewed as adjusted associations, conditional on other weight measurements in the model, change in the direction of association may causes difficulty in the interpretation of individual coefficients. A similar issue arises if one of the six body size measurements is omitted, as the revised plot may look different. In Figure 4, we show lifecourse plots for three alternative scenarios: (i) z-score weight at age 15 years is omitted; (ii) z-score weight at age 8 years is omitted; and (iii) there are only z-score weights at birth and age 19 years. In scenario (i), there is a large change in regression coefficient between ages 8 and 19 years; in scenario (ii), the change is noted between ages 15 and

19 years; and in scenario (iii), the change occurs between birth and age 19 years. These results are not necessarily in conflict with each other, as the body size measurements are sparse and there is no interim measurement between ages 8 and 15 years. However, collinearity causes unstable estimates for regression coefficients and wide confidence intervals, making the interpretation and identification of critical periods difficult.

Path analysis

Lifecourse path analysis18,19 can be viewed as a modification to the lifecourse plot,18 and the model depicted in Figure 3 is one example of the lifecourse path analysis. The lifecourse plot only estimates the ‘direct’ relationships (such as those shown in Figure 3), whereas the path analysis attempts to estimate both direct and indirect paths simultaneously, yielding the overall effect.

Since causal relationships in the path analysis are conditional on other variables in the models, its results are very similar to those from the lifecourse plot: the lifecourse plot can be viewed as one possible lifecourse path model, and the path analysis will yield the same results. Moreover, there are many possible lifecourse path models with slightly modified causal relations among variables, yielding slightly different results. Hence we have not shown the results from the path analysis. Path analysis suffers the same problem of interpretation due to collinearity among repeated measures of the same variables (body size or health outcome).20,21 For instance, the direct effects of early body sizes on a later health outcome in the path analysis are conditional on later body sizes, and if there are confounders for the relation between later body sizes and the health outcome, the estimated direct effect is biased.

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

Conditional models

Conditional body size is defined as the difference between observed and predicted body size.22,23 The predicted body size at age measured on occasion p is obtained by regressing the observed body size on all preceding body sizes (1 ...p-1) since birth (and, potentially, other covariates), for example:

weightp ¼ b0 þ Xp 1

j¼1 bjweightj þ e, ½Equation 1

As the predicted body weight at age on occasion p is b0 þ Pp 1

j¼1 bjweightj, the conditional weight is therefore the residual error. As the residual error term is orthogonal (uncorrelated) to covariates in the model, this ensures that conditional body size on occasion p is always orthogonal to all preceding body sizes and all preceding conditional body sizes.

In the conditional body size approach, the health outcome in later life is regressed on all conditional body sizes plus birth size. It has been argued22,23 that this approach overcomes the problem with collinearity in traditional multiple regression analysis and hence the interpretation of its results is straightforward: the expected change in health outcome given one unit difference between observed and expected body size, conditional on all previous weights.

The conditional body size analysis is equivalent to a series of regression analyses of the outcome (later blood pressure) on each weight, conditional on previous (but not future) weights. For instance, the regression model for SBP on p conditional weights is written as:

SBP ¼ b0 þ Xp j¼1

bjCWTj þ e

where b0 is the intercept, bj the regression coefficient for conditional weight (CWTj) and e the residual error term. The regression coefficients bj(j¼1 to p) can also be obtained by undertaking p multiple regression analyses starting with a simple model with only birthweight as the covariate and then subsequent weight measures are added as covariates one by one:

- SBPð1Þ ¼ að01Þ þ að11ÞWeight1 þ eð1Þ
- SBPð2Þ ¼ að02Þ þ að12ÞWeight1 þ að22ÞWeight2 þ eð2Þ


... SBPðpÞ ¼ að0pÞ þ að1pÞWeight1 þ að2pÞWeight2

þ ::: þ aðppÞWeightp þ eðpÞ

where að0kÞ is the intercept and e(p) the residual error term for the kth (k¼ 1 to p) regression model, and aðikÞ are the regression coefficient for Weightj in the kth model. It can be shown that the bj in Equation 1 are equivalent to the aðkkÞ in the kth model, i.e. the last regression coefficient in each of the 1 to p models. Therefore, the interpretation of conditional

weight is the same as that of raw weight measure with the adjustment for all preceding weights. This method may not completely resolve the collinearity and associated interpretational issues. In general, there are fewer measures per model than in the single lifecourse model, but the size of the standard error is likely to increase with age, since the number of other weight measures included in the model increases.

The conditional weight z-scores analysis (Table 2) shows a similar pattern to that from tracing the z-scores in Figure 2a, i.e. that the association between blood pressure and body size increases with age. As the ‘‘‘direct’ association between blood pressure and body weights increases with age (Table 1) and the correlations between body weights at different ages are positive, the adjustment for preceding weights will diminish the association between blood pressure and the later weight but the general patterns may (and does) remain.

In summary, collinearity among body size measurements and interpretation of coefficients which are conditioned on future measures are potential problems with the lifecourse plot and path analysis. Conditional weight analysis partially resolves the collinearity problem and may seem easier to interpret than the lifecourse plot because each coefficient is explicitly conditioned on past weights only. Consequently, conditional weight analysis may be seen as a compromise between tracing z-scores and lifecourse plot: coefficients in tracing z-scores are simple regression coefficients, and those in lifecourse plot are conditioned on past and future weights. Like tracing body size z-scores, these approaches require that all measures must be taken at the same times/ ages for all individuals.

## Regression with change scores

If our aim is to identify a critical period of time during the lifecourse in which rapid growth in body size is associated with an increased risk of chronic diseases, an intuitive approach is to regress the outcome on the growth in body size in different periods of time during the lifecourse.24,25 For p body weight measurements at different ages, there are p – 1 variables for incremental changes in body weight, and we can regress the outcome y on p – 1 incremental changes in body weight and the first body size or we can regress y on p – 1 incremental changes in body size and the last body size. Note that we cannot regress y on p – 1 incremental changes in body size, the first and the last body size, as this leads to over-parameterization of the model (due to perfect collinearity).

In our example, there are six body weight z-scores from birth to age 19 years, so we may regress SBP on z-score at birth (zwt0) and five incremental changes in z-scores;the Change Score Model 1 in Table 2 shows

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

the results from this multiple regression model. The regression coefficients for growth in weight z-scores during adolescence are relatively larger than early growth and birth size, suggesting a greater impact on SBP, and (in contrast to the methods discussed so far) z-score weight at birth (zwt0) has a positive association with SBP.

Alternatively, SBP can be regressed on the five incremental changes in weight z-scores and weight z-score at age 19 years (zwt19). Change Score Model 2 in Table 2 shows the results from this second multiple regression. Whereas zwt19 seems to have the largest effect on SBP, the regression coefficients for the five incremental changes in weight z-scores in Change Score Model 2 are much smaller than in Change Score Model 1, but later growth still has a larger effect than early growth. Although the two sets of regression coefficients may look different, there is a simple mathematical relationship between them: for the same variables, regression coefficients in Change Score Model 1¼2.58 þregression coefficients in Change Score Model 2. Since zwt19 can be expressed as:

zwt19 ¼ zwt19 15 þ zwt15 8 þ zwt8 2 þ zwt2 1 þ zwt1 0 þ zwt0,

the regression coefficients for the five incremental changes in body weight z-scores in Change Score

- Model 1 are those in Change Score Model 2 plus the regression coefficient for zwt19 in Change Score
- Model 2, which is 2.58; and the regression coefficient for zwt0 in Change Score Model 1 is the same as that for zwt19 in Change Score Model 2.


This model is a re-parameterization of the lifecourse plot model,24 and thus the same advantages and disadvantages apply. However, the weight changes are likely to be less correlated than the actual weights, and thus the problem of collinearity is again at least partially resolved. To include all the incremental changes, birth size and body size in one model requires special statistical methodology, such as partial least squares regression. A detailed explanation of how partial least squares regression may be applied to lifecourse epidemiology is beyond the scope of this review, and we refer readers to our previous studies.26–28

## Multilevel and latent growth curve modelling

There are two approaches to estimating the effects of growth at different phases on health status in later life. A two-stage approach may be adopted by first estimating changes in body size or growth velocity in different growth phases during the lifecourse; health outcomes in later life are then regressed on these estimated growth variables.34–36 Alternatively, we can estimate the growth trajectories and their effects on later health outcomes in the same model.

Both one-stage and two-stage approaches could use multilevel or latent variable methods to model the growth trajectories.

Multilevel models (MLM), also known as randomeffects models or mixed models, can be used to analyse longitudinal data: the repeated measurements are treated as ‘level-one’ variables clustered within subjects treated as ‘level-two’ variables.29–33 Non-linear growth, different phases of growth, and complex level-1 variation or autocorrelation, can be included in such models.31

The growth trajectory model can also be estimated under the statistical framework of latent growth curve modelling (LGCM) which is a special type of structural equation model for longitudinal data analysis.29,30 Similarly to the multivariate MLM, the LGCM can also model jointly the association between the latent growth factors and distal outcome(s), such as SBP. In multilevel models the longitudinal data are in the long format, i.e. the six body weights between birth and age 19 years are treated as repeated measurements and stacked in one column, whereas in LGCM the six body weights are treated as six different variables.

In LGCM, the baseline body weight and change in weights are estimated by two latent variables denoted, for example, as F1 and F2 respectively, whose means are estimated as part of fixed effects and variances as random effects in MLM. The factor loadings for the six body weights on F1 are all unity and, as a result, F1 becomes the estimated baseline body weight. If the factor loadings for the six body weights on F2 are specified by the chronological ages when those weights were measured, F2 is interpreted as the estimated growth in weight per year since birth to age 19 years. One advantage of LGCM is that the first and the last factor loadings can be fixed to be 0 and 19, respectively, whereas the other factor loadings are freely estimated.29 If the growth is nearly linear, the estimated factor loadings should be close to the chronological ages; otherwise they reflect the different growth velocities throughout the lifecourse.

As Figure 1 clearly indicates, growth in body weight does not follow a linear pattern and we therefore estimate a nonlinear growth model by freeing the factor loadings of the middle four body weights on F2. The four factor loadings estimated by the nonlinear model are 1.962, 2.649, 6.663 and 16.561, for weight at ages 1, 2, 8 and 15 years, respectively. This indicates that the growth velocity between birth and age 1 year is about twice as fast as the overall average, and weight gain then becomes much slower between ages 1 and 8 years, greater between ages 8 and 15 years and slows again after age 15 years. Note that by freeing the factor loadings, the growth curve has been linearized, and the mean of F2 estimates the average weight gain per unit of time. Therefore, the association between F2 and SBP is the association between growth velocity in weight

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

(or overall weight gain) and SBP. The associations between F1 (birthweight) and F2 (growth velocity) with SBP are 4.94mmHg/kg (95% CI: 7.72 to 2.15) and 8.41mmHgkg 1yr 1(95% CI: 6.63 to 10.19), respectively. However, it should be noted that these associations are mutually adjusted, i.e. both F1 and F2 are included in the model for SBP. Thus, the large negative association between birthweight and later SBP requires careful interpretation as it is conditioned on subsequent growth.

LGCM and MLM can be used to estimate the effects of growth in different periods of the lifecourse on the health outcomes in later life.24 For instance, to estimate the effect of early (between birth and age 2 years) and later (between ages 2 to 19 years) growth in body weight on SBP, we set up three latent variables in the model: the intercept, the growth in body weight between birth and age 2 years, and the growth between age 2 to age 19 years. This model estimates different linear weight gain velocities between birth and age 2 years, and between ages 2 and 19 years. However, as the assumption of linear growth trend is unlikely to be correct, we free the factor loading of Weight1, Weight8 and Weight15. The factor loading of Weight1 on F2 is 1.48, indicating the growth in weight is greater in the 1st and the 2nd year. The factor loadings of Weight8 and Weight15 on F3 are 4.17 and 14.47, respectively, indicating that the growth velocity in weight between ages 8 and 15 years is greater than that between ages 2 and 8 years and between ages 15 and 19 years. Whereas gain in body weight between ages 2 and 19 years has a positive association with SBP (8.109, 95% CI: 6.43 to 9.78), the association with weight gain between birth and age 2 years is small and negative (-0.674, 95% CI: 2.20 to 0.85), and birthweight has a negative association with SBP (-2.115, 95% CI: 4.50 to

0.18). More details on the results from LGCM can be found in Supplementary data available at IJE online.

Although using LGCM to estimate the effects of growth on later outcomes is more flexible than multiple regression, it also has several disadvantages. First, the number of latent variables for growth in the different phases of the lifecourse is limited by the number of body size measurements. How these phases are demarcated needs guidance from biological theory. Second, measurements of body size need to be made at similar ages for the entire cohort in LGCM (although not for the equivalent MLM).When the number of repeated measurements is large, it becomes possible to use complex semi-parametric or non-parametric functions, such as spline functions,33–35 to model individual growth trajectories within the framework of multilevel modelling, though most commercial software packages have not yet implemented such facilities.

## Growth mixture models

Both MLM and LCGM assume that all individuals follow the same basic pattern of growth with random variation about that pattern. However, there may be subgroups within the population showing different patterns of growth. Two methods can identify trajectories for subgroups: group-based modelling37–39 and growth mixture modelling.40,41 In group-based modelling, whereas different classes have different growth trajectories, subjects within each class are assumed to have identical intercepts (i.e. baseline values) and slopes (i.e. trajectories).39,41 In contrast, in growth mixture modelling, within-class variations are allowed in the estimation of class memberships, i.e. within each class there may be variation in growth trajectories.41 Group-based modelling can be considered a special case of growth mixture modelling, where all within-class variations are constrained to be zero. Different model specifications of the within-class random structure can lead to very different models derived in terms of the ‘best’ number of growth mixtures, their size and composition.

To illustrate growth mixture modelling, we use the macro PROC TRAJ in the statistical software SAS (version 9.1.3)38 to analyse the body weight z-scores. We fit a quartic curve for each group and start with a 2-class model and gradually increase the number of classes.

Figure 5 shows the growth curves for each class in different models. There are several statistical indices for selecting the ‘best’ model,38–42, e.g. Akaike Information Criteria (AIC) and Bayesian Information Criteria (BIC). Both capture model parsimony, though in practice their usefulness is sometimes limited. For instance, Table 3 shows the results of 2- to 5-class models. Both AIC and BIC values reduce with the number of classes, and they are still reducing when the number of classes goes beyond six. However, as the number of subjects in some classes becomes small (less than 5%), we feel it may not be sensible to increase the number of classes.37–41 Consequently, it is not possible to use either index to determine the most parsimonious model. Furthermore, when the number of classes increases, the interpretation of each class in different models becomes less straightforward; researchers need to draw a balance between model complexity and model interpretability.42 For our Cebu cohort example, we viewed the 3-class model ‘best’ in terms of this balance. In this model, class-1 (53%)comprised men who were born small and remained small, and class-2 (44%) comprised men who were born large and remained large; whereas class-3(about 3%) comprised men who were born larger than average and who became even larger after age 8 years. The average SBP in class-1, class-2 and class-3 was 105.0, 107.26 and 117.83 mmHg, respectively, and differences between class-2/class-3 and class-1 are: 2.26mmHg, 95%CI: 0.93 to 3.60; 12.83 mmHg, 95%CI: 8.90 to 16.77.

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

![image 5](<A critical evaluation of statistical approaches to examining the role of growth trajectories in the developmental origins of health and disease_images/imageFile5.png>)

- Figure 5 Weight trajectories identified by group-based models with different numbers of classes


Growth mixture modelling also has several disadvantages. As with LGCM, measurements of body size need to be made at similar ages for the entire cohort. Model specifications are also sometimes arbitrary and the selection of the optimal model is not always straightforward, as shown in our example. In the analysis illustrated, there is no within-class variation for the estimated growth curves, but if withinclass variation is allowed, the growth trajectories would likely look very different.42,43 This emphasizes the importance of specifying the underlying random structure in these types of models, and this should be informed, wherever possible, by an understanding of the biological underlying cause of variation.44 Furthermore, distinctive growth curves such as those in Figure 5 are average patterns from which observed curves may deviate greatly. Finally, the identified trajectories may not always match those hypothesized by

researchers; for instance, in our Cebu example we sought to test whether people with an early catchup growth pattern had a higher risk of developing higher blood pressure in later life, yet no such pattern was identified by GMM. Although we found that men in class-3 (about 3%), who were born larger than average and who also became even larger after age 8 years, had a higher average blood pressure, this does not tell us when or how these differences could have arisen.

## Concluding remarks

Our analyses of the Cebu cohort shows that both simple and more sophisticated approaches can yield some similar conclusions, i.e. that weight, or weight gain in late adolescence, has a fairly large, positive

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

Table 3 Average SBP in each class in different group-based models

95% CI for difference in SBP

Difference in SBPa

Mean SBP SD SBP No. of subjects

- 2-Class Model (BIC¼ 7464.91, AIC¼ 7435.71)

- Class-1 105.38 10.45 666
- Class-2 108.60 10.51 294 3.22 (1.78, 4.66)


- 3-Class Model (BIC¼ 7038.07, AIC¼ 6994.27)

- Class-1 105.00 10.48 511
- Class-2 107.27 10.11 421 2.26 (0.93, 3.60)
- Class-3 117.83 10.81 28 12.83 (8.90, 16.77)


- 4-Class Model (BIC¼ 6807.09, AIC¼ 6748.68)

- Class-1 104.54 10.06 343
- Class-2 106.22 10.26 495 1.68 (0.27, 3.10)
- Class-3 111.55 11.11 116 7.01 (4.85, 9.18)
- Class-4 122.89 8.12 6 18.35 (10.04, 26.66)


- 5-Class Model (BIC¼ 6663.36, AIC¼ 6590.36)


- Class-1 104.41 10.35 200
- Class-2 105.91 10.33 485 1.49 (-0.21, 3.20)
- Class-3 107.28 9.99 229 2.87 (0.91, 4.84)
- Class-4 114.05 12.38 40 9.64 (6.13, 13.15)
- Class-5 122.89 8.12 6 18.48 (10.07, 26.88) aThe reference class is Class-1 in each model.


association with blood pressure in later life. However, there are also differences in conclusions about the association between early growth and later blood pressure. Table 4 provides a summary of some of the advantages and disadvantages of all approaches evaluated in this study. Choice of approach will depend on the hypothesis to be tested (e.g. whether the hypothesis is about associations between size or changes in size and the future outcome) and study design. Where a study has a small number of measures, at defined time-periods (e.g. weight at birth, 1 year and 5 years), the simple methods (e.g. regressing outcome on each weight measure adjusted for previous weight) are likely to be sufficient. For a study with a larger number of measures, and/or different measurement occasions across individuals, multilevel models would be a more suitable approach. Methods which condition on all periods simultaneously (e.g. lifecourse models and plots and path analysis) require careful interpretation if they are not to lead to erroneous conclusions, and should be avoided. Easier to interpret are models that condition only on earlier changes, though models with multiple change points considered simultaneously still yield overall interpretational difficulties. The latent class models can only be interpreted in terms of differences in the entire trajectory rather than specific periods, and should not be used if there are specific hypotheses

about the association between trajectory and outcome, as it is unlikely that the classes identified will correspond exactly to the hypothesis specified.

The lifecourse models (and their associated plots) identified negative associations between some early weight measures and later blood pressure, with wide confidence intervals (including no effect) for all but the last weight measure. In contrast, the inclusion of birthweight and all subsequent weight changes in one model led to the conclusion that birthweight and all subsequent weight changes are positively related to later blood pressure, with the size of the association increasing gradually with age. The latent growth model concluded that birthweight had a large, negative association with SBP, whereas growth velocity had a positive association. For all these methods, care is needed in the interpretation of associations that condition on later (as well as previous) changes. Use of GMM did not identify any classes that demonstrated different initial growth patterns that yielded the same final weight in our chosen 3-class model, and therefore could not be used to examine specific hypotheses about the associations between early growth and later blood pressure. Class-2 and class-3 in the 5-class model did seem to show the same final weight with some differences in earlier life growth trajectories, but their difference in the blood pressure was small (Table 3).

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

Table 4 Summary of advantages and disadvantages of statistical approaches discussed in this review

Advantages Disadvantages Tracing the z-scores Simple, straightforward to implement Just a connection of a series of simple associations at dif-

ferent ages No confidence intervals for the observed trajectories Continuous outcomes have to be dichotomized Body size needs to be measured more or less at the same age

for all cohort members Interpretation could be subject to statistical artefact

Lifecourse plot Simple Collinearity amongst body size measurements may cause problems with interpretation due to wide confidence intervals

Body size needs to be measured more or less at the same age for all cohort members Interpretation not straightforward as conditioning on later

measures. Lifecourse path analysis Causal relations explicitly specified

Body size needs to be measured more or less at the same age for all cohort members Correct causal relations and models are not always easy to identify

Multiple outcomes can be analysed simultaneously

Collinearity can still be a problem Conditional body size analysis Conditional body size variables are

Body size needs to be measured more or less at the same age for all cohort members Equivalent to a series of multiple regression models with

always statistically independent Simple, straightforward to implement and interpret

body size measures included as covariates one by one Though conditional body size variables are always statistically independent, their interpretation is similar to the tracing the z-scores or the lifecourse plot.

Regression with change scores Simple, straightforward to interpret More than one model is possible but interpretations are different Body size needs to be measured more or less at the same age

for all cohort members Is a re-parameterization of the lifecourse plot model Interpretation not straightforward as conditioning on later

measures.

Multilevel modelling Body size does not need to be measured at the same ages for all cohort members

A two-stage approach may be required to test the association between growth and binary health outcomes in later life or specialist software packages such as Mplus are required to undertake this in one step

Estimates individual trajectories Can model nonlinear growth curves

Parameterizing the trajectory may be done in many different ways, and may lead to differing interpretations

Latent growth curve modelling Estimates individual trajectories Can model nonlinear growth curves Straightforward to test the association

Body size needs to be measured more or less at the same age for all cohort members Parameterizing the trajectory may be done in many different ways, and may lead to differing interpretations

between growth and health outcomes in later life in one stage

Correct causal relationships are not always easy to identify as associations with outcome are conditioned on all latent variables

Straightforward to incorporate latent variables

Growth mixture modelling Estimate individual trajectories Identify distinctive subgroups in the

Computer-intensive technique Body size needs to be measured more or less at the same age

population Can model nonlinear growth curves Straightforward to test the association

for all cohort members Choosing the correct model (number of classes) is not always straightforward Class composition (hence interpretation) varies with differ-

between growth and health outcomes in later life in one stage

ent parameterizations of the random variation in the data The interpretation of the classes may not be straightforward The model is likely to identify subclasses of the population

Straightforward to incorporate latent variables

whether or not they exist, and whether or not they are meaningful

Finally, we make a few general comments on the selection and comparisons to be made among the different approaches. First, body size and growth cannot be separated conceptually, because growth is derived from repeated measures of body size. For instance,

when weight at age 19 years is related to the outcome and previous weights are not, this does not necessarily mean that weight on the 19th birthday matters, as weight at age 19 years is also the sum of all previous weight gains and birthweight. Second, to identify

Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

critical sensitive phases throughout the lifecourse may require several statistical approaches to identify growth trajectory features related to adverse health outcomes in later life. Third, we used body weight z-scores trajectories for some approaches and raw weight scores for others. As z-scores measure the relative body size or ranking of one individual in the sample population, changes in z-scores have a different interpretation from changes in raw weights. One potential advantage of using z-scores for weight instead of weight is that variance of weight increases rapidly with age in the first two decades of life. If the research question is, however, to investigate the association between weight change in adulthood (where the variance remains reasonably stable) and health outcomes in old age, raw body weight would be more appropriate.

In conclusion, each of the approaches discussed has their limitations and we may need a combination of these approaches to unravel the complexities we observe in lifecourse research. The exact choice of method depends upon the nature of the available data and the specific research question(s) of interest; model parameterization then depends upon both construct and context of the data under evaluation. However, any method which explicitly or implicitly conditions on the future needs very careful interpretation and should be avoided in general.

## Supplementary Data

Supplementary data is available at IJE online.

## Funding

This project was partly funded by a grant from the UK Medical Research Council (G1000726: Methods for modelling repeated measures in a lifecourse framework). The authors’ work was independent of the funding sources.

## Acknowledgement

The authors would like to thank Laura Howe at the University of Bristol, UK, for her helpful comments on an earlier version of this manuscript. Conflict of interest: None declared.

## References

- 1 Barker DJP. The fetal origins of hypertension. J Hypertens Suppl 1996;14:S117–20.
- 2 Barker DJP, Winter PD, Osmond C, Margetts B, Simmonds SJ. Weight in infancy and death from ischaemic heart disease. Lancet 1989;2:577–80.


- 3 Barker DJP. The fetal origins of type 2 diabetes mellitus. Ann Intern Med 1999;130:322–24.
- 4 Huxley RR, Shiell AW, Law CM. The role of size at birth and postnatal catch-up growth in determining systolic blood pressure: a systematic review of the literature. J Hypertens 2000;18:815–31.
- 5 Leon DA, Koupilova I, Lithell HO et al; Failure to realise growth potential in utero and adult obesity in relation to blood pressure in 50 year old Swedish men. BMJ 1996; 312:401–06.
- 6 Barker DJP. Developmental origins of adult health and disease. J Epidemiol Community Health 2004;58:114–15.
- 7 Barker DJP, Osmond C, Forsen TJ, Kajante E, Eriksson JG. Trajectories of growth among children who have coronary events as adults. N Engl J Med 2005;353: 1802–09.
- 8 Forsen T, Osmond C, Eriksson JG, Barker DJP. Growth of girls who later develop coronary heart disease. Heart 2004; 90:20–24.
- 9 Eriksson JG, Forsen T, Tuomilehto J, Osmond C, Barker DJP. Fetal and childhood growth and hypertension in adult life. Hypertension 2000;36:790–94.
- 10 Bhargava SK, Sachdev HS, Fall CHD et al; Relation of serial changes in childhood body-mass index to impaired glucose tolerance in young adulthood. N Engl J Med 2004; 350:865–75.
- 11 Eriksson JG, Forsen TJ, Osmond C, Barker DJ. Pathways of infant and childhood growth that lead to type 2 diabetes. Diabetes Care 2003;26: 3006–10.
- 12 Barker DJP. Osmond C, Kanjatie E, Eriksson JG. Growth and chronic disease: findings in the Helsinki Birth Cohort. Ann Hum Biol 2009;36: 445–58.
- 13 Adair L. Size at birth and growth trajectories to young adulthood. Am J Hum Biol 2007;19:327–37.
- 14 Dahly DL, Adair LS, Bollen KA. A structural equation model of the developmental origins of blood pressure. Int J Epidemiol 2009;38:538–48.
- 15 Tu YK, Law GR. Re-examining the associations between family backgrounds and children’s cognitive developments in early ages. Early Child Dev Care. 2010;180: 1243–52.
- 16 Cole TJ. Modeling Postnatal Exposures and Their Interactions with Birth Size. J Nutr 2004;134:201–04.
- 17 Cole TJ. The life course plot in life course analysis. In: Pickles A, Maughan B, Wadsworth M (eds). Epidemiological Methods in Life Course Research. Oxford: Oxford University Press, 2007.
- 18 Gamborg M, Andersen PK, Baker JL et al; Life course path analysis of birth weight, childhood growth, and adult systolic blood pressure. Am J Epidemiol 2009;169:1167–78.
- 19 Gamborg M, Jensen GB, Sorensen TIA, Andersen PK. Dynamic Path Analysis in Life-Course Epidemiology. Am J Epidemiol 2011;173:1131–39.
- 20 Kline RB. Principles and Practice of Structural Equation Modeling. New York: Guilford Press, 2011.
- 21 Tu YK. Commentary: Is structural equation modelling a step forward for epidemiologists? Int J Epidemiol 2009;38: 549–51.
- 22 Menezes AM, Hallal PC, Dumith SC et al; Adolescent blood pressure, body mass index and skin folds: sorting out the effects of early weight and length gains. J Epidemiol Community Health 2011;66:149–54.
- 23 Martorell R, Horta BL, Adair LS et al; Consortium on Health Orientated Research in Transitional Societies Group. Weight gain in the first two years of life is an


Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

important predictor of schooling outcomes in pooled analyses from five birth cohorts from low- and middleincome countries. J Nutr 2010;140:348–54.

- 24 De Stavola BL, Nitsch D, dos Santos Silva I et al; Statistical issues in life course epidemiology. Am J Epidemiol 2006;163:84–96.
- 25 Skidmore PM, Hardy RJ, Kuh DJ, Langenberg C, Wadsworth ME. Life course body size and lipid levels at 53 years in a British birth cohort. J Epidemiol Community Health 2007;61:215–20.
- 26 Tu YK, Woolston A, Baxter PD, Gilthorpe MS. Assessing the Impact of Body Sizes Throughout the Lifecourse on Blood Pressure in Later Life Using Partial Least Squares Regression. Epidemiology 2010;21:440–48.
- 27 Tu YK, Davey Smith G, Gilthorpe MS. A New Approach to Age-Period-Cohort Analysis Using Partial Least Squares Regression: The Trend in Blood Pressure in the Glasgow Alumni Cohort. PLoS One 2011;6: e19401.
- 28 Tu YK, Chien KL, Burley V, Gilthorpe MS. Unravelling the effects of age, period and cohort on metabolic syndrome components in a Taiwanese population using partial least squares regression. BMC Med Res Methodol 2011;11:82.
- 29 Bollen K, Curran P. Latent Curve Models. New York: Wiley, 2006.
- 30 Duncan TE, Duncan SC, Strycker LA. An Introduction to Latent Variable Growth Curve Modeling. 2nd edn. Mahwah, NJ: Laurence Erlbaum, 2006.
- 31 Goldstein H. Multilevel Statistical Models. 2nd edn. New York: Wiley, 1995.
- 32 Hox J. Multilevel analysis. Mahwah, NJ: Laurence Erlbaum Associates Inc, 2002.
- 33 Tu YK, Gilthorpe MS. Statistical Thinking in Epidemiology. Boca Raton, FL: Chapman & Hall, 2012.
- 34 Tilling K, Davies NM, Nicoli E et al; Associations of growth trajectories in infancy and early childhood with later childhood outcomes. Am J Clin Nutr 2011; 94(Suppl 6):1808s–13s.
- 35 Howe LD, Tilling K, Benfield L et al; Changes in Ponderal Index and Body Mass Index across Childhood and Their Associations with Fat Mass and Cardiovascular Risk


- Factors at Age 15. PLoS One 2010;5: e15186; doi:10.1371/journal.pone.0015186.
- 36 Tilling K, Davies N, Windmeijer F et al; Promotion of Breastfeeding Intervention Trial (PROBIT) study group. Is infant weight associated with childhood blood pressure? Analysis of the Promotion of Breastfeeding Intervention Trial (PROBIT) cohort. Int J Epidemiol 2011; 40:1227–37.
- 37 Nagin, Daniel S, Tremblay Richard E. Analyzing developmental trajectories of distinct but related behaviors: A group-based method. Psychol Methods 2001; 6:18–34.
- 38 Jones BL, Nagin DS, Roeder K. A SAS procedure based on mixture models for estimating developmental trajectories. Sociol Method Res 2001;29:374–93.
- 39 Nagin DS. Group-based Modelling of Development. Cambridge, MA: Harvard University Press, 2005.
- 40 Muthe´n B. Second-generation structural equation modeling with a combination of categorical and continuous latent variables: New opportunities for latent class/latent growth modeling. In: Collins LM, Sayer A (eds). New Methods for the Analysis of Change. Washington, DC: American Psychological Association, 2001.
- 41 Kreuter F, Muthe´n B. Analyzing Criminal Trajectory Profiles: Bridging Multilevel and Group-based Approaches Using Growth Mixture Modeling. J Quant Criminol 2008;24:1–31.
- 42 Peugh J, Fan X. How Well Does Growth Mixture Modeling Identify Heterogeneous Growth Trajectories? A Simulation Study Examining GMM’s Performance Characteristics. Struct Equ Modeling 2012;19:204–26.
- 43 McIntosh CN. Pitfalls in subgroup analysis based on growth mixture models: a commentary on van Leeuwen et al.(2012). Qual Life Res 2013, doi; 10.1007/s11136-0130385-x.
- 44 Gilthorpe MS, Frydenberg M, Cheng Y, Baelum V. Modelling count data with excessive zeros: The need for class prediction in zero-inflated models and the issue of data generation in choosing between zero-inflated and generic mixture models for dental caries data. Stat Med 2009;28:3539–53.


Downloadedfromhttps://academic.oup.com/ije/article/42/5/1327/622212byHarvardUniversityLibraryuseron02May2026

