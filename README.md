# Scholarship Seeker: A Data-Driven Approach to Student Selection

## Overview

**Scholarship Seeker** is a project that leverages Python and NumPy to analyze graduate student admission data. The primary goal is to identify top candidates for scholarships based on various academic and extracurricular metrics. This analysis helps in making data-driven decisions to award scholarships to the most deserving students.

## Dataset

The dataset (`admission.csv`) includes the following columns:
- **Serial No.**: Unique identifier for each student.
- **GRE Score**: Graduate Record Examination score.
- **TOEFL Score**: Test of English as a Foreign Language score.
- **University Rating**: Rating of the university the student applied to.
- **SOP**: Statement of Purpose strength (out of 5).
- **LOR**: Letter of Recommendation strength (out of 5).
- **CGPA**: Undergraduate GPA (out of 10).
- **Research**: Binary value indicating whether the student has research experience (1 for Yes, 0 for No).
- **Chance of Admit**: Probability of admission (out of 1).

## Key Analyses

### 1. Average GRE Score
Calculate the average GRE score of the students.
```python
mean_gre_score = grad_students['GRE_Score'].mean()
print(f'The average GRE score of the students is {mean_gre_score}.')
