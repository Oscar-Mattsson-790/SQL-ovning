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




Fler övningar:

1: SELECT artists.Name, albums.Title
FROM artists
JOIN albums ON artists.ArtistId = albums.ArtistId

2: SELECT artists.name
FROM artists
JOIN albums ON artists.ArtistId = albums.ArtistId
WHERE albums.Title LIKE 'The%'

3: SELECT tracks.Name
FROM tracks
JOIN artists ON tracks.TrackId = artists.ArtistId
WHERE artists.Name = 'Frank Sinatra'

4: SELECT tracks.Name
FROM tracks
WHERE Composer IS NULL

5: SELECT tracks.name
FROM tracks
WHERE GenreId IS NULL

6: SELECT tracks.Name
FROM tracks
JOIN genres ON tracks.GenreId = genres.GenreId
WHERE genres.Name = 'Latin'

7: SELECT DISTINCT albums.Title
FROM albums
JOIN tracks ON albums.AlbumId = tracks.AlbumId
JOIN genres ON tracks.GenreId = genres.GenreId
WHERE genres.Name = 'Latin'

8: SELECT DISTINCT albums.Title
FROM albums
JOIN tracks ON albums.AlbumId = tracks.AlbumId
JOIN genres ON tracks.GenreId = genres.GenreId
WHERE genres.Name IN ('Jazz', 'Rock')
GROUP BY albums.AlbumId
HAVING COUNT(DISTINCT genres.Name) = 2

9: SELECT tracks.Name
FROM playlists
JOIN playlist_track ON playlists.PlaylistId = playlist_track.PlaylistId
JOIN tracks ON playlist_track.TrackId = tracks.TrackId
WHERE playlists.Name = 'Grunge'

10: SELECT DISTINCT artists.Name
FROM tracks
JOIN playlist_track ON tracks.TrackId = playlist_track.TrackId
JOIN playlists ON playlist_track.PlaylistId = playlists.PlaylistId
JOIN albums ON tracks.AlbumId = albums.AlbumId
JOIN artists ON albums.ArtistId = artists.ArtistId
WHERE playlists.Name = 'Grunge'

11: SELECT DISTINCT playlists.Name
FROM playlists
JOIN playlist_track ON playlists.PlaylistId = playlist_track.PlaylistId
JOIN tracks ON playlist_track.TrackId = tracks.TrackId
JOIN albums ON tracks.AlbumId = albums.AlbumId
JOIN artists ON albums.ArtistId = artists.ArtistId
WHERE artists.Name = 'Led Zeppelin'
