# dtable-ui

When you develop SeaTable UI plugins, the global variable `window.app` provide the data of the current base and some UI functions.

## global data

window.app.dtableStore: the data used to init dtable object.

## interface

### registerPluginItemCallback(pluginName, callback)

Register plugin in the SeaTable main application by pluginName, callback

**parameters:**

`pluginName`： the name as an identity of the plugin, string
`callback`: a function execute the plugin logic, func

**return:**

null

### expandRow(row, rowTable)

Expand a row in row expand dialog in the SeaTable main application.

**parameters:**

`row`：a row used to show in the expand dialog, string
`rowTable`: the table that the row belongs to, object

**return:**

null
