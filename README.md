# DATA115: Washington State Government Finance Data
## Motivation
As a senior student with Accounting major, I have been curious about how Washington state's tax incomes contribute to the state government's finance. In this project, I'm going to explore the finances data of Washington state government from 2015 to 2019.   
### Questions:
#### (1) Which resource accounts for the most revenue of the state government?
#### (2) Which resource of the revenue has the highest growth rate in the last 5 years?
#### (3) 
1. What percentage does taxes account for the total revenue of the state government?
2. which tax category contributes to the largest portion?
3. 
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
## Visualization & Analysis

### Figure 1

<img src="WA_tax.png">

*Caption: Total Taxes are the sum of the General Sales and Gross Receipts Taxes, Selective Sales and Gross Receipts Taxes, License Taxes, and All Other Taxes.*

### Figure 2

![Scatterplot of WA State's License Taxes from 2012 to2019](lic_tax.png)

*The outliers happend in 2012 and 2018. The WA state government had extremely low License Tax collection in 2012, and extremely high amount in 2018.*


*Total Revenue = General Revenue + Liquor Store Revenue + Untility Revenue + Insurance Trust Revenue*

*General Revenue = Intergovernmental Revenue + Total Taxes + Current Charges + Miscellaneous General Revenue*

*Total Taxes = General Sales and Gross Receipts Taxes + Selective Sales and Gross Receipts Taxes + License Taxes +All Other Taxes*

## References

