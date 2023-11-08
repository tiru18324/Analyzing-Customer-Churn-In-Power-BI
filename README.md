# Analyzing-Customer-Churn-In-Power-BI 
---
# Meta data Information
![Screenshot (185)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/6e050c5b-9873-4dde-b5ff-0e088ca31abe) 

# Exploratory Analysis: 
## Step 1 : To create measures and columns
  - we start by creating 2 measures Count of Customers and count of unique customers both are same.
  - Next step we calculate the churn rate with the column churn label having parameters "yes" or "no"
  - In order to calculate churn rate we have to calculate churned customers and apply this formula.
  - `churn rate=churned customers/Total no of customers`
  - it shows the churn rate is **26.86%**.
## Step 2: Investigating Churn Reasons: 
  - Created a column chart to of why customers churned.
    
  ![Screenshot (186)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/88ec79c1-616d-41e8-b583-f57a325ed35f) 
  - By seeing this column chart we can say that **16.87% of our customers leaved** because competitor made better offer it means that we are **not competitive enough** and also 16.54% have left they have better devices both reasong having the same percentages tells that we need to work on our devices, 11% have left they **didn't got the support from the support person** telling we need to work on support persons too
  - Other factors accounting to 5%.
    
    - This tree map shows **main categories of churn** :
      
    ![Screenshot (187)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/d2187094-b179-483a-a271-eeb02d09c3a3)

## Step 3: Using Maps to find Competitors:
   ![Screenshot (188)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/daf0039e-d869-42b7-a3cb-42bb5419a75b)

   - From the above map **churn rate w.r.t no of customers** tells that majority of churned customers are located in california and has **churn rate of 63.24%** , **out of 68 customers 43 customers are churned** which company needs on focus on why it is happening in that california area.
   - Next major state is Pennsylvania. churn rate of **33% which is half** the churn rate of california.

---

# Investigating Churn Patterns - Analysis 

## Analyzing Demographics:
 - In the demographics in metadata we have 2 columns named:
   - Under 30
   - Senior
- Using this we create a measure named demographics with this formula.
  
``` Demographics = if('Databel - Data'[Senior]="Yes","Senior",if('Databel - Data'[Under 30]="Yes","Under 30","Other")) ``` 
- It tells that **seniors having the churn rate 38%** and under 30 people accounting for 23% and others between age groups of abover 30 and below 65 accounting for 24%.
- By creating we can analyze this more deeper with the different age groups having bin size of 5.
![Screenshot (189)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/7d35d5b2-8089-4212-b7ab-6b4c487fa6ed)
- From the above line and stacked column chart we can that churn rate is increasing **when the age is increasing**. we can see a significant amount of churned customers when the age is **60**.
- It also tells ours majority customers lies in the age 45 of customers 694 and age 25, count of customers 674.
- Few customers lies in the Age group 80-85.

## Inspecting Groups
- Databel offers group contracts to customers of same household.
- The advantage of customers is discounted rate. great way to grow the customer base.
- To analyze customers have lower phone bill it has impact on the churn rate
  
![Screenshot (190)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/57823825-943c-4652-854d-72d1a6407367) 

- The above line and stacked column chart tells the churn rate is very less for the groups 2-6 means customers who are having group contracts are less likely to churn.
- we can also there is significant price differences between the customers who are having group contract and no group contract.
- For no group contract people there is 32% churn rate and avg monthly charge is 33$.
- For group contract people the avg monthly charge is 22-23$ and churn rate is around 5-6%.

## Multiple fields to investigate 
- Databel has 3 contract types :
   - One Year
   - Two Year
   - Month To Month
-


  


                                                          



