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

![image](https://github.com/user-attachments/assets/e8a529eb-06de-4421-ac87-fb4e84a71984)

![image](https://github.com/user-attachments/assets/ddc1ca33-01d9-4d84-b374-a56e1d8d0366)
