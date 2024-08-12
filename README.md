# Intorduction
In this project, I worked on real data provided from both websites owned by The Recording Academy, the non-profit organization behind the famous Grammy Awards. I took on the task of examining the effect of splitting up the two websites, and analyzing the data for a better understanding of trends and audience behavior on both websites.

I then chose to compare my findings against grammy.com's number one competitor, The American Music Awards (theAMA.com), to further elaborate upon recommendations for KPI improvements to the developers at grammy.com to optimize their presence within the marketplace. 

# Background
My goal for this project was to be able to both demonstrate and hone my excel skillset to best transform and analyze the provided datasets for optimal business insights. Throughout the process I employed several different types of analytical tools with excel, such as:

- Advanced Formulas
- Statistical Analysis
- Pivot Tables
- A/B Testing
- Data Visualizations

# Objectives for the Project
1. Explore the Data
2. Analyze the Data
3. Device Breakdown
4. Communicate Findings
5. A/B Testing

# Tools I Used

- **Excel** was my primary tool employed to handle everything from data cleaning, transformation and visualization. I decided to use solely excel in order to best demonstrate my developed skillset with the software. 
- Version control was managed through **GitHub**, allowing for systematic tracking of changes, collaboration, and ensuring the integrity of the project's codebase.

# The Analysis

### Explore the Data

Before analyzing any dataset within excel I am always sure to reference the data dictionary provided to better understand the values within all records (rows) and categorys (columns) within a dataset.

| Column  | Description |
| ------------- | ------------- |
| date  | The data the data was captured |
| visitors  | The number of visitors that came to the website on the given date |
| pageviews | The total number of pageviews from all sessions on the given date |
| sessions | The number of unique sessions on the website on the given date. A session is a visit from a user to a webpage in a given time period. If they leave and come back later that would count as two sessions |
| bounced_sessions | The total number of sessions on the given date where the user did not interact with any content on the page |
| avg_session_durations_sec | The average session length in seconds for all sessions on the given date |
| event_type | Whether the date was a regular day or the day the Grammy Awards were being held |
| mobile_visitors | The number of visitors that came from a iOS, Android, or Tablet device on the given date |

I then created a line chart of the number of daily visitors to the Grammy.com website. This visualization helped me spot the days the Grammy Awards themselves were hosted.

<img width="661" alt="image" src="https://github.com/user-attachments/assets/e5368fca-6d23-49aa-ac5b-46e9224fc919">

*Our visualization clearly indicates a significant increase in website visitors around the month of Febuary every year. This is consistent with the timing of the annual Grammy award ceremony. Along with the Grammy's themselves, we also can identify a smaller, yet still substantial spike prior to the Grammy award show itself. This is expected given the information provided to us during our remote check-in with Katie Stockman the Director of Business Intelligence, who elaborated that this increase prior to the main award ceremony is due to the announcement of artist nominations which traditionally kick off the overall Grammy award season.*

I then utilized the Grammys Data sheet in order to create a PivotTable to compare the average daily website visitors on days when an award ceremony was held to those when no awards ceremonies were held.

| Row Labels | Average Visitors per Day |
| ---------- | ------------------------ |
| Grammy Awards | 1,389,590 |
| Regular Day | 32388 |
| Grand Total | 39,922 |

Strictly looking at the amount of traffic on the grammy.com website you can undoubtadly recognize the stark difference in visitors between the days surrounding the awards ceremony and every other day of the year. The Grammy celebrations themselves bring in approximately 1.3 million more visitors to the site compared to an average day within the year. That's over a 4,000% increase in traffic!


### Analyze the Data

The Recording Academy was interested in several KPIs (Key Performance Indicators) to determine if the change from one site to two separate sites has improved these KPIs. In this section I chose to analyze this by calculating the bounce rate, pages per session, and average time on site KPIs.

<img width="939" alt="Screenshot 2024-08-12 at 10 16 42 AM" src="https://github.com/user-attachments/assets/e9fdf645-654a-4755-842f-52d7fbf25c47">

Here is a brief breakdown of my findings:

***Lower User Engagement on Combined Grammys + TRA Data***
The pages_per_session metric for the combined Grammys + TRA data is the lowest at 1.86, compared to 2.78 for the Recording Academy and 2.25 for the Grammys data individually. This suggests that when users interact with both sets of data together, they tend to visit fewer pages per session, indicating lower user engagement.

***Higher Bounce Rate on Grammys + TRA Data***
The bounce rate for the combined Grammys + TRA data is the highest at 41.6%, compared to 33.7% for the Recording Academy and 40.2% for the Grammys data individually. A higher bounce rate indicates that a larger proportion of users are leaving the site without engaging further, which could suggest that the content or structure of the combined data is less effective at retaining user interest.

### Device Breakdown

The development team at grammy.com were eager to know the percentage of visitors coming from mobile devices (iOS, Android, Tablets). They wanted to optimize the experience for mobile users but needed to understand the percentage of mobile users in order to determine the impact it will have on the site. In order to complete this task I decided to use the XLOOKUP function in order to find which searches took place on a mobile device (1) and which didn't (0) and then generated a pivot table in order to calculate the percentage of mobile visitors:

```
=XLOOKUP([@date],'Grammys Data'!O:O,'Grammys Data'!P:P,"0")
```

<img width="728" alt="Screenshot 2024-08-12 at 10 37 43 AM" src="https://github.com/user-attachments/assets/c4f0d780-8ad3-40f0-9a92-c7e1bd4100ff">

Here is a breif breakdown of my findings:

