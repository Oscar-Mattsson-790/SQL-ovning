# SQL-ovning

------------------

2a: SELECT title FROM albums 
2b: SELECT title FROM albums ORDER BY Title ASC

3: SELECT * FROM albums WHERE ArtistId = 58

4: SELECT * FROM customers WHERE Country = 'Canada'
ORDER BY LastName ASC

5: SELECT FirstName, LastName FROM customers WHERE Company = 'Microsoft Corporation'

6: SELECT FirstName, LastName FROM customers WHERE Company IS NULL

7: SELECT FirstName, LastName FROM customers WHERE Country = 'Sweden' OR Country = 'Spain'

8: 
a) SELECT COUNT(*) as count
FROM customers
WHERE Country = 'USA' AND Fax IS NULL;

b) SELECT COUNT(*) as count
FROM customers
WHERE Country = 'USA' AND Fax IS  NOT NULL;

c) SELECT COUNT(*) as count
FROM customers
WHERE Country = 'USA' AND State = 'CA' AND Fax IS  NOT NULL;

9: SELECT Email
FROM customers
WHERE Email LIKE '%com'
OR Email LIKE 'jack%'
OR Email LIKE 'stan%'
OR Email LIKE '%murray%'

10a: SELECT FirstName, LastName
FROM customers
WHERE PostalCode LIKE '6%' 
OR PostalCode LIKE '7%' 
OR PostalCode LIKE '8%'
OR PostalCode LIKE '9%'

10c: SELECT FirstName, LastName
FROM customers
WHERE PostalCode LIKE '6%' 
OR PostalCode LIKE '7%' 
OR PostalCode LIKE '8%' 
OR PostalCode LIKE '9%' 
AND City = 'København';

10d: SELECT FirstName, LastName
FROM customers
WHERE PostalCode LIKE '6%' 
OR PostalCode LIKE '7%' 
OR PostalCode LIKE '8%' 
OR PostalCode LIKE '9%' 
AND (City = 'København' OR City = 'Paris');

11a: SELECT name
FROM tracks
WHERE UnitPrice <> 0.99

11b: SELECT name
FROM tracks
WHERE name LIKE 'Go%'
