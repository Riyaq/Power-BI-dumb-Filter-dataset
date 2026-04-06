This is where FILTER becomes essential and cannot be replaced by simple CALCULATE filters.
<img width="1311" height="191" alt="image" src="https://github.com/user-attachments/assets/9b71eede-490d-421d-bb41-8c6fa2aa1737" />

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
<img width="1314" height="220" alt="image" src="https://github.com/user-attachments/assets/fd077053-6adf-4491-851c-7ffaad023320" />

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
<img width="1266" height="527" alt="image" src="https://github.com/user-attachments/assets/cc426c4f-af08-492c-9fb7-ba7c8fe7c324" />
<br>
<br>

### 3. Calculate Total Sales for products where Avg Transaction Value > 50
```Sales (Avg Txn > 50) =
CALCULATE(
    [Total Sales],
    FILTER(
        VALUES(Products[ProductID]),
        CALCULATE(
            AVERAGEX(
                SalesOrders,
                SalesOrders[Quantity] * SalesOrders[UnitPrice]
            )
        ) > 50
    )
)
```
