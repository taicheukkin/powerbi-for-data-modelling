

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



