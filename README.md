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
Measure	Formula
Gross Sales	GS $ = SUM(fact_actuals_estimates[gross_sales_amount])
Net Invoice sales	NIS $ = SUM(fact_actuals_estimates[net_invoice_sales_amount])
Pre Invoice Deduction	Pre Invoice Deduction $ = [GS $]-[NIS $]
Post Invoice Discount	SUM(fact_actuals_estimates[post_invoice_deductions_amount])
Post Invoice other Deduction	 SUM(fact_actuals_estimates[post_invoice_other_deductions_amount])
Total Post Invoice Deduction	[Post Invoice Deduction $] + [Post Invoice other Deduction $]
Net Sales	NS $ = SUM(fact_actuals_estimates[net_sales_amount])
Manufacturing Cost	SUM(fact_actuals_estimates[manufacturing_cost])
Frieght Cost	SUM(fact_actuals_estimates[freight_cost])
Other Cost	SUM(fact_actuals_estimates[other_cost])
Total COGS	[Manufacturing Cost $] + [Freight Cost $] + [Other Cost $]
Gross Margin	GM $ = [NS $]- [Total COGS $]
Gross Margin %	GM % = DIVIDE([GM $],[NS $],0)
GM/ Unit	DIVIDE([GM $], [Quantity], 0)
Operational Expense	(SUM(fact_actuals_estimates[ads_promotions])+SUM(fact_actuals_estimates[other_operational_expense]))*-1
Net Profit	[GM $]+[Operational Expense $]
Net Profit %	DIVIDE([Net Profit $], [NS $], 0)
<img width="605" height="521" alt="image" src="https://github.com/user-attachments/assets/71c6cf98-9b30-41b7-80f1-f136dde32491" />


