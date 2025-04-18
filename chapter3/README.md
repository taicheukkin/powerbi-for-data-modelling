# Data preparation in power query editor
## 1.1 M-formula query in power query

let 
   Variablename=expression1
  
   #'variablename'=experssion2

in 

   #'Variable name'

- #'variable name'create a query formula step and  reference any the pervious formula step in Power Query
  
![image](https://github.com/user-attachments/assets/a7ec86db-aa06-451b-87df-b0fab4412c4d)

primitive value 
- primitive value: constant value such as number, text,null.

structured value
- contains either primitive values or other structured values
- four structured value: list,record,table,function value

list value: a sequence of values in only one column

![image](https://github.com/user-attachments/assets/3ca6e594-bf92-4364-b5f5-b08d6f2a3dcf)


record value: a set ot field that make rows of data

![image](https://github.com/user-attachments/assets/5b1e1751-8489-4e99-92bb-111c6e0a63d1)

record value containing list value

![image](https://github.com/user-attachments/assets/fb0fa63e-c597-4980-a842-9bdb78b4ad21)


Table value：a set of values organized into columns and row

            ： two way to organize table
![image](https://github.com/user-attachments/assets/4656d8f0-c504-4b13-92e6-f8c4b93b4136)

table holding two lists containing primitive value

![image](https://github.com/user-attachments/assets/3a77d803-5933-4d56-93d3-5ccfef7f4e7a)


Expanding the structured column to new rows

![image](https://github.com/user-attachments/assets/e0f37f95-ff03-44ce-a5dd-37b9508ec86c)


Function value： accepts input parameter
              
              ：followed by output data type（=>)

![image](https://github.com/user-attachments/assets/484c6733-b5e7-43c8-ad5e-986c1c3ea6e7)

list of primitive type
-binary,date, datetime,datetimezone, duration, list,logical, null,number ,record, text, time , type, function, table, any, none


## 1.2 Introduction to power query editors

![image](https://github.com/user-attachments/assets/5bc9d721-3d03-4630-854e-807374402d1e)

![image](https://github.com/user-attachments/assets/6b56fe6f-3293-46dd-838f-9228a13f9cfb)

![image](https://github.com/user-attachments/assets/bb34ff06-f4f0-45e0-ac19-9a345c79674a)

Power query editor has the following function
- 1.ribbon bar, 2.The queries pane, 3.The query setting pane 4.The data view pane 5. statu bar

query pane
- contain table, customer function(fx), query parameters, constant value
- Groups function: to larger  model that may have many queries referencing other queries

![image](https://github.com/user-attachments/assets/ba19a9b3-7928-4a16-b976-9882bafa1596)

tips: select multiple tables by pressing and keeping down Ctrl key

![image](https://github.com/user-attachments/assets/13817445-199e-4dc2-b76e-e848a393c55d)
 
query setting pane 
- two parts : properties and applied steps
  
![image](https://github.com/user-attachments/assets/1c3412df-10b1-4bda-8bb6-4b16e7003d1b)
- you can rename a selected query though query properties

![image](https://github.com/user-attachments/assets/55ea3f88-7966-495c-9c60-857f42c303f1)
- enable load: if this option is not enabled, data will not load into this model
- but if other queries reference this particular query , the others queries will go though all transformation step applied to particular query
- include in report refresh： if ths option is enabled, the query will be refreshed whenever the data is refreshed
  

Data view query

![image](https://github.com/user-attachments/assets/6123df41-2de8-483b-a07d-c6a51299abd5)



![image](https://github.com/user-attachments/assets/88bfcddf-e8f0-4abc-bf20-730d0bffdc79)

- enter parameter:to invoke a function when selected query is a custom  function 

![image](https://github.com/user-attachments/assets/949abee7-ae53-4a60-9f63-336de13ccff6)

output as constant value

![image](https://github.com/user-attachments/assets/f54797a4-ff05-4768-9fdd-8a112d5bc49a)



statu bar

![image](https://github.com/user-attachments/assets/c4a860f2-715a-41f2-bb43-058e4984e54e)

- number of columns

- columns profiling

advanced editor
- to create a bew query or modify an existing query
 ![image](https://github.com/user-attachments/assets/87b859c6-4f21-409a-bff1-6d11f593ea6b)


## Introduction to power query feature for Data modeler

![image](https://github.com/user-attachments/assets/e4faa73f-b581-462a-8e0b-25872707d597)
-setting column profiling to be calculated based on entire dataset


Column quality

![image](https://github.com/user-attachments/assets/9f38f878-0c28-4731-a771-7e60fdd4f636)

![image](https://github.com/user-attach
ments/assets/7c210e57-efbf-4559-9156-2daa324b34bc)

- we can copy data quality for documentation

![image](https://github.com/user-attachments/assets/f650305d-01a2-48b5-b434-8a5f364fb0a2)

- The step for choosing The column

column distribution

![image](https://github.com/user-attachments/assets/f2def41c-c8e5-4366-957f-617bbc8ad1d6)

![image](https://github.com/user-attachments/assets/a4a92aeb-9e0f-4321-909b-6745b95fbf36)
- We want to get lower cardinality

column profile

![image](https://github.com/user-attachments/assets/e3c88f32-9b5d-4a96-bb85-3e010f836d31)
- see more information about selected value


## Understanding query parameter
- we can parametize data source, filter row ,keep rows, remove rows, replace rows

 ![image](https://github.com/user-attachments/assets/895cd826-a97c-4d8c-96d2-a501fb247082)
- step 7: seselect a type from the dropdown list
- step 8 : enter the value depend on the type
  
it is best practice to avoid hardcording the data source by parameterizing them 

![image](https://github.com/user-attachments/assets/36cf29a6-207d-4fa5-8203-f79f342f86e8)
- one keeps server name ,one keep database name  in order to switch from development (Dev) to User acceptance environment(UAT)

![image](https://github.com/user-attachments/assets/280ca00b-3743-48a8-9903-2f39dc3eafd0)

- change query parameter values from power query editor and main window
![image](https://github.com/user-attachments/assets/6e4dc554-9241-4155-8113-cafbc02e385e)

![image](https://github.com/user-attachments/assets/90b30342-52c5-4d31-ad90-2fe1ae374077)


## Understanding custom function

- take care of all calculation logic needed
- define custom funciton as an inline custom function and invoke it within a single query in the advaccned editor
  ![image](https://github.com/user-attachments/assets/1fcbcc0d-24d9-4d5e-9b46-62c1b8a8f92f)

Case study 3.1

- to split the name of 37 columns in product table

  ![image](https://github.com/user-attachments/assets/65323c95-f8bf-4017-ba38-eb8cbadc9912)

- select blank query and open advanced query

    ![image](https://github.com/user-attachments/assets/f528da4a-64d0-44a4-b923-efc1fed8cf84)
    ![image](https://github.com/user-attachments/assets/f52270eb-ff39-425e-b197-d4a9c2e5bf6a)
  - column name is input parameter,resulting in the list of texts

enable formula bar option in power query editor

- ![image](https://github.com/user-attachments/assets/2eba5db4-d5fb-4804-a9f6-279abf15df67)

from formula bar, click the add step buttom(fx)

- ![image](https://github.com/user-attachments/assets/afeb24c8-f15e-4f30-b20d-161eaeba0cb1)

 use teble.transformcolumnName() function and rename all the column
- ![image](https://github.com/user-attachments/assets/12a6f7ec-2f13-4220-a2de-f108cd0cf139)
- ![image](https://github.com/user-attachments/assets/3f2a1750-465f-4ee4-961b-a5f5136a6ada)



Case study 3.2 Recursive function
- create factorial function
- eg. 10!=1*2*3*4*5*6*7*8*9*10

- let
    factorial=(validnumber as number) as number
    if ValidNumber <0
    then error "Negative numbers are not allowed to calculate factorial. Please  select a positive number."
    else
        if validNumber=0
        then 1
        else ValidNumber *@ Factorial(validnumber -1)     
     in
       Factorial

  ![image](https://github.com/user-attachments/assets/27e90491-d54b-4048-b403-566992a0e8fa)

  ![image](https://github.com/user-attachments/assets/1683f69c-a3d8-498f-82a3-ce83a2be4bd2)

  ![image](https://github.com/user-attachments/assets/e64dfdaa-160b-4a92-8b79-f2b29bfd6b37)
