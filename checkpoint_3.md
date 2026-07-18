### Finding total revenue per company.
```sql
SELECT c.CompanyName, 
       ROUND(SUM(od.UnitPrice * od.Quantity * (1 - od.Discount)), 2) AS TotalRevenue -- (1-od.Discount) calculates how much aach company earned WITH the discount.
FROM Customers c
INNER JOIN Orders o ON c.CustomerID = o.CustomerID
INNER JOIN "Order Details" od ON o.OrderID = od.OrderID
GROUP BY c.CustomerID
ORDER BY TotalRevenue DESC
LIMIT 5;
```
[Query 2 result](Results/ch3_r9.png)]

---

### Find categories which have more than 10 products.
```sql
SELECT c.CategoryName, COUNT(p.ProductID) AS ProductCount
FROM Categories c
INNER JOIN Products p ON c.CategoryID = p.CategoryID
GROUP BY c.CategoryID
HAVING COUNT(p.ProductID) > 10;
--- We should use hAVING after grouping. But before grouping, we can use WHERE.
```
[Query 2 result](Results/ch3_r10.png)]

---

### Finding employees who sold more than 50000.
```sql
SELECT e.FirstName, e.LastName,
       ROUND(SUM(od.UnitPrice * od.Quantity * (1 - od.Discount)), 2) AS TotalSales
FROM Employees e
INNER JOIN Orders o ON e.EmployeeID = o.EmployeeID
INNER JOIN "Order Details" od ON o.OrderID = od.OrderID
GROUP BY e.EmployeeID
HAVING TotalSales > 50000
ORDER BY TotalSales DESC;
```
[Query 2 result](Results/ch3_r11.png)]

---





