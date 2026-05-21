Journal of the American Medical Informatics Association, 29(4), 2022, 626–630

https://doi.org/10.1093/jamia/ocab251 Advance Access Publication Date: 3 December 2021

Research and Applications

Research and Applications

# Inference-based correction of multi-site height and weight measurement data in the All of Us research program

Mirza S. Khan 1,2,3 and Robert J. Carroll3

1Geriatric Research Education and Clinical Center (GRECC), Tennessee Valley Health System Veterans Administration Medical Center, Nashville, Tennessee, USA, 2Division of General Internal Medicine and Public Health, Department of Medicine, Vanderbilt University Medical Center, Nashville, Tennessee, USA, and 3Department of Biomedical Informatics, Vanderbilt University Medical Center, Nashville, Tennessee, USA

Corresponding Author: Robert J. Carroll, PhD, Department of Biomedical Informatics, Vanderbilt University Medical Center, 2525 West End Ave, Suite 1475, Nashville, TN 37203, USA; robert.carroll@vumc.org

Received 16 June 2021; Revised 29 September 2021; Editorial Decision 31 October 2021; Accepted 8 November 2021

ABSTRACT

Objective: Measurement and data entry of height and weight values are error prone. Aggregation of medical record data from multiple sites creates new challenges prompting the need to identify and correct errant values. We sought to characterize and correct issues with height and weight measurement values within the All of Us (AoU) Research Program.

Materials and Methods: Using the AoU Researcher Workbench, we assessed site-level measurement value distributions to infer unit types. We also used plausibility checks with exceptions for conditions with possible outlier values, eg obesity, and assessed for excess deviation within individual participant’s records.

Results: 15.8% of height and 22.4% of weight values had missing unit type information. Discussion: We identiﬁed several measurement unit related issues: the use of different units of measure within and between sites, missing units, and incorrect labeling of units. Failure to account for these in patient data repositories may lead to erroneous study results and conclusions.

Conclusion: Discrepancies in height and weight measurement data may arise from missing or mislabeled units. Using site- and participant-level analyses while accounting for outlier value-associated clinical conditions, we can infer measurement units and apply corrections. These methods are adaptable and expandable within AoU and other data repositories.

Key words: electronic health records/statistics and numerical data, body mass index, body height, body weight, biomedical research

## INTRODUCTION

Work from pioneering collaborative multi-institutional research projects, such as the Patient Centered Outcomes Research Network and the Electronic Medical Records and Genomics (eMERGE) network, has expanded to key national initiatives like the National COVID Cohort Collaborative (N3C) and the All of Us Research Program (AoURP). The AoURP aims to enroll 1 million or more participants in the United States, with an emphasis on the inclusion

of groups that have been historically under-represented in biomedical research.1 AoURP began to make this data available on its research platform for approved researchers in 2020.

The magnitude and heterogeneity of AoURP participants has the potential to expand our knowledge and understanding of the interactions between attributes such as social factors and genetics and their role in health and disease. Many efforts are underway or have been implemented to ensure an effective and functional research en-

VC The Author(s) 2021. Published by Oxford University Press on behalf of the American Medical Informatics Association. All rights reserved. For permissions, please email: journals.permissions@oup.com

626

Downloadedfromhttps://academic.oup.com/jamia/article/29/4/626/6448587byHarvardUniversityLibraryuseron13May2026

vironment for AoURP data. Among these considerations is the assessment and correction of errors in anthropometric measurement values, namely height and weight measurements. Height and weight are common measurements obtained during most clinical encounters and are frequently used as covariates in many research studies. Both values are used to calculate body mass index (BMI), which is arguably the easiest to obtain and most widely used metric for obesity in clinical practice. BMI is also a well-established risk factor for many health conditions, such as type 2 diabetes mellitus, hypertension, and other cardiovascular co-morbidities.2 Unfortunately, these measurement values are subject to many potential sources of error. Errors may be related to data entry, poorly calibrated measurement instruments, and non-compliance with measurement protocol. Measurement values are also commonly entered based upon self-report, particularly among wheelchair users and amputees, which is known to be subject to bias.3–5 These erroneous values may then be propagated forward to subsequent encounters, which poses a challenge for data cleaning methods that rely on outlier detection.

