# School_District_Analysis

## Purpose of School District Analysis

This analysis is to determine the effect of academic dishonesty can have on a school districts scores and is the change more pronounced based on different factors. 
Specifically, we will be focusing on the scores from Thomas High School.


## Results

### School District Summary
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
	passing_math_reading = school_data_complete_df[(school_data_complete_df["math_score"] >= 70) & (school_data_complete_df["reading_score"] >= 70)]
```
This code looks in the school_data_complete dataframe and checks to see which students score is above 70 and stores it inside passing_math_count; the same applies for reading.
Creating a new dataframe for the district summary, I pass all of the count information from above into this dataframe which looks something like this:
```
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

This will give you an output that looks like this:

	<img src="https://github.com/Changscorner/School_District_Analysis/blob/main/Resources/district%20analysis%20with%20new%20data.png?raw=true">

The picture above is the output with the new data where all of the nineth graders scores have been replaced with a null value.
The picture below is the output with the old data where nothing has been changed.

	<img src="https://github.com/Changscorner/School_District_Analysis/blob/main/Resources/district%20analysis%20with%20old%20data.png">
	
As you can see both of these images are almost the same when the percentages are rounded to the tenth degree. The reason for this is because the count of students from Thomas High School that
are in ninth grade is negligible in regards to the total count of students which is 39,170. There are differences in all the values are within a 0 to 0.5 range.

###  School Summary
Next we will take a deeper look into the difference between the old and new data for Thomas High School. Take a look at the both of the photos below:

	<img src="https://github.com/Changscorner/School_District_Analysis/blob/main/Resources/school%20summary%20old.png">
	<img src="https://github.com/Changscorner/School_District_Analysis/blob/main/Resources/school%20summary%20new.png">
	
The photo on top is the output with the old data and the one below is for the new data. We are going to specifically look at the data for Thomas High School. If you recall, in the new data we have changed
the data for all the ninth graders in Thomas High School to a null value while in the old data those values are filled in. The main differences are where they are expected; within the % passing math, % passing Reading, % overall passing, and in the average scores for both.
While for the average reading scores there is not much difference, the difference in the percentage of students passing math and reading are gigantic. There is an almost 30% difference for all 3 of the categories.

### Comparisons for Thomas High School

#### Compared To Other Schools
Using the same photo from above we see that compared to the other schools, Thomas High Schools scores with the new date not longer puts them in line with the other schools. Rather, they are significantly underperforming the other schools.

#### Effects of The Change in Data
Let's take a look at the effect of this change in data in terms of math and reading scores by grade for each school.
	
	<img src ="https://github.com/Changscorner/School_District_Analysis/blob/main/Resources/math%20and%20reading%20scores%20with%20nan.png">

The top image is for the reading scores with the new data and the one below is the new data for math scores. As you can see for the nineth graders the grade is set to a null value.
So there is no information there for us to compare.

##### Scores by School Spending
The scores by school spending are not changed by much by making the nineth grader being null. The reason for this is because we took the data from the tenth and twelfth graders and passed them into the dataframe.
The difference for Thomas High School are in the 0 to 0.5 range as well from the old and new data.

##### Scores by School Size
The Scores by School Size

##### Scores by School Type

## Summary
The largest changes in the school district analysis are seen in the scores by school spending, scores by school size, scores by school type, and 


