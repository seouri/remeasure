1234567890();,:

## www.nature.com/ijo International Journal of Obesity

### ARTICLE OPEN

Pediatrics

# Prospective prediction of childhood body mass index trajectories using multi-task Gaussian processes

Arthur Leroy 1,14, Varsha Gupta2,3,14, Mya Thway Tint 2, Delicia Shu Qin Ooi 4, Fabian Yap5,6, Ngee Lek5,6, Keith M. Godfrey 7, Yap Seng Chong2,8, Yung Seng Lee 2,4,9, Johan G. Eriksson2,8,10,11, Mauricio A. Álvarez1,12, Navin Michael2,15 and Dennis Wang 2,3,12,13,15

✉

© The Author(s) 2024, corrected publication 2024

BACKGROUND: Body mass index (BMI) trajectories have been used to assess the growth of children with respect to their peers, and to anticipate future obesity and disease risk. While retrospective BMI trajectories have been actively studied, models to prospectively predict continuous BMI trajectories have not been investigated.

MATERIALS AND METHODS: Using longitudinal BMI measurements between birth and age 10 y from a mother-offspring cohort, we leveraged a multi-task Gaussian process approach to develop and evaluate a uniﬁed framework for modeling, clustering, and prospective prediction of BMI trajectories. We compared its sensitivity to missing values in the longitudinal follow-up of children, compared its prediction performance to cubic B-spline and multilevel Jenss-Bayley models, and used prospectively predicted BMI trajectories to assess the probability of future BMIs crossing the clinical cutoffs for obesity.

RESULTS: MagmaClust identiﬁed 5 distinct patterns of BMI trajectories between 0 to 10 y. The method outperformed both cubic B-spline and multilevel Jenss-Bayley models in the accuracy of retrospective BMI trajectories while being more robust to missing data (up to 90%). It was also better at prospectively forecasting BMI trajectories of children for periods ranging from 2 to 8 years into the future, using historic BMI data. Given BMI data between birth and age 2 years, prediction of overweight/obesity status at age 10 years, as computed from MagmaClust’s predictions exhibited high speciﬁcity (0.94), negative predictive value (0.89), and accuracy (0.86). The accuracy, sensitivity, and positive predictive value of predictions increased as BMI data from additional time points were utilized for prediction. CONCLUSION: MagmaClust provides a uniﬁed, probabilistic, non-parametric framework to model, cluster, and prospectively predict childhood BMI trajectories and overweight/obesity risk. The proposed method offers a convenient tool for clinicians to monitor BMI growth in children, allowing them to prospectively identify children with high predicted overweight/obesity risk and implement timely interventions.

International Journal of Obesity (2025) 49:340–347; https://doi.org/10.1038/s41366-024-01679-0

INTRODUCTION

The increasing global prevalence of childhood obesity represents a major concern, given its strong links to comorbidities like cardiometabolic disease as well as psychopathologies [1, 2]. Not all children with obesity have adverse cardiometabolic or mental health [3, 4], and not all children who develop these conditions

get obesity. This suggests that there might be aberrant growth patterns even within the normal weight range that increase risks for adverse cardiometabolic or mental health. Periods of accelerated weight gain in childhood can result in atherosclerotic changes and increased body fat percentage, which can persist even if the child reverts to normal weight later in life [5, 6].

1Department of Computer Science, The University of Manchester, Manchester, UK. 2Institute for Human Development and Potential, Agency for Science Technology and Research (A*STAR), Singapore, Republic of Singapore. 3Bioinformatics Institute, Agency for Science Technology and Research (A*STAR), Singapore, Republic of Singapore. 4Department of Paediatrics, Yong Loo Lin School of Medicine, National University of Singapore, Singapore, Republic of Singapore. 5Department of Paediatrics, KK Women’s and Children’s Hospital, Singapore, Republic of Singapore. 6Duke-NUS Medical School, Singapore, Republic of Singapore. 7MRC Lifecourse Epidemiology Centre and NIHR Southampton Biomedical Research Centre, University of Southampton and University Hospital Southampton NHS Foundation Trust, Southampton, UK. 8Department of Obstetrics and Gynaecology and Human Potential Translational Research Programme, Yong Loo Lin School of Medicine, National University of Singapore, Singapore, Republic of Singapore. 9Division of Paediatric Endocrinology, Department of Paediatrics, Khoo Teck Puat-National University Children’s Medical Institute, National University Hospital, National University Health System, Singapore, Republic of Singapore. 10Department of General Practice and Primary Health Care, University of Helsinki, Helsinki, Finland. 11Folkhälsan Research Center, Helsinki, Finland. 12Department of Computer Science, University of Shefﬁeld, Shefﬁeld, UK. 13National Heart and Lung Institute, Imperial College London, London, UK. 14These authors contributed equally: Arthur Leroy, Varsha Gupta. 15These authors jointly supervised this work: Navin Michael, Dennis Wang.

✉email: dennis_wang@sics.a-star.edu.sg

Received: 9 June 2024 Revised: 30 October 2024 Accepted: 4 November 2024 Published online: 15 November 2024

Therefore, tracking and characterizing longitudinal childhood growth can provide a more reﬁned picture of the predispositions for adverse health outcomes.

Parents and pediatricians are often interested in the retrospective question of how a child has grown relative to his/her peers. This is often assessed using simplistic approaches like plotting growth assessments on childhood growth charts [7]. While such approaches are useful for detecting aberrant growth trends (e.g., growth faltering/stunting) that require prompt interventions, these provide a crude or misleading picture of how an individual child will grow in the future. While there has been a large body of literature that has focused on retrospective growth assessments using growth clustering [8–12] and individual body mass index (BMI) trajectory modeling [12–17], not many studies have systematically investigated whether continuous BMI trajectories can be prospectively forecasted from prior BMI assessments. Knowing this would be useful for evaluating if/when a child could be expected to cross standard overweight/obesity cut-offs and for prioritizing children for preventive interventions. A child’s BMI trajectory can also reveal more subtle features of growth like growth velocities [18] and alterations in milestones like infancy BMI peak and adiposity rebound, which have been linked to later obesity risk.

