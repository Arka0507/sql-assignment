# SQL Assignment – Data Reconciliation (data1 vs data2)

## Problem
Compare two order datasets using `Order ID` + `Product ID` as a composite key
and find the records that don't match.

## What I did
- Found records in data1 but missing in data2 (LEFT JOIN + IS NULL): **X records**
- Found records in data2 but missing in data1 (RIGHT JOIN + IS NULL): **Y records**
- Calculated the total quantity of the missing records using SUM
- Counted unique Order ID + Product ID combinations

## Sample query
```sql
SELECT COUNT(*) AS Total_Missing
FROM data1 d1
LEFT JOIN data2 d2
  ON d1.`Order ID` = d2.`Order ID` AND d1.`Product ID` = d2.`Product ID`
WHERE d2.`Order ID` IS NULL;
```

## Skills shown
SQL joins · NULL handling · aggregation · data validation

## Files
- `SQL_Assignment.docx` – full questions, queries and output screenshots
