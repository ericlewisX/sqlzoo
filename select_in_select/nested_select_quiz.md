# Select Quiz

<!-- |    __yr__    |  __subject__  |    __winner__    | 
|   :------:   | :-----------: |   :--------:   |
|   1960  |  Chemistry    |     Willard F. Libby     | 
|   1960  |  Literature   |     Saint-John Perse      | 
|   1960  |   Medicine    |    Sir Frank Macfarlane Burnet     | 
|   1960  |   Medicine    |      Peter Medawar       |
|   1960  |   Physics     |      	Donald A. Glaser    |
|   1960  |   Peace       |     Albert Lutuli    | 
|   ...   |    ...        |      ...       |  -->

|    __name__    |  __region__  |    __area__    |  __population__  |  __gdp__  |
|   :--------:   | :--------------: |   :--------:   | :--------------: | :--------------: |
|   Afghanistan  |    South Asia    |     652225     |    26000000      |                  |
|     Albania    |     Europe       |     28728      |    3200000       |    6656000000    |
|    Algeria     |    Middle East   |    2400000     |    32900000      |    75012000000   |
|    Andorra     |     Europe       |      468       |      64000       |                  |
|    Bangladesh  |    South Asia    |    143998      |    152600000     |    67144000000   |
| United Kingdom |     Europe       |   242514       |   59600000       |  2022824000000   |
|      ...       |      ...         |      ...       |      ...         |      ...         |

<br></br>

1. Select the code that shows the name, region and population of the smallest country in each region. 

<!-- |    __name__    |  __population__  |
|   :--------:   | :--------------: |
|    Bahrain     |    1234571       | 
|   Swaziland    |    1220000       | 
|  Timor-Leste   |    1066409       |  -->

```
SELECT region, name, population 
FROM bbc x 
WHERE population <= ALL (SELECT population 
                          FROM bbc y 
                          WHERE y.region=x.region AND population>0)
```

<br></br>

2. Select the code that shows the countries belonging to regions with all populations over 50000.

```
SELECT name,region,population 
FROM bbc x 
WHERE 50000 < ALL (SELECT population 
                    FROM bbc y 
                    WHERE x.region=y.region AND y.population>0)
```

<!-- <table>
  <tr><th colspan=2>Table E</th></tr>
  <tr><td>Albania</td><td>3200000</td></tr>
  <tr><td>Algeria</td><td>32900000</td></tr>
</table> -->

<br></br>

3. Select the code that shows the countries with a less than a third of the population of the countries around it. 

```
SELECT name, region 
FROM bbc x
WHERE population < ALL (SELECT population/3 
                         FROM bbc y 
                         WHERE y.region = x.region AND y.name != x.name)
```

<br></br>

4. Select the result that would be obtained from the following code:  

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
  <tr><td>Bangladesh</td><td>1</td></tr>
  <tr><td>India</td><td>1</td></tr>
  <tr><td>Pakistan</td><td>2</td></tr>
</table>