In the current work, we propose to use a Gaussian processes (GP) algorithm called MagmaClust [19, 20] for modeling, clustering and prospectively forecasting childhood BMI trajectories. A GP is a random process over functions (or curves) that is characterized by a speciﬁc mean and covariance function [21]. GP-based methods offer a probabilistic non-parametric framework by deﬁning a prior distribution over functions, allowing us to capture complex nonlinear relationships while accounting for uncertainty. Observed individual BMI trajectories can be thought of as speciﬁc instantiations of different GPs.

In this study, we extended MagmaClust to perform multiple tasks of learning by sharing information across individual BMI trajectories while clustering the trajectories into distinct patterns. We show that it can perform uncertainty quantiﬁcation of BMI trajectories from a cohort of children followed up from ages 0–10 years. The algorithm focuses on predicting probabilities for missing BMI values at time points when individuals were not measured, outperforming existing methods. When given historic BMI measurements, MagmaClust is able to prospectively compute the probability of acquiring overweight/obesity at future ages.

MATERIALS AND METHODS Cohort dataset

Longitudinal height and weight data between birth and age 10 y were available for 1177 children from the Growing Up in Singapore Towards healthy Outcomes (GUSTO) cohort [22]. Precise data availability at each of the 20 timepoints between birth and age 10 y are provided in Table S1. Calibrated weighing scales were used for measuring weight (SECA 334 up to 18 m and SECA 803 weighing scale beyond 18 m). Recumbent length (SECA 210 mobile measuring mat) was used to compute BMI until age 2, while standing height (SECA 213 Portable Stadiometer) was used for computing BMI beyond age 2. The growth data of 1177 children were randomly split into a training set (N = 600) and a test set (N = 577).

Model ﬁtting

The training set was used to train the MagmaClust model [19, 20]. The test set was used to calculate the evaluation metrics for different experimental conditions and for reference comparisons of MagmaClust with two legacy growth curve ﬁtting approaches: multilevel Jenss-Bayley [13, 15, 23, 24] and cubic B-splines [14, 16, 17]. Spline modeling was performed using the smooth.spline function of the stat R package. JenssBayley weight and height models were hierarchically ﬁtted with a nonlinear mixed effect model using the saemix package in R, which was then used to compute the BMI trajectories. Training and prediction with

MagmaClust were performed using the dedicated R package MagmaClustR, where all GP kernels were set to be squared exponentiated (SE). Additional details on the choice of kernel and hyper-parameters can be found in the Supplementary Materials. The estimation of cubic B-splines requires at least 4 observed time points (534 test data), whereas in Jenss Bailey, we used a total of 551 test data with at least 2 observations per individual (out of 577 test data with at least 1 observed timepoint used for MagmaClust).

BMI prediction

The BMI prediction experiment comprised of two separate tasks: missing data reconstruction and forecasting. Missing data reconstruction corresponds to randomly removing varying percentages of the observed data for each individual and using the remaining points to recover the missing BMI values. For forecasting, we retained all points observed before speciﬁc age thresholds (ranging from 2 y to 8 y) to predict BMI for all testing points after this threshold until age 10y. While evaluation metrics are computed only from predicted data points in both cases, graphical illustrations of trajectories are displayed as continuous BMI curves between ages 0 to 10 y. The evaluation of performances was assessed through mean squared errors (MSE) and uncertainty quantiﬁcation was performed using the Weighted 95% Credible Interval Coverage (WCIC95) metric as described in the Supplementary Materials.

RESULTS Clusters of BMI trajectories in early childhood

We applied MagmaClust to longitudinal BMI data collected from children ages 0 to 10 years. The cluster-speciﬁc mean BMI trends with increasing number of clusters (K) are illustrated in Fig. 1A–D. We evaluated up to K = 10 clusters. However, for K ≥ 6, the additional clusters were empty or contained very few (generally only one) individuals. This suggested that 5 clusters (Fig. 1D) were sufﬁcient to capture the main trends present in the current dataset. When the number of clusters increases from 2 (Fig. 1A) to 5 (Fig. 1D), we observed that while the upper cluster pattern, growing towards BMI values of 26 kg/m2 at age 10 y (Fig. 1A), remained roughly similar, the other cluster seemed to split into more speciﬁc sub-clusters (Fig. 1B–D). An infant BMI peak (with varying peak intensities) was observed at around 9 months for all clusters, with distinctive BMI patterns after infancy (Fig. 1D). While we observed some of the cluster-speciﬁc mean trajectories converged to similar patterns between 3–10 y, they had very distinct trajectories during infancy (age 0–1 y) with different BMI peak levels. Since this is a critical time of child development and there may be important features (eg. different rates of growth acceleration/deceleration) relating to future health outcomes, we chose to retain them as distinct clusters. Figure 1E depicts the mean curves associated with each of the 5 clusters, overlaid on top of the training dataset. Although underlying characteristic patterns can be captured through each cluster’s mean process, note that a continuum of data points exists in between the clusters.

Comparison of MagmaClust, cubic B-splines and Jenss-Bayley methods for missing data reconstruction

For a randomly chosen individual, we show the BMI trajectories ﬁtted using the MagmaClust, cubic B-splines and Jenss-Bayley using the complete set of BMI measurements in Fig. 2 (1st row) and in different sets of 50% randomly under-sampled BMI measurements in Fig. 2 (2nd to 4th rows). In all rows of Fig. 2A, we observed that the curves ﬁtted with B-splines dramatically vary depending on which speciﬁc points are missing. On the other hand, Jenss-Bayley and MagmaClust predictions remain relatively robust regardless of the observed subset (Fig. 2B, C). Regardless of missingness patterns, MagmaClust correctly recovered the mean trend. Uncertainty of predictions (95% credible interval) was shown by displaying multiple trajectories from the posterior distribution (Fig. 2C).

