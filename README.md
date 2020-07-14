# ClinicalTextClassification


In this notebook i implement clinical text classfication on the medical transcription dataset from kaggle
Here we look at Medical Transcriptions dataset from Kaggle https://www.kaggle.com/tboyle10/medicaltranscriptions

Pre-requisites: 

1)NLTK: https://github.com/nltk/nltk 

2)Pandas: https://pandas.pydata.org/

3)Matplotlib: https://matplotlib.org/ 

4)scikit-learn : https://scikit-learn.org/stable/index.html

5)spaCy (https://spacy.io/)

6)https://imbalanced-learn.readthedocs.io/en/stable/#


This data was scraped from mtsamples.com

The task is to correcrtly classify the medical specialties based on the transcription text

Here is the disctibution of samples in the dataset per medical specilaty

Number of sentences in transcriptions column: 140214

Number of unique words in transcriptions column: 35822

===========Original Categories =======================

Cat:1  Allergy / Immunology : 7

Cat:2  Autopsy : 8

Cat:3  Bariatrics : 18

Cat:4  Cardiovascular / Pulmonary : 371

Cat:5  Chiropractic : 14

Cat:6  Consult - History and Phy. : 516

Cat:7  Cosmetic / Plastic Surgery : 27

Cat:8  Dentistry : 27

Cat:9  Dermatology : 29

Cat:10  Diets and Nutritions : 10

Cat:11  Discharge Summary : 108

Cat:12  ENT - Otolaryngology : 96

Cat:13  Emergency Room Reports : 75

Cat:14  Endocrinology : 19

Cat:15  Gastroenterology : 224

Cat:16  General Medicine : 259

Cat:17  Hematology - Oncology : 90

Cat:18  Hospice - Palliative Care : 6

Cat:19  IME-QME-Work Comp etc. : 16

Cat:20  Lab Medicine - Pathology : 8

Cat:21  Letters : 23

Cat:22  Nephrology : 81

Cat:23  Neurology : 223

Cat:24  Neurosurgery : 94

Cat:25  Obstetrics / Gynecology : 155

Cat:26  Office Notes : 50

Cat:27  Ophthalmology : 83

Cat:28  Orthopedic : 355

Cat:29  Pain Management : 61

Cat:30  Pediatrics - Neonatal : 70

Cat:31  Physical Medicine - Rehab : 21

Cat:32  Podiatry : 47

Cat:33  Psychiatry / Psychology : 53

Cat:34  Radiology : 273

Cat:35  Rheumatology : 10

Cat:36  SOAP / Chart / Progress Notes : 166

Cat:37  Sleep Medicine : 20

Cat:38  Speech - Language : 9

Cat:39  Surgery : 1088

Cat:40  Urology : 156

==================================

I try to perform classification on reduced dataset which has the distribution as follows:

============Reduced Categories ======================

Cat:1  Cardiovascular / Pulmonary : 371

Cat:2  Consult - History and Phy. : 516

Cat:3  Discharge Summary : 108

Cat:4  ENT - Otolaryngology : 96

Cat:5  Emergency Room Reports : 75

Cat:6  Gastroenterology : 224

Cat:7  General Medicine : 259

Cat:8  Hematology - Oncology : 90

Cat:9  Nephrology : 81

Cat:10  Neurology : 223

Cat:11  Neurosurgery : 94

Cat:12  Obstetrics / Gynecology : 155

Cat:13  Ophthalmology : 83

Cat:14  Orthopedic : 355

Cat:15  Pain Management : 61

Cat:16  Pediatrics - Neonatal : 70

Cat:17  Psychiatry / Psychology : 53

Cat:18  Radiology : 273

Cat:19  SOAP / Chart / Progress Notes : 166

Cat:20  Surgery : 1088

Cat:21  Urology : 156

============ Reduced Categories ======================

Applying domain knowledge i further reduce this dataset for meaningful results:

===========Reduced Categories======================

Cat:1 Cardiovascular / Pulmonary : 371

Cat:2 ENT - Otolaryngology : 96

Cat:3 Gastroenterology : 224

Cat:4 Hematology - Oncology : 90

Cat:5 Neurology : 317

Cat:6 Obstetrics / Gynecology : 155

Cat:7 Ophthalmology : 83

Cat:8 Orthopedic : 355

Cat:9 Pediatrics - Neonatal : 70

Cat:10 Psychiatry / Psychology : 53

Cat:11 Radiology : 273

Cat:12 Urology : 237

============Reduced Categories======================

On this dataset i get around 67% accuracy. 

The conclusions are:

This dataset is very noisy.

Lot of text in transcriptions overlaps across categories

We can apply domain knowledge to reduce the categories

It is imbalanced dataset and using SMOTE can improve the results

Hand coded features may improve results on this dataset but may not apply to generic transcription datasets.



