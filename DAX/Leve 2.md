### 5. Create a measure to find Total Sales by Region using related tables.
This can be done by many ways-<br>

1. With Allexcept
```
   Sales by Region = 
CALCULATE(
    [Total Sales],
    ALLEXCEPT(Customers, Customers[Region])
)
```

