# School_District_Analysis

## Purpose of School District Analysis

This analysis is to determine the effect of academic dishonesty can have on a school districts scores and is the change more pronounced based on different factors.


##Results

###School District Summary
 There are a 15 unique schools in the date with a total of 39,170 students. To get the school district summary, I first have to find out for each school some datapoints:

	1.) The total amount of students
	2.) The count of students that passed math
	3.) The count of students that passed reading
	4.) The overall percentage of students that passed both
	5.) Average Math Score
	6.) Average Reading Score
	7.) Total Budget

To get the total amount of students I use this code:
```
	student_count = school_data_complete_df["Student ID"].count()
```
This code take the count of how many students there are in the Student ID column.

To get the count of students that passed math and reading I used this code:
```
	passing_math_count = school_data_complete_df[(school_data_complete_df["math_score"] >= 70)].count()["student_name"]
	passing_reading_count = school_data_complete_df[(school_data_complete_df["reading_score"] >= 70)].count()["student_name"]
```
This code looks in the school_data_complete dataframe and checks to see which students score is above 70 and stores it inside passing_math_count; the same applies for reading.





How is the district summary affected?
How is the school summary affected?
How does replacing the ninth graders’ math and reading scores affect Thomas High School’s performance relative to the other schools?
How does replacing the ninth-grade scores affect the following:
Math and reading scores by grade
Scores by school spending
Scores by school size
Scores by school type
Summary: Summarize four major changes in the updated school district analysis after reading and math scores for the ninth grade at Thomas High School have been replaced with NaNs.