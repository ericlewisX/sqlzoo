# SUM and COUNT Lesson

<!-- |    __yr__    |  __subject__  |    __winner__    | 
|   :------:   | :-----------: |   :--------:   |
|   1960  |  Chemistry    |     Willard F. Libby     | 
|   1960  |  Literature   |     Saint-John Perse      | 
|   1960  |   Medicine    |    Sir Frank Macfarlane Burnet     | 
|   1960  |   Medicine    |      Peter Medawar       |
|   1960  |   Physics     |      	Donald A. Glaser    |
|   1960  |   Peace       |     Albert Lutuli    | 
|   ...   |    ...        |      ...       |  --> 
  
### World Country Profile: Aggregate functions  

This tutorial is about aggregate functions such as COUNT, SUM and AVG. An aggregate function takes many values and delivers just one value. For example the function SUM would aggregate the values 2, 4 and 5 to deliver the single value 11.

|    __name__    |  __continent__  |    __area__    |  __population__  |  __gdp__  |
|   :--------:   | :--------------: |   :--------:   | :--------------: | :--------------: |
|   Afghanistan  |     Asia         |     652230     |    25500100      |    20343000000   |
|     Albania    |     Europe       |     28748      |    2831741       |    12960000000   |
|    Algeria     |    Africa        |    2381741     |    37100000      |    188681000000   |
|    Andorra     |     Europe       |      468       |      78115       |     3712000000   |
|    Angola      |    Africa        |    1246700	      |    20609294     |    100990000000   |
|      ...       |      ...         |      ...       |      ...         |      ...         |

<br></br>

1. Show the total population of the world.

`world(name, continent, area, population, gdp)`

<!-- |    __name__    |  __population__  |
|   :--------:   | :--------------: |
|    Bahrain     |    1234571       | 
|   Swaziland    |    1220000       | 
|  Timor-Leste   |    1066409       |  -->

```
SELECT SUM(population)
FROM world
```
```
Correct answer
SUM(populatio..
7118632738
```
    
<br></br>

2. List all the continents - just once each.

```
SELECT DISTINCT continent
FROM world
```   
 
```
Correct answer
continent
Africa
Asia
Caribbean
Eurasia
Europe
North America
Oceania
South America
```

<!-- <table>
  <tr><th colspan=2>Table E</th></tr>
  <tr><td>Albania</td><td>3200000</td></tr>
  <tr><td>Algeria</td><td>32900000</td></tr>
</table> -->

<br></br>

3. Give the total GDP of Africa 

```
SELECT SUM(gdp)
FROM world
WHERE continent = 'Africa'
```

```
Correct answer
SUM(gdp)
1811788000000

```

<br></br>

<!-- 4. Select the result that would be obtained from the following code:  

```
SELECT name FROM bbc
 WHERE population >
       (SELECT population
          FROM bbc
         WHERE name='United Kingdom')
   AND region IN
       (SELECT region
          FROM bbc
         WHERE name = 'United Kingdom')
```
<table>
  <tr><th colspan=2>Table D</th></tr>
  <tr><td>France</td></tr>
  <tr><td>Germany</td></tr>
  <tr><td>Russia</td></tr>
  <tr><td>Turkey</td></tr>
</table> 

<!-- 
|    __name__    |  __length(name)__  |
|   :--------:   | :--------------: |
|    Italy     |    5       | 
|   Malta    |    5       | 
|  Spain   |    5       |  -->
  

<br></br>

5. Select the code that would show the countries with a greater GDP than any country in Africa (some countries may have NULL gdp values).  
<!-- 
|    __name__    |  __region__  |    __area__    |  __population__  |  __gdp__  |
|   :--------:   | :--------------: |   :--------:   | :--------------: | :--------------: |
|   Afghanistan  |    South Asia    |     652225     |    26000000      |                  |
|     Albania    |     Europe       |     28728      |    3200000       |    6656000000    |
|    Algeria     |    Middle East   |    2400000     |    32900000      |    75012000000   |
|    Andorra     |     Europe       |      468       |      64000       |                  |
|      ...       |      ...         |      ...       |      ...         |      ...         |

Pick the result you would obtain from this code:  -->
 
```
SELECT name FROM bbc
WHERE gdp > (SELECT MAX(gdp) 
              FROM bbc 
              WHERE region = 'Africa')
```
<!-- <table>
  <tr><td>Andorra</td><td>936</td></tr>
</table> -->


<br></br>   

6. Select the code that shows the countries with population smaller than Russia but bigger than Denmark.

```
SELECT name FROM bbc
 WHERE population < (SELECT population 
                      FROM bbc 
                      WHERE name='Russia')
   AND population > (SELECT population 
                      FROM bbc 
                      WHERE name='Denmark')
 ```

<br></br>

7. Select the result that would be obtained from the following code: 

```
SELECT name FROM bbc
WHERE population > ALL
     (SELECT MAX(population)
        FROM bbc
        WHERE region = 'Europe')
 AND region = 'South Asia'
```
<table>
  <tr><th colspan=2>Table B</th></tr>
  <tr><td>Bangladesh</td></tr>
  <tr><td>India</td></tr>
  <tr><td>Pakistan</td></tr>
</table>
 -->
