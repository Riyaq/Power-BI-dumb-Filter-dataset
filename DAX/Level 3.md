### 1. High-Value Transactions: Calculate the total sales value for transactions where the total value of that single transaction (Quantity * UnitPrice) was greater than $100.
```
Sales of High Value Transactions = 
CALCULATE(
    [Total Sales],
    FILTER(
        all(SalesOrders),
        SalesOrders[Quantity] * SalesOrders[UnitPrice] > 100
    )
)
```
