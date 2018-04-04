Practice Joins

/* SELECT * FROM Invoice i JOIN InvoiceLine il ON il.invoiceId = i.invoiceId WHERE il.UnitPrice > 0.99  */

/* SELECT i.InvoiceDate, c.FirstName, c.LastName, i.Total FROM Invoice i JOIN Customer c ON c.CustomerId = i.CustomerId ; */

/* SELECT c.FirstName, c.LastName, e.FirstName, e.LastName FROM Customer c JOIN Employee e ON c.SupportRepId = e.EmployeeId; */

/* SELECT a.Title, art.Name FROM Album a JOIN Artist art ON a.AlbumId = art.ArtistId; */

/* SELECT pt.TrackId from PlaylistTrack pt JOIN Playlist p ON pt.PlaylistId = p.PlaylistId WHERE p.Name = 'Music';
 */
 
/*  Select t.Name FROM Track t JOIN PlaylistTrack p ON t.TrackId = p.TrackId WHERE p.PlaylistId = 5;  */

/* SELECT t.Name, pl.Name FROM Track t JOIN PlaylistTrack pt ON t.TrackId = pt.TrackId JOIN Playlist pl ON pt.PlaylistId = pl.PlaylistId  */

/* SELECT t.Name, a.Title FROM Track t JOIN Album a ON t.AlbumId = a.AlbumId JOIN Genre g ON g.GenreId = t.GenreId WHERE g.Name = "Alternative" */

Practice Nested Queries

/* SELECT * FROM Invoice WHERE InvoiceId IN ( SELECT InvoiceId FROM InvoiceLine WHERE UnitPrice > 0.99) */

/* Select * FROM PlaylistTrack WHERE PlaylistId IN (SELECT PlaylistId FROM Playlist WHERE Name = "Music") */

/* SELECT Name FROM Track WHERE TrackId IN (SELECT PlayListId FROM PlaylistTrack WHERE PlaylistId = 5) */

/* SELECT * FROM Track WHERE GenreId IN (SELECT GenreId FROM Genre WHERE Name = "Comedy") */

/* SELECT * FROM Track WHERE AlbumId IN (SELECT AlbumId FROM Album WHERE Title = "Fireball")  */

/* SELECT * FROM Track WHERE AlbumId IN (SELECT AlbumId FROM Album WHERE ArtistId IN (SELECT ArtistId FROM Artist WHERE Name = "Queen")) */

Practice Updating Rows 

/* UPDATE Customer SET Fax = null WHERE Fax IS NOT null */
/* 
UPDATE Customer SET Company = "Self" WHERE Company IS null */

/* UPDATE Customer SET LastName = "Thompson" WHERE FirstName = "Julia" AND LastName = "Barnett" */

/* UPDATE Customer SET SupportRepId = 4 WHERE Email = "luisrojas@yahoo.cl"; */

/* UPDATE Track SET Composer = "The darkness around us" WHERE GenreId IN (SELECT GenreId FROM Genre WHERE Name = "Metal") AND Composer IS null */

Group By

/* SELECT Count(*), g.Name FROM Track t JOIN Genre g ON t.GenreId = g.GenreId GROUP BY g.Name */

/* SELECT Count(*), g.Name FROM Track t JOIN Genre g ON t.GenreId = g.GenreId WHERE g.name = "Pop" OR g.name = "Rock" GROUP BY g.Name */

/* SELECT a.Name, Count(*) FROM Artist a JOIN Album al ON a.ArtistId = al.ArtistId GROUP BY a.ArtistId */

Use Distinct

/* SELECT DISTINCT Composer FROM Track */

/* SELECT DISTINCT BillingPostalCode FROM Invoice */

/* SELECT DISTINCT Company FROM Customer */

Delete Rows

/* DELETE FROM practice_delete WHERE Type = "bronze"  */

/* DELETE FROM practice_delete WHERE Type = "silver" */

/* DELETE FROM practice_delete WHERE Value = 150 */

eCommerce

/*  CREATE TABLE Users (
  UserId integer primary key autoincrement,
  Username varchar(512),
  Email text
); */

/* CREATE TABLE Products (
  ProductId integer PRIMARY KEY autoincrement,
  Name varchar(512),
  Price float(2)
);  */
 
/* CREATE TABLE Orders (
  OrderId integer PRIMARY KEY autoincrement,
  UserId integer REFERENCES Users(UserId),
  ProductId integer REFERENCES Products(ProductId)
); */

/* INSERT INTO Users(Username, Email) VALUES("Jarid", "jarid@gmail.com"), 
("Jake", "jake@gmail.com"),
("Tom", "tom@gmail.com") */

/* INSERT INTO Products(Name, Price) Values("cheetos", .99),
("burger", 5.00),
("salad", 3.49) */

/* INSERT INTO Orders (UserId, ProductId) VALUES(1,1),(2,2),(3,3) */

/* SELECT * FROM Products WHERE ProductId = (SELECT ProductId FROM Orders WHERE OrderId = 1) */

/* SELECT * FROM Orders */

/* SELECT Sum(price) as Total FROM Orders o JOIN Products p ON o.Productid = p.ProductId WHERE price IS NOT null   */

