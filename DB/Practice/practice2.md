Задания для самопроверки по Базам Данных  
Практика 2:  

1.
SELECT Color, COUNT(*) AS Count  
FROM Production.Product AS   
WHERE ListPrice >= 30 AND Color is NOT null  
GROUP BY Color  

2.
SELECT Color, MIN(ListPrice) AS MinPrice  
FROM Production.Product  
WHERE ListPrice >= 100 AND Color is NOT null  
GROUP BY Color  

3.
SELECT ProductSubcategoryID, COUNT(*) AS Count  
FROM Production.Product    
GROUP BY ProductSubcategoryID  

4.
SELECT ProductID, COUNT(SalesOrderDetailID) AS Count  
FROM Sales.SalesOrderDetail  
GROUP BY ProductID  

(Можно в каунт не вставлять ордеры, а считать просто айдишники)

5.
SELECT SalesOrderID, COUNT(SalesOrderDetailID) AS Count  
FROM Sales.SalesOrderDetail  
GROUP BY SalesOrderID  
HAVING COUNT(SalesOrderDetailID) > 5  

6.
SELECT CustomerID, COUNT(SalesOrderID) as Count  
FROM Sales.SalesOrderHeader  
GROUP BY CustomerID, OrderDate  
HAVING COUNT(SalesOrderID) > 1  

7.
SELECT SalesOrderID, COUNT(ProductID) AS Count  
FROM Sales.SalesOrderDetail  
GROUP BY SalesOrderID  
HAVING COUNT(ProductID) > 3  

8.
SELECT ProductID, COUNT(SalesOrderID) AS Count  
FROM Sales.SalesOrderDetail   
GROUP BY ProductID  
HAVING COUNT(SalesOrderID) > 3  

9.
SELECT ProductID, COUNT(SalesOrderID) AS Count  
FROM Sales.SalesOrderDetail   
GROUP BY ProductID  
HAVING COUNT(SalesOrderID) = 3 OR COUNT(SalesOrderID) = 5  

10.
SELECT ProductSubcategoryID, COUNT(*) AS Count  
FROM Production.Product  
GROUP BY ProductSubcategoryID  
HAVING COUNT(*) > 10  

11.
SELECT ProductID  
FROM Sales.SalesOrderDetail  
WHERE OrderQty = 1  
GROUP BY ProductID  

12.
SELECT TOP 1 SalesOrderID  
FROM Sales.SalesOrderDetail  
GROUP BY SalesOrderID  
ORDER BY COUNT(DISTINCT ProductID) DESC  

13.
SELECT TOP 1 SalesOrderID  
FROM Sales.SalesOrderDetail  
GROUP BY SalesOrderID  
ORDER BY SUM(UnitPrice * OrderQty) DESC  

14.
SELECT ProductSubcategoryID, COUNT(*) AS Count  
FROM Production.Product  
WHERE ProductSubcategoryID is NOT null AND Color is NOT null  
GROUP BY ProductSubcategoryID  

вместо * может быть ProductID

15.
SELECT Color, COUNT(ProductID) AS Count  
FROM Production.Product  
WHERE Color is NOT null  
GROUP BY Color  
ORDER BY COUNT(ProductID) DESC  

16.
SELECT ProductID, COUNT(OrderQty) AS Count   
FROM Sales.SalesOrderDetail   
WHERE OrderQty > 1  
GROUP BY ProductID  
HAVING COUNT(DISTINCT SalesOrderID) > 2
