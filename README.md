# An Analysis of Kickstarter Campaigns

## Overview of Project
Louise (client) wants to launch a fundraising campaing for a theater play. The project must focus on the client's requests and provide a clear understanding of the main drivers of theater/plays fundraising campaigns.

### Purpose
Analyze data to find insights to help Louise (client) decide the best month(s) to launch and the most profitable range goal for fundraising. 
## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
1) Created a pivot table and line graph to analyze by month the theater campaigns that were successful, failed and canceled
    a) Filters Years (All) and Parent Category (Theater). 'Theater is a focus for our client'
    b) Outcomes as columns and Value Counts for successful, failed and canceled by month. 'Understanding the number of campaigns by month of each outcome with a graph to visualize trends'
    ![Alt text](C:\Users\jqu23\OneDrive\Desktop\Boot Camp\Excel Challenge\Resources\Theater_Outcomes_vs_Launch.png "Theater_Outcomes_vs_Launch")


### Analysis of Outcomes Based on Goals
1) Created a range of goal amounts and it percentages based on the total projects
    a) Used countifs with the criteria of subcategory "plays", Outcome "successful, failed and canceled", goal range "based on column goal"
    b) To make it simpler to use countifs in the other columns I created an additional row with the different outcomes as reference in the countifs. This step made it easier to calculate for the other outcomes. =COUNTIFS(Kickstarter!$R:$R,"plays",Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<5000",Kickstarter!$F:$F,B$1).
        1) Column R is the subcategory "plays" that had to be fixed throughout the different ranges and outcomes. 
        2) Column D is the goal amount that also had to be fixed and depending on the range being counted we had to add quotes. 
        3) B$1 is the different outcomes being analyzed, I had it fixed on row 1 to be able to use it for the other outcomes. 
    ![Alt text](C:\Users\jqu23\OneDrive\Desktop\Boot Camp\Excel Challenge\Resources\Countifs_outcome_reference.png "Countifs_Outcome_Reference")
2) Used sum to get the total projects who were successful, failed or canceled for plays. =Sum(Number Successful, Numer Failed, Number Canceled)
3) The percentage of each outcome being analyzed with a simple division. =Number X / Total Projects. The percentage per row had to add to 100%. 
4) Generated a line graph to visually see the range of goals that are must succesfull within plays. 
![Alt text](C:\Users\jqu23\OneDrive\Desktop\Boot Camp\Excel Challenge\Resources\Theater_Outcomes_vs_Launch.png "Theater_Outcomes_vs_Launch")
### Challenges and Difficulties Encountered
 1)  Did not encounter any challenges in the Analysis of Outcomes Based on Launch Date. Some challenges that could be encountered:
    a) How to set months with the Data Created Columns
    b) How to sort the outcomes in descending order
    c) How to create a line graph for the pivot table
    d) How to save the image as .png
2) Encountered some challenges with Analysis of Outcomes Based on Goals
    a) Use the countifs for two ranges such as 1000 to 4999. Googled different ways to do this and concluded that the best option is to create two different criteria. "Kickstarter!$D:$D,">=1000",Kickstarter!$D:$D,"<5000""
    b) I've alwyas preferred to use formulas that can be duplicated into other columns, with reference ($) that lets you move the formulas nad have certain columns and/or rows fixed made it easier for me. 
    c) Once the line graph was created, the goals range overlapped. I selected the ranges and modified the font size to see the ranges clearly. 
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
    1) Luanching a theater fundraising in the months of May, June and July may have a higher probability of being succesfull. Though we must look at other variables to give a final conclusion. 
    2) The number of fundraising campaigns concentrate from May to August with higher percentage of succesfull campaigns. The fundraising campaings that start in October seem to fail more and may be due to having no canceled campaings. 
- What can you conclude about the Outcomes based on Goals?
    1) Fundraising campaigns based on subcategory "plays" may have a higher probability of success when the goal is between 35K and lower than 45K. 
    2) Fundraising campaigns between 25K and 30K and higher than 45K have a lower probability of being successful. 
- What are some limitations of this dataset?
    1) Even though the data covers 8 years and 19 countries there are only 1066 data points for plays. There are few data points to evaluate tendencies over time and even considering analyzing by country. 
    2) Besides theater, all other categories have very few data points to get a coherent conclusion. 
    3) In order to analyze/compare goal and pledged correctly we must standardize the currency. 

- What are some other possible tables and/or graphs that we could create?
    1) Create a column in Kickstarter with the exchange rate to USD and analyze the outcomes based on goals with this new exchange rate. 
    2) Create a time series line graph for theater/plays to better understand the trend through the years. 
    3) Theater Otucomes by Launch Date in percentages instead of counts to understand if the increase in success is based on an increase in campaigns or that they are more succesfull in those months. 
