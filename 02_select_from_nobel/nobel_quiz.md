# Select Quiz

|    __yr__    |  __subject__  |    __winner__    | 
|   :------:   | :-----------: |   :--------:   |
|   1960  |  Chemistry    |     Willard F. Libby     | 
|   1960  |  Literature   |     Saint-John Perse      | 
|   1960  |   Medicine    |    Sir Frank Macfarlane Burnet     | 
|   1960  |   Medicine    |      Peter Medawar       |
|   1960  |   Physics     |      	Donald A. Glaser    |
|   1960  |   Peace       |     Albert Lutuli    | 
|   ...   |    ...        |      ...       | 


<br></br>

1. Pick the code which shows the name of winner's names beginning with C and ending in n. 

<!-- |    __name__    |  __population__  |
|   :--------:   | :--------------: |
|    Bahrain     |    1234571       | 
|   Swaziland    |    1220000       | 
|  Timor-Leste   |    1066409       |  -->

```
SELECT winner FROM nobel
WHERE winner LIKE 'C%' AND winner LIKE '%n'
```

<br></br>

2. Select the code that shows how many Chemistry awards were given between 1950 and 1960.

```
SELECT COUNT(subject) FROM nobel
WHERE subject = 'Chemistry'
AND yr BETWEEN 1950 and 1960
```

<!-- <table>
  <tr><th colspan=2>Table E</th></tr>
  <tr><td>Albania</td><td>3200000</td></tr>
  <tr><td>Algeria</td><td>32900000</td></tr>
</table> -->

<br></br>

3. Pick the code that shows the amount of years where no Medicine awards were given. 

```
SELECT COUNT(DISTINCT yr) FROM nobel
WHERE yr NOT IN (SELECT DISTINCT yr 
                  FROM nobel 
                  WHERE subject = 'Medicine')
```

<br></br>

4. Select the result that would be obtained from the following code: 

```
SELECT subject, winner FROM nobel WHERE winner LIKE 'Sir%' AND yr LIKE '196%'
```
<table>
  <tr><th colspan=2>Table E</th></tr>
  <tr><td>Medicine</td><td>Sir John Eccles</td></tr>
  <tr><td>Medicine</td><td>Sir Frank Macfarlane Burnet</td></tr>
</table> 

<!-- 
|    __name__    |  __length(name)__  |
|   :--------:   | :--------------: |
|    Italy     |    5       | 
|   Malta    |    5       | 
|  Spain   |    5       |  -->


<br></br>

5. Select the code which would show the year when neither a Physics or Chemistry award was given. 
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
SELECT yr FROM nobel
WHERE yr NOT IN (SELECT yr 
                  FROM nobel
                  WHERE subject IN ('Chemistry','Physics'))
```
<!-- <table>
  <tr><td>Andorra</td><td>936</td></tr>
</table> -->


<br></br>

6. Select the code which shows the years when a Medicine award was given but no Peace or Literature award was.

```
SELECT DISTINCT yr
FROM nobel
WHERE subject='Medicine' 
  AND yr NOT IN (SELECT yr FROM nobel 
                  WHERE subject='Literature')
  AND yr NOT IN (SELECT yr FROM nobel
                  WHERE subject='Peace')
 ```

<br></br>

7. Pick the result that would be obtained from the following code: 

```
SELECT subject, COUNT(subject) 
FROM nobel 
WHERE yr ='1960' 
GROUP BY subject
```
<table>
  <tr><th colspan=2>Table E</th></tr>
  <tr><td>Chemistry</td><td>1</td></tr>
  <tr><td>Literature</td><td>1</td></tr>
  <tr><td>Medicine</td><td>2</td></tr>
  <tr><td>Peace</td><td>1</td></tr>
  <tr><td>Physics</td><td>1</td></tr>
</table>
