# chapter 2
## Virtual table 
- lineage :relationship between virtual table and physical table
- we can create relationships between those virtual table programmatically
	- Not actual relationship data model

Virtual table  vs calculated table 

- If you create DAX function to selectively load data from other table
  - calculated table

- If you do some table operation with data and load with the result
  - virtual table

 ## case study 2.1
 
 ![image](https://github.com/user-attachments/assets/9005838e-f770-49f3-8f97-943848c036ec)

 ![image](https://github.com/user-attachments/assets/ed0c052f-fad7-45b3-bbef-f65338ed00f5)
 
 - Create  virtual table by using filter table function
 - Sum function calculate the value

![image](https://github.com/user-attachments/assets/41c33dcc-82af-446e-ad4e-6177aac68b9b)

![image](https://github.com/user-attachments/assets/3426c938-31c5-4a4e-98c5-ec1232b8c68f)

- Create the virtual table of customers with more than 4 orders for products of products
- Filter function to filter the results of values() to show the customer keys that have more than 4 orders for products with a list price greater than 100

![image](https://github.com/user-attachments/assets/ffe3dc67-c4c6-499f-a4e1-b9cfaea5cbb8)

Visualizing displaying the result of virtual table
- You can create calculated table for visualizing the result of virtual table
- Using DAX studio to create calculated table


## case study 2.2
  ![image](https://github.com/user-attachments/assets/3928a593-3370-443c-8a52-4024515a4b8c)

  ![image](https://github.com/user-attachments/assets/34e862c4-52a9-48c3-9c39-e040dfc1d8cf)

One flat rate for the standard cost associated with each product

![image](https://github.com/user-attachments/assets/8525f33f-a490-4d61-b39c-a7fb02f8f3b1)

productstandardCost is grouped by  product key table


![image](https://github.com/user-attachments/assets/4223e77c-f704-47d8-8914-d5d2bea7c277)

Naturalinnerjoin: inner join
- We added 0 days to 'internet sales'[OrderDate] to construct for the virtual table derived from the internet sales table

- We multiplied currencykey by1  to construct the currencykeyjoin column in both table

- Must have same data type before inner join

- The join must have same lineage if there is physical relationship between two tables


## Notes
The best practice is to implement business logic in source code when possible

- If not ,using power query editor
- If create virtual logic multiple time  , create calculated table or physical relationship without granularity of table

## time intelligence
example of function
![image](https://github.com/user-attachments/assets/e8a529eb-06de-4421-ac87-fb4e84a71984)

![image](https://github.com/user-attachments/assets/ddc1ca33-01d9-4d84-b374-a56e1d8d0366)

![image](https://github.com/user-attachments/assets/e8f12d16-c17a-4a2d-a76b-09b696334bb6)

![image](https://github.com/user-attachments/assets/2a8ea875-97d4-4d1a-bee8-2db60124893c)


## Handling the null and adnormity

-step 1: create the calucated columns
![image](https://github.com/user-attachments/assets/baff5338-5dcd-4714-80d7-9dc1f565519e)

-step 2: return the MTD based on calculated columns
![image](https://github.com/user-attachments/assets/c3c2a83b-5a3a-4683-9143-7700f0933383)


## period over period calculation
- one area chart on the report canvas
- the user can choose between year over year or month over month calculation

![image](https://github.com/user-attachments/assets/56a82c90-ff72-4e14-aa59-0b0ef0cb9329)

![image](https://github.com/user-attachments/assets/1b1ac8b6-7cf0-4798-bf78-78d0ead15d4d)

![image](https://github.com/user-attachments/assets/598c03a9-4644-4a7b-897b-4a44e8022a73)

![image](https://github.com/user-attachments/assets/eb57860e-a961-4c4e-97cd-96b2973055b6)


two problem 
- MoM Variance as example
- incorrect variance values when there are no sales in a day last month
- future dates show up for internet sales LM

implication
- we want variance return internet sale when internet sale LM is null
- we want variance return null when internet sale is null 

Better method
![image](https://github.com/user-attachments/assets/5dea7261-1027-45e7-99b4-d9fb96b70e19)

explanation 

- all function
  - Returns all the rows in a table, or all the values in a column, ignoring any filters that might have been applied.

- firstnonblank function
  - Returns the first value in the column for which the expression has a non blank value.

- lastnonblank function
  -Returns the last value in the column for which the expression has a non blank value.

-filter function
 -get the valid dates that fall between two variable

-sumx function
  - sumx() iterate through the row of virtual table


 ## Create area chart
 
step1 create table
![image](https://github.com/user-attachments/assets/39e76dac-aa15-4b3c-9f55-1758bb1c0e8b)

step2 measure for end users to switch the measure dynamically 
![image](https://github.com/user-attachments/assets/e1d1c9c8-31f4-4575-a2ed-790b00d57226)

step 3 create area graph(pop variance) and slicer(period over period)
![image](https://github.com/user-attachments/assets/9b8a5164-c25c-4d7e-a1fd-aedc324410e6)

if the end user select MoM variance from the slicer it call the Internet Sales Variance measure, it calls internet sales YoY Variance 



##

