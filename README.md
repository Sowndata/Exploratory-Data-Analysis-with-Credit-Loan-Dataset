# Exploratory-Data-Analysis-with-Credit-Loan-Dataset
This is a dataset with the 100 top-rated movies from the past decade along with various pieces of information about the movie, its actors, and the voters who have rated these movies online.  This project is to find some interesting insights into these movies and their voters, using Python.

The key aspects of this project is to perform effective exploratory data analysis using python

### **Data understanding and preparation**

Identifying and removing the redundant variables

Removing the variables having extremely high number of missing values as we will not get any information from variables having more than 50 percent of missing values. Missing value and outlier treatment are mandatory steps to make the data clean and ready for analysis.

Identified the values to replace missing values

Missing values have been identified and replaced appropriately.

Identified the outliers in the data

CNT_CHILDREN, AMT_INCOME_TOTAL, AMT_CREDIT, AMT_ANNUITY, AMT_GOODS_PRICE ,DAYS_EMPLOYED are few columns which have outliers and are treated accordingly.

### **Data cleaning and Manipulation**

Data quality issues

Data quality issues have been resolved. For Example, as the days are given as negative values, we need to used -round() to convert it into positive values. We need to do the same transformation for other dates. 

It can be performed like:

curr_appl['DAYS_BIRTH']=curr_appl['DAYS_BIRTH'].apply(lambda x:int(abs(x)/365))

Binning continuous variables

Converted annual salary, income_credit into bins (binning annual income into high, medium, low). We can drive more insights from that. It is also one of the way to treat outliers.

### **Data Analysis**

 Covered all aspects of EDA such as univariate, bivariate etc. This is an essential step before we start performing machine learning.

Division of data

Since there is a data imbalance, hence we have divided the data into 2 categories with target=0 and target =1. It would make more sense to perform analysis on target=0 dataframe rather on full data.

Dividing the dataset for target=1(client with payment difficulties) and target=0(all other)

loan_data_Target0=loan_data.loc[loan_data["TARGET"]==0]

loan_data_Target1=loan_data.loc[loan_data["TARGET"]==1]

Segmented Univariate Analysis

Performed segmented univariate analysis covering most of the relevant categorical and continuous variables. This will help us extracting important insights and observations from the data which in turn helps businesses to make accurate decisions.

Correlation matrix

Compared the correlation and calculated the top 10 correlated pair of continuous variables. This is an important step to know the highly correlated variables. This step is significant when we apply Machine learning on this data.

Joined the previous application dataframe

Merged the previous application data with the application data to perform bivariate analysis. 

Bivariate Analysis

Analyzed contract status (loan status approved, canceled, refused, etc.) and found how various variables such as gender, loan type, education are impacting loan status using bivariate analysis.

Finally, business recommendations (Insights)  based on the data analysis are presented. Identifying key drivers and their impact on the business is the most important idea behind performing descriptive analytics.
