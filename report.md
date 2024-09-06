# HHA 507 Assignment
#### This is a report file that will be explaining the analysis, the code, key findings, and any challenges that was faced during this assignment. I will also be reflecting on the implictions of my findings for healthcare providers and policy makers.

### The Analysis
  - Data was loaded from 'https://data.cms.gov/sites/default/files/2023-04/67157de9-d962-4af0-bf0e-3578b3afec58/inpatient.csv'
  - I found random codes that I wanted to explore namely:
      - PRNCPAL_DGNS_CD : this code identifies the primary reason for a patient's admission and is considered their primary diagnosis
      - ICD_DGNS_CD1 : this code is the first in a series of diagnosis code
      - ICD_PRCDR_CD1 : this code identifies the main medical procedure performed during patient's visit (in this case inpatient)
      - CLM_DRG_CD : this code can be useful for analyzing financial aspects as it relates to DRG (diagnosis-related group)
      - ADMTG_DGNS_CD: this code indiciates the dianosis made at time of admission. Can be important to track changes in patient's LOS (length of stay)
      - HCPCS_CD : this code is used for billing Medicare and Medicaid, and covering procedures and services. Important from financial aspects
      - FST_DGNS_E_CD : this code hiighlights contributing factors to the patient's health (e.g., enviromental factors, accidents, etc.)
      - NCH_DRG_OUTLIER_APRVD_PMT_AMT : this code is the payment amount that is outside the typical DRG payment because of high cost association
  -  All explaination of the codes are found in the "codebook-ffs-claims.pdf" found at cms.gov
  -  The medical codex data was then analyzed including determining any missing or null values in the codex-related columns
  -  A summary of the most common codes were found in the dataset such if certain DRG codes are more common and when ICD codes are specific values for E11, which is for Type 2 Diabetes

### The Code
  - To load data and separate them due to "|":

 ` data = pd.read_csv('https://data.cms.gov/sites/default/files/2023-04/67157de9-d962-4af0-bf0e-3578b3afec58/inpatient.csv', sep='|') `

  - To display the first few rows of the dataset:

  `print(data.head()) `

  - To see a the header of the columns in an easier way:
    ` for i in data.columns:
      print(i) `
    
  -  To identify columns related to medical codexes:
 
`pricipal_dgns = data['PRNCPAL_DGNS_CD']`

 `icd_DGNS_code1 = data['ICD_DGNS_CD1'] `

`icd_PRCDR_code1 = data['ICD_PRCDR_CD1'] `

`clm_DRG_code = data['CLM_DRG_CD'] `

`admtg_DGNS_code = data['ADMTG_DGNS_CD'] `

`hcpcs_code = data['HCPCS_CD'] `

`fst_FGNS_E_code = data['FST_DGNS_E_CD'] `

`outlier_amt = data['NCH_DRG_OUTLIER_APRVD_PMT_AMT'] `
    
  -  To analyze the frequency of each unique value. For example:

`pricipal_dgns_frequency = pricipal_dgns.value_counts()
print("Principal Diagnosis Codes Frequency:\n", pricipal_dgns_frequency) `

  -  To handle missing values. For example:

`missing_principal_dgns = pricipal_dgns.isnull().sum() `

  -  For summary section. For example, top 5 most common codes for Principal Diagnosis Codes:

` print("Top 5 Most Common ICD Diagnosis Code 1:\n", icd_DGNS_frequency1.head(5)) `


### Key and Intersting Findings

  - Z733 is the most common principal diagnos and ICD code 1, which relates to lifestyle influence
  - Z7682 is the most common for admitting dianosis which is for organ transplant
  - W86 is the most common external cause code which is the exposure to eletric currents
  - CLM_DRG_CD 10.0 is the most common among patients with Type 2 diabetes


### Challenges 

  - Very new to coding so lots of copying and pasting error
  - Trying to stay consistent with naming data is a bit of a headache and also looking up what the codes meant
  - Trying to understand when an error occured, luckily the AI on Google colab helped a bit
  - Not quite sure what the message after `print(data.head())` is trying to tell me

### Implications
  -  Z733 being the most common diagnoses among inpatient population suggests that lifestyle or behavior-related issues is a health concern. This is important for policymakers and heatlhcare providers to perhaps focus on lifestyle or behaviors of patients such as social determinants of health, patient education,and prevention.
    - Understanding most frequent diagnosis can help policymakers focus on the right areas.









