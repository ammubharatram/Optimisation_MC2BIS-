# Optimisation Of Transaction Monitoring Process in AML Using A Statistical Approach

## Description 
### **Problem:** 
Due to increasingly strict Anti Money Laundering regulations banks, among others, are:
1) Receiving sometimes billions of euros in fines for not complying properly
2) Hiring teams of people to manually investigate the alerts generated by current AML systems

### **Our Goal:**
Develop new system using sound statistical methodology that:
1) Complies with current regualtions
2) Automatically reduces the number of false positives generated and hence investigator workload

## Data:
For privacy reasons we cannot release data set but it is alerted transaction data from a Hungarian bank collected over 2 years (Aug 2014 - Sept 2016).

## **Overview of plan:**
![2 Stage Process](https://user-images.githubusercontent.com/30290960/30808840-f2261de4-a1ff-11e7-8dd6-3b748376f57a.PNG)

Detailed presentation can be found here ![2 Stage Process](https://user-images.githubusercontent.com/30290960/30808840-f2261de4-a1ff-11e7-8dd6-3b748376f57a.PNG)

### Flow of transactions
- *'Transactions'* generated when a customer of the bank buys or sells something.
- All *'Transactions'* go through AML system and turn into *'Alerts'* when a customer performing a transaction coincides with one of the hypothesized rules for money launderers, eg. a transaction is made to or from a high risk country.
- *'Alerts'* are then investigated over a period of 2 years and at the time of the query (assumed just after Sept 2016) we were given the status of the alerts. From this we could deduce whether the alerts were put forward to *'SAR'* or not.

Stage 1 - We receive data set of alerted transactions with labels of SAR (Suspicious Activity Report) or No SAR. 
- Our goal here is to:
  - Create predictive model to predict No SAR and find the optimal cut off value to autclose non suspicious alerts
  - Explain importance of the variables (Very important as bank employee must be able to explain to investigator why the AML system has autoclosed an alert)

Stage 2 - We take a look at the rules used to generate the original alerts and tune them for each customer profile. This will reduce the original number of alerts generated next time around!

### *Stage 1*
Methodology:

1) Initial Data Cleaning
2) Top down segmentation - domain knowledge based segmentation of bank customers (personal, government, small or medium Enterprises and medium to large companies)
3) Feature selection, replacing missing values  
4) Standardization and exploratory analysis - Ridit Scoring
5) Bottom up clustering - algorithm based clustering (Sparse K means, Clara, Robust Spare K-means)
6) Model Building - Logistic regression, XGBoost, LogitBoost, Decision Tree, Random Forest
7) Model Evaluation and Autoclosing of alerts

### *Stage 2*
Methodology:

1) Get each scenario and extract rules from each
2) Take scenario one and extract current threshold value for each rule and store it
3) On each customer profile tune scenario one
4) Repeat for all scenarios

See Wiki for details

## **Still To Do**
- Find optimal cut off value for best model of Cluster 1
- Develop stage 2 optimisation and link in subgroup discovery algorithm with this (to generate data driven rules instead of knowledge based)
3) 

## **Issues That Arose And Improvements To Be Made**


 
 
## Team:
- https://github.com/robbiebroughton
- https://github.com/CarlosOrtegaV
- https://github.com/ammubharatram
