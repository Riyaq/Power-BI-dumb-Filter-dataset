Take this as a table -
```
DateTable = ADDCOLUMNS(
    CALENDAR(DATE(2024,1,1), DATE(2025,10,30)),
    "Year", YEAR([Date]),
    "MonthNumber", MONTH([Date]),
    "MonthName", FORMAT([Date],"MMMM"),
    "Quarter", FORMAT([Date],"Q"),
    "WeekDay", FORMAT([Date],"dddd")
)
```
