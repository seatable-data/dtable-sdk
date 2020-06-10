# Tutorial

We will use a simple example to show how easy it is to modify a dtable in realtime. This example will read the first column in a table and write "Hello xxx" in the second column.

## The code

The code is very short. You can find it at GitHub (<https://github.com/seatable/dtable-sdk/tree/master/example>)

```javascript
import fs from 'fs';
import path from 'path';
import DTable from '../src/dtable';

const configPath = path.resolve(__dirname, './example.json');
const config = JSON.parse(fs.readFileSync(configPath).toString());

let dtable = new DTable();
let test = new Test(dtable);

async function init() {
  await dtable.init(config);
  dtable.subscribe('dtable-connect', () => { test.sayHello(); });
  dtable.subscribe('remote-dtable-changed', () => { test.sayHello(); });
  await dtable.syncWithServer();
}

init();

```

The code is explain as below.

## Step by step guide

You should create a dtable named `sayHello` . Add a view called `Default_view` and add two columns named `Name` and `Result` . Add two rows and change the cell in the Name column as shown below.

| Name | Result |
| :--- | :----- |
| Mike |        |
| Judy |        |

Generate API Token for the table and add a configuration file( example.json ), including the following parameters:

```javascript
{
    "APIToken": "xxxxxxxx",
    "server": "http://127.0.0.1:8001",
    "workspaceID": "x",
    "dtableName": "xxxxxxxx"
}

```

Load JSON file then transfer into object.

```javascript
const configPath = path.resolve(__dirname, './example.json');
const config = JSON.parse(fs.readFileSync(configPath).toString());

```

Create a new dtable and initialize it with your config:

```javascript
let dtable = new DTable();
let test = new Test(dtable);

await dtable.init(config);

```

Subscribe connect and data-change events. When dtable updated, use a callback function to scan the rows and make changes:

```javascript
dtable.subscribe('dtable-connect', () => { test.sayHello(); });
dtable.subscribe('remote-dtable-changed', () => { test.sayHello(); });

class Test {
  constructor(dtable) {
    this.dtable = dtable;
  }
  sayHello() {
    let { dtable } = this;
    let table = dtable.getTableByName('sayHello');
    if (!table) return;
    dtable.forEachRow('sayHello', 'Default_View', (row) => { 
      let name = row['Name'];
      const res = `Hello ${name}`;
      if (row['Result'] && row['Result'].text === res) {
        return;
      }
      let updated = {};
      updated['Result'] = res;
      dtable.modifyRow(table, row, updated);
      debug('Change row succeeded.');
    });
  }
}

```

`syncWithServer()` will load the initial whole table from the SeaTable server asynchronously, then watch additional changes on the server, and `remote-dtable-changed` will be emitted when there are changes on the server.

```javascript
await dtable.syncWithServer();

```

After running the example, `Result` column will be changed accordingly:

| Name | Result     |
| :--- | :--------- |
| Mike | Hello Mike |
| Judy | Hello Judy |


