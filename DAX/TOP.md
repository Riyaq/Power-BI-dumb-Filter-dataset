### 1. Top 3 Customers on Sales
```
Top 2 Customers Sales = 
CALCULATE(
    [Total Sales],
    KEEPFILTERS(
        TOPN(
            2,
            ALL(Customers[CustomerName]),
            [Total Sales],
            DESC
        )
    )
)
```
```
Top 3 Customers by Sales = 
CALCULATE (
    [Total Sales],
    KEEPFILTERS(TOPN(
    2,
    ALL(Products[ProductName]),
    [Total Sales], DESC,
    Products[ProductName], ASC
)
 )
)
```
