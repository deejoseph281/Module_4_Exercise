# School_District_Analysis

## Resources

Using Python 3.7 for Module 4

## Background

We had a new version of the student data with several changes including an added column for 'Student Budget'. We needed to rework our analysis with the new dataset.

## School District Analysis 

### Deliverable 1

* Collect the student data into a DataFrame. 

First we need to import the required libraries and dependencies. I've additionally included an ignore function for filter warnings.

![image](https://user-images.githubusercontent.com/115019829/199133526-5a578d8f-2d63-454b-8a2b-e86194ee5b4c.png)

To collect the data, we need to use Pandas read_csv and os.path.join functions to import the data from the new_student_data.csv file, and create a DataFrame called student_df.

![image](https://user-images.githubusercontent.com/115019829/199133495-38b07524-8bb6-4418-9ec0-921d3a7f3390.png)

### Deliverable 2

* Prepare a cleaned version of the DataFrame.

As in any data analysis, we will first need to identify discrepancies and cleanse the data. We first checked for rows that were blank using isna function, then verified what percentage of the data was blank. From the isna.mean(), we concluded that the reading and math scores had 10% and 5% blanks, respectively. For the purpose of this analysis, we can conclude the blank data to be immaterial to the analysis since we are primarily interested in the reading and math scores of the students who completed the assessments.

![image](https://user-images.githubusercontent.com/115019829/199140471-c57d96d1-0a95-4a92-a125-b26ab3fe0d25.png)

We dropped the blanks using dropna() function. We also verified if there were duplicates within the data set and removed any duplicate rows using drop_duplicates().

![image](https://user-images.githubusercontent.com/115019829/199140789-e3ba18a8-4646-4a12-81d5-7dac9d657d56.png)

Finally, we need to ensure that the data types are easily manipulated by removing the 'th' from the grade levels as this will make it difficult to sort and combine the results by grade. We then converted the object to an integer to allow for easy reference. 

![image](https://user-images.githubusercontent.com/115019829/199141125-b8b49ed0-ce18-4119-8d02-3039f9b1e010.png)

### Deliverable 3

* Summarize key pieces of data using describe() to get a full summary of the reading scores, math scores, and schoold budget. We were interested in the avaerage math score using mean() function, and identifying the minimum reading score. 

![image](https://user-images.githubusercontent.com/115019829/199141282-25f0702f-f08e-48ad-b454-ec3e4e36f269.png)

### Deliverable 4

* Drill down into the data to analyze the specific subsets

Our initial analysis was to look up the summary of the 9th grade results. 

![image](https://user-images.githubusercontent.com/115019829/199141666-cfacdb9b-98f1-4dc5-b1db-156ea93f3bbb.png)

We identified the minimum reading score was from Dixon High School, and compared the minimum reading score at Dixon High School with the average reading score at Dixon High School using loc to look up the school name and output the reading scores and using mean() to provide the average of all of the reading scores at Dixon High School. 

![image](https://user-images.githubusercontent.com/115019829/199141997-ee058a4b-0615-49d2-82a9-8a1d45a80af7.png)
![image](https://user-images.githubusercontent.com/115019829/199142069-e494a918-44da-4e9a-b721-10e388c0f4a4.png)

### Deliverable 5

* Compare the data.

We compared the data by school type to understand the average budget of Charter Schools and Public Schools. We needed to group the schools by school type using the groupby() function.

![image](https://user-images.githubusercontent.com/115019829/199142391-ba3f41f2-9a5f-454b-b868-db66a286c387.png)

We also needed to understand the total number of students at each school, sorted from largest to smallest which required using groupby() for the school and count() to identify the total number of students. Then, we needed to groupby() school to output the count of the students by each high school. 

![image](https://user-images.githubusercontent.com/115019829/199142659-3824ce85-e192-48d5-a2d8-2740bbbf6f13.png)

Finally, we needed to use groupby() and mean() to understand the average math score by grade at Charter Schools and Public schools. We required the loc function to lookup the math score column in our data table output. 

![image](https://user-images.githubusercontent.com/115019829/199142795-82e1b86c-f877-4cf8-8950-059576ad95cc.png)

## Summary

From our analysis we were able to extrapolate the following: 
* 10% of the students did not complete or do not have data for their reading scores.
* 5% of the students did not complete or do not have data for their math scores.
* The average math score for all students in the district who have completed the assessment is 64.67.
* The lowest reading score in the district was 10.5 from Dixon High School.
* The average reading score of 11th and 12th graders in the district was 74.90.
* The average budget of public schools is $911,195 and charter schools is $872,625.
* There are 15 high schools in the district, with Montgomery High School being the largest -- 2,038 students.
* The smallest high school in the district is Chang High school -- 171 students.
* The average math scores for charter school 9th, 10th, and 11th graders is higher than public school. 
* The average math score for charter school 12th graders is lower than public school. 

