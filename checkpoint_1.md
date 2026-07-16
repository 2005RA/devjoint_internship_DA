# Checkpoint 1 — Basic SELECT / WHERE / ORDER BY / LIMIT

### Query 1: Which products cost more than $50, cheapest first?
```sql
SELECT ProductName, UnitPrice
FROM Products
WHERE UnitPrice > 50
ORDER BY UnitPrice ASC;
```
![Query 1 result](Results/cp1_q1.png)

---
