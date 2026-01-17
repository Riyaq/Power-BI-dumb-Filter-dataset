### What happens if you remove the relationship between SalesOrder and Product and try to calculate Total Sales by Category?

Step 1 : Remove relationship btw Product table and SalesOrder. <BR>
Step 2 : Write code
```
Total sales by Category =
     CALCULATE(
          [TOTAL SALES],
             TREATAS(                               
                      VALUES (Product[Product_id]), --Give me the list of ProductIDs that are currently visible.
                      SalesOrder(Product_id)
                    )
              )
```
TREATAS -- Treat these ProductIDs from Products table as if they are filtering SalesOrder[ProductID]
