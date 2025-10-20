# MIS 311: Introduction to Business Analytics

## Group Project: Student Sleep Pattern

Dataset: Student Sleep Pattern

## 1. Introduction 

- What lifestyle factors significantly affect the quality of sleep among students, and how can these factors be optimized to improve sleep and academic performance for EIU students?

- The primary objectives of using this dataset are to investigate and understand the relationships between various lifestyle factors and the sleep patterns of university students.

- To build a model that can estimate a EIU student's sleep quality using their lifestyle factors (e.g., screen time, physical activity, caffeine intake) as predictors.

- This dataset is a synthetically generated collection of data designed to model the sleep patterns of 500 university students. It was created for educational and research purposes to provide a realistic, yet artificial, basis for statistical analysis and machine learning without involving real individuals.

- The dataset includes 14 variables for each student, covering:

Demographics: Age, Gender, University Year

Lifestyle Factors: Study Hours, Screen Time, Caffeine Intake, Physical Activity

Sleep Metrics: Sleep Duration, Sleep Quality (a subjective 1-10 rating), and typical sleep/wake times for both weekdays and weekends.

<img width="359" height="308" alt="image" src="https://github.com/user-attachments/assets/65d20585-c8b4-4af1-8daf-ad997c1de39d" />

## 2. Data Source Flowchart 

Obtain the Data Create a visual flowchart showing the journey of your dataset. This flowchart should show: 

• Data origin: where did the data come from? Was it collected from hospital department, ERP systems, survey, or other sources? 

Kaggle is an online community and platform for data scientists and machine learning practitioners. The data is synthetic, meaning it was artificially generated and does not represent real individuals. However, it follows realistic distributions and relationships to provide a useful basis for analysis and modeling.

Data scientists and machine learning engineers can use it as a safe sandbox for practicing their skills in data cleaning, exploratory analysis, and building predictive models without any privacy concerns. For students and educators, it's an excellent tool for learning and teaching; students can apply their knowledge to class projects, while teachers can use it for assignments and examples in data science courses. Finally, researchers can leverage this dataset to test new analytical methods and algorithms in a controlled environment before moving on to more complex, real-world data.

• Data processing: What steps were taken to prepare the data for analysis? Did it involve data cleaning, aggregation or transformation? 

1. Start: Analyze Student Sleep

The process begins with the goal of analyzing the provided dataset to understand patterns in student sleep.

2. Data Acquisition

The raw dataset, 08_Student Sleep Pattern.csv, is loaded for inspection.

3. Initial Exploratory Data Analysis (EDA)

A first look at the dataset reveals its initial state:

Size: 502 records and 14 attributes (columns).

Task: Check column data types and identify any data quality issues.

4. Data Quality Check & Findings

Standardize column name

Duplicate Values: There is 1 duplicate record found in the dataset.

Check is it correct data type for each column

Missing Values: It's discovered that 4 different attributes each have one missing value:

University_Year
Sleep_Duration
Physical_Activity
Weekend_Sleep_Start

5. Data Cleaning

To ensure the quality and accuracy of the analysis, the following actions are performed:

Remove Duplicates: The single duplicate row is deleted.

Handle Missing Values: The few rows containing missing data are removed. This is a common strategy when the number of affected rows is very small compared to the total dataset size.

6. Final Dataset

After the cleaning steps, the result is a finalized, clean dataset. It now has:

- Approximately 497 records.
- 14 attributes.
- Zero missing values and zero duplicate records.

## 3. Data to Insights

### 3.1. Analytical Methodology:

- To ensure a thorough and robust analysis, we adopted a multi-layered methodology, progressing from a broad overview to specific, hypothesis-driven tests. This approach allowed us to identify not only what was happening, but also to rigorously investigate why.

- Descriptive Analysis: We began by computing a full suite of descriptive statistics (Mean, Median, Mode, Standard Deviation) to establish a foundational understanding of the student cohort's typical behaviors and identify any immediate red flags.

- Segmentation Analysis: Utilizing PivotTables, we segmented the dataset by University_Year and Gender to move beyond general averages and compare specific subgroups, allowing us to isolate cohorts that might be disproportionately at risk.

- Inferential Statistical Testing (Correlation & Regression): To move from observation to conclusion, we employed two powerful inferential techniques:

Correlation Matrix: This was used to perform an initial test of association, quantifying the linear relationship between pairs of variables.

Multiple Linear Regression: This was the definitive test of our primary hypothesis. We constructed a model with Sleep_Quality as the dependent variable and the five key lifestyle factors as independent variables to determine if they had any statistically significant predictive power.