In addition to common measurement and recording errors found in electronic health records (EHRs), the maturity of common data model implementations varied across AoURP sites as some organizations have long-standing research data warehouses while others were built for this Program. Inconsistencies among sites, whether legitimate variation in convention or potential errors, introduced further challenges when handling multi-site data in the AoURP. This variation is common in large research networks, and was especially evident in this pooled dataset in a way that is not always as apparent in federated networks.

Prior published work on cleaning anthropometric measurements were often developed at a single institution or in a federated way in multi-site consortia with expert local knowledge.5,6 These methods fail to consider some of the issues that arise in harmonizing data from many sites of varying data model maturity.

Here, we describe our method for height and weight measurement value evaluation and correction that we developed for the All of Us Research Program dataset. This method is currently implemented and available for use within the AoURP Researcher Workbench. Our approach includes inference and correction of missing or mislabeled measurement units and erroneous measurement values. Additionally, we detail some of the unique challenges posed by multi-site data collection that we were able to identify and how we addressed these issues.

## MATERIALS AND METHODS

Study design

We developed our method for measurement unit inference based upon earlier work conducted at a single academic medical center.7 We adapted this approach based on our analysis of data from

224360 AoURP participants present in the R2019Q4R3 Curated Data Repository (CDR). Our study included all AoURP participants, excluding those less than 18 years of age. This method generates 2 major outputs: (1) values for height and weight with standardized units of cm and kg; (2) measurement row-level metadata flags that can be used to drop or review potentially erroneous values.

At this time, AoURP data includes participant surveys, physical measurements captured as a part of in-person study enrollment, and EHR data with transformations if and when appropriate for privacy considerations.8 The AoURP collected the height and weight data in

this analysis from consented participants in 2 ways. Data were deposited by the enrolling healthcare provider to the Data and Research Center and by trained program staff taking measurements and entering them in the HealthPro system. Participating sites mapped health record data to the Observational Medical Outcomes Partnership (OMOP) common data model.8,9

Data were accessed through the All of Us Researcher Workbench. The All of Us Researcher Workbench is a secure, cloudbased platform for handling and analysis of AoURP data. To comply with the AoURP Data and Statistics Dissemination Policy, we refrain from disclosing group counts with fewer than 20 members.10

We employ a general framework as outlined in Figure 1, which was then tailored to handle each body measurement type as detailed below.

Height data

Height measurements were obtained from the Measurements table using the corresponding OMOP concept identifiers for height (3036277, 3023540, and 3019171). Those height measurements with values recorded as null, zero, or taken when the participant was less than 18 years old were excluded.

Outlier height conditions

We identified individuals with conditions that may be associated with extreme height measurements or height variation relative to the unaffected patient population. This mitigates the possibility of incorrectly treating valid height values as being erroneous or potential outliers. The base diagnostic codes for such conditions were obtained from previous work implemented at Vanderbilt University Medical Center (VUMC).7 This earlier work used International Classification of Diseases (ICD) codes. We translated these conditions to the corresponding OMOP concept identifier, typically Systematized Nomenclature of Medicine (SNOMED). Each concept and its corresponding child concepts were manually reviewed by a physician. During this process, concepts were added to capture other similar conditions or excluded if considered too general or unlikely to be associated with atypical height values. The resulting collection of conditions were used to identify individuals with one or more of these conditions. The complete list of concept IDs used for outlier height conditions is available at https://github.com/mirzask/AoU_ HtWt.

Height value conversion using inferred units

We inferred the measurement units using previously defined thresholds and converted all measures to centimeters.7 Height values between 0.9 and 2.3 were assumed to be in meters, and converted to centimeters by multiplying by 100. Those values between 3.0 and 7.5 were treated as being in units of feet and were multiplied by 30.48. Height measurements between 36.0 and 89.9 were interpreted as being in inches, and these values were multiplied by 2.54. After conversion, the measurement unit was also updated to centimeters. All remaining values were kept unchanged.

Other height value considerations

