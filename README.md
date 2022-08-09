# Kickstarting with Excel

## Overview of Project
This project examines data from 4,113 Kickstarter campaigns to determine relationships and trends in the data as it relates to the campaign outcomes. The data is organized and formatted in a way that allows for the isolation of data relating to theater projects and plays. That data is then analyzed to reveal trends and the results distilled in to visualations that make the data easier to understand.

### Purpose
The purpose of this project is to reveal trends in the Kickstarter campaign data, and visualize them in a way that helps the customer make decisions that aid in the success of future campaigns. Specifically, the projects purpose is to gather insights about the relationship between theater/play campaign outcomes, and their launch dates and goal amounts. The customer intends to fund future theater projects and plays using Kickstarter, and would like to know the best practices to use to help ensure future success.

## Analysis and Challenges
To begin, the data is imported into Excel and organized into a format that can be analyzed. Unix time codes are converted into usable dates and campaigns are sorted into Parent and Subcategories. Once the data has been organized, analysis can begin.

### Analysis of Outcomes Based on Launch Date
A pivot table is created that gives the total number of each category of outcome (successful, failed, canceled, live) based on the month of the year that the campaign was launched, as well as the grand totals of each month and outcome category. This table allows for filtering based on launch year and Parent category. To remove irrelevant data the table is filtered to show only the "theater" Parent category, and "live" outcomes are omitted. From this table a Line graph is created that shows the number of outcomes in each of the outcome categories for each month of the year.

![Outcomes vs Launch Date](https://github.com/Jforbus/kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
A new table of data is created to compare the outcomes of the campaigns in the "plays" Subcategory based on their goal amounts. The goal amounts are divided into 12 ranges, and the total number of each relevant category of outcome (successful, failed, canceled) within each goal range is counted using the `COUNTIFS()` function. Outcome totals for each of the goal ranges is then calculated using the `SUM()` function. With this data a percentage of each outcome for all given goal ranges is calculated. These percentages are used to create a Line graph that shows the percentage of each outcome category within each of the given goal ranges.

![Outcomes vs Goals](https://github.com/Jforbus/kickstarter-analysis/blob/main/Resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered
The creation of the pivot table to correctly show Outcomes based on Launch Date is a potential challenge. Determining which of the available variables to assign to the *Filters*, *Columns*, *Rows*, and *Values* fields requires an understanding of the creation of pivot tables in Excel as well as familiarity with the data being analyzed. Additionally, getting the pivot table to show only the months of the year in the *Rows* field requires the removal of a portion the set of variables that Excel creates when a Date variable is added to a field.

Another difficulty encountered centers around the `COUNTIFS()` function used for the Outcomes based on Goals data. The function requires the accurate input of the search parameters to provide correct counts. The goal ranges were originally input using `<` and `>` terms where `<=` and `>=` terms should have been used. This resulted in significant errors in the data as all goal values that were equal to the range parameters were omitted. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

    When we examine the Outcomes based on Launch Date graph we see clearly that their is a significant increase in successful outcomes in May, with the rate of successful outcomes tapering down through June and July. We can conclude from this that May is the best time to launch a campaign for Theater projects. We can also see that failed outcomes remain relatively consistent through these months, suggesting these campaings have additional factors contributing to their failure.

- What can you conclude about the Outcomes based on Goals?
   
    From our analysis of the Outcomes based on goals data we can conclude that campaigns with lower goal amounts have a much higher rate of success. The rate of success of campaigns for plays with goal amounts of less than $5,000 is more than 70%. Once goal amounts cross the  $5,000 and $10,000 thresholds the success rate falls significantly, and it continues to decline as the goal amounts are increased.

- What are some limitations of this dataset?
    
    This dataset does not include subcategories for the campaign locations. Countries like the US are very large, with vast cultural differences between regions.   This is potentially misleading as a campaign run in one region of a country could face significantly different circumstances than a campaign ran in another. 
          
- What are some other possible tables and/or graphs that we could create?
   
    Other perspectives on the data would likely prove informative. The duration of each campaign could be calculated and from this a table and graph created that analyzed the outcome of each campaign based on campaign duration. From this we could conclude if a campaign's duration has any relation to its outcome. Additionaly, a table that compares the average donation amount to outcomes could also be helpful. If it can be determined that successful campaigns generate a large number of small donations, or receive a relatively small number of large donations, this could lead to decision making that greatly increases the chance of a campaigns success.
