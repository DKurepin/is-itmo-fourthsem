Задания для самопроверки по Базам Данных  
Практика 3:  

1.
SELECT P.Name, PSC.Name
FROM Production.Product AS P INNER JOIN
Production.ProductSubcategory AS PSC
ON P.ProductSubcategoryID=PSC.ProductSubcategoryID
WHERE ListPrice >= 100 AND Color = 'Red'  

2.
SELECT P.Name, PSC.Name
FROM Production.ProductSubcategory AS P INNER JOIN
Production.ProductSubcategory AS PSC
ON P.ProductSubcategoryID!=PSC.ProductSubcategoryID
AND P.Name = PSC.Name

По идее правильный запрос, но результатов ноль  

3.
SELECT PC.Name, COUNT(P.ProductID) AS Count
FROM Production.Product AS P INNER JOIN
Production.ProductSubcategory AS PSC
ON P.ProductSubcategoryID=PSC.ProductSubcategoryID
JOIN Production.ProductCategory as PC
ON PSC.ProductCategoryID=PC.ProductCategoryID
GROUP BY PC.Name  

4.
SELECT PSC.Name, COUNT(P.ProductID) AS Count
FROM Production.Product AS P INNER JOIN
Production.ProductSubcategory AS PSC
ON P.ProductSubcategoryID=PSC.ProductSubcategoryID
GROUP BY PSC.Name, PSC.ProductSubcategoryID  

5.
SELECT TOP 3 PSC.Name, COUNT(P.ProductID) AS Count
FROM Production.Product AS P INNER JOIN
Production.ProductSubcategory AS PSC
ON P.ProductSubcategoryID=PSC.ProductSubcategoryID
GROUP BY PSC.Name, PSC.ProductSubcategoryID
ORDER BY COUNT(P.ProductID) DESC  

6.
SELECT PSC.Name, MAX(P.ListPrice) AS MaxPrice
FROM Production.Product AS P INNER JOIN
Production.ProductSubcategory AS PSC
ON P.ProductSubcategoryID=PSC.ProductSubcategoryID
WHERE P.Color = 'Red'
GROUP BY PSC.Name, PSC.ProductSubcategoryID  

7.
SELECT v.Name, COUNT(p.ProductID) AS Count
FROM Purchasing.ProductVendor AS pv INNER JOIN
Purchasing.Vendor AS v
ON v.BusinessEntityID = pv.BusinessEntityID
JOIN Production.Product as p
ON pv.ProductID = p.ProductID
GROUP BY v.Name  

8.
SELECT p.Name
FROM Purchasing.ProductVendor AS pv 
INNER JOIN Production.Product as p
ON pv.ProductID = p.ProductID
GROUP BY p.Name
HAVING COUNT(DISTINCT pv.BusinessEntityID) > 1  

9.
SELECT TOP 1 p.Name AS ProductName
FROM Production.Product AS p
JOIN Purchasing.ProductVendor AS pv
ON p.ProductID = pv.ProductID
GROUP BY p.Name
ORDER BY COUNT(pv.BusinessEntityID) DESC  

10.
SELECT TOP 1 pc.Name AS CategoryName
FROM Production.Product AS p
JOIN Production.ProductSubcategory AS psc
ON p.ProductSubcategoryID = psc.ProductSubcategoryID
JOIN Production.ProductCategory AS pc
ON psc.ProductCategoryID = pc.ProductCategoryID
JOIN Purchasing.ProductVendor AS pv
ON p.ProductID = pv.ProductID
GROUP BY pc.Name
ORDER BY COUNT(p.ProductID) DESC  

11.
SELECT pc.Name AS CategoryName, COUNT(psc.ProductSubcategoryID) AS CountCategory, COUNT(p.ProductID) AS CountProduct
FROM Production.Product AS p
JOIN Production.ProductSubcategory AS psc
ON p.ProductSubcategoryID = psc.ProductSubcategoryID
JOIN Production.ProductCategory AS pc
ON psc.ProductCategoryID = pc.ProductCategoryID
JOIN Purchasing.ProductVendor AS pv
ON p.ProductID = pv.ProductID
GROUP BY pc.Name  

12.
SELECT v.CreditRating AS CreditRating, COUNT(ProductID) AS ProductCount
FROM Purchasing.ProductVendor AS pv
JOIN Purchasing.Vendor AS v
ON pv.BusinessEntityID = v.BusinessEntityID
GROUP BY v.CreditRating
