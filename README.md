# kickstarter-analysis
Performing analysis on Kickstarter data to uncover trends
## Overview of Project

Louise, a playwright, acquired our help to raise money for her upcoming play, Fever. Using Excel, we parsed through a large dataset of crowdfunding data to determine what factors if any should be considered in planning her campaign. By analyzing this dataset and looking at how other crowdfunding campaigns performed, we were able to help Louise have a successful campaign. However, Louise is now interested in whether two other factors affect theater campaign performs: launch date and funding goal.

### Purpose

The purpose of this project is to provide Louise with data on how launch dates and funding goals impact the performance of a campaign in a visually appealing and easily digestible manner.

## Analysis and Challenges  

### Analysis of Outcomes Based on Launch Date

To determine the impact of launch date on performance, I first needed to create a new data column. This column is labeled **Years** and the following function was used to extrapolate the year from the **Date Created Conversion** : =year(). One challenged that I initially faced when attempting to apply this function to the dataset is that some campaigns were missed. This was due to previous filters that I had not cleared. After clearing the prior filters, I tried the function again with success.

Next, I created a pivot table that was placed in a new sheet titled **Theater Outcomes by Launch Date.** This pivot table was filtered by *Parent Category* and *Years,* *Outcomes* was placed in columns and *Date Created Conversion* was place in rows. It is important to note that excel automatically adds *Years2* and *Quarters* to rows when initially placing the date created conversion to rows; these need to be removed. The final PivotTable Fields looks as follows:

![image](https://user-images.githubusercontent.com/105028515/172935301-1cca7e59-7afc-4241-b262-d12f84a84710.png)

Since Louise in only interested in theater campaigns and we are not interested in ongoing campaigns, the parent category was filtered on *theater* within the pivot table and *live* was deselected from the column labels. The row labels within the pivot table were also changed to display the months of the year and the campaign outcomes were sorted in descending order. The complete pivot table appears as follows: 

![image](https://user-images.githubusercontent.com/105028515/172935324-914dd09f-688d-4b57-a593-8e45db1794f2.png)

Finally, a line chart was created from the pivot table to display this data visually. This line chart is titled **Theater Outcomes Based on Launch Date** and shows the number of successful, failed, and canceled projects by month. This line chart is looks as follows: 

![image](https://user-images.githubusercontent.com/105028515/172935361-94f739ea-32f3-4b07-b9d6-69aaa89f4263.png)

### Analysis of Outcomes Based on Goals

To determine how the goal affected the success of the campaign, a new sheet was created in the workbook to hold the relevant data. This sheet was titled “Outcomes Based on Goals” and includes the following columns: Goal, Number Successful, Number Failed, Number Canceled, Total Projects, Percentage Successful, Percentage Failed, and Percentage Canceled. Projects were sorted based on their goal amount. To do this, dollar-amount ranges were added in the “Goal” column as seen below. 

![image](https://user-images.githubusercontent.com/105028515/172935398-910a2330-f4b9-4925-ba70-4f2539eec5cd.png)

Using COUNTIFS() functions, the number of successful, failed, and canceled plays was determined for each of these goal ranges. The SUM() function was used to determine the total number of plays in each goal range. This was needed in order to determine the percentage of successful, failed, and canceled plays in each goal range as each is equivalent to the number in each category divided by the sum of all in each goal range. The final dataset is displayed below, along with the functions used in the *Less than 1000* goal range row.

![image](https://user-images.githubusercontent.com/105028515/172935433-53abbda8-b6da-469f-941e-e0c576b2d111.png)
![image](https://user-images.githubusercontent.com/105028515/172935450-37654dca-2cc8-4161-ae47-6193c9871dac.png)

## Results

By analyzing theater outcomes by launch date, we can see that May and June have the highest number of successful campaigns while December has the lowest number of successful campaigns. We are also able to conclude that more campaigns are cancelled in January than in any other month. By analyzing outcomes based on campaign goal, we see those campaigns for plays with goals in the $5000 - $9999 range have the highest rate of success and that no play campaigns were cancelled.

While this dataset can provide us with a lot of information for which we are able to analyze and come to reasonable conclusions, it is important to note that there may be other important factors dictating the success of these campaigns that are not recorded in this dataset. Furthermore, there is always additional ways in which the data can be analyzed that may give us a different story. For example, when analyzing theater outcomes by launch date, only the “count” was considered. I mentioned previously that May and June have the highest number of successful campaigns, but I did not mention is that May and June also had the highest total number of campaigns. This begs the question – Are May and June actually the best months to have a campaign or do we simply see a higher number of successful campaigns as a result of there being more total campaigns? What is not considered and would likely be more valuable is to analyze the success rate of campaigns by month instead. Further analysis on this dataset should include a line graph of the percentage of campaigns that are successful, failed, and cancelled, by month.