A B

###### E

Cluster size 122 478

Cluster size

25.0

|![image 1](<Prospective prediction of childhood body mass index trajectories using multi-task Gaussian processes_images/imageFile1.png>)<br><br>Cluster size<br><br>![image 2](<Prospective prediction of childhood body mass index trajectories using multi-task Gaussian processes_images/imageFile2.png>)<br><br>![image 3](<Prospective prediction of childhood body mass index trajectories using multi-task Gaussian processes_images/imageFile3.png>)<br><br>![image 4](<Prospective prediction of childhood body mass index trajectories using multi-task Gaussian processes_images/imageFile4.png>)<br><br>![image 5](<Prospective prediction of childhood body mass index trajectories using multi-task Gaussian processes_images/imageFile5.png>)<br><br>44 77 89 124 266| | | | | |
|---|---|---|---|---|---|
| | | | | | |


73 241 286

24

22.5

20.0

BMI

BMI

20

17.5

30

16

15.0

12.5

12

0.0 2.5 5.0 7.5 10.0

0.0 2.5 5.0 7.5 10.0

Age (years)

Age (years)

C D

BMI

Cluster size 44 77 89 124 266

Cluster size 48 128 158 266

20

25

25

BMI

BMI

20

20

10

15

15

0.0 2.5 5.0 7.5 10.0

0.0 2.5 5.0 7.5 10.0

0.0 2.5 5.0 7.5 10.0

Age (years)

Age (years)

Age (years)

- Fig. 1 Cluster-speciﬁc mean BMI curves with increasing number of clusters. A K = 2, (B) K = 3, (C) K = 4, and (D) K = 5. E Mean BMI curves associated with K = 5 overlaid on observations from the training data set, colored according to their most probable cluster.


To assess the effect of the number of clusters on the performance of MagmaClust, we randomly removed 50% of the observations in all 577 individuals in the test set and used the remaining observations to compute predictions. The prediction performance with missing data for MagmaClust (from 2 to 5 clusters), Jenss-Bayley and B-splines in Table S2 show lower MSE for MagmaClust, irrespective of the number of clusters. The MSE of the 5-cluster MagmaClust model was, for instance, 24% lower than Jenss-Bayley and 79% lower than B-splines. Overall, the random effects methods (MagmaClust and multi-level Jenss-Bayley) exhibited better performance at missing data reconstruction than those merely relying on individual data (Fig. S1). In Table S3, we compared reconstruction performances of the 5-cluster MagmaClust model with Jenss-Bayley and B-splines when the proportion of missing data increased from 10% to 90%. Overall, MagmaClust’s errors only slightly increased (0.90 to 2.84) when we increased the missing data ratio. Conversely, while B-splines and Jenss-Bayley remained reasonably efﬁcient for low proportions (below 50%), they typically struggled as the missing data ratio increased. Concerningly, the number of computational runtime errors for splines started to rise dramatically above 50% of missing points.

Comparison of MagmaClust, Cubic B-splines, Jenss-Bayley methods for prospective forecasting of childhood BMI

Using BMI observations collected before different age thresholds (2 y, 3 y, 4 y, 5 y, and 6 y), we predicted the BMI trajectories till age 10 y. Table S4 shows the forecasting performances of MagmaClust, B-splines and Jenss-Bayley models on all testing individuals for a forecasting period going from the age threshold to age 10 y. The Jenss-Bayley model’s MSE was 1.62 times higher than MagmaClust when forecasting from ages 6 to 10 y. This error ratio increased to 3.26 when forecasting was performed using data from ages 2 to 10 y. The performance of splines was much worse, with 9-fold higher MSE for forecasting from ages 6 to 10 y and 86-fold higher MSE for ages 2 to 10 y when compared to MagmaClust. These ﬁndings highlight the unsuitability of splines in forecasting tasks, particularly for long-term forecasting. Overall, by identifying relevant patterns from early BMI measurements, MagmaClust demonstrated its ability to forecast probable trajectories accurately, even several years in advance.

For illustration in Fig. 3, we display the prediction results of MagmaClust and Jenss-Bayley for one random individual for 3 prediction ranges (ages 2 to 10 y, 4 to 10 y, and 6 to 10 y). An intuitive way to represent the time-varying uncertainty in the

trajectory predicted by MagmaClust is to draw and display multiple trajectories from the posterior distribution, as in Fig. S1 and Fig. 3A. We observed that MagmaClust’s forecasts provided an accurate mean trend for all three different prediction ranges, with additional data seeming to narrow the range of probable trajectories and prediction errors (Fig. 3B). In contrast, we observed that Jenss-Bayley predictions quickly diverged from testing values (Fig. 3C).

MagmaClust based tool to predict overweight/obesity in childhood using history of BMI growth

We leveraged MagmaClust’s BMI forecasts to assess the risk of overweight/obesity at age 10 y using BMI data observed up to different age thresholds. To identify overweight/obesity at age 10 y, we used the sex-speciﬁc 90th percentile from BMI reference data obtained from Singaporean children (BMI > 22 for girls and BMI > 22.8 for boys) [7]. Note that while we illustrate the use of the tool for predicting overweight/obesity status at age 10 y, the tool can be readily adapted for different weight thresholds and different ages. For each child, we generated 100,000 instantiations of probable trajectories from the predictive posterior distribution provided by MagmaClust to count the proportion of trajectories that crossed the overweight threshold at the age of 10 y. We represent in Fig. 4 an example of a random boy (A) and girl (B). In both cases, for the purpose of visualization, we display 100 probable trajectories (out of 100,000 probable trajectories of the same individual) predicted from ages 0 to 6 y and focus on the curves crossing the sex-speciﬁc overweight/obesity threshold. The ratio of the number of trajectory instantiations of a child crossing overweight threshold to the total number of trajectory instantiations of a child was deﬁned as the probability of overweight/ obesity for a given child. Although the mean trend of those predictions is below the overweight/obesity threshold, the probability of being overweight at age 10 y remains non-null (4% for the boy and 3% for the girl). Such a tool provides a valuable risk quantiﬁcation of undesirable events several years in advance by leveraging the well-calibrated uncertainty coming from MagmaClust results.

