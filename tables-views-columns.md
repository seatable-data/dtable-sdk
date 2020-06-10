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
