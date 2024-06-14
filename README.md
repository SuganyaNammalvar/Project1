



# PWC-Customer Churn Dashboard


## Problem Statement

Extracted customer demographics and insights for the retention manager reflecting the KPIs.

Following tasks are:

.Define proper KPIs.

.Create a dashboard for the retention manager reflecting the KPIs.

.Write a short email to him (the engagement partner) explaining your findings, and include suggestions as to what needs to be changed.

.Services each customer has signed up for: phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies.

.Customer account information: how long as a customer, contract, payment method, paperless billing, monthly charges, total charges and number of tickets opened in the categories administrative and technical.

.Demographic info about customers – gender, age range, and if they have partners and dependents.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : In this dataset,it has 23 columns and 7043 rows.
- Step 5 : Added additional conditional column named "Loyalty".Formula is "if tenure is less than 12 then output will be < 1 year"
and so on ..

- Step 6:Remove unnecessary rows and columns 

- Step 7 :Each of the column were validated under the correct data type.
- Step 8 :Close and load into PowerBI.


 Following DAX expression were used:

% of partner = divide(CALCULATE(COUNT(Churn_table[Partner]),Churn_table[Partner]="yes",Churn_table[Churn]="yes"),calculate(count(Churn_table[Partner]),Churn_table[Churn]="yes"),0)

% of dependents = divide(CALCULATE(COUNT(Churn_table[Dependents]),Churn_table[Dependents]="yes",Churn_table[Churn]="yes"),calculate(count(Churn_table[Dependents]),Churn_table[Churn]="yes"),0)

% of senior citizen = divide(CALCULATE(COUNT(Churn_table[SeniorCitizen]),Churn_table[SeniorCitizen]=1,Churn_table[Churn]="yes"),calculate(count(Churn_table[SeniorCitizen]),Churn_table[Churn]="yes"),0)

Churn rate % = divide(CALCULATE(COUNT(Churn_table[Churn]),Churn_table[Churn]="yes"),calculate(count(Churn_table[Churn]),ALLSELECTED(Churn_table[Churn])))

Count of multiplelines yes = CALCULATE(COUNTA(Churn_table[MultipleLines]),Churn_table[MultipleLines]IN{"yes"})

% of Tech support = divide(CALCULATE(COUNT(Churn_table[TechSupport]),Churn_table[TechSupport]="yes",Churn_table[Churn]="yes"),calculate(count(Churn_table[TechSupport]),Churn_table[Churn]="yes"),0)   

% of streaming movies = divide(CALCULATE(COUNT(Churn_table[StreamingMovies]),Churn_table[StreamingMovies]="yes",Churn_table[Churn]="yes"),calculate(COUNT(Churn_table[StreamingMovies]),Churn_table[Churn]="yes"),0)

% of phone service = divide(CALCULATE(COUNT(Churn_table[PhoneService]),Churn_table[PhoneService]="yes",Churn_table[Churn]="yes"),CALCULATE(COUNT(Churn_table[PhoneService]),Churn_table[Churn]="yes"),0)

% of paperless = divide(CALCULATE(COUNT(Churn_table[PaperlessBilling]),Churn_table[PaperlessBilling]="yes",Churn_table[Churn]="yes"),calculate(COUNT(Churn_table[PaperlessBilling]),Churn_table[Churn]="yes"),0)

% of Online backup = divide(CALCULATE(COUNT(Churn_table[OnlineBackup]),Churn_table[OnlineBackup]="yes",Churn_table[Churn]="yes"),calculate(count(Churn_table[OnlineBackup]),Churn_table[Churn]="yes"),0) 

% Multiple LINES = divide(CALCULATE(COUNT(Churn_table[MultipleLines]),Churn_table[MultipleLines]="yes",Churn_table[Churn]="yes"),calculate(count(Churn_table[MultipleLines]),Churn_table[Churn]="yes"),0)   

% Device protection = divide(CALCULATE(COUNT(Churn_table[DeviceProtection]),Churn_table[DeviceProtection]="yes",Churn_table[Churn]="yes"),calculate(count(Churn_table[DeviceProtection]),Churn_table[Churn]="yes"),0)   

streaming TV in % = divide(CALCULATE(COUNT(Churn_table[StreamingTV]),Churn_table[StreamingTV]="yes",Churn_table[Churn]="yes"),calculate(COUNT(Churn_table[StreamingTV]),Churn_table[Churn]="yes"),0)


 

       
        


 
 # Report Snapshot (Power BI DESKTOP)

 ![image](https://github.com/SuganyaNammalvar/Project1/assets/142667989/2c318ce9-a9a0-4d59-971c-1fffd0f18055)


 
![image](https://github.com/SuganyaNammalvar/Project1/assets/142667989/f1e94c83-0f19-41ba-b76f-a961c9e4637a)

 
 


### Insights

.7,043 customers are identified as being at risk of churning.

.The customer base is fairly balanced, with 49.52% male (3,490 customers) and 50.48% female (3,560 customers).

.The most common payment method is electronic (2.4K customers), followed by mailed check (1.6K), bank transfer (1.5K), and credit card (1.5K).

.Highest churn rate at approximately 50% in electronic check.

.Lower churn rates(Bank transfer,credit card,Mailed check)compared to electronic check.



### Improvement Areas

.Given the high churn rate among customers using electronic check, consider providing more secure and convenient payment options.

.Implement loyalty programs for long-term subscribers to encourage retention.

.Educate Customers who has the lower churn rates associated with mailed checks, bank transfers, and credit cards might encourage customers to switch from electronic checks.


