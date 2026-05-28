# Finance-Insights
# Goal of the Project
This project is done to create a dashboard showing trends of key finance metrics enabling data driven decision making.
# Procedure
1. Loading datasets from excel and SQL.
2. Creating a Data Model.
3. Computing key metrics using DAX measures.
4. Creating a table visual showing showuing key metric values for a current and last fiscal year and YOY change %.
5. Displaying key metrics trends over time in a line chart visual.
6. Created market-wise and product-wise analytical visuals with Year-over-Year (YoY) percentage change metrics
   
# DAX formula used to compute key metrics
P & L values = 

var res = SWITCH(
TRUE(),
MAX('P & L Rows'[Order]) =1, [GS $]/1000000,
MAX('P & L Rows'[Order])  =2, [Pre Invoice Deduction $]/1000000,
MAX('P & L Rows'[Order])  =3, [NIS $]/1000000,
MAX('P & L Rows'[Order])  =4, [Post Invoice Deduction $]/1000000,
MAX('P & L Rows'[Order]) =5, [Post Invoice other Deduction $]/1000000,
MAX('P & L Rows'[Order])=6,[Post Invoice Deduction $]/1000000+[Post Invoice other Deduction $]/1000000,
MAX('P & L Rows'[Order])  =7, [NS $]/1000000,
MAX('P & L Rows'[Order]) =8, [Manufacturing Cost $]/1000000,
MAX('P & L Rows'[Order])  =9, [Freight Cost $]/1000000,
MAX('P & L Rows'[Order])  =10, [Other Cost $]/1000000,
MAX('P & L Rows'[Order])  =11,[Total COGS $]/1000000,
MAX('P & L Rows'[Order]) =12, [GM $]/1000000,
MAX('P & L Rows'[Order]) =13, [GM %]*100,
MAX('P & L Rows'[Order]) =14, [GM / Unit],
MAX('P & L Rows'[Order]) =15, [Operational Expense $]/1000000,
MAX('P & L Rows'[Order]) =16, [Net Profit $]/1000000,
MAX('P & L Rows'[Order]) =17, [Net Profit %]*100)

return 
IF(HASONEVALUE('P & L Rows'[Description]), res, [NS $]/1000000)
#


