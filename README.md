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
```



### 2. Students with TOEFL Scores Greater than 110
Identify the number of students with a TOEFL score greater than 110.
mean_gre_score = grad_students['GRE_Score'].mean()
print(f'The average GRE score of the students is {mean_gre_score}.')
```python
t_score_gt_110 = len(grad_students[grad_students['TOEFL_Score']>110])
print(f'The number of students having TOEFL Score greater than 110 is {t_score_gt_110}.')

```



### 3. Students Who Conducted Research
Count how many students have conducted research.

```python
no_of_research_stds = len(grad_students[grad_students["Research"]==1])
print(f"Total of {no_of_research_stds} students conducted research.")
```



### 4. Highest Chance of Admit
Identify the student(s) with the highest chance of admission and their GRE scores.

```python
highest_chance = grad_students[grad_students['Chance_of_Admit']==grad_students['Chance_of_Admit'].max()]
highest_chance_gre = highest_chance['GRE_Score']
print("Students who have the highest chance of admit: ")
print(highest_chance)
print(f"Their GRE scores are: {highest_chance_gre}")
```


### 5. Top Students for Scholarships
Filter students with TOEFL scores greater than 110, find those with the highest GRE scores, and ensure the top three have a perfect SOP score.

```python
higher_toefl = grad_students[grad_students['TOEFL_Score']>=110]
higher_gre = higher_toefl[higher_toefl['GRE_Score']==higher_toefl["GRE_Score"].max()]
top_three = higher_gre[higher_gre['SOP']==higher_gre["SOP"].max()]
top_three = sorted(top_three, key=lambda x: x['CGPA'], reverse=1)
top_three = np.array(top_three)
print("These are the top three students: ")
print(top_three)
```



### Key Findings
- **Average GRE Score**: The average GRE score of the students is 316.81.
- **High TOEFL Scores**: 120 students have a TOEFL score greater than 110.
- **Research Experience**: 219 students have conducted research.
- **Top Admission Chances**: The highest chance of admission is held by students with GRE scores of 336, 340, and 334.
- **Top Candidates for Scholarships**: The top three students, identified by high TOEFL and GRE scores and perfect SOP scores, have CGPAs of 9.74, 9.66, and 9.50 respectively.



### Conclusion
This project demonstrates the use of Python and NumPy for a structured analysis of student admission data. By identifying top candidates based on key academic metrics, it provides a data-driven approach to awarding scholarships. This method ensures that scholarships are granted to the most deserving students, thereby enhancing the selection process.
