## SUM and COUNT Quiz

1. Select the statement that shows the sum of population of all countries in 'Europe' 


 `SELECT name, population FROM bbc WHERE region = 'Europe'`

 `SELECT population FROM bbc WHERE region = 'Europe' SUM BY region`

 `SELECT SUM(population) FROM bbc WHERE region = 'Europe'`

 `SELECT SUM(population FROM bbc WHERE region = 'Europe')`

 `SUM population FROM bbc WHERE region = 'Europe'`

2. Select the statement that shows the number of countries with population smaller than 150000

 `SELECT COUNT(name) FROM bbc WHERE population < 150000`

 `SELECT COUNT(population < 150000) FROM bbc`

 `SELECT name FROM bbc WHERE population < 150000`

 `SELECT population AS COUNT FROM bbc WHERE population < 150000`

 `SELECT SUM() FROM bbc WHERE population < 150000`

3. Select the list of core SQL aggregate functions

  `AVG(), COUNT(), FIRST(), LAST(), SUM()`

  `AVG(), COUNT(), MAX(), MEDIAN(), MIN(), ROUND(), SUM()`

  `AVG(), COUNT(), CONCAT(), FIRST(), LAST(), MAX(), MIN(), SUM()`

  `AVG(), COUNT(), MAX(), MIN(), SUM()`

  `COUNT(), SUM()`

4. Select the result that would be obtained from the following code:
```
 SELECT region, SUM(area)
   FROM bbc 
  WHERE SUM(area) > 15000000 
  GROUP BY region
```

Table-AEurope	17000000
Table-BEurope	17000000
Asia-Pacific	23460000
North America	21660000
Table-CEurope
Asia-Pacific
North America
No result due to invalid use of the GROUP BY function
No result due to invalid use of the WHERE function

5. Select the statement that shows the average population of 'Poland', 'Germany' and 'Denmark'

 `SELECT AVG(population) FROM bbc WHERE name = ('Poland', 'Germany', 'Denmark')`

 `SELECT AVG(population) FROM bbc WHERE name IN ('Poland', 'Germany', 'Denmark')`

 `SELECT AVG(population) FROM bbc WHERE name LIKE ('Poland', 'Germany', 'Denmark')`

 `SELECT AVG(population) FROM bbc WHERE name LIKE (Poland, Germany, Denmark)`

 `SELECT population FROM bbc WHERE name IN ('Poland', 'Germany', 'Denmark')`

6. Select the statement that shows the medium population density of each region

 `SELECT region, AVG(population/area) AS density FROM bbc`

 `SELECT region, COUNT(population)/COUNT(area) AS density FROM bbc GROUP BY region`

 `SELECT region, SUM(population)/COUNT(area) AS density FROM bbc GROUP BY region`

 `SELECT region, SUM(population)/SUM(area) AS density FROM bbc HAVING region`

 `SELECT region, SUM(population)/SUM(area) AS density FROM bbc GROUP BY region`

7. Select the statement that shows the name and population density of the country with the largest population

 `SELECT name, density AS population/area FROM bbc WHERE population = MAX(population)`

 `SELECT name, density AS population/area FROM bbc WHERE population = (SELECT MAX(population) FROM bbc)`

 `SELECT name, MAX (population) FROM bbc WHERE population / (SELECT area FROM bbc)`

 `SELECT name, population/area AS density FROM bbc WHERE population = (SELECT MAX(population) FROM bbc)`

 `SELECT name, population/area AS density FROM bbc WHERE population > (SELECT MAX(population) FROM bbc)`

8. Pick the result that would be obtained from the following code:
```
 SELECT region, SUM(area) 
   FROM bbc 
  GROUP BY region 
  HAVING SUM(area)<= 20000000
```

Table-A732240
13403102
17740392
4943771
Table-BAfrica	22550927
Asia-Pacific	28759578
Europe	23866987
North America	21660000
Table-CAfrica
Asia-Pacific
Europe
North America
Table-DAmericas	732240
Middle East	13403102
South America	17740392
South Asia	9437710
Table-EAmericas
Middle East
South America
South Asia