To evaluate the practical utility of our overweight probabilities, we compared the observed and predicted overweight status at age 10 y, using BMI data below different age thresholds (2 y, 4 y, 6 y, & 8 y). Within the 577 individuals in the test set, only 297 (148 girls, 149 boys) had BMI data at age 10. Among them, 40 children crossed overweight cutoff at age 10 y. In Fig. 5A, we show the

##### A B C

|12<br><br>14<br><br>16<br><br>18<br><br>20<br><br>0.0 2.5 5.0 7.5 10.0<br><br>Age (years)<br><br>BMI<br><br>observed data<br><br>missing data fitted Jenss-Bayley model|
|---|
|12<br><br>14<br><br>16<br><br>18<br><br>20<br><br>0.0 2.5 5.0 7.5 10.0<br><br>Age (years)<br><br>BMI|
|12<br><br>14<br><br>16<br><br>18<br><br>20<br><br>0.0 2.5 5.0 7.5 10.0<br><br>Age (years)<br><br>BMI|


20

20

observed data

observed data

missing data fitted B-splines model

missing data

No missing data

fitted instances of GP

18

18

mean instance of GP

BMI

BMI

BMI

16

16

14

14

12

0 3 6 9

0.0 2.5 5.0 7.5 10.0

Age (years)

Age (years)

|12<br><br>14<br><br>16<br><br>18<br><br>20<br><br>0 3 6 9<br><br>Age (years)<br><br>BMI|
|---|
|12<br><br>14<br><br>16<br><br>18<br><br>20<br><br>0 3 6 9<br><br>Age (years)<br><br>BMI|


20

50% missing data

18

BMI

BMI

BMI

16

14

0.0 2.5 5.0 7.5 10.0

Age (years)

20

50% missing data

18

BMI

BMI

BMI

16

14

0.0 2.5 5.0 7.5 10.0

Age (years)

20

20

20

50% missing data

18

18

18

BMI

BMI

BMI

16

16

16

14

14

14

12

12

| | |
|---|---|
| | |


0 3 6 9

0.0 2.5 5.0 7.5 10.0

0.0 2.5 5.0 7.5 10.0

Age (years)

Age (years)

Age (years)

- Fig. 2 Sensitivity of BMI trajectory models to missing data. A B-splines, (B) Jenss-Bayley and (C) MagmaClust all ﬁt the observed BMI values (black points) well for an individual from birth to age 10. For the same individual, three examples are shown where there is a different set of missing values (red points) occur in 50% of the data. B-splines modeling can lead to large differences in reconstruction, while Jenss-Bayley is more robust. MagmaClust provides robustness, an accurate ﬁt and uncertainty quantiﬁcation. Note that the slight bump around age 3 y in the B-spline and MagmaClust BMI trajectories are due to the switch from length to height for computation of BMI, and the higher ﬁdelity of these methods to the underlying data trend, when compared to the parametric Jenss-Bayley model.


computed probabilities of overweight/obesity at age 10 y for all 297 children. We notice that as we increased the age range of training data for forecasting, the accuracy of identiﬁcation of true children with overweight/obesity greatly improved. These probabilities provide a continuous degree of risk of overweight/ obesity. To evaluate the match between these overweight/obesity probabilities and observed weight status at age 10 y, we considered 5% probability as a decision cutoff. The corresponding sensitivity, speciﬁcity, accuracy, positive predictive value (PPV) and negative predictive value (NPV) for different prediction ranges are shown in Fig. 5B. The sensitivity greatly increased with the increase in number of observed timepoints used for trajectory prediction. When the trajectories were predicted using data till age 8 y, 90% of children who had overweight/obesity at age 10 y were correctly identiﬁed. The positive predictive value remained moderate, increasing from 0.44 to 0.71 for prediction intervals ranging from 8 y to 2 y. Overall, MagmaClust attributed low probabilities to the vast majority of children who turned out not to be overweight at age 10. The speciﬁcity of the method for detecting overweight/obesity status at age 10 remained very high (0.94 to 0.96) even for predictions starting at age 2 y.

Concordantly, the negative predictive value was also consistently high (0.80 to 0.98) over the different prediction intervals. We observed that in some cases, the predicted trajectories using BMI data up to a certain age cutoff deviate signiﬁcantly from the observed trajectories, with the predictions recalibrating towards the observed trajectories when data from addition timepoints are included in the model (Fig. S2).

DISCUSSION

We developed and evaluated a non-parametric and probabilistic framework for BMI trajectory modeling and forecasting individual childhood BMI trajectories, and forecasting the risk of childhood overweight/obesity status using MagmaClust. While MagmaClust identiﬁes cluster-speciﬁc mean processes as an intermediate step of its prediction pipeline, these cluster-speciﬁc mean trends already constitute meaningful insights into distinctive BMI childhood growth patterns in this population. One critical aspect to note is that, as in other mixture models, an individual child may not strictly belong to one cluster. Instead, each cluster’s weight for a child corresponds to the membership probability of belonging

#### A B C

|−10 0 10<br><br>Error (Mean pred − True value)|
|---|
|−10 0 10<br><br>Error (Mean pred − True value)|


Testing data Training data

Testing data Training data

22.5

22.5

Training from age 0 to 2

20.0

20.0

BMI

BMI

17.5

17.5

15.0

15.0

12.5

12.5

0.0 2.5 5.0 7.5 10.0

0.0 2.5 5.0 7.5 10.0

Age (years)

Age (years)

22.5

22.5

Training from age 0 to 4

20.0

20.0

BMI

BMI

17.5

17.5

15.0