Following the value conversions to centimeters using inferred units, the median height for the total population was calculated. The median value for the population during the development of this process was 166.4 cm. For each individual, height values greater than 3% above or below their median height were flagged as possibly being erroneous if the patient did not have a condition that may otherwise

Downloadedfromhttps://academic.oup.com/jamia/article/29/4/626/6448587byHarvardUniversityLibraryuseron13May2026

![image 1](<Inference-based correction of multi-site height and weight measurement data in the All of Us research program_images/imageFile1.png>)

- Figure 1. General framework used to infer measurement unit types to infer measurement units and identify and correct erroneous values or unit types.


explain this discrepancy, ie an outlier height condition as previously described. Additionally, those individuals with only 2 height value recordings with significant disagreement between these 2 values were also flagged. Significant disagreement was defined as a greater than 14 unit difference between the 2 values.7

Weight data

Weight recordings were captured from the Measurements table using the following OMOP concept identifiers for weight measurements: 3025315, 3013762, and 3023166. Using the OMOP Vocabulary, we identified and reviewed the LOINC codes that specified quantified patient body weights. Weights with a value of null, zero, or taken when the participant was less than 18 years old were excluded. Where weight values were recorded as being negative, the absolute value was used.

Outlier weight conditions

Like the approach described above for height values, we identified 216 conditions that may be associated with extreme weight measurements or weight variation relative to the unaffected patient population. Again, we used ICD codes for such conditions from previous work at VUMC as our basis.7 These ICD codes were translated to the equivalent OMOP standard concepts, typically SNOMED codes, and reviewed along with their child concepts by a physician. We further classified conditions as those that may lead to higherthan-normal weights or lower than normal weights, ie high and low outlier groups. The full list of concept IDs used as high and low out-

lier weight conditions can be found at https://github.com/mirzask/ AoU_HtWt.

Pre-processing weight data

We manually reviewed the weight distributions at each site by the provided measurement unit: kilograms, pounds, ounces, or missing. One site demonstrated a bimodal distribution with a missing structured measurement unit. One peak was in the range of plausible kilogram values, and the other in the range of plausible ounce values. We processed this site independently prior to implementing our general approach described below. For this site and measurement unit type, weight values greater than 1000 were considered to be in ounces and converted to kilograms (kg) by dividing by 35.274; the others were presumed to be in kilograms and kept unchanged. All weight values greater than 16000 were functionally excluded.

Unit conversions

Certain study sites recorded weight values using more than one measurement unit or the unit type was missing. Thus, we used the following procedure to infer weight measurements. At each study site, the median weight was calculated for each measurement unit as defined by the provided measurement unit. For example, if a study site provided weight records using 2 measurement units, we calculated 2 median values for the site. This median weight value was then used to infer the weight measurement unit. If the median weight at a site for a given measurement unit was between 120 and 300, the values for that provided unit were expected to be in pounds. Thus, all weight

Downloadedfromhttps://academic.oup.com/jamia/article/29/4/626/6448587byHarvardUniversityLibraryuseron13May2026

![image 2](<Inference-based correction of multi-site height and weight measurement data in the All of Us research program_images/imageFile2.png>)

- Figure 2. Random sample of 25% of the population, stratiﬁed by speciﬁed by (A) height and (B) weight measurement units. (A) The distribution of raw (blue) and cleaned (red) height values is shown. There is a distinct set of values reported as being in centimeters that appear mislabeled; this density of values appears to be most consistent with inches. Height values with missing units appear to be either in feet, inches, or centimeters. (B) The distribution of raw weight values for units in grams, kilograms, ounces, and pounds is shown. Raw and cleaned weight values with missing measurement units are shown using a log-10 scale for better visualization of the value range.


values at the site for this particular unit type were then converted to kilograms by dividing by 2.2046. When the median weight at a site for a given measurement unit was greater than 1200, we interpreted the weight values as being in ounces. These values were converted to kilograms by dividing by 35.274. Where the median weight at a site for a given unit type was between 60 and 110, the weight values were interpreted as being in kilograms and the values were kept unchanged. Measurement units were updated to reflect conversion to or determination of weight values as being in kilograms.

