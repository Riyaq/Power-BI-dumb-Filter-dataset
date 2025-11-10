### 1. Total Sales
```
Total Sales = 
sumx(SalesOrders, SalesOrders[Quantity]*SalesOrders[UnitPrice])
```
### 2. Total Profit
You can do this by Calculated Col as well.
```
Total Profit = 
CALCULATE( [Total Sales]-SUMX(SalesOrders,SalesOrders[Quantity]*RELATED(Products[CostPrice])))
```
### 3. Total Qty sold 
```
Total Qty Sold = 
sum(SalesOrders[Quantity])
```
### 4. Average Selling Price
```
AVG Selling Price / qty =
DIVIDE([Total Sales],[Total Qty Sold])
```
