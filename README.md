

# chapter 1 
## powerbi layer

1. the data preparation layer
- power query

2. data model layer
- the data view/The model view 

3. the data visualization layer
- the report view
- eg.calcuated table,calculated columns and measures

data flows
- data visualization <-data model<-data preparation
 

## query parameter
- defined in the data preparation layer (transformation step)
-  eg. name column is filtered by the parameter list(list of capital letter, E,O,P)
- the value in the parameter list are not loaded into data model u

## efficient datamodel
- perform well
- be business-driven
- decrease the level of complexity
- be maintainable with low costs

## case study
O data
- slow to load because of online resource
- Consider import a portion of data(1 or 2 year data)
- 1 GB file size(if you have powerbi pro licence)

Excel
- Many formula quite hard to maintain
- Need to be prepared to replicate a lot of formulas in powerbi (modifying in excel may easily break your data processing in power query)

Data warehouse in sql server
- characteristics: the grain of both fact table From time perspective is  day,hour,minutes
- Decide to import a portion of data or whole data(if so, composite model with aggregation is prefered)
- Analyze the metric down to the minutes or day level enough

- A big mistake to start getting data from the source systems before framing your questions around business processes. Requirement, technology limitation


 ## star schema and snowflaking 

Transaction system(snowflake schema)
- Improve system performance in Creating new records and updating/deleting existing records
- Go through normalization process to decrease data redundancy and data entry performance

Star schema
- the table has been already joined based on business entities
- denormalized table
- business is not interested in seeing transaction at the second level

Depending on the business requirement
- end up having some level of normalization along with some denormalization
- prefer denormalization so that it can describe all the detail as much as possible


## Hands on exercise
- goal: denormalize the product category and subcategory table
- Star+Snowflakes: product+(subcategory+product category)

- Denormalized to only product table by merging queries(left join) in  power query



## file size
- Maximum size of individual dataset 
- 1 GB for each dataset published to Powerbi service

To keep the file size just below the limit
- import necessary columns only
- import just a portions of data 
- filter some data
- use aggregation to a very low granularity
- Eg. Minutes to day level


## data load
Incremental data load 
- Significantly improve data refreshing performance 
- decrease amount of processing load on the tenant


Shared dataset(professional and permium users)
- a dataset used across various reports in a modern workplace
- powerbi professionals and powerbi premium licensing plans


Powerbi dataflows(professional and permium users)
- You can share data perparation, data cleaning and data transformation

Data modeling is an ongoing process
- information gathering from the business -> data preparation based on business logic ->data modeling ->test the logic->Demonstrating the business logic in basic data visualization ->

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

T- he join must have same lineage if there is physical relationship between two tables


## Notes
The best practice is to implement business logic in source code when possible

- If not ,using power query editor
- If create virtual logic multiple time  , create calculated table or physical relationship without granularity of table


