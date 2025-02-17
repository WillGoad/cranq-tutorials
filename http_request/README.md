# CRANQ http-request

## Using http dispatcher - From "get task" to "post a todo item"

### Step 1 - Http Get

Objective: Get #1 task data from https://jsonplaceholder.typicode.com/ and write to the console

New concepts:

- use http dispatcher for getting data

!["Http get app in Cranq"](./http_request_1.png)

### Step 2 - Http Get with parameterized url

Objective: Get arbitrary task (id comes from parameter) data from https://jsonplaceholder.typicode.com/ and write the result to the console

New concepts:

- use string templater

!["Http get with parameterized url app in Cranq"](./http_request_2.png)

### Step 3 - Reusable Task getter node

Objective: Create a reusable component for getting task data from https://jsonplaceholder.typicode.com/ and write the result to the console

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

- use Http dispatcher error output pott

!["Http get app in Cranq"](./http_request_6.png)
