# Select Quiz

|    __name__    |  __region__  |    __area__    |  __population__  |  __gdp__  |
|   :--------:   | :--------------: |   :--------:   | :--------------: | :--------------: |
|   Afghanistan  |    South Asia    |     652225     |    26000000      |                  |
|     Albania    |     Europe       |     28728      |    3200000       |    6656000000    |
|    Algeria     |    Middle East   |    2400000     |    32900000      |    75012000000   |
|    Andorra     |     Europe       |      468       |      64000       |                  |
|      ...       |      ...         |      ...       |      ...         |      ...         |

1. Select the code which produces this table :

|    __name__    |  __population__  |
|   :--------:   | :--------------: |
|    Bahrain     |    1234571       | 
|   Swaziland    |    1220000       | 
|  Timor-Leste   |    1066409       | 

`SELECT` name, population \
`FROM` world \
`WHERE` population `BETWEEN` 1000000 AND 1250000


2.
