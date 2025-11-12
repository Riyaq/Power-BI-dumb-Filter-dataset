### 5. Create a measure to find Total Sales by Region using related tables.
This can be done by many ways-<br>

1. With ALLEXCEPT
```
Sales by Region = 
CALCULATE(
    [Total Sales],
    ALLEXCEPT(Customers, Customers[Region])
)
```

2. With REMOVEFILTERS
```
Sales by Region 2 = 
CALCULATE(
    [Total Sales],
    REMOVEFILTERS(Customers),
    VALUES(Customers[Region])
)
```
3. With KEEPFILTERS
```
Sales by Region 3 = 
CALCULATE(
    [Total Sales],
    KEEPFILTERS(VALUES(Customers[Region])),
    ALL(Customers)
)
```
### 6. Create a measure to find percentage of Total Sales by Region using related tables.

```
% of Total Sales by Region 2 = DIVIDE([Total Sales]*100,CALCULATE([Total Sales],all(Sheet1)))
```
