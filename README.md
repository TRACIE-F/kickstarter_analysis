# Kickstarter Analysis for *Fever*

## Overview of Project
The following data and analysis were compiled to support a successful fundraiser for production of *Fever*. 

### Purpose
In an effort to support additional kickstarters for the production of *Fever*, we analyzed pre-existing kickstarter data to determine what factors may contribute to successful outcomes. By analyzing the kickstarter goals in relation to success rate, we can help determine what a additional realistic goals for *Fever* look like, and make suggestions for adjustments that could contribute to a better fundraising outcome. By analyzing kickstarter launch dates in relation to success rate, we can further improve chances for a successful outcome, even if only by avoiding months with extremely low success rates. Simply put, our data analysis is meant to take the lessons learned from other theater fundraisers and implement them to *Fever*'s benefit.   

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
Determining the outcomes of a theater kickstarter based on the launch date began with cleaning up the original data.

**Dates**
The original data contained Epoch dates, which I had never encountered before. It's safe to say that most individuals will have a much easier time interpreting data utilizing standard dates.
![Date_Conversion](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Date_Conversion.png)

I also added a "Years" column, which allowed for a filter on the pivot table mentioned below.
![Years](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Years.png)

**Split category**
Splitting up the parent category and subcategory allowed for more nuanced data sorting, and for the purpose of this specific analysis, allowed me to filter by the "theater" parent category.
![Category_Split](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Category_Split.png)

With this cleaned data, I created a pivot table (pictured below) which counted the number of successful, failed, and canceled kickstarter campaigns sorted by the month they launched. Rows held the month of campaign launch and columns held the outcomes and their count per month. The chart was filtered to only show the parent category of "Theater," with an option to filter by year.
![Pivot_Table](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Pivot_Table.png)

From this pivot table, I created a line chart to show any trends in the data, helping to determine if there are truly any months to launch a campaign with a higher likelihood of success or months to avoid due to low success rates of others.
![Theater_Outcomes_vs_Launch](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals
To determine the success of goals, I began with the COUNTIFS formula and selected the pertinent data to have counted. 
![Skewed_Data](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Skewed_Data.png)

Below is pictured the formula for canceled kickstarters between $20,000 and $24,999 within the subcategory of "plays."
![Locked_Formula](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Locked%20Formula.png)

I then added a calculation to determine the percentage of failed, successful, and canceled kickstarter campaigns occurred within a goal range.
![Percentage](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Percentage.png)

The resulting visualization is a line chart tracking the percentage of successful, failed, and canceled kickstarter campaigns for plays within specified ranges.

![Outcomes_vs_Goals](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered
### Theater Outcomes Based on Launch Date
With the "Theater Outcomes Based On Launch Date" chart, I encountered minor challenges in setting up my pivot table.
![Chart_Order](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Chart_Order.png)
Initially, the data order was "Canceled," "Successful," and then "Failed." This made my line chart a little more difficult to follow at a glance as the key was in a different stacked order than the data on the graph. A little bit of Googling helped me re-arrange the columns without disrupting the data. 
A challenge I anticipated, but did not run into with this chart, was ensuring the timeline was using a row label that was months rather than quarters. Other tables automatically defaulted the timeline to quarters, and I was able to correct this with assistance from [Pryor Learning](https://www.pryor.com/blog/grouping-excel-pivottable-data-by-month/).

### Outcomes based on Goal
The "Outcomes Based on Goal" chart was much more of a challenge. First and foremost, determining how to set the parameters between two sets of numbers (ex. 1000 to 4999) presented some challenges. Google sorted those challenges out quickly. Sorting out the "COUNTIFS" formula was a matter of trial and error once I figured out how to pull the columns I needed. I tested my first formula (less than 1000), and then went back to the main "Kickstarter" sheet to utilize filters and do a rough count to feel more confident in my results.

**Fewer 9s**
To make the formula easier to type out, I utilized some critical thinking skills. I then realized early on typing whole numbers at least felt easier than multiple 9s, and chose to make my formulas start with "greater than or equal to" the bottom number, and "less than" the bottom range for the next row.
![Locked_Formula](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Locked%20Formula.png)

**Locking Columns**
Another challenge I encountered was a result of sheer forgetfulness. As soon as I determined the proper formula for the first row, I copied and pasted it over into the second row to begin converting "successful" to "failed" in my formula. Unfortunately, I had forgotten to use $ to help preserve the columns I wanted to pull data from, and spent a good amount of time pondering why I was getting a significant number of zero values. I manually adjusted for a while, then remembered to add a $ before transferring over to the "canceled" column.
![Unlocked_Formula](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Unlocked_Formula.png)
![Locked_Formula](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Locked%20Formula.png)

---
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
![Theater_Outcomes_vs_Launch](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

1. Fundraising around December and January seem to be the worst time for success. I would assume the global popularity of Christmas would contribute heavily. Competing for everyone's attention and money are incredibly difficult at this time of the year.
2. May and June look like the best potential months for launching a campaign. There are significantly more successful campaigns seeing success in this timeframe, with a slight dip in failed campaigns launched in June.

- What can you conclude about the Outcomes based on Goals?
![Outcomes_vs_Goals](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Outcomes_vs_Goals.png)

The two most distinct areas of success appear to be less than $5,000 and $35,000 to $44,999. Therefore:
That second round of heavy success had such a heavy and distinct drop-off, I would guess (and verify in the table) there weren't a significant number of overall campaigns, which is skewing the data.
![Skewed_Data_Highlights](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Skewed_Data_Highlights.png)

With more data to back up the trend, campaigns with goals below $5,000 genuinely tend to be distinctly more likely to be successful, rather than the 50/50 split for some slightly larger amounts. 

- What are some limitations of this dataset?
One of the main limitations I noted was the outliers. One campaign had a fundraising goal of $10, which it exceeded. Therefore, it's a "successful" campaign. There were a handful of strange outliers that undoubtedly skew the data story. 

For the US data, it would have been interesting to track where the campaigns launched regionally, and overlay it with something like income levels. I suspect drilling down into the local market might offer additional insights.

A deeper layer of data I found myself curious about was not just the success of the kickstarter, but the overall financial viability of the production. If *Fever* set a goal of $5,000 and reached that fundraising goal, they technically did not raise enough capital for the production to happen - Louise had a budget of $10,000. Does the dataset allow for tracking a single project with multiple kickstarters? Do projects with multiple kickstarters do progressively worse?

The currency could pose an issue when comparing kickstarter goals and success rates. For example, 4,000 GPB is quite different from 4,000 USD. Comparing without a conversion feels like it could skew the data.

When looking at Outcomes Based on Goals

- What are some other possible tables and/or graphs that we could create?
The additional tables I would create from this dataset are:
1. Number of backers & average donation in conjunction with goal. Are campaigns seeing huge numbers of donors or are they seeing a few donors with big bucks that might skew some of the data?
2. Lengh of campaign. Does campaign length impact anything?
