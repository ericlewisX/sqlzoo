# Select Quiz

|    __name__    |  __region__  |    __area__    |  __population__  |  __gdp__  |
|   :--------:   | :--------------: |   :--------:   | :--------------: | :--------------: |
|   Afghanistan  |    South Asia    |     652225     |    26000000      |                  |
|     Albania    |     Europe       |     28728      |    3200000       |    6656000000    |
|    Algeria     |    Middle East   |    2400000     |    32900000      |    75012000000   |
|    Andorra     |     Europe       |      468       |      64000       |                  |
|      ...       |      ...         |      ...       |      ...         |      ...         |

<br></br>

1. Select the code which produces this table :

|    __name__    |  __population__  |
|   :--------:   | :--------------: |
|    Bahrain     |    1234571       | 
|   Swaziland    |    1220000       | 
|  Timor-Leste   |    1066409       | 

`SELECT` name, population \
`FROM` world \
`WHERE` population `BETWEEN` 1000000 `AND` 1250000

<br></br>

2. Pick the result you would obtain from this code:

```
SELECT name, population
FROM world
WHERE name LIKE 'Al%'
```

<table>
  <tr><th colspan=2>Table E</th></tr>
  <tr><td>Albania</td><td>3200000</td></tr>
  <tr><td>Algeria</td><td>32900000</td></tr>
</table>

<br></br>

3. Select the code which shows the countries that end in A or L. 

```
SELECT name
FROM world
WHERE name LIKE '%a' OR name LIKE '%1`
```

<br></br>

4. Pick the result from the query 
```
SELECT name,length(name)
FROM world
WHERE length(name)=5 and continent='Europe'
```

|    __name__    |  __length(name)__  |
|   :--------:   | :--------------: |
|    Italy     |    5       | 
|   Malta    |    5       | 
|  Spain   |    5       | 


<br></br>

5. Here are the first few rows of the world table: 

|    __name__    |  __region__  |    __area__    |  __population__  |  __gdp__  |
|   :--------:   | :--------------: |   :--------:   | :--------------: | :--------------: |
|   Afghanistan  |    South Asia    |     652225     |    26000000      |                  |
|     Albania    |     Europe       |     28728      |    3200000       |    6656000000    |
|    Algeria     |    Middle East   |    2400000     |    32900000      |    75012000000   |
|    Andorra     |     Europe       |      468       |      64000       |                  |
|      ...       |      ...         |      ...       |      ...         |      ...         |

Pick the result you would obtain from this code: 
```
SELECT name, area*2 FROM world WHERE population = 64000
```
<table>
  <tr><td>Andorra</td><td>936</td></tr>
</table>


<br></br>

6. Select the code that would show the countries with an area larger than 50000 and a population smaller than 10000000.

```
SELECT name, area, population
FROM world
WHERE area > 50000 AND population < 10000000
 ```

<br></br>

7. Select the code that shows the population density of China, Australia, Nigeria and France 

```
SELECT name, population/area
FROM world
WHERE name IN ('China', 'Nigeria', 'France', 'Australia')
```
