# DATA115: Washington State Government Finance Data
## Motivation

### Questions:
#### (1) Which resource accounts for the most revenue of the state government?
#### (2) Which resource of the revenue has the highest growth rate in the last 5 years?
#### (3) What is the trend of the fiscal year financial balance of WA in the past 10 years? Surplus or debt? Growing or decline?

## Data Sources
In this project, both Washington State government's [finances data](Raw_Data/WAgov_Finance_2012_2019.csv) and [detailed tax colleciton data](Raw_Data/WA_TaxCollectionsDetailed_2016_to_2020.csv) are obtained from US Census Bureau. According to US Census Brueau, the data is collected by a mail canvass of state government offices that are directly involved with state finance and state-administrated tax.
The finances data contains total of 384 recordes about the government's revenues, taxes, and expenditures from 2012 to 2019.
The detailed tax collection data provides a total of 155 recordes from 2016 to 2020, including 30 tax categories.
## Data Process
The main issue for those two datasets is the numbers are stored as text instead of numbers. 
Another issue is that many columns have the same values, and those columns are not necessary for this project. For example, in Finances Dataset, the whole column of Geographic Area Name are Washington.

There are two datasets, and I performed some processing steps for both data sets:
#### (1) Finances Dataset
1. I deleted the first row and 9 columns but only left three columns, which are Year, Meaning of Aggregate Description, and Amount.
2. I converted the values in column Year and column Amount to Number.
3. "X" in column Amount means incomplete information or not applicable information. I replaced "X" with "0" in the column Amount.
#### (2) Detailed Tax Collection Dataset
1. I deleted three columns: Geographic Area Name, Meaning of Survey Component, Meaning of Type of Government.
2. I converted the values in column Year and column Amount Formated to Number.
3. I ordered the data set by Aggregated Description in Descending. 
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

