# Kickstarting with Excel

## Overview of Project
This analysis is based on real world scenario. Louise organized a $10,000 fundraising campaign using Crowfunding, an online platform to raise money for a specific cause. Louise came close to her campaign goal and now wants to understand how similar campaigns performed based on their goal and launch date. 
### Purpose
The purpose of this work is to organize, sort and analyze the Crowfunding data that was offered in the assignment. This work will provide insights and visualize campaign outcomes that will help Louise understand the performance of their campaign. 

## Analysis and Challenges
The analysis consists of two technical deliverables: A) a visual that organizes the campaigns outcomes based on launch date, and B) a visual that expresses the campaigns outcomes based on goals. I organized the analysis in the following tree steps.
#### Getting Ready
I started the analysis by opening the resources I needed to fulfill this assignment. I was familiar with the Kickstarter *crowfunding data because of the exercises in module 1. However, if I wouldn’t have been familiar with it, I’d suggest familiarizing yourself first. Since I was going to deal with a large set of data (4115 campaigns and 21 characteristics each) it was helpful to freeze the title panel to know the title for each column. 
#### Sorting the Data
My data was organized and sorted because of the exercises in Module 1. This means that I was able to filter the category that interested me based on Louise’s campaign (Theatre, Play). I had created a parent category and a subcategory, I was interested in Theater (parent category) and Plays (subcategory). I also had sorted the data's date, meaning that I knew when the campaigns were launched, when they were ended and how long they lasted. This was perhaps one of the most challenging steps when I was sorting the data. I didn’t know how to convert unix timestamps into a more readable format. Thankfully section 1.3.3 "Timing Success" taught me how to do it and I managed to do it well. After following these steps, the launch date could be filtered by month and year. 
### Analyzing the Data
This last step was probably the most fun. The aim was to create two visuals, the first one to analyze outcomes based on launch date and the second one to analyze outcomes based on goals. Please read below for more details. 

### Analysis of Outcomes Based on Launch Date
The aim of this visual was to analyze the campaigns outcomes based on date. Does the launch date affect the results of the campaign? Are campaigns launched in December more successful than the ones launched in April? This visual answer those questions. 

The first step was to create a pivot table and organized the Theatre Play campaigns by the month of the launch date and the number of campaigns that were successful, failed and canceled. Then, using the information on the table the second step consisted on create a chart. See Theater_Outcomes_vs_Launch.png  

One of the challenges I faced was to figure out how to make the pivot table, what information include in the rows and which one in the columns. Something helpful was to think “What do I want to know?”. When I figured that I wanted to know how many plays were successful, failed or canceled by each month, I understood how the variables needed to be filtered and organized.   Since the months were the independent variable, they must go on the X axis and rows, and since the number of plays where the dependent variable, they must go on the Y axis and columns. 
 
### Analysis of Outcomes Based on Goals

This was probably the most challenging deliverable of this analysis. The aim of this visual was to categorize the campaigns based on their goal. There were 12 categories. The first one included campaign for less than $1000 and the last one campaigns greater than $50,000. Each row told how many campaigns were in that category, how many were successful, canceled or failed to reach their goal. 

I used the function COUNTIFS(…) to obtain the amount of campaigns that were successful, failed or canceled within those goal categories. I learned to use conditionals and to block a parameter within a sheet using F4. The most challenging aspect was to figure out a way to include only the number of campaigns within a certain parameter. 


### Challenges and Difficulties Encountered
This task took me a long time because I experienced mainly three challenges. 

#### First Challenge
I wasn’t familiar with the function COUNTIFS (…). So I googled information about COUNTIFS to understand the concept before applying it. I learned that COUNTIFS is a function that applies criteria to cells across multiple ranges and counts the number of times all criteria are met (taken from https://support.microsoft.com/en-us/office/countifs-function-dda3dc6e-f74e-4aee-88bc aa8c2a866842#:~:text=The%20COUNTIFS%20function%20applies%20criteria,course%20called%20Advanced%20IF%20functions.). 

#### Second Challenge
I didn’t know how to extract the information contained in a cell from other excel sheets. So I read closely how the information within the function was written and realized that I could extract information from other excel sheets just by writing in apostrophes the name of the sheet I wanted to use. 

For example in this functionCOUNTIFS (Kickstarter!F2:F4115,'Outcomes Based on Goals'!D1,Kickstarter!$D$2:$D$4115,B3,Kickstarter!$R$2:$R$4115,"plays")-D2 “Kickstarter” and “Outcomes Based on Goals” are names corresponding to the sheets I want to reference. 

#### Third Challenge
I was confused about how to obtain a count within a parameter. For example, how to obtain the count of campaigns between $5000 and $9999. I solved this using a mathematical way. To find the number of campaigns between $5,000 and $9,999 I counted all the campaigns below $9,999 and deducted the ones below $4,999.  So the countif read as following 
COUNTIFS(Kickstarter!F2:F4115,'Outcomes Based on Goals'!D1,Kickstarter!$D$2:$D$4115,B7,Kickstarter!$R$2:$R$4115,"plays")-SUM(D2:D6)




## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
By looking at the amount of successful campaigns we could say that May was the most successful month with 111 successful campaigns. However, this number could be deceiving because May was also the month with the highest amount of total campaigns. Therefore, when analyzing the most successful launch date, we have to take instead the success percentage of the campaigns. 
If we look at the success percentage, MAy is still the most successful month followed by June. The least successful month is October, with a 43% failed. However, to reiterate once more the importance to look at the percentage and not the number, we can see that October has less failed campaigns than May *50 versus 52. 

The average success rate is 61% for any campaign and only 4 months are below this average> January, August, October and December. The average failure rate is 37% and only 4 months are above this average> August, October and December. Therefore, we could conclude that August, October and December are the worst months to launch a campaign. January is not included because it didn't meet both criteria. 

- What can you conclude about the Outcomes based on Goals?
The outcomes based on goals show that the most common goal was between $1000 and $4999, which was also the most successful range (387 successful campaigns). However, if we look at the percentage we could say that campaigns below $1000 were the most successful (76% success versus 73%).
 While it could be suggested that this is due to the fact that the goal was more attainable, the results in the following category might contradict this argument. The least successful category was $25000 to $29999. But it is interesting because the next bracket $30000 to $34999 had a better success rate. Showing that it is not always the case that a higher goal equals a less probable success rate. 


- What are some limitations of this dataset?
Although the data provides valuable information about kickstarter campaigns I believe there is not enough information on the analysis based on goals to draw firm conclusions about campaigns larger than $10000. I mention this because the amount of campaigns varies drastically and I believe there is not enough sample to draw firm conclusions. 


- What are some other possible tables and/or graphs that we could create?
We could analyze the information also by country. I would also be interested in analyzing the amount of time that it took successful campaigns to reach their goal. 
I would also like to analyze how many backers had a successful campaign and figure out the average donation amount.
I would also like to know how close were the failed campaigns to reach their goal. 
