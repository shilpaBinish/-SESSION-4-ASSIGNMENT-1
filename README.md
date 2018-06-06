# -SESSION-4-ASSIGNMENT-1

df1 = data.frame(CustId = c(1:6), Product = c(rep("TV", 3), rep("Radio", 3)))
df2 = data.frame(CustId = c(2, 4, 6), State = c(rep("Texas", 2), rep("NYC", 1)))
df1 #left table
df2 #right table
For the above given data frames and tables perform the following operations:
1. Return only the rows in which the left table have match

> df=sqldf("select df1.custid,product from df1 inner join df2 where df1.custid=df2.custid")
> df
  CustId Product
1      2      TV
2      4   Radio
3      6   Radio

2. Return all rows from both tables, join records from the left which have matching keys in the right table.

> dfj=sqldf("select * from df1 inner join df2 where df1.custid=df2.custid")
> dfj
  CustId Product CustId..3 State
1      2      TV         2 Texas
2      4   Radio         4 Texas
3      6   Radio         6   NYC
