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
-- we will see the count of cutomers in each contract and churn rate in the contracts, is gender affecting the churn rate wrt contract.


![Screenshot (191)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/fbd73653-2d3e-4e41-8cc3-67adea35d38e)

- From the multi row card we can see that **46% churn rate is from monthly contracts** the people who have taken **monthly contract are more likely to churn than the people who taken yearly contract**.
- We can see that our customers prefer taking montly contracts 3411 **more than 50% are in those monthly contracts** followed by Two year and 1 year.
- while considering gender there is much differnce between the **male and female having churn rates of 45% and 47%**. Females is slightly higher than the male one.



## Unlimited Plans 

- Databel Has hypothesis that:
  
> people who are not on unlimited plan are most likely to churn.

To investigate how data plans affects the churn rate. 
- We will create 3 groups based on data consumption:
  
     - Less than 5GB
     - Between 5 and 10GB
     - 10 or more GB

``` Grouped Consumption = if('Databel - Data'[Avg Monthly GB Download]<5,"Less than 5 GB",if('Databel - Data'[Avg Monthly GB Download]<10,"Between 5 and 10 GB","10 or more GB")) ```


![Screenshot (201)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/ab252395-ddb7-48a4-a6fe-0952b82552d1)



- The **hypothesis is incorrect** based on the above table that the people who have taken **unlimited plan has more churn rate** than who didn't taken it. it also tells that we have 4494 customers in the unlimited data plan and **2193 customers are with no data plan** combining both we have 6687 customers.
- We will also see whether data consumption has any effect on it.

![Screenshot (203)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/1989c2b5-659f-4761-a78c-f44fbd9f19cd)


- From this above clustered bar chart we can see that group 1 i.e. **who use less than 5GB has 34% greater churn rate than people who dont use it** has less churn rate 12%.
- Group 2 and Group 3 are same wrt to the usage of unlimited data plan having **churn rates of 29-33%.**



# International Calls:

- To analyze international activity of customers and its relationship to churn rate.
- we create a matrix between this 2 column Intrplan and Intractive.
  
![S02](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/9d594584-e703-428c-94b5-858e061ea6d6) 

- From the above matrix we can see when **International plan is there and it doesn't have International calls active means there is more churn rate** for those customers having high churn rate of **71.19%**. 
- And viceversa International plan is not there and it have International calls active means there is more churn rate churn rate of 40.34%.
- If they dont have both means there is churn rate of 20%. lowest churn is possible when **both International plan and International calls active is yes having churn rate of 7.59%**.
  
![Screenshot (198)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/f7d2eb04-50d2-43bf-9c56-5767c1d5144f)

- If we consider the california state it has "International plan is yes and International calls not active means" - **100% churn rate in this category** which we need to focus.


# Contract Type: 

- Databel want to improve it's customer support since there are reported issues there lets analyze payment method, contract type and how many months a person is a customer
- lets see churn rate decreases over time or not. yes it decreases over time.
- Most of the customers who use payments is by
    - Debit card - 55.36%.,
    - Credit Card - 39.09%,
    - Paper check - 5%

![Screenshot (195)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/d71cdc58-0d3c-46ba-ad2a-a858ce76d10c) 

- we can see at the starting years of customer journey we have more churn rate with month to month 64% churn rate and it occured after 49 months of churn rate 63%.
- 1 year contract has churn rate 33% after 19 months and after 74 months.



# Sharing Your Analysis:

![Screenshot (199)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/f0b0abbe-7a1d-4053-adf3-1d733bd0697b) 

- Created a Dashboard by collating all the information from the best insights possible into databel Key concerns.
- How this **different churn categories, types of contracts, Reasons, States can effect** the churn.
- We can see that california has high churn in month-to-month Contract **churn rate of 79%**.
- 303 customers had churned because competitor made better offer and **1579 people churned are from month to month** contract type.
- 203 people have churned because of the attitude of our support person.


# Payment Method and Contract Category With Customer Service Calls: 

- For this we create a measure Avg Customer Service Calls ` Avg Customer Service Calls = (sum('Databel - Data'[Customer Service Calls])/COUNT('Databel - Data'[Customer Service Calls])) `

![Screenshot (200)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/1840d77d-8a06-4a03-aabb-62a75b165be1) 

- we have 6123 customer service calls from that **3112 calls we get from payment method of direct debit and having monthly contract** which makes half of our calls. having average customer service calls of 1.47 and those people having **churn rate of **53.90%**** and they have been customer of us i.e. account length of 18 months.
- After the Direct Debit we have paper check which has the avg customer service calls of 1.36 and has a churn rate of 57.33% and the account length of 8 months.
- For the people who are yearly contract also facing some issue with the direct debit payment having around 837 customer service calls which is greater when comapred to credit and paper check.
- The churn rate is high for those customers. now it is clear the people who uses customer service often are the people who churn more than average. In this case customers who are using monthly contract are using direct debit as payment method.



# International and Data Plan: 
- It is good to observe extra charges based on the data consumptions.
- For the people who use 10 or more GB having Avg Extra Data Charges of 31.19 and Average Extra International Charges of 46.76.
- The people who use less than 5GB has churn rate of 34.71% and having Avg international charge of 34.
- The people who are using data between 5GB and 10GB having same extra data charges of 31-32 but there is a significant difference with the international plan.
- **We can say the people have to pay extra if they are not on unlimited data plan and they are charged more for Extra Intenrational Charges**.


# More Insights: 

![Screenshot (202)](https://github.com/tiru18324/Analyzing-Customer-Churn-In-Power-BI/assets/71921628/23e567d8-c8da-4815-a8ec-250d62b8112c) 

- Even though we have higher churn rate for **california we have the less no of customer call**s. 44 customer calls.
- GA Has the 109 service call which is highest than all other states.


--- 
---
---






  


                                                          



