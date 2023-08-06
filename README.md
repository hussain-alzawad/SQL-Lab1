# SQL-Lab1
- Create a table "BooksAuthors" containing two fields (AuthorId, BookId)
CREATE Table BooksAuthors (
	AuthorId int,
    BookId int
)

- Insert at least 5 records into the BooksAuthors table.
INSERT into BooksAuthors (authorid, bookid)
VALUES (1,1), (2,2), (3,3), (4,4), (5,5)

- Write a statement that will select the Country column from the Authors table.
SELECT country from Authors

- Select all the different values from the Country column in the Authors table.
SELECT DISTINCT country from Authors

- Write an SQL query to return only Authors whose name begins with S.
SELECT name 
from Authors
WHERE name like "s%"

- List the number of Authors in each country.
select country , count (*)
FROM Authors
GROUP by country

- Select all records from the Authors table, and sort the result alphabetically by the column's name.
select * from Authors 
ORDER by Authors.name

- Select all records from the Authors table, and sort the result reversed alphabetically by the column name.
select * from Authors 
ORDER by Authors.name DESC

- Select all records where the Title column has the value ‘Great ' from the Books table.
select *
from Books
WHERE title like "%Great%"

- Use the NOT keyword to select all records where the country is NOT "USA".
select * 
from Authors
where not country = "USA"

- Select all records where the country column has the value 'USA' or ‘India' from the “Authors” table
select * 
from Authors
where country = "USA" or country = "India"

- Select all records where the age column has the value BETWEEN 50 - 60 in the “Authors” table.
select * 
from Authors
where age BETWEEN 50 and 60
  
- Use the MIN function to select the record with the smallest value of the Age column from the “Authors” table.
select name, min(age)
from Authors

- Choose the correct `JOIN` clause to view all books and their authors.

select *
from Authors
join Books on Authors.id = books.iselect *
from Authors
join BooksAuthors on Authors.id = BooksAuthors.authorid
join Books on BooksAuthors.bookid = Books.id
