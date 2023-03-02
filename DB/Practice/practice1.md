Задания для самопроверки по Базам Данных
Практика 1:

1. 
SELECT p.Name, p.Color, p.Size

FROM Production.Product AS p

2.
SELECT p.Name, p.Color, p.Size

FROM Production.Product AS p

WHERE p.ListPrice > 100

3. 

SELECT p.Name, p.Color, p.Size

FROM Production.Product AS p

WHERE p.ListPrice > 100 AND p.Color = 'Black'

4.

SELECT p.Name, p.Color, p.Size

FROM Production.Product AS p

WHERE p.ListPrice > 100 AND p.Color = 'Black'

ORDER BY ListPrice ASC

5.
SELECT TOP 3 p.Name, p.Size
FROM Production.Product AS p
WHERE p.Color = 'Black'
ORDER BY ListPrice DESC

6.
SELECT p.Name, p.Color
FROM Production.Product AS p
WHERE p.Color is NOT null AND p.Name is NOT null

7.
SELECT DISTINCT p.Color
FROM Production.Product AS p
WHERE ListPrice BETWEEN 10 AND 50

8.
SELECT p.Color
FROM Production.Product AS p
WHERE p.Name like 'L%' AND p.Name like '__N%'

9.
SELECT p.Name
FROM Production.Product AS p
WHERE p.Name like '[DM]%' AND LEN(p.Name) > 3

10.
SELECT p.Name
FROM Production.Product AS p
WHERE p.SellStartDate>='2012-01-01'

11.
SELECT p.Name
FROM Production.ProductSubcategory AS p

12.
SELECT p.Name
FROM Production.ProductCategory AS p

13.
SELECT p.FirstName
FROM Person.Person AS p
WHERE p.Title = 'Mr.'

14.
SELECT p.FirstName
FROM Person.Person AS p
WHERE p.Title is null
