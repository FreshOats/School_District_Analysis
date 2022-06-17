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


---
### Ranking the Top and Bottom Schools
One of the biggest issues in contention is whether Thomas High School will maintain it's rank when accounting for the aberrant scores. Based on the initial analysis, Thomas High School ranked in the top 5 schools in the district at #2. This discrepancy has the potential to change their ranking, as the overall passing rates of most of the top 5 are within hundredths of a percent of one another. 

![Top_5_1](https://user-images.githubusercontent.com/33167541/174186457-b4fbf090-1f3d-474d-878e-3dae7eded747.png)


![Top_5_2](https://user-images.githubusercontent.com/33167541/174186516-191bd629-98b8-4c12-81ba-80595ea4485c.png)


With such a close distribution of passing rates, it's important to verify where Thomas High School should stand with respect to passing rates:
- After the removal of 9th grade scores, the Overall passing rate changed from 90.95% to 90.63%
- The math passing rate changed from 93.27% to 93.19%
- The reading passing rate changed from 97.31% to 97.02%

While all of the passing rates decreased with the modification, the ranking by Overall Passing Rate did not change, as Thomas HS still stood a few hundredths of a point ahead of Griffin High School. As Thomas was in the top 5, the bottom 5 schools were not affected by these data, and are presented below:

![Bottom_5](https://user-images.githubusercontent.com/33167541/174188536-29e158e8-8d39-4a1a-9cf5-57bc915ed641.png)


---
### Performance by Grade
#### Math Scores
Clearly the performance metric by grade cannot be analyzed with the 9th grade at Thomas High School. Within the other schools, the performance per year is fairly consistent, and the Thomas HS data before the removal suggest that this is still the case. In the case of math, there is a much broader variance in the math scores across schools than within schools by year. 
- Huang High School has the lowest score of 75.9 in the tenth grade, with an average across grades of 76.6
- Holden High School has the highest score of 85.0 in the 11th grade, with an average across grades of 83.8
- The range of math scores across the high schools is 9.1 points
- Thomas High School reported 83.6 for the 9th grade
- Thomas High School had an average of 83.4 only considering the 10th, 11th, and 12th grades

![Math_by_Grade_1](https://user-images.githubusercontent.com/33167541/174189880-d8561d1b-1c78-4269-88aa-ebeef838f148.png)


![Math_by_Grade_2](https://user-images.githubusercontent.com/33167541/174190128-1a369acb-de1f-46e9-a810-fdcce125139b.png)


These data show that the math programs within each school are consistent throughout the 4 years of education, which shows the district where to potentially focus on hiring better math teachers. Reading on the other hand did not have such a broad variance across the schools.

#### Reading Scores
In reading, all of the grades at all of the schools maintained an average above 80.0. 
- Huang High School has the lowest score of 80.3 in the 12th grade, with an average of 81.1
- Holden High school has the highest score of 84.7 in the 12th grade, with an average of 83.9
- The range of reading scores across the high schools is 4.4 points
- Thomas High School reported 83.7 for the 9th grade
- Thomas High School had an average of 83.9 considering only the 10th, 11th, and 12th grades

![Reading_by_Grade_1](https://user-images.githubusercontent.com/33167541/174190921-3ecf57e8-e28b-44aa-944d-fae7b95e0a15.png)


![Reading_by_Grade_2](https://user-images.githubusercontent.com/33167541/174190932-b8b99089-5daa-4821-bcf7-d7cde09932d6.png)


These data show that there is more consistency across the schools' reading programs than the math programs. 


---
### Performance by Budget per Student
Considering which schools have the highest and lowest math and reading scores, Holden and Huang, respectively, it's important to determine whether it's a funding issue, size issue, or something else altogether. In evaluating the the school's budget per student, one would expect that the students with more funding will generally have better scores. Schools were separated into 4 groups based on quartiles of the budget distribution. Following the adjustment for the 9th grade removal from Thomas High School, the following changes were reported in the _$631-645_ range:
- Average Math Score dropped 0.02 points
- Average Reading Score increased 0.02 points
- % Passing math did not change
- % Passing reading dropped by 0.1%
- % Overall passing dropped by 0.1% 

![Scores_per_Capita_2](https://user-images.githubusercontent.com/33167541/174191380-24e35b03-88ee-48ed-b5ca-2b926d1016ef.png)


Interestingly, the opposite effect of the expectation is what is observed - an effect that wasn't changed at all with the adjustments to the data following the Thomas HS data removal. The schools with the highest passing rate had the least funding per student, and the correlation continued; as the money per student increased, the overall passing rate decreased. 
  There are many possible explanations for this: size, exclusivity, school type, student to teacher ratio... The data for school type and size is available, but the other aspects are mentioned because this is a drastic correlation, and prior to making any concrete conclusions, it is important to consider as many factors as possible.
  
--- 
### Performance by School Size
The last data showed that the schools with more money per student actually had lower scores and pass rates in reading, math, and overall. School size presents a different consideration. Initially, the analysis grouped schools with fewer than 1000 students together, then schools from 1000 to 2500 students, and then schools with greater than that amount. In this district, that grouped most of the schools in the last group and very few in the first group. Similar to the grouping in the budget per student, the sizes were broken up by where they fall in the distribution, but keeping together schools very close in number of students. There was a good splitting point at 1800 students and then schools above 3000. Once again, after adjusting for the Thomas High School affair, the following changes were noted in "Small(<1799)" schools: 
- Average math score decreased by 0.01 point
- Average reading score decreased by 0.01 point
- Math passing rate did not change
- Reading passing rate decreased by 0.1%
- Overall passing rate did not change


![Scores_by_Size_2](https://user-images.githubusercontent.com/33167541/174193308-9c9ab355-4377-477e-8bc7-33e6baee2f03.png)


These data presented that the smaller schools performed better in all respects than did the medium schools, which in turn did better in all respects than the large schools. When considering this information with the performance compared to the budget per student, it would seemingly suggest that school size correlates with the budget per student, though this is not the case. Holden High School is small and has a low budget, and it is the top performing school. Huang High School on the other hand has a high budget per student, but it is only a medium school. Within the medium schools, there is a clear division where some schools tout an overall passing rate over 90% whereas others are below 55%. One thing is clear though: none of the large schools, all of which are in the upper half of per student budgets, have a passing rate higher than 55%. This suggests that the size of school is a better indicator of passing rate than the amount spent, however, the divide in the mid-size schools needs to be further investigate by school type. 


--- 
### Success by School Type
Two types of schools are in the public school district investigated: district schools and charter schools. None of the charter schools are large; the largest charter has 2283 students, which is far from being a small school. 
- The range of number of students of charter schools is 1856, with the largest at 2283 and the smallest at 427 students
- The range of number of students of district schools is 2237, with the largets at 4976 and the smallest at 2739 students

Thomas High School is a charter school, but when removing the 9th grade data, the numbers weren't influenced very much, so little that the number of decimals had to be increased to even verify that the aberrant data were removed. 

![Scores_by_Type_1](https://user-images.githubusercontent.com/33167541/174196526-c29f4de0-c644-4c75-9d6a-491396e9f021.png)


![Scores_by_Type_2](https://user-images.githubusercontent.com/33167541/174196536-bc58b06c-e61b-4497-b235-b6c3eded82e2.png)


--- 
### Performance Conclusions
This analysis shows a huge difference between the district schools and the charter schools in high favor of the charter school performance. The facts that have been presented in concert show that within these correlations are some patterns: 
1. District schools larger than the any of charter schools, including medium sized charter schools
2. The correlation with the budget per student is not a good indicator, since the charter schools with high budgets are high performers, whereas 3 out of the 4 district schools are in the highest budget bracket, and the volume of students and type of school have a seemingly greater impact on the scores

Typically charter schools have a lower student:teacher ratio, meaning fewer students per teacher. The more individualized approach caters to better learning in general, and this is ideal in smaller settings. When just comparing the medium sized schools, it becomes clear that size alone isn't a great indicator. The following are the medium size schools by rank:
1. Cabrera High Schoo, charter, 1858 students, 91.3% passing
2. Wilson High School, charter, 2283 students, 90.6% passing
3. Wright High School, charter, 1800 students, 90.3% passing
4. Ford High School, district, 2739 students, 54.3% passing
5. Huang High School, district, 2917 students, 53.5% passing
6. Figueroa High School, district, 2949 students, 53.2% passing

In this medium range, from 1800 to 3000 students, there is a bimodal distribution in the passing rates with one mode around 53% passing and the other around 91% passing, whereas the number of students does not share this same tight cluster. 
