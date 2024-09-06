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


