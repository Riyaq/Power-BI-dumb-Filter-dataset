### 5. Create a measure to find Total Sales by Region using related tables.
This can be done by many ways-<br>
Best to Worst <br>
KEEPFILTERS(light weight)> VALUES > ALLEXCEPT(Removes filters except some columns)> ALLSELECTED > REMOVEFILTERS / ALL <br> 
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

### 7. Calculate the total sales value, but only for products where the color is "Red".
```
Sales of Red Product = CALCULATE([Total Sales], Products[Color]="Red")
```
### 8.Calculate the total sales value for sales where the Quantity sold was greater than 2.
```
Sales of Product Qty more than 2 =
CALCULATE(
    [Total Sales],
    SalesOrders[Quantity] > 2
)
```
