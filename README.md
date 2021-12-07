# DATA115: Washington State Government Finance Data
## Motivation
As a senior student with a major of Accounting, I was curious about the governmental financial performance. When I assessed the financial data of Washington state government, I noticed that governmental revenues consist of many scources, such as intergovernmental revenue, general revenue, utility revenue, total taxes, and so on. Thus, through this project, I would like to find out the answers of the questions: 
1. What was the revenue performance of Washington state government from 2012 to 2019? 
2. Did revenue increase or decrease stably or in certain pattern? If no, which revenue resources might be responsible for it? 
3. How does each revenue resource contribute to the total revenue?

## Data Sources
There are three raw data sets located in the folder [Raw_Data](https://github.com/yjysquid/DATA115/tree/main/Raw_Data):
1. [WAgov_Finance_2012_2019.csv](Raw_Data/WAgov_Finance_2012_2019.csv)
2. [WA_TaxCollectionDetailed_2016_to_2020.csv](Raw_Data/WA_TaxCollectionsDetailed_2016_to_2020.csv) 
3. [2015-stc-detailed.csv](Raw_Data/2015-stc-detailed.csv)

They are all obtained from US Census Bureau.
According to US Census Brueau, the data sets are collected by a mail canvass of state government offices that are directly involved with state finance and state-administrated tax.
## Data Process
The main issue for those datasets is that the numbers are stored as text instead of numbers. 
Another issue is that many columns have the same values, and those columns are not necessary for this project. For example, in Finances Dataset, the whole column of Geographic Area Name are Washington.

The processing for the first 2 raw datasets are performed as following steps:
1. Delete unncessary columns and row, and remain the three columns: Year, Meaning of Aggregate Description, and Amount.
2. Convert the values in column Year and column Amount to Number.
3. Replace "X" in column Amount with "0."
Then, we will get the two datasets:
[WAgov_2012_2019_Financial_data.csv](Processed_Data/WAgov_2012_2019_Financial_data.csv) and
[WA_TaxDetailed_2016_to_2020_processed.csv](Processed_Data/WA_TaxDetailed_2016_to_2020_processed.csv)

The processing for the third raw dataset are performed as following steps:
1. Delete unncessary columns and row, and remain only 2 columns: Tax Type and Washington.
2. Add a column "Year" between the two column and fill out Year column with "2015."
3. Change column title "Tax Type" to "Meaning of Aggregate Description."
4. Change column title "Washington" to "Amount."
5. Replace "X" in column Amount with "0."
6. Then, we will get the dataset:[2015-stc-tax_processed.csv](Processed_Data/2015-stc-tax_processed.csv) 

1. Merge those three processed datasets into one.
2. Remove duplicates and the records of 2012-2014 and 2020.
3. Then, we will get the dataset: [2015-2019_processed.csv](Processed_Data/2015-2019_processed.csv)
## Visualization
Once I started to process the data, I wondered the changes in total revenue and total expenditure from 2012 to 2019. 
Figure 1 is a line chart that represents the trend of total revenue and total expenditure from 2012 to 2019. 
Figure 2 includes two boxplots that represent the changes in total revenue and total expenditure indivigually from 2012 to 2019.
Both charts show the total revenue was not as stably growing as the total expenditures over time. 
In the line chart, we can also see that the total revenue decreased in 2015 and 2016 and was even less than the total expenditure. 
The boxplot shows that total revenue has a larger IQR than total expenditure, indicating that total revenues spread out further. In other words, yearly total revenue wasn't growing steadily.

|*Figure 1*                                                                      |*Figure 2*                                                            |
|--------------------------------------------------------------------------------|:--------------------------------------------------------------------:|
|                  <img src="image folder/line_chart.png">                       |           <img src="image folder/boxplot_changes.png">               |

## Analysis
In order to see which revenue sources affected the decrease in the total revenue, I used stacked bar chart to gain the insight of each revenue source's contribution to the total revenue. Figure 3 is a stacked bar chart that represents the breakdown of total revenue into each revenue sources. In Figure 3, we can see that most revnue sources have steady growth except Insurance Trust Revenue. We can intuitively see that Insurance Trust Revenue had larger change in amount than other revenue sources. The stacked bar chart shows Insurance Trust Revenue had a  obvious decrease in 2015 and 2016, compared to other income categories. 
*Figure 3*
<img src="image folder/rev12-19.png">
*Caption:*

<img src="image folder/box plot_rev12-19.png">



*Total Revenue = General Revenue + Liquor Store Revenue + Untility Revenue + Insurance Trust Revenue*

*General Revenue = Intergovernmental Revenue + Total Taxes + Current Charges + Miscellaneous General Revenue*

*Total Taxes = General Sales and Gross Receipts Taxes + Selective Sales and Gross Receipts Taxes + License Taxes +All Other Taxes*

## References

