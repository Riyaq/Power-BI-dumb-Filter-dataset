This is where FILTER becomes essential and cannot be replaced by simple CALCULATE filters.
### 1. Calculate the total sales value for products that have a total lifetime Quantity sold greater than 5.
```
Sales where lifetime sold > 17 = 
CALCULATE(
    [Total Sales],
    FILTER(
        VALUES(Products[ProductID]),
        CALCULATE(SUM(SalesOrders[Quantity])) > 17
    )
)
```
### 2. Calculate the total sales value for products whose average transaction value (UnitPrice * Quantity) is less than $30, but whose total quantity sold is greater than 5.
```
Sales (Avg <30 && Qty >5) =
CALCULATE(
    [Total Sales],
    FILTER(
        VALUES(Products[ProductID]),
        CALCULATE(
            AVERAGEX(
                SalesOrders,
                SalesOrders[UnitPrice] * SalesOrders[Quantity]
            )
        ) < 30
        &&
        CALCULATE(SUM(SalesOrders[Quantity])) > 5
    )
)
```