***High Mobile Usage*** This high percentage indicates that the majority of visitors are accessing the site via mobile devices. This suggests that optimizing the website for mobile users is critical, as their experience could significantly impact overall user engagement and satisfaction. Given this insight, team grammy.com team should prioritize mobile-friendly design and functionality improvements to enhance the user experience for the vast majority of their audience.

### Communicate Findings

Based upon my findings during this project I was asked if my recommendation would be that the websites remain separate? I was asked to provide a 2-3 paragraph answer using details from the analysis work above explaining why or why not they should stay separate. Here is my following reccomendation:

"Following the analysis of the data provided by Ray and the team at Grammy.com, we can confidently recommend that continuing to leave the sites disjoined is the optimal business decision. Our insights demonstrate substantial improvements within the two new websites compared to the combined site, in the way of various key perfomance indicators (KPI's) such as pages per session, bounce rate and the average time on site. Looking at the average rate of pages per session we can see that by seperating the sites led to an increase for this metric by .5 to 1 page per session on average. The bounce rate also saw a significant decrease following the transition. Most notably the Recording Academy site saw nearly an 8% drop in thier bounce rate after the website split. Grammy.com also saw a bounce rate decrease, albeit not as notable as TRA at around a 1% drop. The average time on site is the most interesting KPI of the three, given that it is the only one that seems to display a decrease in overall visitor engagement rather than an increase. 

The previous website iteration was able to average around a minute and a half in time on site which was improved upon by the Recording Academy branch of the new webpages, at just over two minutes of visitor engagement. However, Grammy.com experienced a decrease to just over a minute of vistor engagement per session. Digging into the data a little deeper this discrepency may be likely due to the nature of the ceremonies themselves, with many visitors logging on to the site in order to quickly determine the award winners of the evening and then immediately leaving. This is also likely to be the primary contributing factor as to why the bounce rate for Grammy.com did not experience as much of a dercrease compared to that of the Recording Academy."

The grammy.com team was also interested in comparing metrics of the Grammy.com website to that of their main competitor, The American Music Awards (theAMAs.com). Below you will find a dashboard of the key metrics from The AMAs:

<img width="614" alt="image" src="https://github.com/user-attachments/assets/ac9e1847-108b-4f3c-bc80-d64f9ae507cb">

The following are my data-driven recommendations for the grammy team in order to better optimaize their websites performance:

"Given that the American Music Awards are the only a true competitor to the Grammy's and not the Recording Academy, we will only be comparing the AMA's dashboard to the findings discovered throughout our analysis of the grammy.com data. 
- Beginning with total visits, grammy.com averages just under 40K visitors per day while theAMA.com averages just under 38K per day. Looking further into the data we can also identify that this number is a 44% decrease from the month prior, making this metric a possible anomaly.
- It also looks to be that theAMA.com draws in far more mobile users (87%) than grammy.com (74%).
  - Marketing efforts to promote the Grammy app can likely lead to a boost in these numbers.
- The AMA's website also seems to generate a slightly higher page per session (PPS) rate at 2.74 PPS, compared to the Grammy's at only 2.25 PPS.
  - A/B testing ought to be perfomed in order to discover what information the average user is seeking and then leverage those insights to develop more strategic content to hopefully increase a vistors PPS.
- The KPI which demonstrates the widest delta between the AMA's and the Grammy's is that of average time on site. According to the AMA dashboard they are able to keep a visitor engaged onsite for an average of just under 6 minutes, while grammy.com is only achieving an average of under a minute and a half of visitor engagement.
  - That's a difference of 76.5% which could be possibly limited by incorporating videos on the homepage, incentivizing visitors to stay on the site longer.
- Finally, the bounce rate for the AMA's is almost 13% higher than that of the Grammy's.
  - Continuing to improve upon this KPI would also likely require further A/B testing to decipher what improvements in features such as; the webpage menu bar, animations during page changes, etc., would further decrease the bounce rate."

### A/B Testing

In my calculations for the grammy.com team, I noticed that there was indeed a difference in the pages_per_session metric between the "Grammys + TRA" content and the Recording Academy Data sheet. The development team wanted to know if that difference is *statistically significant* and asked me to perform an A/B Test on the results:

<img width="942" alt="Screenshot 2024-08-12 at 11 03 43 AM" src="https://github.com/user-attachments/assets/233f40d1-3a9a-4f2f-b668-d37e61be0005">

I reached these conclusions by choosing to run a two tailed t-Test within excel in order to verify my findings:

<img width="487" alt="Screenshot 2024-08-12 at 11 04 45 AM" src="https://github.com/user-attachments/assets/40bc10e1-f7e5-4566-b737-1455063cdd51">

# What I Learned

Deciding to embark upon this analytical endeavor I've successfully integrated advanved Excel functions and other features within my data analytical toolbelt:

***Excel Functions***: Crucial to data analysis because they enable efficient data manipulation, calculation, and visualization, allowing analysts to draw insights quickly from large datasets. Mastering these functions enhances accuracy and productivity, making it easier to identify trends, patterns, and outliers essential for informed decision-making.

***Statisical Aanalysis through Excel***: Provides a versatile and accessible platform to perform complex calculations, visualize data trends, and derive meaningful insights from datasets. Additionally, Excel's wide availability and integration with other tools make it an essential skill for efficiently analyzing and presenting data in various professional contexts.

***PivotTables***: Allows for quick and efficient summarization, organization, and analysis of large datasets, enabling users to uncover trends, patterns, and insights without complex formulas. Pivot tables also offer flexibility in dynamically adjusting the data view, making them a powerful tool for informed decision-making and reporting.

***A/B Testing***: Allows analysts to make data-driven decisions by comparing two versions of a variable, determining which performs better in real-world scenarios. This method not only improves the accuracy of conclusions drawn from data but also helps optimize outcomes by identifying the most effective strategies or changes.
