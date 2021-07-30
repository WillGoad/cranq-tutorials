# CRANQ http-request

## Using http dispatcher - From "get task" to "post a todo item"

### Step 1 - Http Get

Objective: Get #1 task data from https://jsonplaceholder.typicode.com/ and write to the console

New concepts:

- use http dispatcher for getting data

!["Http get app in Cranq"](./http_request_1.png)

**Description:**
We create a CRANQ progam which gets data from https://jsonplaceholder.typicode.com/todos/1 REST api endpoint

**Steps:**

- Create a new structure node for the example
  - rename the node to **http get example**
  - add new input port to it and rename it to **start**
  - add new output port to it and rename it to **log**
- Navigate into the [http get example] node by double click
- We need a http dispatcher for calling the api
  - add a _io/http/Request dispatcher_ node by search
  - rename it to **get task**
  - set the Value of the &lt;verb&gt; port to **"GET"**
  - set the Value of the &lt;headers&gt; port to **""** (empty string)
  - set the Value of the &lt;body&gt; port to **""** (empty string)
- We need at least one signal for triggering [get task] node. We use the &lt;url&gt; input port for it
  - add a new _data/Store_ node by search for storing the url of the api
  - rename it to **url**
  - set the Value of the &lt;data&gt; port to **"https://jsonplaceholder.typicode.com/todos/1"**
- connect the &lt;data&gt; output port of the [url] node to the &lt;url&gt; input port of [get task] node
- connect the &lt;start&gt; input port of [http get example] parent node to the &lt;read&gt; input port of [url] node
- the data type of the Value of &lt;body&gt; output of [get task] node is string. We would like to use it as an object so we need to parse it to JSON.
  - add _data/dictionary/JSON parser_ node by search
  - rename it to **body to json object**
- connect the &lt;body&gt; output port of [get task] node to &lt;json&gt; input port of [body to json object]
- connect the &lt;parsed&gt; output port of [body to json object] node to &lt;log&gt; input port of [http get example] parent node
- when you run the program you get the data of the todo with id 1

### Step 2 - Http Get with parameterized url

New concepts:

- use string templater

!["Http get with parameterized url app in Cranq"](./http_request_2.png)

### Step 3 - Reusable Task getter node

New concepts:

- structure node
- navigation

!["Reusable Task getter node"](./http_request_3.png)

### Step 4 - Http Post

Objective: Post #209 task to https://jsonplaceholder.typicode.com/ and write the result to the console

New concepts:

- use http dispatcher for posting data

!["Http get app in Cranq"](./http_request_4.png)

### Step 5 - Check Http dispatcher status

Objective: Try to get data from invalid resource and check if the response status is 200 and write the result of the check to the console

New concepts:

- use equality checker
- use fork

!["Http get app in Cranq"](./http_request_5.png)

### Step 6 - Check Http dispatcher error

Objective: Get data from not existing url and write the error to the console

New concepts:

- use Http dispatcher error output port

!["Http get app in Cranq"](./http_request_6.png)
