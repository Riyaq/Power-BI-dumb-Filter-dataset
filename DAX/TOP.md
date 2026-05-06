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

### If you find your region slicer is actually not working then use ALLSELECTED instead -
```
Top 2 customer = CALCULATE( [Total Sales],
                            KEEPFILTERS(
                                        TOPN(2,
                                        ALLSELECTED(Customer[CustomerName]),
                                        [Total Sales], DESC)
                                     )
                          )

```



