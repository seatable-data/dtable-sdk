# statistics

### generatorStatId(statItems）

Get a random string of length 4 as the ID of the statistical item

**parameters：**

* `statItems` : An array which contains all statistic items

**return：**

a random string of length 4,  `h5U7` 

### calculateGeolocationBasicChart(statItem, tables)

Get statistics data

**parameters：**

* `statItem` :  current statistic item 
* `tables` :  an array containing all tables of the database

**return: **

an array containing statistics data

```
[
   {  
      name: 'xxx',
      value: 'number',
      rows: [{_id: 'row_id', column1_key: 'column_key', column2_key: 'column_key', ...}],
   }, 
   ...
]

```


