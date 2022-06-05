# Exploratory-Data-Analysis-with-Credit-Loan-Dataset
This project aims at applying the idea of EDA in a real business scenario. Apart from applying the techniques basic EDA, we also develop a basic understanding of risk analytics in banking and financial services and understand how data is used to minimise the risk of losing money while lending to customers.

### **Business Understanding**

The loan providing companies find it hard to give loans to the people due to their insufficient or non-existent credit history. Because of that, some consumers use it as their advantage by becoming a defaulter. Suppose you work for a consumer finance company which specialises in lending various types of loans to urban customers. You have to use EDA to analyse the patterns present in the data. This will ensure that the applicants capable of repaying the loan are not rejected.

When the company receives a loan application, the company has to decide for loan approval based on the applicant’s profile. Two types of risks are associated with the bank’s decision:

- If the applicant is likely to repay the loan, then not approving the loan results in a loss of business to the company
- If the applicant is not likely to repay the loan, i.e. he/she is likely to default, then approving the loan may lead to a financial loss for the company.

The data given below contains the information about the loan application at the time of applying for the loan. It contains two types of scenarios:

- **The client with payment difficulties:** he/she had late payment more than X days on at least one of the first Y instalments of the loan in our sample,
- **All other cases:** All other cases when the payment is paid on time.

When a client applies for a loan, there are four types of decisions that could be taken by the client/company):

1. **Approved:** The Company has approved loan Application
2. **Cancelled:** The client cancelled the application sometime during approval. Either the client changed her/his mind about the loan or in some cases due to a higher risk of the client he received worse pricing which he did not want.
3. **Refused:** The company had rejected the loan (because the client does not meet their requirements etc.).
4. **Unused offer:**  Loan has been cancelled by the client but on different stages of the process.

In this project, We apply EDA to understand how consumer attributes and loan attributes influence the tendency of default.

### **Data Understanding**

This dataset has 3 files as explained below:

*1. 'application_data.csv'*  contains all the information of the client at the time of application.The data is about whether a **client has payment difficulties.**

*2. 'previous_application.csv'* contains information about the client’s previous loan data. It contains the data whether the previous application had been **Approved, Cancelled, Refused or Unused offer.**

*3. 'columns_description.csv'* is data dictionary which describes the meaning of the variables.

### **Data preparation**

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