15.0

12.5

12.5

0.0 2.5 5.0 7.5 10.0

0.0 2.5 5.0 7.5 10.0

Age (years)

Age (years)

22.5

22.5

Training from age 0 to 6

20.0

20.0

BMI

BMI

17.5

17.5

15.0

15.0

12.5

12.5

0.0 2.5 5.0 7.5 10.0

−10 0 10

0.0 2.5 5.0 7.5 10.0

Age (years)

Error (Mean pred − True value)

Age (years)

- Fig. 3 Prospective forecasting of childhood BMI. A Illustration of MagmaClust forecasts for a random illustrative individual, observed until age 2 (top), age 4 (middle), and age 6 (bottom). Historic BMI values (black) are used for training the model and the future BMI values (red) are used for evaluating predictions from the model. The thick purple line represents the mean prediction, whereas the thin pink lines correspond to 50 curves sampled from posterior distribution. B Uncertainty quantiﬁcation of errors from MagmaClust’s forecasts across all individuals and all testing points. C The Jenss-Bayley model ﬁts a single curve using historic values but its future trajectory deviates from the future BMI values. For all predicted testing points, (sorted by decreasing uncertainty on the y-axis), the pink region corresponds to the 95% credible interval predicted from model; and the red dot is the absolute error to the true value.


to that cluster. As the sum of all weights equals 1, we assume that each child belongs to a mixture of clusters. The estimates of BMI trajectories from MagmaClust were compared to two existing methods: cubic B-splines with ﬁxed effects only and Jenss-Bayley model accounting for random effects. We found that both MagmaClust and Jenss-Bayley models remained robust regardless of the missing values proportions, as these methods account for random effects in the cohort. However, it was observed that before age 2 y, when BMI changed rapidly, MagmaClust accurately captured the peak region, resulting in smaller MSE. Also, as the proportion of missing values increased from 10% to 90%, MSE increased from 0.90 to 2.84 in the case of MagmaClust, compared with a 0.94 to 8.06 increase for Jenss-Bayley. Regarding BMI forecasting into the future, only MagmaClust demonstrated accurate predictions up to age 10 y. The accuracy of BMI predictions remained consistent across various intervals for the forecasting periods, ranging from ages 2–10 y to ages 8–10 y. The ability to visualize the uncertainty of the predictions by drawing multiple curves from the posterior distribution is another major advantage of probabilistic frameworks compared to frequentist approaches like Cubic B-splines and Jenss-Bayley. Cubic B-splines were found to be not robust to missing values for retrospective modeling and not very useful for prospective forecasting. Splines are known to be particularly sensitive to data sparsity on boundaries where they tend to provide inaccurate linear extrapolations [16]. One important point regarding mixed-effect Jenss-Bayley and MagmaClust is that borrowing information from the entire population may have the effect of pulling more extreme

trajectories towards the mean trajectory (or cluster-speciﬁc mean trajectory in MagmaClust). This phenomenon (referred to as shrinkage in mixed-effect models) may have some beneﬁcial effects in real-world settings. Compared to a prospective longitudinal cohort study, real-world longitudinal BMI growth data is likely to be quite noisy (due to measurement errors, varying instruments, non-standardized measurement protocols and outliers) as well as sparse (due to irregular sampling and missing height/weight values). Against this background, the mixed-effect Jenss-Bayley model and MagmaClust may produce more robust trajectory estimates, given their ability to borrow growth information from across the population when compared to methods that only use growth data from a single individual.

As an additional downstream analysis for quantifying the uncertainty of predicted trajectories, we computed instantiations of BMI predictions (up to 100,000 possible trajectories) for each individual child. This allowed us to compute, at any age, the probability of crossing the overweight thresholds. Such an approach provides a practical tool to assess the probability of acquiring overweight/obesity in the future from historical BMI growth data. Note that the proposed approach makes efﬁcient use of the complete longitudinal BMI growth trajectory measured up to a certain time point for predicting future risk of overweight/ obesity. This is in contrast to earlier approaches which have usually relied on continuous weight/BMI or categorical weight status at a single time point [25–29], change in weight/BMI z-scores between two time points [28, 30], or timing/intensity of growth milestones like infancy BMI peak [31, 32] or adiposity

A B

22.5

22.5

20.0

20.0

BMI

BMI

17.5

17.5

15.0

15.0

overweight trajectory mean trajectory

Testing data Training data

12.5

12.5

0.02.55.07.510.0

0.02.55.07.510.0

Age(years)

Age(years)

- Fig. 4 The overweight probability can be estimated from MagmaClust predictions by computing the proportion of posterior instantiations (possible trajectories) crossing the corresponding sex-speciﬁc threshold for BMI to be classiﬁed as overweight (red lines). A Example of a male child showing 4 of the 100 posterior instantiations cross threshold of BMI = 22.8 kg/m2. B Example of a female child showing 3 of the 100 posterior instantiations cross threshold of BMI ¼ 22Kg=m2.


![image 6](<Prospective prediction of childhood body mass index trajectories using multi-task Gaussian processes_images/imageFile6.png>)

Fig. 5 Comparison of observed and predicted overweight status at age 10 y. A Visualization of overweight/obesity probabilities estimated from MagmaClust predictions for different forecasting periods. Children are colored according to their observed overweight status at age 10 (overweight threshold is BMI > 22 for girls and BMI > 22.8 for boys). B Measures of negative predictive value (NPV), positive predictive value (PPV), speciﬁcity, sensitivity and accuracy for identifying overweight/obesity status at age 10 y for different forecasting ranges (2–10 y, 4–10 y, 6–10 y and 8–10 y) when the overweight/obesity probability decision cutoff was set to 5%.

rebound [33, 34] for predicting future overweight/obesity risk. In the current work, for identifying overweight/obesity status at age 10 y, we used an arbitrary decision cutoff of 5% for the proportion of predicted trajectories crossing the overweight threshold at age 10 y. This cutoff could easily be adapted depending on the clinical context and needs (e.g. a higher cutoff can be used for triaging only high-risk children towards more intensive interventions). From empirical evaluation, we reported high accuracy at all ages (86% to 94%) for this prospective overweight/obesity status

