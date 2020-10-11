# Rows

### forEachRow(tableName, viewName, callback)

Use tableName and viewName to get rows then execute callback function

**parameters：**

* `tableName`: table Name, string
* `viewName`: view Name, string
* `callback(row)`: async callback function, parameters: 
  * row, object

**return：**

null

### getRowById(table, rowId)

Get a row by its ID

**parameters：**

* `table`: the sub-table, object
* `rowId`: rowId, string

**return：**

row, object

### getRowsById(table, rowIds)

Get rows by its ids

**parameters：**

* `table`: the sub-table, object
* `rowIds`: rowIds, array

**return：**

rows, array

### appendRow(table, rowData)

Insert a new row with rowData at the end of the table

**parameters：**

* `table`: the table where the row will be appended, object
* `rowData`: row data,  `{ 'column_name1': 'updated_value1', 'column_name2': 'updated_value2', ... }`

**return：**

null

### deleteRowById(table, rowId)

Delete a row in the table by table an tableId

**parameters：**

* `table`: the sub-table, object
* `rowId`: row id, string

**return：**

null

### modifyRow(table, row, updated)

modify row date in a table

**parameters：**

* `table`:  the table where the row will be modified, object
* `row`: the row object, object
* `updated`: an object containing the updated columns, `{ 'column_name1': 'updated_value1', 'column_name2': 'updated_value2', ... }` 

**return：**

null

### getViewRows(view, table)

Get all rows data by view, table

**parameters：**

* `view`: the view used to find row data， object
* `table`:  the table used to find row data, object

**return：**

rowsdata, array

### getInsertedRowInitData(view, table, row_id)

Get the row's init data which will be insert current table by view, table, row_id

**parameters：**

* `view`: the view used to insert new row， object
* `table`:  the table used to insert new row, object
* `row_id`: the insert's row id, string

**return：**

rowdata, object

### addRow(tableName, rowData, viewName)

Add a new row into table by tableName and viewName

**parameters：**

* `tableName`: the table's name used to insert new row, string,
* `rowData`:  the inserted row's data, object
* `viewName`: the view's name used to insert new row, string

**return：**

null

### getGroupRows(view, table)

Get rows data of grouped view through table, view

**parameters：**

* `view`: the view used to get rows， object
* `table`:  the table used to get rows, object

**return：**

rows, array