After the above conversions, the median weight for each subject was calculated. For each subject, we then compared each individual recorded weight value to their median weight. Each weight value recorded between 1.5 and 3 times a subject’s median weight was interpreted as being in pounds and was converted to kg by dividing by 2.2046. Each weight value 24–50 times a subject’s median weight was assumed to be in ounces and was divided by 35.274. Where weight values were converted to kilograms, the unit type was also updated.

Other weight value considerations

- • Pregnancy: participants with a pregnancy-related condition were identiﬁed as possibly being pregnant for 1 month before or after start date for record of a pregnancy-related condition to avoid exclusion of pregnancy-related weight changes.
- • Weights above 250 kg: participants with 3 or more weight records above 250 kg were treated as having an outlier weight condition.
- • 33% or more weight discrepancy: for non-pregnant patients, any weight(s) 33% above or below a participant’s median weight in any 2-year time window with 3 or more weight recordings was ﬂagged as a potentially implausible value.


• Large discrepancy when only 2 recordings: As with height, for those with only 2 weight recordings, we ﬂagged values where the difference between the 2 values was greater than 14 units as containing potentially implausible values.

## RESULTS

Of the 224360 AoURP participants present in the R2019Q4R3 CDR, 72600 participants had at least 1 measurement of height from their EHR, 75080 participants had at least 1 measurement of weight from their EHR, and 182740 individuals had height and weight recorded during the AoURP in-person enrollment.

Height

Of the 1566377 raw height values, 15.8% had missing measurement units. We additionally found some potential errors in specified units. The raw height values ranged from a minimum of 0.2 to a maximum of 16164.6 with a mean height of 107.3 and median of 70.0. Cleaned height values ranged from 0.2 to 457.0 cm; mean and median height were 167.1 and 166.2 cm, respectively. The distribution of raw and cleaned height data is shown in Figure 2A.

Weight

Of the 1 941949 total weight value measurements, 22.4% of values lacked any specified measurement units. The raw weight values ranged from 90 to a maximum value of 184107 with a mean of 712.0 and median of 158.0. The cleaned weight values ranged from 30.0 to 413.2 kg; mean and median weights were 86.5 and 82.6 kg, respectively. The distribution of raw and cleaned weight data is shown in Figure 2B.

Downloadedfromhttps://academic.oup.com/jamia/article/29/4/626/6448587byHarvardUniversityLibraryuseron13May2026

## DISCUSSION

Our work highlights several challenges working with common measurement values from multiple sites. These include the use of different units of measure within and between sites, missing units, and incorrect labeling of measurement units.

Examining measures of central tendency and spread, eg median and interquartile range, alone may fail to reveal inconsistencies or anomalies within the data. Site-level visualization of measurement distributions and analyses allowed us to identify plausible value ranges for different measurement units. Inspection of value distributions revealed that one site’s weight records had a bimodal distribution with peaks in 2 distinct ranges and measurement units were missing. This site’s values were individually pre-processed based on these findings as described above.

In addition to characterizing the data, we applied data correction approaches based on earlier work at VUMC.7 Our approach accounts for conditions associated with normal physiologic change, such as pregnancy, or anticipated changes, such as weight change following bariatric surgery, to avoid falsely flagging or correcting plausibly valid measurements that appeared unusual looking only at the measurement itself. Moreover, we conduct additional height and weight value checks for gross deviations that may arise from other sources of error, such as typographical or other data entry errors. After applying our method, the distribution of height and weight values takes a unimodal normal distribution centered at expected population averages (Figure 2).

## CONCLUSION

This study highlights and addresses challenges that arise due to the heterogeneity of source data across the AoURP. Issues include the use of multiple or missing unit types and discordant measurement values. We analyzed height and weight measurement values within and across sites to inform measurement unit inference and correction to standard metric units where appropriate. Our method provides an informed foundation for users of AoURP data by standardizing units and addressing some errors present in the data. Furthermore, these methods are adaptable and expandable as more data sources are integrated to the AoURP data resource.

## FUNDING

