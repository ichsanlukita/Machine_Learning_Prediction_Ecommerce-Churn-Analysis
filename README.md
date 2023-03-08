# Caspstone-3---Muhammad-Ichsan-Lukita---Ecommerce-Churn-Analysis


# E-commerce Customer Churn
by: Muhammad Ichsan Lukita


---
# Backgrounds:
An E-commerce aims to adjust the strategy for customer churn that occurs. Analysis is needed to identify the most likely customer tendencies to leave the service within the platform.

In order to preserve revenue health within the organization besides getting customers retaining existing customers from churning is very important for the company.
<br><br>
Therefore an analytical approach with Machine Learning is considered as the suitable forecasting approaches in presenting insights to find pattern based on predictions and recommendations on the business strategy


---
# Problem Statement:
- What factors can influence customer churn?
- What business strategies can companies implement to reduce churn rates and retain customers?


---
# Objective:
- Finding potential dependent factors on customer churn
- Provide measurable predictive results as recommendations for strategic steps,
in order to provide promotions that are right on target to maintain customer loyalty

# Conclusion:


 - FP:
we predict the customer will churn (action --> we give a promotion at a cost of $100), even though it actually doesn't churn
- FN:
we predict that the customer will not churn (action --> we don't pay attention to this customer), even though it actually churns (losing a customer at a cost of $500)




- FP Cost:
$150
-FN Cost:
$675


**Without using ML**

 Before using ML, the company did not know which customers would be churned, so it had to pay for promotions to all customers. Companies do not want to take risks because the cost of losing customers is greater.

 We assume that when a customer is given a promotion, that customer will not churn.

 - Company expenses on promotion (TP+FP+TN+FN):
$150 x 653 = $97,950
- Targeted promotion at churn (TP+FN):
$150 x 107 = $16,050
- This means that the company spends promotional costs in vain on loyal customers:
$ 97,950 - $ 16,050 = $ 81,900

 **By using ML**

 After using ML, companies can predict which customers will churn, so that they can spend on promotions that are more targeted. - Business expenses for false advertising to loyal customers (FP):
$150 x 46 = $6,900
- Companies lose customers due to unpredictable churn (FN).
$675 x 15 = $10,120
- This means that the company has suffered a loss.
$6,900 + $10,120 = $17,020

 **Less reduction after using ML**

 - Loss before using ML:
$81,900
- Loss after using ML:
$17,020
- ML succeeded in reducing the company's loss by 79.21% --> ($81,900 - $17,020) / $81,900 


-----
# Recommendation
  
**Businesses**:

- Customers with a Tenure period of less than 3 months have to be our concern how to retain them by giving promos in this case could be Cashback, Discount, etc.

- Customers with the distance between Warehouse To Home categorized in the range 5 - 15 KM having the likelihood to be churn. Meaning we have to trigger them by using promotions such as free delivery


- Customers who are 9 months from the last day of purchase in DaySinceLastOrder. It is necessary to give promotions to customers with these criteria to stimulate purchase activities, as a retention strategy

- Implementing prediction analysis by developing Machine Learning in order to capture the churn pattern of a customer.



**Machine Learning and Data**:

- There are columns with other features that are directly related to the services that e-commerce companies provide and customer transactions, such as the average number of customer purchases, the number of product purchases per month, the duration of product delivery, and so on

- A model can be improved by tuning hyperparameters with values already obtained as references or by adding additional parameters. 

- There are columns with other features that are directly related to the services that e-commerce companies provide and customer transactions, such as the average number of customer purchases, the number of products purchased per month, the duration of product delivery, and so on. 

- Raise the consumer data to produce predictions that are more accurate. 

- The requirement to equate formats or commercial phrases to prevent meaning bias.
