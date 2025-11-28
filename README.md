# BioInsight

## Purpose
The purpose of this code notebook is to preprocess **BRFSS survey data 2024** into a useable format for prediction diabetes into **3 classes**:
1. No Diabetes
2. Pre-Diabetes
3. Diabetes (Type 2 only).

The dataset originally has **457,670 survey** responses and **301 features (columns)**, but based on diabetes disease research regarding factors influencing Type 2 diabetes disease, only selected features are included in this analysis.


**Link to Dataset:** [Diabetes Health Indicators Dataset](https://www.kaggle.com/datasets/rudritarahman/cdc-brfss-survey-data-2024)

## Extracted Features
The following features will be extracted from the original dataset:

**Data Filtering:**

* `PREDIAB2`: (Ever told) (you had) diabetes?  (If it's Yes and respondent is female, ask was this only when you were pregnant? If Respondent says pre-diabetes or borderline diabetes, use response code 4.)

  | Value | Value Label |
  | :------- | :------: |
  | 1	| Yes |
  | 2	| Yes, but female told only during pregnancy |
  | 3	| No |
  | 4	| No, pre-diabetes or borderline diabetes |
  | 7	| Don't know/Not Sure |
  | 9	| Refused |
  | BLANK	| Not asked or Missing |


* `DIABETE4`: (Ever told) (you had) diabetes?  (If it's Yes and respondent is female, ask was this only when you were pregnant? If Respondent says pre-diabetes or borderline diabetes, use response code 4.)

  | Value | Value Label |
  | :------- | :------: |
  | 1	| Yes |
  | 2	| Yes, but female told only during pregnancy |
  | 3	| No |
  | 4	| No, pre-diabetes or borderline diabetes |
  | 7	| Don't know/Not Sure |
  | 9	| Refused |
  | BLANK	| Not asked or Missing |


* `DIABTYPE`: According to your doctor or other health professional, what type of diabetes do you have?

  | Value | Value Label |
  | :------- | :------: |
  | 1	| Type 1 |
  | 2	| Type 2 |
  | 7	| Don't know/Not Sure |
  | 9	| Refused |
  | BLANK	| Not asked or Missing |


---


**Main Features:**

* `_AGEG5YR`: Fourteen-level age category

  | Value | Value Label |
  | :------- | :------: |
  | 1	| Age 18 to 24 |
  | 2	| Age 25 to 29 |
  | 3	| Age 30 to 34 |
  | 4	| Age 35 to 39 |
  | 5	| Age 40 to 44 |
  | 6	| Age 45 to 49 |
  | 7	| Age 50 to 54 |
  | 8	| Age 55 to 59 |
  | 9	| Age 60 to 64 |
  | 10	| Age 65 to 69 |
  | 11	| Age 70 to 74 |
  | 12	| Age 75 to 79 |
  | 13	| Age 80 or older |
  | 14	| Don't know/Refused/Missing |


* `_SEX`: Calculated sex variable

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Male |
  | 2 | Female |
  | BLANK | Not asked or Missing |


* `_RACE`: Race/ethnicity categories

  | Value | Value Label |
  | :------- | :------: |
  | 1 | White only, non-Hispanic |
  | 2 | Black only, non-Hispanic |
  | 3 | American Indian or Alaskan Native only |
  | 4 | Asian only |
  | 5 | Native Hawaiian or other Pacific Islander only |
  | 6 | Other race only, non-Hispanic |
  | 7 | Multiracial, non-Hispanic |
  | 8 | Hispanic |
  | 9 | Don’t know/Refused/Missing |


* `WTKG3`: Reported weight in kilograms

  | Value | Value Label |
  | :------- | :------: |
  | 2300 - 29500 | Weight in kilograms [2 implied decimal places] |
  | BLANK  | Don’t know/Refused/Not asked or Missing |


* `HTM4`: Reported height in meters

  | Value | Value Label |
  | :------- | :------: |
  | 91 - 244 | Height in meters [2 implied decimal places] |
  | BLANK | Don’t know/Refused/Not asked or Missing |


* `_BMI5`: Body Mass Index (BMI)

  | Value | Value Label |
  | :------- | :------: |
  | 1 - 9999 | 1 or greater [2 implied decimal places] |
  | BLANK | Don’t know/Refused/Missing |


* `_BMI5CAT`: Four-categories of Body Mass Index (BMI)

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Underweight (< 18.50) |
  | 2 | Normal Weight (18.50 - < 25.00) |
  | 3 | Overweight (25.00 – < 30.00) |
  | 4 | Obese (30.00 - < 99.99) |
  | BLANK | Don’t know/Refused/Missing |


* `_TOTINDA`: Adults who reported doing physical activity or exercise during the past 30 days other than their regular job

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Had physical activity or exercise |
  | 2 | No physical activity or exercise in last 30 days |
  | 9 | Don’t know/Refused/Missing |


* `EDUCA`: What is the highest grade or year of school you completed?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Never attended school or only kindergarten |
  | 2 | Grades 1 through 8 (Elementary) |
  | 3 | Grades 9 through 11 (Some high school) |
  | 4 | Grade 12 or GED (High school graduate) |
  | 5 | College 1 year to 3 years (Some college or technical school) |
  | 6 | College 4 years or more (College graduate) |
  | 9 | Don’t know/Refused/Missing |


* `INCOME3`:  Is your annual household income from all sources:  (If respondent refuses at any income level, code it Refused)

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Less than \$10,000 |
  | 2 | \$10,000 to < \$15,000 |
  | 3 | \$15,000 to < \$20,000 |
  | 4 | \$20,000 to < \$25,000 |
  | 5 | \$25,000 to < \$35,000 |
  | 6 | \$35,000 to < \$50,000 |
  | 7 | \$50,000 to < \$75,000 |
  | 8 | \$75,000 to < \$100,000 |
  | 9 | \$100,000 to < \$150,000 |
  | 10 | \$150,000 or more |
  | 77 | Don’t know/Not sure |
  | 99 | Refused |
  | BLANK | Missing |


* `MARITAL`: Are you: (marital status)

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Married |
  | 2 | Divorced |
  | 3 | Widowed |
  | 4 | Separated |
  | 5 | Never married |
  | 6 | Member of unmarried couple |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `_RFDRHV9`: Heavy drinkers (adult men having more than 14 drinks per week and adult women having more than 7 drinks per week)

  | Value | Value Label |
  | :------- | :------: |
  | 1 | No |
  | 2 | Yes |
  | 9 | Don’t know/Refused/Missing |


* `_RFBING6`: Binge drinkers (males having five or more drinks on one occasion, females having four or more drinks on one occasion)

  | Value | Value Label |
  | :------- | :------: |
  | 1 | No |
  | 2 | Yes |
  | 9 | Don’t know/Refused/Missing |


* `_SMOKER3`: Four-level smoker status:  Everyday smoker, Someday smoker, Former smoker, Non-smoker

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Current smoker - now smokes every day |
  | 2 | Current smoker - now smokes some days |
  | 3 | Former smoker |
  | 4 | Never smoked |
  | 9 | Don’t know/Refused/Missing |


* `_MENT14D`: 3 level not good mental health status: 0 days, 1-13 days, 14-30 days

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Zero days when mental health not good |
  | 2 | 1–13 days when mental health not good |
  | 3 | 14+ days when mental health not good |
  | 9 | Don’t know/Refused/Missing |


* `_PHYS14D`:  3 level not good physical health status: 0 days, 1-13 days, 14-30 days

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Zero days when physical health not good |
  | 2 | 1-13 days when physical health not good |
  | 3 | 14+ days when physical health not good |
  | 9 | Don’t know/Refused/Missing |


* `GENHLTH`: Would you say that in general your health is:

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Excellent |
  | 2 | Very good |
  | 3 | Good |
  | 4 | Fair |
  | 5 | Poor |
  | 7 | Don’t know/Not Sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `ADDEPEV3`: (Ever told) (you had) a depressive disorder (including depression, major depression, dysthymia, or minor depression)?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `CHCOCNC1`: (Ever told) (you had) melanoma or any other types of cancer?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `CHCSCNC1`: (Ever told) (you had) skin cancer that is not melanoma?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `CVDCRHD4`: (Ever told) (you had) angina or coronary heart disease?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `CVDINFR4`: (Ever told) you had a heart attack, also called a myocardial infarction?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `CVDSTRK3`: (Ever told) (you had) a stroke?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `HAVARTH4`:  (Ever told) (you had) some form of arthritis, rheumatoid arthritis, gout, lupus, or fibromyalgia?  (Arthritis diagnoses include: rheumatism, polymyalgia rheumatic, osteoarthritis (not osteoporosis), tendonitis, bursitis, bunion, tennis elbow, carpal tunnel syndrome, tarsal tunnel syndrome, joint infection, Reiterates syndrome, ankylosing spondylitis;)

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `CHCKDNY2`: Not including kidney stones, bladder infection or incontinence, were you ever told you had kidney disease?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `CHCCOPD3`: (Ever told) (you had) C.O.P.D. (chronic obstructive pulmonary disease), emphysema or chronic bronchitis?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `MEDCOST1`: Was there a time in the past 12 months when you needed to see a doctor but could not because you could not afford it?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes |
  | 2 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `PDIABTS1`: When was the last time you had a blood test for high blood sugar or diabetes by a doctor, nurse, or other health professional?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Within the past year (anytime less than 12 months ago) |
  | 2 | 	Within the past 2 years (1 year but less than 2 years) |
  | 3 | 	Within the past 3 years (2 years but less than 3 years) |
  | 4 | Within the past 5 years (3 to 4 years but less than 5 years ago) |
  | 5 | Within the past 10 years (5 to 9 years but less than 10 years ago) |
  | 6 | 10 years ago or more |
  | 7 | Don’t know/Not sure |
  | 8 | Never |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `CHECKUP1`: About how long has it been since you last visited a doctor for a routine checkup?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Within past year (anytime less than 12 months ago) |
  | 2 | Within past 2 years (1 year but less than 2 years ago) |
  | 3 | Within past 5 years (2 years but less than 5 years ago) |
  | 4 | 5 or more years ago |
  | 7 | Don’t know/Not sure |
  | 8 | Never |
  | 9 | Refused |
  | BLANK | Not asked or Missing |


* `PERSDOC3`: Do you have one person or a group of doctors that you think of as your personal health care provider?

  | Value | Value Label |
  | :------- | :------: |
  | 1 | Yes, only one |
  | 2 | More than one |
  | 3 | No |
  | 7 | Don’t know/Not sure |
  | 9 | Refused |
  | BLANK | Not asked or Missing |
