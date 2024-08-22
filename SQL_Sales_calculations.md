Calculate total Sales by City

```SQL
SELECT Sales.Country, Owners.City, SUM(Procedures.Price) AS TotalSales
FROM Sales
LEFT JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode
LEFT JOIN Pets ON Sales.PetID = Pets.PetID
LEFT JOIN Owners On Pets.OwnerID = Owners.OwnerID
GROUP BY Owners.City
ORDER By TotalSales DESC;
```
Calculate total Sales by Pet Kind

```SQL
SELECT Pets.Kind, SUM(Procedures.Price) AS TotalSales
FROM Sales
LEFT JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode
LEFT JOIN Pets ON Sales.PetID = Pets.PetID
GROUP BY Pets.Kind
ORDER By TotalSales DESC;
```

Calculate total Sales by City and Pet Kind

```SQL
SELECT Owners.City, Pets.Kind, SUM(Procedures.Price) AS TotalSales
FROM Sales
LEFT JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode
LEFT JOIN Pets ON Sales.PetID = Pets.PetID
LEFT JOIN Owners On Pets.OwnerID = Owners.OwnerID
GROUP BY Owners.City, Pets.Kind
ORDER By Owners.City;
```

Calculate Average sales by City

```SQL
SELECT Owners.City, AVG(Procedures.Price) AS AverageSales
FROM Sales
LEFT JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode
LEFT JOIN Pets ON Sales.PetID = Pets.PetID
LEFT JOIN Owners On Pets.OwnerID = Owners.OwnerID
GROUP BY Owners.City
ORDER By Owners.City;
```
