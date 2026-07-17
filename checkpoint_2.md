### 
```sql
SELECT o.OrderID, p.ProductName, c.CategoryName, q.Quantity # here o, p, c and q are aliases for Orders, Products, etc.
FROM Orders o # o alias for Orders table
INNER JOIN "Order Details" q ON o.OrderID = q.OrderID # q is alias for "Order Details" table. I used double quotes because normally sql does not parse spaces in table names.
INNER JOIN Products p ON q.ProductID = p.ProductID # Joins table Order Details and table Products with their mutual column ProductID.
INNER JOIN Categories c ON p.CategoryID = c.CategoryID
ORDER BY o.OrderID
LIMIT 20;
```sql 
