# DAX Measures Used in Dashboard

## Total Sales
```DAX
Total Sales = SUM ( 'Orders'[Sales] )
Purpose: Calculates overall revenue from all orders.

**## Total Profit**
Total Profit =
SUM ( 'Orders'[Profit] )
Purpose:
Calculates overall profit from all transactions. Used in profitability cards and comparisons.

**## Product Sales Rank**
Product Sales Rank =
RANKX (
    ALL ( 'Orders'[Product Name] ),
    [Total Sales],
    ,
    DESC,
    DENSE
)
Purpose: Dynamically ranks products based on total sales

**## Top 3 Product Sales**
Top 3 Product Sales =
IF ( [Product Sales Rank] <= 3, [Total Sales], BLANK() )
Purpose: Returns sales value only for the Top 3 products to be used in visuals