detection procedure and a quickly increasing sensitivity, allowing us to identify 20% of the actual overweight children using BMI data from age 0 to 2 y, rising up to 90% when using data from ages 0 to 8 y. The PPV increased from 44% to 71% in the same interval. The speciﬁcity and NPV for detecting overweight/obesity at age 10 y were consistently high for all prediction intervals (over 94% and 80% respectively). The proposed MagmaClust-based approach for probabilistic prediction of future obesity risk only uses prior BMI growth history as input. Note that, while we have

not explicitly used conventional risk factors for obesity like short breastfeeding duration, early time of weaning, low physical/high sedentary activity and diet quality for the prediction of obesity risk, these factors interact with the genetic growth potential to inﬂuence the BMI growth trajectory. Obesogenic risk factors cannot cause obesity without ﬁrst modifying the BMI growth trajectories. Thus, using BMI growth history to predict future obesity risk implicitly also takes prior exposure to environmental risk factors also into account.

In this study, we have cut off BMI growth data at arbitrary ages (2 y, 4 y, 6 y, & 8 y) to predict future overweight/obesity. For clinical translation, these times could be redeﬁned based on visits to pediatricians (e.g. well-child visits and vaccination visits). If previously forecasted mean BMI trajectories for a child are available, then marked deviations from previously forecasted trajectories may be a result of adverse environmental or behavioral factors (e.g. sudden changes in nutritional patterns or physical activity) and may provide a signal for pediatricians to prioritize these children for follow-ups and interventions.

While existing literature emphasizes the signiﬁcance of monitoring and detailing the longitudinal growth of children to gain a more nuanced understanding of potential predispositions for adverse adult health [35–38], we introduced a methodology to prospectively predict future BMI growth trends. MagmaClust possesses the ﬂexibility to undergo retraining by incorporating future growth data, for instance, for capturing post-pubertal growth trends or incorporating growth data from more geographies and ethnicities to generate more representative models. This adaptability enables the extension of predictions to older ages, providing a robust tool for ongoing assessments of childhood growth trajectories. This offers both a methodological advancement and a practical tool to monitor expected growth trends and possible deviations from expected trends during childhood and can enable appropriate interventions.

DATA AVAILABILITY

The data used in the manuscript are available on request, on approval by the GUSTO executive committee. Data catalog and request form can be found at https:// gustodatavault.sg/.

CODE AVAILABILITY