### 3.2. Analysis Results and Key Insights:

### Descriptive Analysis:

1. Sleep_Quality

Most Critical Insight: The students' sleep quality is at an extremely alarming level.

What the data says:

Mode = 1: This is the most shocking discovery. The most common score students use to rate their sleep quality is 1 (the worst possible level).

Median = 5: This means that 50% of the students surveyed rate their own sleep from average (5/10) downwards.

Mean = 5.36: Although the average is slightly above 5, the Mode reveals that the actual picture is much worse.

2. Sleep_Duration

Key Insight: Students are suffering from severe and chronic sleep deprivation.

What the data says:

Mode = 4.1 hours: The most common amount of sleep is only 4.1 hours. This is an extremely low figure, indicating that a large group of students is in a state of severe sleep deprivation that affects their ability to study and function normally.

Mean = 6.47 hours: This figure is already below the recommended range (7-9 hours), but the Mode indicates an even more serious problem.

Minimum = 4 hours: The minimum value of 4 hours confirms this critical situation.

3. Study_Hours

Key Insight: Academic pressure is very high and there is significant polarization.

What the data says:

Mode = 10.4 hours: The most common amount of study time is more than 10 hours per day. This shows a trend of very high-intensity studying, which is likely to cause stress and occupy all available rest time.

Standard Deviation = 3.47: The high standard deviation shows a large difference in study habits: there is a group that studies a great deal, while others study significantly less.

4. Caffeine_Intake

Key Insight: Caffeine is a common coping mechanism.

What the data says:

The Mean, Median, and Mode all revolve around the value of 2. This is very consistent, showing that a typical student consumes about 2 caffeinated beverages per day. This may be a mechanism to stay awake, compensating for the lack of sleep.

5. Screen_Time (for entertainment)

Key Insight: Time spent on screens for entertainment is quite high.

What the data says:

Mode = 3.6 hours: The most common amount of screen time (not including studying) is nearly 4 hours. This is a considerable amount of time that could affect sleep quality if it occurs right before going to bed.

6. Physical_Activity

Key Insight: The level of physical activity is highly varied.

What the data says:

Mean = 62.2 minutes: The average of about 1 hour/day is quite good.

Standard Deviation = 35.1 minutes: The high standard deviation and large range (from 0 to 120 minutes) show a clear polarization: one group is very active, while another group is almost completely sedentary.

### Pivot table: 

1. Analysis by University Year:

Sleep duration remains relatively stable for the first three years (~6.5 hours), but there is a significant decline for 4th-Year students, whose average falls to 6.31 hours.

Counter-intuitively, sleep quality tends to improve with seniority, peaking in the 3rd Year (5.55) before dipping slightly in the 4th Year (5.34), suggesting a process of adaptation.

2. Analysis by Gender:

The amount of sleep is nearly identical across all genders (around 6.5 hours).

However, male students report a sleep quality that is approximately 8-9% lower (5.10) than their female and other counterparts, pointing to a qualitative, not quantitative, issue.

### Correlation

All the correlation coefficients between lifestyle factors (Study Hours, Screen Time, etc.) and sleep outcomes are extremely close to zero.

It is not true that students who study more necessarily sleep less.

It is not true that students with more screen time have predictably worse sleep quality.

The lack of any meaningful linear relationship necessitated a more powerful, multi-variable test.

### Regression

R-squared = 0.4%: All five lifestyle factors combined explain only 0.4% of the variation in students' sleep quality.

Adjusted R-squared = Negative: A negative value is a definitive sign of a very poor model, indicating it is worse at predicting the outcome than simply using the average.

P-values: Every single P-value for the independent variables is substantially greater than the standard 0.05 threshold. Therefore, we fail to reject the null hypothesis for every variable. There is no statistical evidence that any of these factors has a meaningful impact.

Coefficients: All coefficients are extremely close to zero, meaning even a large change in one of these behaviors would result in a predicted change in sleep quality that is practically meaningless.

# 4. Conclusion 

Based on the text provided, here are the key main ideas:

Key Findings on Student Sleep

- Widespread Poor Sleep: Students exhibit alarmingly poor sleep, with very low self-reported sleep quality and an average sleep duration (6.47 hours) below the recommended amount.

- No Correlation with Lifestyle Factors: Counter to common assumptions, the analysis found no significant statistical relationship between sleep outcomes and lifestyle factors like study hours, screen time, caffeine intake, or physical activity.

- Identification of Vulnerable Groups: The data reveals specific student groups are more affected. 4th-year students experience a drop in sleep duration, and male students report significantly lower sleep quality compared to others.
