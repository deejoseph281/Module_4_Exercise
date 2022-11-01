# School_District_Analysis

## Resources
Using Python 3.7 for Module 4

## Background
We had a new version of the student data with several changes including an added column for 'Student Budget'. We needed to rework our analysis with the new dataset.

## Summary
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


