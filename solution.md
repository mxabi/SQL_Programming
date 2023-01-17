SQL Review Lesson 5:

1. List all the Canadian Cities and their populations

select city, population from north_american_cities WHERE country = 'Canada';

2. Order all the cities in the United States by their latitude from north to south 

select city form north_american_cities WHERE country = 'United States' ORDER BY latitude desc;

3. List all the cities west of Chicago, ordered from west to east 

select * from north_american_cities WHERE longitude < -87.629798 ORDER BY longitude;

4. List the two largest cities in Mexico (by population) 

SELECT * FROM north_american_cities WHERE country = 'Mexico' ORDER BY population desc limit 2;

5. List the third and fourth largest cities (by population) in the United States and their population 

select city,population from north_american_cities where country = 'United States' ORDER BY population desc limit 2 offset 2;

SQL Lesson 6: Multi-table queries with JOINs 

1. Find the domestic and international sales for each movie
SELECT title, domestic_sales, international_sales FROM movies
INNER JOIN boxoffice ON movies.id = boxoffice.movie_id;

3. Show the sales numbers for each movie that did better internationally rather than domestically
SELECT title, domestic_sales, international_sales FROM movies
INNER JOIN boxoffice ON movies.id = boxoffice.movie_id WHERE international_sales > domestic_sales;

5. List all the movies by their ratings in descending order
SELECT title, rating FROM movies
INNER JOIN boxoffice ON movies.id = boxoffice.movie_id ORDER BY rating desc;

SQL Lesson 7: Outer Joins
1. Find the list of all buildings that have employees
Select distinct building from employees;
  
3. Find the list of all buildings and their capacity
select * from buildings

5. List all buildings and the distinct employee roles in each building (including empty buildings)

