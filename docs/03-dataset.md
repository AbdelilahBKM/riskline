# Dataset: Default of Credit Card Clients

- Source: UCI Machine Learning Repository, dataset id 350 (Yeh, I-C., 2009)
- DOI: 10.24432/C55S3H
- License: CC BY 4.0 (attribution required; keep this notice in the README)
- Format: single .xls file, ~5.3 MB, 30,000 rows
- Task: binary classification
- Target: `default payment next month` (1 = default, 0 = no default)
- Class balance: ~21% positive / ~79% negative

## Feature groups
- Credit: LIMIT_BAL
- Demographics: SEX, EDUCATION, MARRIAGE, AGE
- Repayment status history: PAY_0, PAY_2 ... PAY_6 (ordinal codes)
- Bill amounts: BILL_AMT1 ... BILL_AMT6
- Payment amounts: PAY_AMT1 ... PAY_AMT6

## Known data-quality issues (handled in Phase 2 validation)
- Duplicate rows
- Undocumented category values in EDUCATION, MARRIAGE and PAY_*
- Overlapping time windows across the six monthly columns
- Header row offset in the .xls (data starts on the second row)
- Column naming is inconsistent (PAY_0 has no PAY_1)

## Caveats
- Taiwan, April-September 2005: not representative of any current lending
  population. This is a learning model, not a credit model.
- SEX, AGE and MARRIAGE are protected attributes in real credit scoring.
  Kept here for the learning exercise; no fairness validation is performed.