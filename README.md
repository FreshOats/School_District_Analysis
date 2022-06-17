# School District Analysis
***Evaluating how Falsified Grades Impacted a School District***
#### by Justin R. Papreck
---

## Overview

The competition getting into colleges and universities is extreme, and it is absolutely critical that the schools and students are evaluated fairly across the country. Different schools can be evaluated by several metrics, including school size, type, and budget per student to see why certain schools outperform others. A particular school district evaluated their schools and rankings based on the assumption that the grades were unaltered and fairly reported; however it was indicated that the 9th grade scores from math and reading at Thomas High School had been altered. The impact that this would have on the school's upper classmen as well as on the other schools in the district could be massively impacted depending on the severity of the altered grades. 

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


While these numbers seem small, if the trends follow with the 9th graders at Thomas HS, this could potentially indicate that students who would have potentially failed had their grades inflated such that they would pass, impacting the pass rates. This metric would not have been altered if only passing students had passed their courses. 

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
1. Cabrera High School, charter, 1858 students, 91.3% passing
2. Wilson High School, charter, 2283 students, 90.6% passing
3. Wright High School, charter, 1800 students, 90.3% passing
4. Ford High School, district, 2739 students, 54.3% passing
5. Huang High School, district, 2917 students, 53.5% passing
6. Figueroa High School, district, 2949 students, 53.2% passing

In this medium range, from 1800 to 3000 students, there is a bimodal distribution in the passing rates with one mode around 53% passing and the other around 91% passing, whereas the number of students does not share this same tight cluster. 





---
---
## Code Analysis
The code required two dependencies: pandas and numpy.

``` 
import pandas as pd
import numpy as np
```

There were several considerations in coding that took place upon the exploratory analysis of this data. Initially, it was uncovered that a subset of students thought it would be funny to give themselves titles, such as Dr. as a prefix or PhD as a suffix. After confirming that there were no null values in the data, a string replace function was used to replace any of the discovered prefixes or suffixes and replaced with an empty string. 

```
students_data_df = pd.read_csv(data)

prefixes_suffixes = ["Dr. ", "Mr. ", "Mrs. ", "Ms. ", "Miss ", " MD", " DDS", " DVM", " PhD"]

for word in prefixes_suffixes:
    students_data_df["student_name"] = students_data_df["student_name"].str.replace(word, "")
    
students_data_df
```

This dataset needed to be merged with a second dataset containing the school information from each district including the school size and budget. Since there were no null values, the merge was a straightforward left join:

```
school_data_complete_df = pd.merge(students_data_df, school_data_df, on=["school_name", "school_name"])
```

At this point in the analysis, it was important to consider the fabrication of grades for the ninth grade of Thomas High School, and that information would have to be carefully dealt with. Using a df.loc[] call, the math and reading scores were set to null values for the 9th grade classes at Thomas High School:

```
student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"), ("math_score", "reading_score")] = np.nan
```

Since the totals would all be affected by removing a subset of the students, the new adjusted total had to be determined for the calculations of score averages and percentages. The student total would remain the same for the budget per student calculations. 

```
# Counting the number of 9th Graders at Thomas High School
ninth_count = school_data_complete_df[(school_data_complete_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th")]["Student ID"].count()

# Get the total student count 
student_count = school_data_complete_df["Student ID"].count()


# The adjusted student count subtracts the Thomas High School 9th graders from the total
student_count_adjusted = student_count - ninth_count
```

The math and reading passing rates were calculated and then converted to passing percentages. Using conditionals, the overall passing rate dependent on math and reading passes was determined as well. 

```
# Calculate the passing rates using the "clean_student_data"
passing_math_count = school_data_complete_df[(school_data_complete_df["math_score"] >= 70)].count()["student_name"]
passing_reading_count = school_data_complete_df[(school_data_complete_df["reading_score"] >= 70)].count()["student_name"]

# Calculate the passing percentages with the new total student count
passing_math_percentage = passing_math_count / student_count_adjusted * 100
passing_reading_percentage = passing_reading_count / student_count_adjusted * 100


# Calculate the students who passed both reading and math
passing_math_reading = school_data_complete_df[(school_data_complete_df["math_score"] >= 70) & (school_data_complete_df["reading_score"] >= 70)]


# Calculate the number of students that passed both reading and math
overall_passing_math_reading_count = passing_math_reading["student_name"].count()


# Calculate the overall passing percentage with new total student count
overall_passing_percentage = overall_passing_math_reading_count / student_count_adjusted * 100

```

Following these procedures, a new DataFrame was established using a key:values and subsequent formatting. This df provided the district summary. 

```
# Create a DataFrame
district_summary_df = pd.DataFrame(
          [{"Total Schools": school_count, 
          "Total Students": student_count, 
          "Total Budget": total_budget,
          "Average Math Score": average_math_score, 
          "Average Reading Score": average_reading_score,
          "% Passing Math": passing_math_percentage,
         "% Passing Reading": passing_reading_percentage,
        "% Overall Passing": overall_passing_percentage}])
```

Following the district summary, the summary per school required the additional step of grouping. The following process was followed: 

