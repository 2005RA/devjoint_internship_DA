### Ranking products by price within each categrory
```sql
-- LEt's rank products by price within each category (RANK). We should number them (ROW_NUMBER) and track cumulative revenue over time (running SUM)

-- Query 1: Ranking products by price within their category
SELECT ProductName, CategoryID, UnitPrice,
       RANK() OVER (PARTITION BY CategoryID ORDER BY UnitPrice DESC) AS PriceRank
FROM Products;
```
![Result](Results/ch5_r1.png)


```sql
-- Query 2 Number every order per customer, oldest first
SELECT CustomerID, OrderID, OrderDate,
       ROW_NUMBER() OVER (PARTITION BY CustomerID ORDER BY OrderDate) AS OrderNumber
FROM Orders;
```
![Result](Results/ch5_r2.png)

```sql
-- Query 3: Running total of revenue over time (month by month)
SELECT strftime('%Y-%m', o.OrderDate) AS Month, -- '%Y-%m' this part takes year and month from the date.
       SUM(od.UnitPrice * od.Quantity * (1 - od.Discount)) AS MonthlyRevenue,
       SUM(SUM(od.UnitPrice * od.Quantity * (1 - od.Discount))) 
           OVER (ORDER BY strftime('%Y-%m', o.OrderDate)) AS RunningTotal
FROM Orders o
INNER JOIN "Order Details" od ON o.OrderID = od.OrderID
GROUP BY Month
ORDER BY Month;
```
![Result](Results/ch5_r3.png)

