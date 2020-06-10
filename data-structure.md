# Data Structure

## Objects in DTable SDK

### Row

A row is an object, use `row['colum_name']` to access the cell value for a specific column. There are some special fields

* `_id` : The id of the row
* `_creator` : The creator for this row
* `_ctime`: The create time for this row

Different types of columns have different value types:

* `simple-text` : string
* `number` : number
* `single-select` : option Name, string
* `date` : string, in format `2020-01-01` or `2020-01-01 10:00` 
* `check` : boolean
* `long-text` : markdown string
* `image` : array, each element of the array is the URL of image
* `multi-select` : array, each element of the array is an option Name
* `collaborator` : array, each element of the array is a collaborator's ID
* `link` : array, each element of the array is a link Name
* `file` : array, each element of the array is a file object  `[{name: string, url: string, size: number, type: 'file'}]`

### Column

A column object consists of the following fields:

* `type` : The type of the column(long-text, single-select, number, file and so on), string
* `name` : The name of the table, string

### Table

A table object consists of the following fields:

* `name` : The name of the table, string


