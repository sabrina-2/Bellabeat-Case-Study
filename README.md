# Bellabeat Case Study

Project type : Data Analytics Case Study   
Tools used : Microsoft Excel, Google BigQuery, Tableau

<ins>Case study summary</ins> 

Bellabeat is a high-tech manufacturer of health-focused products for women. They have the following products
- Bellabeat app: The Bellabeat app provides users with health data related to their activity, sleep, stress,
menstrual cycle, and mindfulness habits. This data can help users better understand their current habits and
make healthy decisions. The Bellabeat app connects to their line of smart wellness products.
- Leaf: Bellabeat’s classic wellness tracker can be worn as a bracelet, necklace, or clip. The Leaf tracker connects
to the Bellabeat app to track activity, sleep, and stress.
- Time: This wellness watch combines the timeless look of a classic timepiece with smart technology to track user
activity, sleep, and stress. The Time watch connects to the Bellabeat app to provide you with insights into your
daily wellness.
- Spring: This is a water bottle that tracks daily water intake using smart technology to ensure that you are
appropriately hydrated throughout the day. The Spring bottle connects to the Bellabeat app to track your
hydration levels.
- Bellabeat membership: Bellabeat also offers a subscription-based membership program for users.
Membership gives users 24/7 access to fully personalized guidance on nutrition, activity, sleep, health and
beauty, and mindfulness based on their lifestyle and goals.

You are a junior data analyst on the marketing team at Bellabeat. Urška Sršen, cofounder and Chief Creative Officer of Bellabeat, believes that analyzing smart
device fitness data could help unlock new growth opportunities for the company. You have been asked to analyze smart device data to gain insight into how consumers are using their smart devices. The insights you discover will then help guide marketing strategy for the company. You will present your analysis to the Bellabeat executive team along with your high-level recommendations for Bellabeat’s marketing strategy. The dataset you will use can be found on Kaggle https://www.kaggle.com/datasets/arashnic/fitbit

<ins>Business task</ins>

Analyze smart device usage for an existing products to gain insights on consumer behaviour that can help drive the marketing strategy of Bellabeat

<ins>Stakeholders</ins>

- Urška Sršen: Bellabeat’s cofounder and Chief Creative Officer
- Sando Mur: Mathematician and Bellabeat’s cofounder; key member of the Bellabeat executive team

<ins>Data sources used</ins>

-Fitbit Fitness Tracker Data (used for analysis):     
Thirty eligible Fitbit users consented to the submission of personal tracker data, including minute-level output for physical activity, heart rate, and sleep monitoring. These datasets were generated by respondents to a distributed survey via Amazon Mechanical Turk between 03.12.2016-05.12.2016.  
Limitations : Low since small sample size and important information, such as age, gender, location, etc of participants is unknown. 

-CDC data:       
Data about health statistics is used
www.cdc.gov/healthyweight/assessing/bmi/adult_bmi/index.html
www.cdc.gov/sleep/about_sleep/how_much_sleep.html
www.cdc.gov/physicalactivity/basics/adults/index.htm

-Age and gender demographics of fitness device user:     
https://www.today.com/money/smartwatch-or-fitness-tracker-why-age-sex-matter-1d80410946

-Social media usage:     
https://www.pewresearch.org/internet/fact-sheet/social-media/

<ins>Data used from Fitbit Dataset</ins>

- dailyActivity_merged.csv
- dailyCalories_merged.csv
- dailySteps_merged.csv
- sleepDay_merged.csv
- weightLogInfo_merged.csv

<ins>Processing Data</ins>

All the csv files were cleaned using Microsoft Excel. I looked for null values in the rows. I also split the date time column into two separate column, one for data in the short date format and one for time.

I then loaded the data in Google BigQuery after which I proceeded to use SQL for analysis ( Present in SQL code)   
The following steps were taken:    
1- I viewed all the data present to make sure all the data was imported correctly   

2- I checked the number of distinct id in each csv file. Results:
       -dailyActivity : 33      
       -dailyCalories : 33        
       -dailySteps : 33       
       -sleepDay : 24      
       -weightLog : 8         
This shows that the data is inconsistent as we are told that there are 30 participants. Some data has more entries while some have missing data.    

3- I then checked the average stat for the data.      
       - Average Daily Steps : 7638 steps. CDC recommends 10000 steps a day so that mark is not reached          
       - Average Active Minutes : 227.52 minutes out of which 21.16 minutes has very active activity. CDC recommends 75 minutes of vigorous activity a week so users                                   are reaching that goal.       
       -Average Calories burned : 2304 calories. 3500 calories are required to burn to lose 1 pound of weight 
       -Average Sleep Hours : Roughly 7 hours. This value is within CDC recommendation      
       -Avergae BMI - 25.19 which falls under the overweight category.    

4- I then proceeded to find the relationships between different data and visualized the results using tableau.           
- Relationship between Average Activity and Average Calories burned : There is a positive correlation between average activity and the average calories burned.
       
![Dashboard 1 (1)](https://user-images.githubusercontent.com/101150323/196565554-42679b84-008a-4934-9d8e-c062a8aa3da7.png)
       
      
      
      
- Relationship between Average Steps and Average Calories burned: There is a positive correlation between average steps and average calories burned.
       
![Dashboard 1 (2)](https://user-images.githubusercontent.com/101150323/196565882-f104e9da-fcd2-46c2-9d87-1cfd08396213.png)



- Relationship between Average Activity and Total Hours of Sleep : No correlation

![Dashboard 1 (3)](https://user-images.githubusercontent.com/101150323/196566117-804bd7b7-828e-4d20-a094-60f4a4c5135c.png)



- Relationship between Average Activity and BMI (Not reliable due to small dataset) : Negative correlation between Average Activity and BMI

![Dashboard 2](https://user-images.githubusercontent.com/101150323/196566223-d34cf83a-a4e0-4d52-b12f-1e8b0f4421a3.png)


