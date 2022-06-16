# School District Analysis
***Evaluating how Falsified Grades Impacted a School District***
#### by Justin R. Papreck
---

## Overview

The competition getting into colleges and universities is extreme, and it is absolutely critical that the schools and students are evaluated fairly across the country. A particular school district evaluated their schools and rankings based on the assumption that the grades were unaltered and fairly reported; however it was indicated that the 9th grade scores from math and reading at Thomas High School had been altered. The impact that this would have on the school's upper classmen as well as on the other schools in the district could be massively impacted depending on the severity of the altered grades. 

### Purpose

Using Python with Pandas, the data were cleaned and evaluated, comparing the values with all students to those after removing the questionable scores. Becuase of the nature of this information, several parameters had to be investigated: 
1. The overall district performance in math, reading, and passing rates
2. The performance summaries per schoool 
3. The school ranks within the district
4. Performance in math and reading by grade
5. Metrics on performance compared to spending per student
6. Metrics on performance compared to school size
7. Metrics on performance compared to school type

---
## Results and Analysis

It was determined that despite the grade discrepancies at Thomas High School, there was not a major impact on any of the parameters investigated, though there were changes up to 1% across some of the parameters. 

---
### Overall District Performance

It's important to evaluate the overall district performance, not only from within the district but also on a state level, especially if some schools are expecting state-allocated funds. As originally analayzed, the math and reading scores had been inflated, as can be seen when comparing the the figures before and after the removal of the Thomas HS 9th graders. 
- The 9th grade at Thomas HS was made up of 461 students, out of the 39,170 students in the district
- After their scores were removed, the average math score dropped by 0.06 points
- After their scores were removed, the average reading score dropped by 0.02 points 
- The percentage of students who passed math dropped from 75.0% to 74.8%
- The percentage of students who passed reading dropped from 85.8% to 85.7%
- The overall percentage of students who passed dropped from 65.2% to 64.9%

![District_Summary_1](https://user-images.githubusercontent.com/33167541/174171630-343eb82d-16ab-4477-8ff9-eb6da209181a.png)


![District_Summary_2](https://user-images.githubusercontent.com/33167541/174171637-a8956a8a-0908-4f57-ae02-236c101344e2.png)


While these numbers seem small, if the trends follow with the 9th graders at Thomas HS, this could potentially indicated that students that would have potentially failed had their grades inflated such that they would pass, impacting the pass rates. This would not have been impacted if only passing students had passed their courses. 

---
### Performance Summaries Per School

When looking at the individual schools, the parameters considered were the type of school: district or charter, total number of students, school budget and budget per student, and then the average scores and passing frequencies based on math and reading. The summary only changed for Thomas HS after the removal of the 9th grade scores, as shown in the second figure. The school type, total students, total budget, and per student budget did not change after the modifications, as expected. The scores for math and reading and subsequent percentages changed. 
- Average math score decreased from 83.42 to 83.35
- Average reading score increased from 83.85 to 83.90
- The percentage of students who passed math decreased from 93.27 to 93.19
- The percentage of students who passed reading decreased from 97.31 to 97.02
- The overall pass rate of students decreased from 90.95 to 90.63

![School_Summary_1](https://user-images.githubusercontent.com/33167541/174184668-581a4566-610b-495b-b959-2359e7063545.png)


![School_Summary_2](https://user-images.githubusercontent.com/33167541/174184699-53d79506-3d5c-4407-856a-385808f4c0e7.png)


  The decreasing average in math is consistent with the drop in percentage of passing students in math, which further supports that students below the passing threshold had inflated grades, artificially showing a higher pass rate than was achieved. The most interesting statistic is the increased average reading score after the removal of the 9th grade, which indicates that at least one of the 9th graders potentially had artificially lowered grades instead of inflated grades. While this seemingly contradicts the finding that the passing rate decreased, this isn't a logical conclusion. The mean can be impacted heavily by the extremes, whereas the number of grades just above or below the threshold of passing will not be influenced by massive changes at the extreme. One student earning a 99 can have their score dropped to a 70.1 (perhaps by a malicious programmer), and while they still pass, the average score would drop. Removing such a discrepancy could account for the increase in the reading average despite the decreased number of passing students.  
