# DATA115: Washington State Government Finance Data
## Motivation
As a senior student with a major of Accounting, I was curious about the governmental financial performance. When I assessed the financial data of Washington state government, I noticed that governmental revenues consist of many scources, such as intergovernmental revenue, general revenue, utility revenue, total taxes, and so on. Thus, through this project, I would like to find out the answers of the questions: 
1. What was the revenue performance of Washington state government from 2012 to 2019? 
2. Did revenue increase or decrease stably or in certain pattern? If no, which revenue resources might be responsible for it? 
3. How does each revenue resource contribute to the total revenue?

## Data Sources
I obtained [WAgov_Finance_2012_2019.csv](Raw_Data/WAgov_Finance_2012_2019.csv) from US Census Bureau.
According to US Census Brueau, the data sets are collected by a mail canvass of state government offices that are directly involved with state finance and state-administrated tax.
## Data Process
The main issue for the dataset:
1. The numbers are stored as text instead of numbers. 
2. Many columns have the same values, and those columns are not necessary for this project. For example, in Finances Dataset, the whole column of Geographic Area Name are Washington.
3. Everyting is mixed in the same columns. For example, total revenue, total expenediture, and other revenue sources are all in the same column, and their amounts are all in the "Amount" column. This issue makes it hard to process the data and produce charts.

The processing for the raw dataset are performed as following steps:
1. Delete unncessary columns and row, and remain the three columns: Year, Meaning of Aggregate Description, and Amount.
2. Convert the values in column Year and column Amount to Number.
3. Replace "X" in column Amount with "0."
4. Extract revenue-related rows from raw dataset and save as seperate csv file [Revenue.csv](Processed_Data/Revenue.csv). 
5. Extract expenditure-related rows from raw dataset and save as seperate csv file [Expenditure.csv](Processed_Data/Expenditure.csv).
6. Extract total revenue and total expenditure from raw dataset and save as seperate csv file [Total.csv](Processed_Data/Total.csv).

## Visualization
Once I started to process the data, I wondered the changes in total revenue and total expenditure from 2012 to 2019. 
Figure 1 is a line chart that represents the trend of total revenue and total expenditure from 2012 to 2019. 
Figure 2 includes two boxplots that represent the changes in total revenue and total expenditure indivigually from 2012 to 2019.
Both charts show the total revenue was not as stably growing as the total expenditures over time. 
In the line chart, we can also see that the total revenue decreased in 2015 and 2016 and was even less than the total expenditure. 
The boxplot shows that total revenue has a larger IQR than total expenditure, indicating that total revenues spread out further. In other words, yearly total revenue wasn't growing steadily.

|Figure 1                                                                        | Figure 2                                                             |
|--------------------------------------------------------------------------------|:--------------------------------------------------------------------:|
|                  <img src="image folder/line_chart.png">                       |           <img src="image folder/boxplot_changes.png">               |

## Analysis
In order to see which revenue sources affected the decrease in the total revenue in 2015 and 2016, I used a stacked bar chart to gain insight into each revenue source's contribution to the total revenue. Figure 3 represents the breakdown of total revenue into each revenue source. We can see that most revenue sources had steady growth except Insurance Trust Revenue, which decreased in 2015 and 2016. 

#### Figure 3.
<img src="image folder/rev12-19.png">

I further used boxplot to see the distrubution of each revenue source over time. In Figure 4, we can intuitively see that Insurance Trust Revenue had the largest IQR compared to other revenue sources. This indicates that Insurance Trust Revenue fluctuate overtime and may have a larger deviation than other sources. 

#### Figure 4.
<img src="image folder/boxplot_rev_src.png">

Though liquor store revenue has an outlier in the boxplot, its amount, as shown in Table 1 is not large enough to affect total revenue. 
#### Table 1. Liquor Store Revenue from 2012 to 2019
|Year|Liquor Store Revenue|
|----|:------------------:|
|2012|$612106             |
|2013|       0            | 
|2014|       0            | 
|2015|       0            | 
|2016|       0            | 
|2017|       X            |   
|2018|       X            |    
|2019|       X            |

*Data extracted from raw dataset [WAgov_Finance_2012_2019.csv](Raw_Data/WAgov_Finance_2012_2019.csv). "X" means data not available. Amount in $ million.*

## Conclusion
Compared to steadily increasing expenditure, the Washington state government's total revenue fluctuates due to fluctuating Insurance Trust Revenue.
Total revenue consists of 7 primary sources: Intergovernmental Revenue, Utility Revenue, Liquor Store Revenue, Total Taxes, Insurance Trust Revenue, Current Charges, and Miscellaneous General Revenue. Insurance Trust Revenue was the main source that affected the decrease in total revenue in 2015 and 2016. Utility Revenue and Liquor Store Revenue account for tiny portions that don't really affect the fluctuation of the total revenue. Total Taxes accounts for the most significant part of the total revenue. It also has stable growth, so I would have liked to carry out additional analyses to extend this analysis.

## References
US Census Bureau.(2021). *State Government Finances: US and States: 2012 - 2019.* US Census Bureau:https://data.census.gov/cedsci/table?q=Washington%20state&t=State%20Government%20Finances&tid=GOVSTIMESERIES.GS00SG01&hidePreview=true
