# Student Performance Analysis

Exploratory data analysis and prediction of final mathematics grades of secondary-school students from two Portuguese schools.

## Dataset

`student-mat.csv` contains 395 students and 33 variables (demographics, family, study habits, lifestyle, absences and three grades `G1`, `G2`, `G3` on a 0-20 scale).
Source: UCI Machine Learning Repository, *Student Performance* dataset (P. Cortez and A. Silva, 2008). See the UCI page for the dataset license.

## Research questions

1. What does the sample look like (sex, school, age)?
2. How are final grades distributed, and do they differ by sex or school?
3. Which factors are related to the final grade `G3`?
4. How well can linear regression predict `G3`, with and without the previous grades `G1` and `G2`?
5. Can logistic regression predict whether a student passes (`G3` >= 10)?

## Main findings

- `G3` is very strongly correlated with `G2` (r = 0.90) and `G1` (r = 0.80). Past failures have the strongest negative correlation among the other variables (r = -0.36).
- Linear regression: test R² = 0.77 with `G1` and `G2`, but only about 0.13 without them.
- Logistic regression (pass/fail): accuracy 0.91 with `G1` and `G2`; without them accuracy is 0.67, the same as always predicting "passed".
- 38 students have `G3 = 0`; the reason is not known, so the analysis is repeated without them.
- The data is observational, so the results show associations, not causes.

## Files

| File | Description |
|---|---|
| `student_analysis.ipynb` | Full analysis notebook |
| `student-mat.csv` | Dataset |
| `requirements.txt` | Python packages |

## How to run

```bash
pip install -r requirements.txt
jupyter notebook student_analysis.ipynb
```

Keep `student-mat.csv` in the same folder as the notebook.
