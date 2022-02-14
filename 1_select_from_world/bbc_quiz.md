# BBC Quiz


|    __name__    |  __continent__  |    __area__    |  __population__  |  __gdp__  |
|   :--------:   | :--------------: |   :--------:   | :--------------: | :--------------: |
|   Afghanistan  |    South Asia    |     652225     |    26000000      |                  |
|     Albania    |     Europe       |     28728      |    3200000       |    6656000000    |
|    Algeria     |    Middle East   |    2400000     |    32900000      |    75012000000   |
|    Andorra     |     Europe       |      468       |      64000       |                  |
|   Brazil    |    South America    |     8550000    |    182800000      |  564852000000   |
|     Colombia   |   South America  |     1140000    |    45600000       |        |
|    Nauru      |    Asia-Pacific   |    21          |    9900           |       |
|    Uzbekistan |   Central Asia    |    447000      |      26000000       |               |
|      ...       |      ...         |      ...       |      ...         |      ...         |

<br></br>

1. Select the code which gives the name of countries beginning with U.

```
SELECT name
FROM world
WHERE name LIKE 'U%'
```

<!-- 
|    __name__    |  __population__  |
|   :--------:   | :--------------: |
|    Bahrain     |    1234571       | 
|   Swaziland    |    1220000       | 
|  Timor-Leste   |    1066409       | 

`SELECT` name, population \
`FROM` world \
`WHERE` population `BETWEEN` 1000000 `AND` 1250000 -->

<br></br>

2. Select the code which shows just the population of United Kingdom? 

```
SELECT population
FROM world
WHERE name = 'United Kingdom'
```
<!-- 
<table>
  <tr><th colspan=2>Table E</th></tr>
  <tr><td>Albania</td><td>3200000</td></tr>
  <tr><td>Algeria</td><td>32900000</td></tr>
</table> -->

<br></br>

3. Select the answer which shows the problem with this SQL code - the intended result should be the continent of France:

```
SELECT continent 
FROM world 
WHERE 'name' = 'France'
```
<table>
  <tr><td>'name' should be name</td></tr>
</table>

<br></br>

4. Select the result that would be obtained from the following code: 

```
SELECT name, population / 10 
FROM world 
WHERE population < 10000
```
<table>
  <tr><td>Nauru</td><td>990</td></tr>
</table>

<!-- |    __name__    |  __length(name)__  |
|   :--------:   | :--------------: |
|    Italy     |    5       | 
|   Malta    |    5       | 
|  Spain   |    5       | 
 -->

<br></br>

5. Select the code which would reveal the name and population of countries in Europe and Asia  

<!-- |    __name__    |  __region__  |    __area__    |  __population__  |  __gdp__  |
|   :--------:   | :--------------: |   :--------:   | :--------------: | :--------------: |
|   Afghanistan  |    South Asia    |     652225     |    26000000      |                  |
|     Albania    |     Europe       |     28728      |    3200000       |    6656000000    |
|    Algeria     |    Middle East   |    2400000     |    32900000      |    75012000000   |
|    Andorra     |     Europe       |      468       |      64000       |                  |
|      ...       |      ...         |      ...       |      ...         |      ...         |

Pick the result you would obtain from this code:  -->

```
SELECT name, population
FROM world
WHERE continent IN ('Europe', 'Asia')
```
<!-- <table>
  <tr><td>Andorra</td><td>936</td></tr>
</table> -->


<br></br>

6. Select the code which would give two rows 

```
SELECT name FROM world
WHERE name IN ('Cuba', 'Togo')
 ```

<br></br>

7. Select the result that would be obtained from this code: 

```
SELECT name FROM world
WHERE continent = 'South America'
AND population > 40000000
```

<table>
  <tr><td>Brazil</td></tr>
  <tr><td>Colombia</td></tr>
</table>
