### Original research

# Artificial intelligence-driven anthropometric assessment for young children: evaluating the accuracy and practicality of a digital image-based length and weight prediction tool

## Daniel Chan,1,2 Mei Chien Chua,1,3 Matthew Hadimaja,4 Sankha Mukherjee,4 Jill Wong,4 Fabian Yap 1,2

To cite: Chan D, Chua MC, Hadimaja M, et al. Artificial intelligence-driven anthropometric assessment for young children: evaluating the accuracy and practicality of a digital image-based length and weight prediction tool. BMJ Health Care Inform 2025;32:e101540. doi:10.1136/ bmjhci-2025-101540

► Additional supplemental material is published online only. To view, please visit the journal online (https://doi.org/10.1136/ bmjhci-2025-101540).

Parts of this work were previously presented at the 56th Annual Meeting of the European Society for Paediatric Gastroenterology, Hepatology and Nutrition, held on 15–18 May 2024 in Milan, Italy. The data presented herein include additional analyses and updates that are not included in the conference presentation.

Received 09 April 2025 Accepted 18 November 2025

© Author(s) (or their employer(s)) 2025. Re-use permitted under CC BY-NC. No commercial re-use. See rights and permissions. Published by BMJ Group.

For numbered affiliations see end of article.

Correspondence to Professor Fabian Yap; fabian.yap.k.p@singhealth. com.sg

### ABSTRACT

Background Monitoring early childhood growth is vital, as growth faltering could indicate nutritional or health issues requiring prompt intervention. Our study’s aim was to assess the performance of a length-weight artificial intelligence (LWAI) tool for predicting children’s length and weight from smartphone images. Methods This observational, single-centre study recruited children aged 0–18 months. Investigators measured length and weight in clinic using WHO standard recommendations and captured six images per child in a supine position, while parents took six similar images at home. Within each image, LWAI identifies specific body landmarks and a reference object, then extracts and uses image features to predict the child’s length and weight. The LWAI’s performance was assessed by comparing length/weight prediction versus actual measurements. User experience was collected through questionnaires. Results A total of 215 participants (mean age 6.1 months) were included, and length/weight predictions were generated for 98% (2184/2224) of the images. The mean absolute error (MAE) and mean absolute percentage error (MAPE) for length were 2.47cm (4.04%) for individual images and 1.89cm (3.18%) for grouped images (participants with ≥9 images). The corresponding MAE/MAPE for weight were 0.69kg (11.68%) and 0.56kg (9.02%), respectively. Regarding usability, 97% of parents who reported not routinely measuring their child’s growth indicated that they would start doing so regularly if a digital tool was available to them. Conclusions The LWAI tool can predict length and weight in children ≤18 months, offering a practical, convenient, artificial intelligence-powered alternative for growth monitoring in home and clinical settings. Trial registration number NCT05079776.

### INTRODUCTION

Monitoring early childhood growth is a fundamental aspect of paediatric health, with length and weight serving as key indicators of an infant’s health and nutritional status.1–3 Faltering length and weight can have several

|WHAT IS ALREADY KNOWN ON THIS TOPIC<br><br>⇒ Accurate early childhood growth monitoring is crucial for identifying health concerns, but conventional methods of length and weight measurement are often difficult for parents to perform at home. Artificial intelligence-powered digital anthropometry presents a promising alternative.<br><br>WHAT THIS STUDY ADDS<br><br>⇒ This study demonstrates the feasibility and accuracy of a length-weight artificial intelligence tool for predicting length and weight in infants and toddlers 18 months and below, showing the potential of using smartphone images for convenient growth monitoring in clinical or home settings.<br><br>HOW THIS STUDY MIGHT AFFECT RESEARCH, PRACTICE OR POLICY<br><br>⇒ The findings suggest that digital anthropometry could facilitate paediatric growth monitoring by enabling regular at-home assessments. It could also be integrated into clinical settings, supporting telemedicine and public health programmes. This approach may improve the accessibility of early childhood growth monitoring, facilitating earlier detection of growth-related health issues and potentially enhancing paediatric health outcomes.|
|---|


causes, including higher nutritional needs, excessive nutrient loss and, most commonly, insufficient caloric intake, especially a lack of protein, essential vitamins and minerals. Adverse outcomes of faltering growth range from short-term effects like impaired immune function to long-term consequences such as cognitive deficits.2 4 Conversely, excessive weight gain could suggest an increased risk of childhood obesity and its associated cardiometabolic complications such as insulin resistance.2 5–7

BMJHealth&CareInformatics:firstpublishedas10.1136/bmjhci-2025-101540on9December2025.Downloadedfromhttps://informatics.bmj.comon2May2026byguest. Protectedbycopyright,includingforusesrelatedtotextanddatamining,AItraining,andsimilartechnologies.

Accurate length and weight measurement in very young children presents technical challenges. Weight measurement requires calibrated scales, which need regular maintenance.8 9 Length measurement is even more challenging, requiring a specialised, calibrated length board and correct positioning and restriction of the infant’s movement. This requires at least two skilled personnel to position the child, which may be impractical outside clinical settings.2 3 8 9 Therefore, while regular anthropometric measurements are crucial for growth monitoring,2 3 it is often impractical for parents to perform these at home, leading to delayed detection of abnormal growth patterns until routine well-baby health visits.

Artificial intelligence (AI) and digital anthropometry (DA) offer promising solutions to these challenges. AI applications have demonstrated success in estimating body measurements through mobile device images in adults and older children.10–13 However, measuring preambulatory infants presents unique challenges due to their heterogeneous body shapes and silhouettes, constant movement and difficulty in maintaining proper posture.8 9 These factors require specialised DA algorithms. Several innovative approaches have been developed to address challenges in DA for infants and young children.12–19 These generally use image-based methods to predict growth parameters, with some employing augmented reality to enhance accuracy.12–19 However, many of these technologies face limitations of cost or specialised equipment requirements, which can hinder widespread adoption.12–19 There is an unmet need for an accurate, user-friendly digital tool for convenient at-home or in-clinic infant growth assessment using only a mobile device.

Our study team previously developed a length artificial intelligence (LAI) tool to predict the length of infants aged 0–18 months using mobile device images.20 In a pilot study, LAI demonstrated accuracy comparable to that reported in a general paediatric clinic and community health settings.9 21 Importantly, both investigators and parents reported ease in capturing the required photos; the LAI tool does not require specialised equipment or body segment markers, making it practical for home and paediatric clinic use. Parent feedback indicated interest in extending the tool’s capabilities for predicting other anthropometric parameters and growth tracking using WHO growth charts.20

Weight must be interpreted in conjunction with length measurements. The WHO has established international growth standards for children up to age 5, with weight for length used up to 2 years and weight for height from 2 years to 5 years.22 Deviations from these standards may indicate health issues requiring nutritional interventions and medical attention. Building on parents’ feedback and the clinical importance of assessing both key growth parameters, our research question focused on creating a new tool that provides a more comprehensive solution for monitoring infant growth trajectories. Therefore, we developed the length-weight artificial intelligence (LWAI)

tool, designed to simultaneously predict the length and weight of infants ≤18 months from mobile device images.

### METHODS Study design, participants and assessments

The study design, eligibility and assessments have been previously described.20 This observational, cross-sectional, single-centre study recruited children aged 0–18 months. Eligible participants were those able to undergo length and weight measurements using the standardised technique recommended by WHO,23 with parents who had a smartphone/tablet with internet access to complete the study questionnaire and upload images.

The study adhered to Good Clinical Practice, the Declaration of Helsinki and local regulations. Parental written consent was obtained before any study procedures. The study was registered at ClinicalTrials.gov (NCT05079776).20

On day 1 (clinic setting), two separate investigators measured participants’ length and weight using standardised WHO measurement techniques.23 Body weight was measured with an electronic weighing scale accurate to the nearest 0.1kg, and recumbent length was measured using a length board accurate to the nearest 0.1cm. If the discrepancies exceeded 0.1kg or 0.5cm, a third measurement was taken, and the average was used as input for the LWAI algorithm.

Photo-taking guidelines for investigators and parents included specific instructions on the setting, child positioning and reference card placement (figure 1).20 On day 1, investigators took six top-view photos of participants in a supine position with a standard-sized reference card. On day 1 or 2, parents took and uploaded six similar photos of their children at home.

An online questionnaire was administered to investigators and parents to evaluate their user experience and AI tool acceptability.20

### LWAI overview

The LWAI employs machine learning techniques to predict length and weight from single or multiple digital images. Details on the development of the tool were provided in a previous publication on the LAI tool.20 The algorithm requires input of a digital image of the participant in a supine position alongside a standard reference card (CR80 dimension: 85.6mm by 54.0mm) (figure 1). Key steps include: (1) Feature extraction: body landmark extraction models detect key features on the participant’s body, while reference detection and segmentation models locate the reference card in the image. The pixel dimensions of the card are then compared against its known physical dimensions to calculate a pixel-per-metric value. (2) Length and weight prediction: the algorithm generates a predicted value only if the key feature extraction steps are successful. The extracted features are used in the LWAI model to predict the participant’s body length and weight. (3) Warning system: there are preset automated

BMJHealth&CareInformatics:firstpublishedas10.1136/bmjhci-2025-101540on9December2025.Downloadedfromhttps://informatics.bmj.comon2May2026byguest. Protectedbycopyright,includingforusesrelatedtotextanddatamining,AItraining,andsimilartechnologies.

![image 1](<Artificial intelligence-driven anthropometric assessment for young children - evaluating the accuracy and practicality of a digital image-based length and weight prediction tool_images/imageFile1.png>)

- Figure 1 LWAI algorithm overview. The requirements for the setting, the child’s attire and position, and reference card placement when capturing images in the supine position are as outlined. Images are uploaded and processed by the LWAI algorithm. The reference detection and segmentation models convert pixels to size based on the known dimensions of the reference card. Simultaneously, the body landmark extraction model identifies key body landmarks to predict body segment length and weight. The system also generates warning signals for images that do not meet the criteria for accurate length and weight estimation. AI, artificial intelligence; LWAI, length-weight artificial intelligence.


flags to detect images that do not meet specified requirements (figure 1). Warning labels include card and body overlap, incorrect card aspect ratio, improper card segmentation and width or height pixel size deviations.20

### Model training and performance metrics

The LWAI model was trained following the same process as the LAI model.20 The training set comprised a combined dataset of investigator-collected images with corresponding investigator-generated length and weight measurements, excluding images with warnings. A fivefold cross-validation method was employed.20 24 25

Performance metrics were assessed per image for individual predictions and per participant for grouped predictions. For participants with at least nine successful length and weight predictions, the results were averaged to generate a single predicted weight or length. The error (E) represents the difference between the measured and predicted values, with the absolute error (AE) being the absolute value of this difference (kilogram for weight and centimetre for length). The absolute percentage error (APE) represents the AE expressed as a percentage of the measured weight or length. Mean absolute error (MAE) provides the average of all AEs across the dataset, while

mean absolute percentage error (MAPE) represents the average of all APEs.

### RESULTS Characteristics of participants and image data

A total of 215 participants were recruited (51% female, mean age of 6.1 months), with 200 completing the study and providing all required data, including length and weight measurements, images for LWAI input and questionnaire responses.20 Online supplemental table 1 shows the length and weight of the participants, stratified by age group (0–6, >6–12 and >12 months). Of 2490 images collected, 266 (11%) were excluded for non-adherence to image quality requirements and/or protocol deviations. Among the 2224 evaluable images analysed, length and weight prediction was successful for 2184 (98%), with 1384 (62%) classified as free from any warning labels.

### Length and weight prediction performance of the LWAI

For the 1384 images without warning labels, length and weight predictions were generated for both individual and grouped images (averaging ≥9 images, n=54). Consistent with our previous study’s findings, using grouped images significantly improved prediction accuracy.20

BMJHealth&CareInformatics:firstpublishedas10.1136/bmjhci-2025-101540on9December2025.Downloadedfromhttps://informatics.bmj.comon2May2026byguest. Protectedbycopyright,includingforusesrelatedtotextanddatamining,AItraining,andsimilartechnologies.

![image 2](<Artificial intelligence-driven anthropometric assessment for young children - evaluating the accuracy and practicality of a digital image-based length and weight prediction tool_images/imageFile2.png>)

- Figure 2 Distributions of APE and AE, and scatter plots of predicted versus measured length and weight for individual and grouped images. AE, absolute error; APE, absolute percentage error.


For length, the MAE (MAPE) was 2.47cm (4.04%) for individual images and 1.89cm (3.18%) for grouped images. Overall, 90% of the length predictions were within 5.09cm (8.57%) of measured lengths for individual images and 3.89cm (7.27%) for grouped images. Most length predictions were within 10% of the measured length for individual images and within 5% for grouped images (figure 2). The MAE (MAPE) for weight prediction was 0.69kg (11.68%) for individual images and 0.56kg (9.02%) for grouped images. Overall, 90% of the weight predictions were within 1.52kg (24.60%) of measured weight for individual images and 1.19kg (19.18%) for grouped images. Most weight predictions were within 30% of the measured weight for individual images and within 15% for grouped images (figure 2).

Predictions of the MAE for weight increase with age while the predicted MAPE decreases. For length, the MAE also increases with age, but the MAPE remains largely constant. Additionally, male participants showed smaller prediction errors for both length and weight than female participants (table 1).

We calculated body mass index (BMI) (kg/m²) for all individual images based on the predicted length and weight and compared it with the BMI calculated based on measured length and weight. For BMI predictions from individual images, most were within 20% of the measurement-based BMI, with an MAE (MAPE) of 1.35 kg/m2 (8.50%). A high degree of overlap was observed between the distributions of predicted BMIs and the

BMIs calculated from measured length and weight, across all age groups and varying lengths and weights (figure 3).

### User experience questionnaire

Our earlier study indicated that 85% of investigators and 72% of parents had no difficulties in capturing the required photos for most participants.20 Here, we analysed how the AI tool could facilitate regular growth

Table 1 Mean absolute error and MAPE for length and weight across age groups and sex

Weight Length MAE (kg)

MAPE (%)

MAE (cm)

MAPE (%)

n

Age group (months)

0–6 885 0.63 12.87 2.25 4.05 6–12 306 0.80 9.97 2.71 3.94 >12 193 0.84 8.96 3.16 4.17

Sex

Female 722 0.75 12.94 2.61 4.26 Male 662 0.64 10.32 2.31 3.80

The table shows prediction errors for length and weight categorised by age group and sex. n denotes number of images. MAE, mean absolute error; MAPE, mean absolute percentage error.

BMJHealth&CareInformatics:firstpublishedas10.1136/bmjhci-2025-101540on9December2025.Downloadedfromhttps://informatics.bmj.comon2May2026byguest. Protectedbycopyright,includingforusesrelatedtotextanddatamining,AItraining,andsimilartechnologies.

![image 3](<Artificial intelligence-driven anthropometric assessment for young children - evaluating the accuracy and practicality of a digital image-based length and weight prediction tool_images/imageFile3.png>)

- Figure 3 Prediction of BMI: (A) predicted BMI versus measured BMI, (B) MAE for BMI, (C) BMI versus measured length, (D) BMI versus measured weight, (E) BMI versus age. BMI, body mass index; MAE, mean absolute error; MAPE, mean absolute percentage error.


monitoring, especially in home and community settings. Questionnaire responses revealed that 56% of parents did not routinely measure their child’s growth at home, but 97% of these parents would be willing to perform growth measurements regularly if provided with a digital tool (figure 4).

### DISCUSSION

Monitoring early childhood growth is critical for assessing health and nutritional status, yet accurate length and weight assessment in preambulatory children remains challenging.1 2 8 9 22 There is an unmet need for a userfriendly, accessible, mobile device-based AI tool for convenient anthropometric assessment in both home and clinical settings. As a proof of concept, we developed the LWAI tool, an AI-powered platform that predicts length and weight for children aged 0–18 months from images. The LWAI tool may be used by parents, caregivers or clinic staff without specialised training, requiring only a mobile device for image capturing and an easily procured reference card. Accessibility and ease of use are its key advantages, eliminating the need for specialised equipment or extensive training. Optimal performance requires specific conditions, such as appropriate lighting, a uniform background and correct positioning of the camera relative to the child, which can be easily managed

with guidance. Importantly, the tool’s design minimises any disturbance to the child during measurement.

In our study, the LWAI tool demonstrated feasibility in predicting length and weight in infants. Consistent with our preliminary findings on the LAI tool, we observed that using grouped images significantly reduced error magnitude (MAE and MAPE), underscoring the importance of capturing and analysing multiple images to enhance accuracy.20 For grouped images, most weight predictions fell within 15% of the measured weight using the standard WHO method, and length predictions were within 5% of the measured length. Furthermore, the LWAI tool’s accuracy in measuring length with grouped images, with an MAE of 1.89cm, approached the interobserver technical error of measurement (TEM) of 1.41cm achieved in a paediatric clinic, and 1.25–1.59cm range achieved in a community health setting using standard WHO method.9 21 The MAE (MAPE) for grouped images (weight: 0.56kg (9.02%), length: 1.89cm (3.18%)) is consistent with previous findings on mobile AI-assisted tools for weight16 and length predictions14 in infants or children. Methods that require physical placement of markers may help with body landmark detection, but are cumbersome, often requiring specialised training and are less likely to be used regularly.15

This proof-of-concept study demonstrates the feasibility and acceptability of mobile device-based anthropometric

BMJHealth&CareInformatics:firstpublishedas10.1136/bmjhci-2025-101540on9December2025.Downloadedfromhttps://informatics.bmj.comon2May2026byguest. Protectedbycopyright,includingforusesrelatedtotextanddatamining,AItraining,andsimilartechnologies.

![image 4](<Artificial intelligence-driven anthropometric assessment for young children - evaluating the accuracy and practicality of a digital image-based length and weight prediction tool_images/imageFile4.png>)

- Figure 4 The likelihood that parents will measure their child’s growth at home using either conventional methods or a digital tool. Responses from parents: n=200. Question 1: ‘How often do you measure your child’s length manually at home currently?’ Question 2: ‘If a tool measures your child’s length automatically from an image, how often would you use it?’ Response options: never, less than once a month, at least once a month, at least once every 2 weeks, at least once a week, daily. Among parents who reported never measuring their child’s length (55.7% in Question 1), 97% reported they would measure at least once a month if a digital tool were available (uestion 2).


measurements for infants and young children. We acknowledge that further refinement of the LWAI algorithm is needed to improve accuracy. One promising approach is the use of video data, which yields much larger numbers of images and increases the likelihood of obtaining high-quality images for more accurate prediction, which could further enhance the tool’s performance. Future work may focus on improving accuracy using video data and augmented reality to enhance reference card detection. Additionally, a calibration feature could be incorporated, allowing users to input actual measurements taken during clinical visits to fine-tune the algorithm, thereby personalising predictions for each child. Other technologies, such as depth-of-field sensors available on some consumer devices, could potentially be integrated to further improve performance. In this study, we also observed variability in prediction accuracy across different age groups and sexes, suggesting the need for further refinement to ensure consistent accuracy across different demographics. The Paediatric Augmented Reality Scale tool, for instance, includes sex-based adjustments for weight prediction in children.16 Additional factors that could affect accuracy warrant further investigation, and future iterations of the LWAI algorithm could improve accuracy by accounting for these factors.

We extended the LWAI tool’s functionality beyond length and weight prediction to calculate BMI based on these predictions. The MAPE for BMI prediction was

8.50%, indicating that the tool is feasible for estimating BMI. There is potential to further expand the functionality of the tool to encompass additional WHO growth indicators, such as Z-scores for weight for age, length for age and weight for length. This expansion could provide a more comprehensive representation of growth status and allow a more comprehensive assessment of child growth trajectories.

The usability questionnaire revealed that the LWAI tool has the potential to significantly enhance parental engagement in growth monitoring. Notably, 97% of parents who do not routinely measure their child’s growth at home using traditional methods expressed a willingness to use a digital tool for regular monitoring (figure 4). By empowering parents to actively track their children’s growth, the LWAI tool could promote regular monitoring, allowing for earlier detection of potential health issues and timely intervention.

For length, interobserver TEMs using the standard WHO method have been reported as 1.41cm in a paediatric clinic,21 1.25–1.59cm in a community health setting9 and 0.48–0.70cm in the ‘gold standard’ WHO Multicenter Growth Reference Study.22 26 Weight measurements in infants and toddlers typically exhibit variability of approximately 300g,27 with parent-reported studies generally reporting accuracy within ±1kg of measured values.28 In clinical care, acceptable intraobserver and interobserver reliability is <2%, with measurement noise of about

BMJHealth&CareInformatics:firstpublishedas10.1136/bmjhci-2025-101540on9December2025.Downloadedfromhttps://informatics.bmj.comon2May2026byguest. Protectedbycopyright,includingforusesrelatedtotextanddatamining,AItraining,andsimilartechnologies.

±0.3kg.27 29 Weight prediction error is generally lower in younger, lighter children, consistent with our findings, which show smaller prediction errors in lighter/smaller infants (figure 2). Although the current accuracy of the LWAI tool is acceptable for parental use at home, we aim to refine its precision to meet more stringent standards for clinical practice and research applications, aiming for a weight and length prediction deviation within ±0.5kg and ±0.5cm. It is important to note that the currently reported prediction error includes both the tool’s prediction error and a human measurement error component, relative to the true value of length or weight. For instance, human error for gold-standard length measurement typically ranges from 0.5 cm to 0.7cm, which could account for a substantial fraction of the 1.89cm total prediction error reported for the LWAI tool. Therefore, we are developing evaluation methods to isolate and quantify the tool’s prediction error separately from human measurement error, enabling optimisation of the tool based on its true prediction error, and more meaningful comparisons of tool performance with human measurement.

In clinical settings, the tool could potentially reduce the burden on healthcare providers by simplifying growth assessment procedures. It could enable the seamless transfer of growth parameters into medical records, facilitating early alerts for abnormal growth patterns. By integrating into telemedicine and remote clinical care, the tool enables healthcare providers to track children’s anthropometric measurements from home, with follow-up conducted through virtual or telephone consultations. This reduces the need for in-person visits and helps alleviate clinic waiting times. While easy access to the tool may increase parental concern about the implications of measurements and demand for healthcare consultations, it also ensures consistent, repeatable and well-documented growth monitoring at a crucial stage of child development. Beyond individual care, and by contributing to the broader digital healthcare ecosystem, the tool has the potential for supporting large-scale public health programmes30, particularly in low-resource settings with limited access to clinical measurements, thereby contributing to global health promotion efforts.

We recognise the limitations of our study. As this study serves primarily as a proof of concept, a simple crosssectional design was implemented at a single centre involving a cohort of healthy children, which precludes exploration of the tool’s ability to monitor growth trends over time. The single-centre setting may limit the generalisability of the results, and excluding children with growth-related disorders limits the tool’s effectiveness in detecting or predicting abnormal growth patterns in high-risk populations, thereby constraining its applicability to apparently healthy infants and children.20 Future research should explore capabilities such as monitoring growth over time and assessing performance in more diverse populations, such as children with suspected growth issues, older children, as well as including a larger cohort to further refine and customise the LWAI tool

for a broader range of clinical applications. The tool has been further refined based on preliminary results, and ongoing projects are underway to evaluate the feasibility and acceptability of the improved version.

### CONCLUSION

Our study comprehensively evaluated the performance and usability of LWAI, demonstrating its feasibility in predicting body length and weight among infants and toddlers ≤18 months within clinical and household settings. The MAE/MAPE for grouped images was 0.56kg (9.02%) for weight and 1.89cm (3.18%) for length. Notably, length predictions using grouped images closely approximated the interobserver TEM typically achieved in paediatric clinics and community health settings. By harnessing AI capabilities and the widespread use of mobile devices, LWAI offers a practical and accessible alternative to conventional anthropometric measurement methods. As digital health technologies evolve, integrating AI-assisted tools like LWAI could significantly enhance the accessibility of regular early childhood growth assessment and improve health outcomes for children.

Author affiliations 1Duke-NUS Medical School, Singapore 2Endocrinology Service, Department of Paediatrics, KK Women's and Children’s Hospital, Singapore

- 3Department of Neonatology, KK Women's and Children’s Hospital, Singapore
- 4Danone Research & Innovation, Singapore


Acknowledgements Medical writing and editorial support were provided by Tech Observer Asia Pacific Pte Ltd. We also thank Ms. Brigitte Sim for her assistance in the successful execution of the study procedures.

Contributors All authors were jointly responsible for the study conception and design. DC, FY, MCC collaborated on participant recruitment, data acquisition and collection. JW contributed to funding acquisition and project management. MH and SM designed and implemented the AI algorithm and analysed the data. All authors contributed to the interpretation of the results; participated in drafting, reviewing and revising the manuscript; and approved the final version for submission. FY is the guarantor of this study.

Funding The study was funded by Danone Research & Innovation, Singapore. Competing interests JW, MH and SM are employees of Danone Global Research & Innovation. DC, MCC, and FY are investigators of this study. Patient consent for publication Not applicable.

Ethics approval This study involves human participants and was approved by the KK Women’s and Children’s Hospital’s independent ethics committee before its initiation (approval number: 2021/2540). Participants gave informed consent to participate in the study before taking part.

Provenance and peer review Not commissioned; externally peer reviewed. Data availability statement Data are available upon reasonable request.

Supplemental material This content has been supplied by the author(s). It has not been vetted by BMJ Publishing Group Limited (BMJ) and may not have been peer-reviewed. Any opinions or recommendations discussed are solely those of the author(s) and are not endorsed by BMJ. BMJ disclaims all liability and responsibility arising from any reliance placed on the content. Where the content includes any translated material, BMJ does not warrant the accuracy and reliability of the translations (including but not limited to local regulations, clinical guidelines, terminology, drug names and drug dosages), and is not responsible for any error and/or omissions arising from translation and adaptation or otherwise.

BMJHealth&CareInformatics:firstpublishedas10.1136/bmjhci-2025-101540on9December2025.Downloadedfromhttps://informatics.bmj.comon2May2026byguest. Protectedbycopyright,includingforusesrelatedtotextanddatamining,AItraining,andsimilartechnologies.

Open access This is an open access article distributed in accordance with the Creative Commons Attribution Non Commercial (CC BY-NC 4.0) license, which permits others to distribute, remix, adapt, build upon this work non-commercially, and license their derivative works on different terms, provided the original work is properly cited, appropriate credit is given, any changes made indicated, and the use is non-commercial. See: https://creativecommons.org/licenses/by-nc/4.0/.

2017 IEEE Global Humanitarian Technology Conference (GHTC);

- 2017:1–9.

- 15 Tang M, Sun M-T, Seda L, et al. Measuring infant’s length with an image. 2018 Asia-Pacific signal and information processing association annual summit and conference (APSIPA ASC);

2018:335–9.

- 16 Nah S, Choi S, Kang N, et al. An augmented reality mobile application for weight estimation in paediatric patients: A prospective single-blinded cross-sectional study. Ann Acad Med Singap 2023;52:660–8.
- 17 Bougma K, Mei Z, Palmieri M, et al. Accuracy of a handheld 3D imaging system for child anthropometric measurements in population-based household surveys and surveillance platforms: an effectiveness validation study in Guatemala, Kenya, and China. Am J Clin Nutr 2022;116:97–110.
- 18 Jefferds MED, Mei Z, Palmieri M, et al. Acceptability and Experiences with the Use of 3D Scans to Measure Anthropometry of Young Children in Surveys and Surveillance Systems from the Perspective of Field Teams and Caregivers. Curr Dev Nutr 2022;6:nzac085.
- 19 Andrews ET, Ashton JJ, Pearson F, et al. Handheld 3D scanning as a minimally invasive measuring technique for neonatal anthropometry. Clin Nutr ESPEN 2019;33:279–82.
- 20 Chua MC, Hadimaja M, Wong J, et al. Exploring the Use of a Length AI Algorithm to Estimate Children’s Length from Smartphone Images in a Real-World Setting: Algorithm Development and Usability Study. JMIR Pediatr Parent 2024;7:e59564.
- 21 Jamaiyah H, Geeta A, Safiza MN, et al. Reliability, technical error of measurements and validity of length and weight measurements for children under two years old in Malaysia. Med J Malaysia 2010;65 Suppl A:131–7.
- 22 de Onis M, WHO Multicentre Growth Reference Study Group. Reliability of anthropometric measurements in the WHO Multicentre Growth Reference Study. Acta Paediatr 2006;95:38–46.
- 23 World Health Organization. Training course on child growth assessment - WHO child growth standards. 2008.1–47.
- 24 Sohil F, Sohali MU, Shabbir J. An introduction to statistical learning with applications in r. In: Statistical theory and related fields, 6. 2022: 87.
- 25 Hastie T, Tibshirani R, Friedman J. The elements of statistical learning data mining, inference, and prediction. New York: Springer, 2009.
- 26 de Onis M, Onyango AW, Van den Broeck J, et al. Measurement and standardization protocols for anthropometry used in the construction of a new international growth reference. Food Nutr Bull 2004;25:S27–36.
- 27 Wright CM, Hope-McGill F, Sivakanthan H, et al. Short-term weight variability in infants and toddlers: an observational study. Arch Dis Child 2025;110:283–6.
- 28 Himes JH. Challenges of accurately measuring and using BMI and other indicators of obesity in children. Pediatrics 2009;124 Suppl 1:S3–22.
- 29 Carsley S, Parkin PC, Tu K, et al. Reliability of routinely collected anthropometric measurements in primary care. BMC Med Res Methodol 2019;19:84.
- 30 Chan D. Proactive steps to population health: Starting early, starting right. Ann Acad Med Singap 2023;52:278–9.




ORCID iD Fabian Yap https://orcid.org/0000-0003-1083-7958

### REFERENCES

- 1 de Onis M, WHO Multicentre Growth Reference Study Group. WHO Child Growth Standards based on length/height, weight and age. Acta Paediatr 2006;95:76–85.
- 2 Yap F, Lee YS, Aw MMH. Growth Assessment and Monitoring during Childhood. Ann Acad Med Singap 2018;47:149–55.
- 3 Kiernan BD, Mascarenhas M. Growth assessment and its significance. In: Vachani JG, ed. Failure to thrive and malnutrition: a practical, evidence-based clinical guide. Cham: Springer International Publishing, 2023: 33–72.
- 4 Smith A, Shah M, Badireddy M. Failure to thrive. 2023. Available: https://www.ncbi.nlm.nih.gov/books/NBK459287/
- 5 Young BE, Johnson SL, Krebs NF. Biological determinants linking infant weight gain and child obesity: current knowledge and future directions. Adv Nutr 2012;3:675–86.
- 6 Aris IM, Chen L-W, Tint MT, et al. Body mass index trajectories in the first two years and subsequent childhood cardio-metabolic outcomes: a prospective multi-ethnic Asian cohort study. Sci Rep 2017;7:8424.
- 7 Michael N, Gupta V, Fogel A, et al. Longitudinal characterization of determinants associated with obesogenic growth patterns in early childhood. Int J Epidemiol 2023;52:426–39.
- 8 Mwangome M, Berkley J. Measuring infants aged below 6 months: experience from the field. 2014. Available: https://www.ennonline. net/fex/47/measuring [Accessed 10 Sep 2024].
- 9 Laar ME, Marquis GS, Lartey A, et al. Reliability of length measurements collected by community nurses and health volunteers in rural growth monitoring and promotion services. BMC Health Serv Res 2018;18:118.
- 10 Mocini E, Cammarota C, Frigerio F, et al. Digital Anthropometry: A Systematic Review on Precision, Reliability and Accuracy of Most Popular Existing Technologies. Nutrients 2023;15:302.
- 11 Heymsfield SB, Bourgeois B, Ng BK, et al. Digital anthropometry: a critical review. Eur J Clin Nutr 2018;72:680–7.
- 12 Soller T, Huang S, Horiuchi S, et al. Portable digital devices for paediatric height and length measurement: A scoping review and target product profile matching analysis. PLoS One 2023;18:e0288995.
- 13 Kustiawan TC, Nadhiroh SR, Ramli R, et al. Use of mobile app to monitoring growth outcome of children: A systematic literature review. Digit Health 2022;8:205520762211386.
- 14 Fletcher R, Diaz XS, Bajaj H, et al. Development of smart phonebased child health screening tools for community health workers.


BMJHealth&CareInformatics:firstpublishedas10.1136/bmjhci-2025-101540on9December2025.Downloadedfromhttps://informatics.bmj.comon2May2026byguest. Protectedbycopyright,includingforusesrelatedtotextanddatamining,AItraining,andsimilartechnologies.