The MagmaClust framework is implemented as an R package called MagmaClust, available on the CRAN, while a development version can be found on GitHub (https:// github.com/ArthurLeroy/MagmaClustR). To help experiments’ reproducibility, all computations, results and trained models presented in this article are stored in the following GitHub repository https://github.com/ArthurLeroy/BMI_MagmaClust.

REFERENCES

- 1. Wang Y, Lobstein T. Worldwide trends in childhood overweight and obesity. Int J Pediatr Obes. 2006;1:11–25.
- 2. Kansra AR, Lakkunarajah S, Jay MS. Childhood and adolescent obesity: a review. Front Pediatr. 2020;8:581461.
- 3. Garcia-Hermoso A, Agostinis-Sobrinho C, Camargo-Villalba GE, Gonzalez-Jimenez NM, Izquierdo M, Correa-Bautista JE, et al. Normal-weight obesity is associated with poorer cardiometabolic proﬁle and lower physical ﬁtness levels in children and adolescents. Nutrients. 2020;12:1171.
- 4. Carsley S, Pope E, Tu K, Parkin PC, Toulany A, Birken CS. Association between weight status and mental health service utilization in children and adolescents. J Can Acad Child Adolesc Psychiatry. 2020;29:229–40.
- 5. Tirosh A, Shai I, Afek A, Dubnov-Raz G, Ayalon N, Gordon B, et al. Adolescent BMI trajectory and risk of diabetes versus coronary disease. N. Engl J Med. 2011;364:1315–25.
- 6. Dulloo AG, Jacquet J, Seydoux J, Montani JP. The thrifty ‘catch-up fat’ phenotype: its impact on insulin sensitivity during growth trajectories to obesity and metabolic syndrome. Int J Obes. 2006;30:S23–35.
- 7. Healthy weight, Healthy children. In: Healthier Child, Brighter Future Toolkit. Singapore Health Promotion Board. March 2015. https://ch-api.healthhub.sg/api/


- public/content/6388cea4f0834765a4383ce7dbbf7124?v=5208ce49. Accessed 10 Nov 2024.
- 8. Nylund KL, Asparouhov T, Muthén BO. Deciding on the number of classes in latent class analysis and growth mixture modeling: a Monte Carlo simulation study. Struct Equ Modeling A Multidiscip J. 2007;14:535–69.
- 9. Jung T, Wickrama K. An introduction to latent class growth analysis and growth mixture modeling. Soc Personal Psychol Compass. 2008;2:302–17.
- 10. Mattsson M, Maher GM, Boland F, Fitzgerald AP, Murray DM, Biesma R. Groupbased trajectory modelling for BMI trajectories in childhood: a systematic review. Obes Rev. 2019;20:998–1015.
- 11. Michael N, Gupta V, Fogel A, Huang J, Chen L, Sadananthan SA, et al. Longitudinal characterization of determinants associated with obesogenic growth patterns in early childhood. Int J Epidemiol. 2023;52:426–39.
- 12. Aris IM, Bernard JY, Chen L-W, Tint MT, Pang WW, Lim WY, et al. Infant body mass index peak and early childhood cardio-metabolic risk markers in a multi-ethnic Asian birth cohort. Int J Epidemiol. 2017;46:513–25.
- 13. Jenss RM, Bayley N. A mathematical method for studying the growth of a child. Hum Biol. 1937;9:556.
- 14. Tilling K, Macdonald-Wallis C, Lawlor DA, Hughes RA, Howe LD. Modelling childhood growth using fractional polynomials and linear splines. Ann Nutr Metab. 2014;65:129–38.
- 15. Carles S, Charles MA, Forhan A, Slama R, Heude B, Botton J. A novel method to describe early offspring body mass index (BMI) trajectories and to study its determinants. PLoS ONE. 2016;11:e0157766.
- 16. Carl de Boor. A Practical Guide to Splines. In: Applied Mathematical Sciences,

1978. https://doi.org/10.1007/978-1-4612-6333-3.

- 17. de Boor C. On calculating with B-splines. J Approx Theory. 1972;6:50–62.
- 18. Ong YY, Rifas-Shiman SL, Perng W, Belfort MB, Law E, Hivert M-F, et al. Growth velocities across distinct early life windows and child cognition: insights from a contemporary US cohort. J Pediatr. 2023;263:113653.
- 19. Leroy A, Latouche P. MagmaClustR: clustering and prediction using multi-task Gaussian processes with common mean. https://arthurleroy.github.io/ MagmaClustR/ 2023.
- 20. Leroy A, Latouche P, Guedj B, Gey S. MAGMA: inference and prediction using multi-task Gaussian processes with common mean. Mach Learn. 2022;111:1821–49.
- 21. Rasmussen CE, Williams CKI. Gaussian Processes for Machine Learning. In: The MIT Press, 2005. https://doi.org/10.7551/mitpress/3206.001.0001.
- 22. Soh SE, Tint MT, Gluckman PD, Godfrey KM, Rifkin-Graboi A, Chan YH, et al. Cohort proﬁle: growing up in Singapore towards healthy outcomes (GUSTO) birth cohort study. Int J Epidemiol. 2014;43:1401–9.
- 23. Botton J, Heude B, Maccario J, Ducimetière P, Charles MA. Postnatal weight and height growth velocities at different ages between birth and 5y and body composition in adolescent boys and girls. Am J Clin Nutr. 2008;87:1760–8.
- 24. Botton J, Scherdel P, Regnault N, Heude B, Charles MA. Postnatal weight and height growth modeling and prediction of body mass index as a function of time for the study of growth determinants. Ann Nutr Metab. 2014;65:156–66.
- 25. Shinoda G, Nagaoka Y, Ueno F, Kurokawa N, Takahashi I, Onuma T, et al. Association between being overweight in young childhood and during school age and puberty. Children. 2023;10:909.
- 26. Simmonds M, Llewellyn A, Owen CG, Woolacott N. Predicting adult obesity from childhood obesity: a systematic review and meta‐analysis. Obes Rev. 2016;17:95–107.
- 27. Yu Z, Han S, Zhu G, Zhu C, Wang X, Cao X, et al. Birth weight and subsequent risk of obesity: a systematic review and meta‐analysis. Obes Rev. 2011;12:525–42.
- 28. Geserick M, Vogel M, Gausche R, Lipek T, Spielau U, Keller E, et al. Acceleration of BMI in early childhood and risk of sustained obesity. N. Engl J Med. 2018;379:1303–12.
- 29. Roy SM, Spivack JG, Faith MS, Chesi A, Mitchell JA, Kelly A, et al. Infant BMI or weight-for-length and obesity risk in early childhood. Pediatrics. 2016;137:5.
- 30. Zheng M, Lamb KE, Grimes C, Laws R, Bolton K, Ong KK, et al. Rapid weight gain during infancy and subsequent adiposity: a systematic review and meta‐analysis of evidence. Obes Rev. 2018;19:321–32.
- 31. Sun J, Nwaru BI, Hua J, Li X, Wu Z. Infant BMI peak as a predictor of overweight and obesity at age 2 years in a Chinese community-based cohort. BMJ Open. 2017;7:e015122.
- 32. Roy SM, Chesi A, Mentch F, Xiao R, Chiavacci R, Mitchell JA, et al. Body mass index (BMI) trajectories in infancy differ by population ancestry and may presage disparities in early childhood obesity. J Clin Endocrinol Metab. 2015;100:1551–60.
- 33. Rolland-Cachera M, Deheeger M, Maillot M, Bellisle F. Early adiposity rebound: causes and consequences for obesity in children and adults. Int J Obes. 2006;30:S11–7.
- 34. Zhou J, Zhang F, Qin X, Li P, Teng Y, Zhang S, et al. Age at adiposity rebound and the relevance for obesity: a systematic review and meta-analysis. Int J Obes. 2022;46:1413–24.


- 35. Eriksson JG, Forsén T, Tuomilehto J, Osmond C, Barker DJP. Early adiposity rebound in childhood and risk of Type 2 diabetes in adult life. Diabetologia. 2003;46:190–4.
- 36. Rolland-Cachera MF, Cole TJ. Does the age at adiposity rebound reﬂect a critical period? Pediatr Obes. 2019;14:e12467.
- 37. Cole TJ. Children grow and horses race: is the adiposity rebound a critical period for later obesity? BMC Pediatr. 2004;4:6.
- 38. Perng W, Rahman ML, Aris IM, Michelotti G, Sordillo JE, Chavarro JE, et al. Metabolite proﬁles of the relationship between body mass index (BMI) milestones and metabolic risk during early adolescence. Metabolites. 2020;10:316.


ACKNOWLEDGEMENTS

We acknowledge the GUSTO study group members: This study group includes: Airu Chia, Andrea Cremaschi, Anna Magdalena Fogel, Anne Eng Neo Goh, Anne RifkinGraboi, Anqi Qiu, Arijit Biswas, Bee Wah Lee, Birit Froukje Philipp Broekman, Candida Vaz, Chai Kiat Chng, Chan Shi Yu, Choon Looi Bong, Daniel Yam Thiam Goh, Dawn Xin Ping Koh, Dennis Wang, Desiree Y. Phua, E Shyong Tai, Elaine Kwang Hsia Tham, Elaine Phaik Ling Quah, Elizabeth Huiwen Tham, Evelyn Chung Ning Law, Evelyn Keet Wai Lau, Evelyn Xiu Ling Loo, Fabian Kok Peng Yap, Falk Müller-Riemenschneider, Franzolini Beatrice, George Seow Heong Yeo, Gerard Chung Siew Keong, Hannah Ee Juen Yong, Helen Yu Chen, Hong Pan, Huang Jian, Huang Pei, Hugo P S van Bever, Hui Min Tan, Iliana Magiati, Inez Bik Yun Wong, Ives Lim Yubin, Ivy Yee-Man Lau, Jacqueline Chin Siew Roong, Jadegoud Yaligar, Jerry Kok Yen Chan, Jia Xu, Johan Gunnar Eriksson, Jonathan Tze Liang Choo, Jonathan Y. Bernard, Jonathan Yinhao Huang, Joshua J. Gooley, Jun Shi Lai, Karen Mei Ling Tan, Keith M. Godfrey, Keri McCrickerd, Kok Hian Tan, Kothandaraman Narasimhan, Krishnamoorthy Naiduvaje, Kuan Jin Lee, Li Chen, Lieng Hsi Ling, Lin Lin Su, Ling-Wei Chen, Lourdes Mary Daniel, Lynette Pei-Chi Shek, Maria De Iorio, Marielle V. Fortier, Mary Foong-Fong Chong, Mary Wlodek, Mei Chien Chua, Melvin Khee-Shing Leow, Michael J. Meaney, Michelle Zhi Ling Kee, Min Gong, Mya Thway Tint, Navin Michael, Neerja Karnani, Ngee Lek, Noor Hidayatul Aini Bte Suaini, Oon Hoe Teoh, Peter David Gluckman, Priti Mishra, Queenie Ling Jun Li, Sambasivam Sendhil Velan, Seang Mei Saw, See Ling Loy, Seng Bin Ang, Shang Chee Chong, Shiao-Yng Chan, Shirong Cai, Shu-E Soh, Stephen Chin-Ying Hsu, Suresh Anand Sadananthan, Swee Chye Quek, Tan Ai Peng, Varsha Gupta, Victor Samuel Rajadurai, Wee Meng Han, Wei Wei Pang, Yap Seng Chong, Yin Bun Cheung, Yiong Huak Chan, Yung Seng Lee, Zhang Han.

AUTHOR CONTRIBUTIONS

DW, JGE, and MAA conceived the study. AL, VG, NM, and DW contributed to the study design, data interpretation and wrote the initial version of the manuscript. AL and VG performed data analysis. MTT, JGE, YSL, YSC, KMG, NL, FY, DOSQ, MAA, and DW contributed to administrative and material support. MTT, YSL, NL, FY, and DOSQ contributed to the data acquisition and preparation. All authors contributed to the critical revision of the manuscript for important intellectual content. AL, VG, NM, and DW had full access to the data in the study and took responsibility for the integrity of the data and the accuracy of the data analysis. AL, VG, NM, and DW are the guarantors of the paper.

FUNDING

The study is supported by the National Research Foundation (NRF) under the Open Fund-Large Collaborative Grant (OF-LCG; MOH-000504) administered by the Singapore Ministry of Health’s National Medical Research Council (NMRC) and the Agency for Science, Technology and Research (A*STAR). In RIE2025, the study is supported by funding from the NRF’s Human Health and Potential (HHP) Domain, under the Human Potential Programme. AL, MAA and DW is supported by the Wellcome Trust (17068/Z/

19/Z). DW is additionally supported by A*STAR Early Childhood Grant (H24P2M0005), the Academy of Medical Sciences Professorship (APR7_1002) and the Engineering and Physical Sciences Research Council (EP/V029045/1). NM is supported by the A*STAR Prenatal/Early Childhood Grant (H24P2M0006). VG acknowledges support from A*STAR Pitchfest CDF (232D800032). KMG is supported by the UK Medical Research Council (MC_UU_12011/4), the National Institute for Health and Care Research (NIHR Senior Investigator (NF-SI-0515-10042) and NIHR Southampton Biomedical Research Centre (NIHR203319)) and Alzheimer’s Research UK (ARUK-PG2022A-008).

COMPETING INTERESTS

K.M.G., Y.S.C., and F.Y. received reimbursement for speaking at conferences sponsored by companies selling nutritional products. K.M.G., and Y.S.C. are part of an academic consortium that has received research funding from Société Des Produits Nestlé S.A. and BenevolentAI Bio Ltd, and are co-inventors on patents ﬁled on nutritional factors and metabolic risk outside the submitted work. All other authors declare that they have nothing to disclose.

ETHICS APPROVAL

This study was approved by both the National Healthcare Group Domain Speciﬁc Review Board (D/2009/021 & B/2014/00411) and the SingHealth Centralized Institutional Review Board (2018/2767 & 2019/2406). It was conducted in accordance with the ethical standards set forth in the 1964 Declaration of Helsinki and its later amendments Written informed consent was obtained from all children and their parents.

ADDITIONAL INFORMATION

Supplementary information The online version contains supplementary material available at https://doi.org/10.1038/s41366-024-01679-0.

Correspondence and requests for materials should be addressed to Dennis Wang.

Reprints and permission information is available at http://www.nature.com/ reprints

Publisher’s note Springer Nature remains neutral with regard to jurisdictional claims in published maps and institutional afﬁliations.

Open Access This article is licensed under a Creative Commons Attribution 4.0 International License, which permits use, sharing,

adaptation, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons licence, and indicate if changes were made. The images or other third party material in this article are included in the article’s Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included in the article’s Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will need to obtain permission directly from the copyright holder. To view a copy of this licence, visit http:// creativecommons.org/licenses/by/4.0/.

© The Author(s) 2024, corrected publication 2024