MSK was supported by the US Department of Veterans Affairs Office of Academic Affiliations Advanced Fellowship in Medical Informatics. RJC was supported for this work by the NIH OD 5 U2C OD023196 and NCATS 5 UL1 TR002243. The All of Us Research Program is supported by the National Institutes of Health, Office of the Director: Regional Medical Centers: 1 OT2 OD026549, 1 OT2 OD026554, 1 OT2 OD026557, 1 OT2 OD026556, 1 OT2 OD026550, 1 OT2 OD 026552, 1 OT2 OD026553, 1 OT2 OD026548, 1 OT2 OD026551, 1 OT2 OD026555, and IAA #: AOD 16037; Federally Qualified Health Centers: HHSN 263201600085U; Data and Research Center: 5 U2C OD023196; Biobank: 1 U24 OD023121; The Participant Center: U24 OD023176; Participant Technology Systems Center: 1 U24 OD023163; Communications and Engagement: 3 OT2 OD023205 and 3 OT2 OD023206; and Community Partners: 1 OT2 OD025277, 3 OT2 OD025315, 1 OT2 OD025337, and 1 OT2 OD025276.

## AUTHOR CONTRIBUTIONS

All authors conceived the study design. MSK performed data collection and data analysis. All authors performed interpretation of the results and contributed to the writing and review of the manuscript.

## ACKNOWLEDGMENTS

The All of Us Research Program would not be possible without the partnership of its participants.

## CONFLICT OF INTEREST STATEMENT

The authors (MSK and RJC) declare that there is no conﬂict of interest.

## DATA AVAILABILITY

Data used for this study is available to approved researchers following registration, completion of ethics training, and attestation of a data use agreement through the All of Us Research Workbench platform (available at https:// workbench.researchallofus.org/).

## REFERENCES

- 1. The “All of Us” Research Program. N Engl J Med 2019; 381: 668–76.
- 2. Powell-Wiley Tiffany M, Paul P, Burke Lora E, et al.; On behalf of the American Heart Association Council on Lifestyle and Cardiometabolic Health; Council on Cardiovascular and Stroke Nursing; Council on Clinical Cardiology; Council on Epidemiology and Prevention; and Stroke Council. Obesity and cardiovascular disease: a scientiﬁc statement from the American Heart Association. Circulation 2021; 143 (21): e984–1010.
- 3. No€el PH, Copeland LA, Perrin RA, et al. VHA Corporate Data Warehouse height and weight data: opportunities and challenges for health services research. J Rehabil Res Dev 2010; 47 (8): 739–50.
- 4. Greenwood JLJ, Narus SP, Leiser J, et al. Measuring body mass index according to protocol: how are height and weight obtained? J Healthc Qual 2011; 33 (3): 28–36.
- 5. Goodloe R, Farber-Eger E, Boston J, et al. Reducing clinical noise for body mass index measures due to unit and transcription errors in the electronic health record. AMIA Jt Summits Transl Sci Proc 2017; 2017: 102–11.
- 6. Muthalagu A, Pacheco JA, Aufox S, et al. A rigorous algorithm to detect and clean inaccurate adult height records within EHR systems. Appl Clin Inform 2014; 5 (1): 118–26.
- 7. Jiang Y, Basford M, Kirby J, et al. Systematic and longitudinal approach to height, weight, and body mass index data cleaning for efﬁcient reuse of EHR data for research. In: AMIA 2016 Summit on Translational Bioinformatics. San Francisco, CA, USA; 2016.
- 8. Ramirez AH, Sulieman L, Schlueter DJ, et al. The All of Us Research Program: data quality, utility, and diversity. medRxiv 2020;2020.05.29.20116905. doi:10.1101/2020.05.29.20116905.
- 9. Klann JG, Joss MAH, Embree K, et al. Data model harmonization for the All Of Us Research Program: Transforming i2b2 data into the OMOP common data model. PLoS One 2019; 14 (2): e0212463.
- 10. The All of Us Research Program. The All of Us Research Program: Data and statistics dissemination policy. https://www.researchallofus.org/wpcontent/themes/research-hub-wordpress-theme/media/2020/05/AoU_Policy_Data_and_Statistics_Dissemination.pdf (Accessed June 1, 2021).


Downloadedfromhttps://academic.oup.com/jamia/article/29/4/626/6448587byHarvardUniversityLibraryuseron13May2026

