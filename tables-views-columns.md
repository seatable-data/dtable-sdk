# Tables and Columns

## Table

### getTables()

Get all tables

**parameters：**

none

**return：**

tables, array

### getActiveTable()

get the table been switched current time in the dtable

**parameters**

none

**return**

table, object

### getTableByName(name)

Get a sub-table by name

**parameters：**

* `name`: tableName, string

**return：**

table, object

### getTableById(id)

Get a sub-table by id

**parameters：**

* `id`: id, string

**return：**

table, object

### addTable(tableName)

Insert a new sub-table in the table

**parameters：**

* `tableName`: table's name, string

**return：**

null

### deleteTable(tableName)

Delete a sub-table one of the tables in the dtable

**parameters：**

* `tableName`: table's name, string

**return：**

null

### renameTable(previousName, tableName)

rename a sub-table one of the tables in the dtable

**parameters：**

* `previousName`: table's old name, string
* `tableName`: table's new name, string

**return：**

null

## View

### getViews(table)

Get all the views of the table

**parameters：**

* `table`, object

**return：**

views, array

### getActiveView()

Get the view been switched current time in the dtable

**parameters：**

none

**return：**

view, object

### getViewByName(table, name)

Get a view form the table by view's name

**parameters：**

* `name`: viewName, string

**return：**

table, object

### addView(tableName, viewName)

Add a view into the table by tableName and viewName

**parameters：**

* `tableName`: table's name, string
* `viewName`: view's name, string

**return：**

null

### renameView(tableName, previousName, viewName)

Rename view's name by tableName, perviousName, viewName

**parameters：**

* `tableName`: table's name, string
* `perviousName`: view's pervious name, string
* `viewName`: view's name, string

**return：**

null

### deleteView(tableName, previousName, viewName)

delete a view from table by tableName and viewName

**parameters：**

* `tableName`: table's name, string
* `perviousName`: view's pervious name, string
* `viewName`: view's name, string

**return：**

null


## Column

### getColumns(table)

Get columns from the table

**parameters：**

* `table`: sub-table, object

**return：**

columns, array

### getShownColumns(table, view)

Get columns that are display in the dtable by table and view 

**parameters：**

* `table`: the sub-table used to find columns, object
* `view`: the table's view used to find columns, object

**return：**

columns, array

### getColumnByName(table, name)

Get a column by its name

**parameters：**

* `table`: the sub-table, object
* `name`: columnName, string

**return：**

column, object
