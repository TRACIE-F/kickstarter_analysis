# Kickstarter Analysis for *Fever*

## Overview of Project
The following data and analysis were compiled to support a successful fundraiser for production of *Fever*. 

### Purpose
In an effort to support additional kickstarters for the production of *Fever*, we analyzed pre-existing kickstarter data to determine what factors may contribute to successful outcomes. By analyzing the kickstarter goals in relation to success rate, we can help determine what a additional realistic goals for *Fever* look like, and make suggestions for adjustments that could contribute to a better fundraising outcome. By analyzing kickstarter launch dates in relation to success rate, we can further improve chances for a successful outcome, even if only by avoiding months with extremely low success rates. Simply put, our data analysis is meant to take the lessons learned from other theater fundraisers and implement them to *Fever*'s benefit.   

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
![Theater_Outcomes_vs_Launch](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)
Determining the outcomes of a theater kickstarter based on the launch date began with cleaning up the original data.

1. Dates
![Date_Conversion](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Date_Conversion.png)
The original data contained Epoch dates, which I had never encountered before. It's safe to say that most idividuals will have a much easier time interpreting data utilizing standard dates.

2. Split category
![]()
Splitting up the parent category and subcategory allowed for more nuanced data sorting, and for the purpsose of this specific analysis, allowed me to filter by the "theater" parent category.

With this cleaned data, I created a pivot table (pictured below) which counted the number of successful, failed, and canceled kickstarter campaigns sorted by the month they launched. 

### Analysis of Outcomes Based on Goals
![Outcomes_vs_Goals](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Outcomes_vs_Goals.png)
This graph also began with a data cleanup, building on the work stated above.
1. Years, to sort any trends from year to year.
![]()

### Challenges and Difficulties Encountered
### Theater Outcomes Based on Launch Date
With the "Theater Outcomes Based On Launch Date" chart, I encountered minor challenges in setting up my pivot table.
![Chart_Order](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Chart_Order.png)
Initially, the data order was "Canceled," "Successful," and then "Failed." This made my line chart a little more difficult to follow at a glance as the key was in a different stacked order than the data on the graph. A little bit of Googling helped me re-arrange the columns without disrupting the data. 
A challenge I anticipated, but did not run into with this chart, was ensuring the timeline was using a row label that was months rather than quarters. Other tables automatically defaulted the timeline to quarters, and I was able to correct this with assistance from [Pryor Learning](https://www.pryor.com/blog/grouping-excel-pivottable-data-by-month/).

### Outcomes based on Goal
The "Outcomes Based on Goal" chart was much more of a challenge. First and foremost, determining how to set the parameters between two sets of numbers (ex. 1000 to 4999) presented some challenges. Google sorted those challenges out quickly. Sorting out the "COUNTIFS" formula was a matter of trial and error once I figured out how to pull the columns I needed. I tested my first formula (less than 1000), and then went back to the main "Kickstarter" sheet to utilize filters and do a rough count to feel more confident in my results.

**Fewer 9s**
![Locked_Formula](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Locked%20Formula.png)
To make the formula easier to type out, I utilized some critical thinking skills. I then realized early on typing whole numbers at least felt easier than multiple 9s, and chose to make my formulas start with "greater than or equal to" the bottom number, and "less than" the bottom range for the next row.

**Locking Columns**
![Locked_Formula](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Locked%20Formula.png)
![Unlocked_Formula](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Unlocked_Formula.png)
Another challenge I encountered was a result of sheer forgetfulness. As soon as I determined the proper formula for the first row, I copied and pasted it over into the second row to begin converting "successful" to "failed" in my formula. Unfortunately, I had forgotten to use $ to help preserve the columns I wanted to pull data from, and spent a good amount of time pondering why I was getting a significant number of zero values. I manually adjusted for a while, then remembered to add a $ before transferring over to the "canceled" column.

---
## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
![Theater_Outcomes_vs_Launch](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

1. Fundraising around December and January seem to be the worst time for success. I would assume the global popularity of Christmas would contribute heavily. Competing for everyone's attention and money are incredibly difficult at this time of the year.
2. May and June look like the best potential months for launching a campaign. There are significantly more successful campaigns seeing success in this timeframe, with a slight dip in failed campaigns launched in June.

- What can you conclude about the Outcomes based on Goals?
![Outcomes_vs_Goals](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Outcomes_vs_Goals.png)

The two most distinct areas of success appear to be less than $5,000 and $35,000 to $39,999. Therefore:
That second round of heavy success had such a heavy and distinct dropoff, I would guess (and verify in the table) there weren't a significant number of overall campaigns, which is skewing the data.

![Skewed_Data](https://github.com/TRACIE-F/kickstarter_analysis/blob/main/Resources/Skewed_Data.png)

With more data to back up the trend, campaigns with goals below $5,000 genuinely tend to be distinctly more likely to be successful, rather than the 50/50 split for some slightly larger amounts. 

- What are some limitations of this dataset?
Currency unconverted, strange outliers (goals of $10 are successful), a lack of follow-up after a successful campaign was the play produced or did they not raise enough capital, 

- What are some other possible tables and/or graphs that we could create?
Backers & average donation in conjunction with goal. Are campaigns seeing huge numbers of donors or are they seeing a few donors with big bucks that might skew some of the data?
Lengh of campaign - does campaign length impact anything?