```
# Determine the School Type
per_school_types = school_data_df.set_index(["school_name"])["type"]

# Calculate the total student count
per_school_counts = school_data_complete_df["school_name"].value_counts()

# Calculate the total school budget and per capita spending
per_school_budget = school_data_complete_df.groupby(["school_name"]).mean()["budget"]
# Calculate the per capita spending.
per_school_capita = per_school_budget / per_school_counts

# Calculate the average test scores
per_school_math = school_data_complete_df.groupby(["school_name"]).mean()["math_score"]
per_school_reading = school_data_complete_df.groupby(["school_name"]).mean()["reading_score"]

# Calculate the passing scores by creating a filtered DataFrame
per_school_passing_math = school_data_complete_df[(school_data_complete_df["math_score"] >= 70)]
per_school_passing_reading = school_data_complete_df[(school_data_complete_df["reading_score"] >= 70)]

# Calculate the number of students passing math and passing reading by school
per_school_passing_math = per_school_passing_math.groupby(["school_name"]).count()["student_name"]
per_school_passing_reading = per_school_passing_reading.groupby(["school_name"]).count()["student_name"]

# Calculate the percentage of passing math and reading scores per school
per_school_passing_math = per_school_passing_math / per_school_counts * 100
per_school_passing_reading = per_school_passing_reading / per_school_counts * 100

# Calculate the students who passed both reading and math
per_passing_math_reading = school_data_complete_df[(school_data_complete_df["reading_score"] >= 70) & (school_data_complete_df["math_score"] >= 70)]

# Calculate the number of students passing math and passing reading by school
per_passing_math_reading = per_passing_math_reading.groupby(["school_name"]).count()["student_name"]

# Calculate the percentage of passing math and reading scores per school
per_overall_passing_percentage = per_passing_math_reading / per_school_counts * 100
```

Similar to the process in the previous step, this was put into a DataFrame and filtered using the df.loc[] procedure, also as above. After the new average scores and percentages were determined for the 10-12th grade classes at Thomas High School, the data needed to replace the data from the original data table. This was done using the df.loc[] procedure, setting the new values:
```
per_school_summary_df.loc[["Thomas High School"], ["% Passing Math"]] = THS_passing_math_percentage
per_school_summary_df.loc[["Thomas High School"], ["% Passing Reading"]] = THS_passing_reading_percentage
per_school_summary_df.loc[["Thomas High School"], ["% Overall Passing"]] = THS_overall_passing_percentage
```

The schools were ranked using a df.sort_values function to show both the top and bottom 5 schools in the district:

```
top_schools = per_school_summary_df.sort_values(["% Overall Passing"], ascending=False)
top_schools.head()

bottom_schools = per_school_summary_df.sort_values(["% Overall Passing"], ascending=True)
bottom_schools.head()
```

To analyze the scores by grade at each of the schools, a few steps needed to be taken. Each grade needed its own subset of the data for both the math and the reading scores: 

```
# Create a Series of scores by grade levels using conditionals.
ninth_graders = school_data_complete_df[(school_data_complete_df["grade"] == "9th")]
tenth_graders = school_data_complete_df[(school_data_complete_df["grade"] == "10th")]
eleventh_graders = school_data_complete_df[(school_data_complete_df["grade"] == "11th")]
twelfth_graders = school_data_complete_df[(school_data_complete_df["grade"] == "12th")]
    
# Group each school Series by the school name for the average math score.
ninth_grade_math_scores = ninth_graders.groupby(["school_name"]).mean()["math_score"]
tenth_grade_math_scores = tenth_graders.groupby(["school_name"]).mean()["math_score"]
eleventh_grade_math_scores = eleventh_graders.groupby(["school_name"]).mean()["math_score"]
twelfth_grade_math_scores = twelfth_graders.groupby(["school_name"]).mean()["math_score"]

# Group each school Series by the school name for the average reading score.
ninth_grade_reading_scores = ninth_graders.groupby(["school_name"]).mean()["reading_score"]
tenth_grade_reading_scores = tenth_graders.groupby(["school_name"]).mean()["reading_score"]
eleventh_grade_reading_scores = eleventh_graders.groupby(["school_name"]).mean()["reading_score"]
twelfth_grade_reading_scores = twelfth_graders.groupby(["school_name"]).mean()["reading_score"]


# Combine each Series for average math scores by school into single data frame.
math_scores_by_grade = pd.DataFrame({
    "9th": ninth_grade_math_scores,
    "10th": tenth_grade_math_scores,
    "11th": eleventh_grade_math_scores,
    "12th": twelfth_grade_math_scores})

math_scores_by_grade
```
This process was repeated for the reading scores, followed by some fun and exciting formatting. All of the formatting was done the same way as this single example.

```
math_scores_by_grade["9th"] = math_scores_by_grade["9th"].map("{:.1f}".format)
```

To analyze the spending per student and the school sizes, the data needed to be separated into bins. Initially the .describe() function was used to get the quartiles, and then the bins and labels were set using the following process:

```
# Establish the spending bins and group names.
per_school_capita.describe()

# Separate bins by quartile
bins = [0, 585, 630, 645, 675]
bin_names = ["<$586", "$586-630", "$631-645", "$646-675"]

per_school_capita.groupby(pd.cut(per_school_capita, bins)).count()


# Categorize spending based on the bins.
per_school_summary_df["Spending Ranges (Per Student)"] = pd.cut(per_school_capita, bins, labels=bin_names)
per_school_summary_df
```

The rest of the procedure followed minor changes in the previously presented code to accommodate the needs of that specific task. Occasionally the number of decimals was changed to be able to see some of the minor differences between the before/after removing the Thomas High School 9th grade data. 
