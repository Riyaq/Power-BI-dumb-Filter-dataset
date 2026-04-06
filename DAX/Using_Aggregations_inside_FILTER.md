This is where FILTER becomes essential and cannot be replaced by simple CALCULATE filters.
### 1.Calculate the total sales value for products that have a total lifetime Quantity sold greater than 5.
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
