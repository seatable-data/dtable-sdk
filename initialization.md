# Initialization

## init(config)

Initialize dtable object, under the hood, the dtable uuid and dtable server address will be fetched.

**parameters:**

null

**return:**

null

## syncWithServer()

Load the table from the server, then watch changes on the server and send local changes to the server.

**parameters:**

null

**return:**

null

## subscribe(eventType, fn)

subscribe event with function

**parameters：**

* `eventType`: type of event, string
* `fn`: callback function, event handler

**return：**

null
