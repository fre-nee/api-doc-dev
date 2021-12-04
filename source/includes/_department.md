# Department

## Get Departments

```javascript
import Parse from "parse";

const res = await Parse.Cloud.run("getDepartments");
```

> The above command returns JSON structured like this:

```json
[
  {
      "name": "NSFW",
      "createdAt": "2020-08-29T11:35:45.248Z",
      "updatedAt": "2020-08-29T11:35:45.248Z",
      "objectId": "dx3FBrIewC"
  }
];

```

### cloud function

`getDepartments`

This cloud function returns list of departments.

### Parameters

NOT REQUIRED

## Create Department

```javascript
import Parse from 'parse'

const res = await Parse.Cloud.run("createDepartment",
  { <PARAMETERS> })
```

> The above command returns JSON structured like this:

```json
[
  {
      "name": "NSFW",
      "createdAt": "2020-08-29T11:35:45.248Z",
      "updatedAt": "2020-08-29T11:35:45.248Z",
      "objectId": "dx3FBrIewC"
  }
];

```

### cloud function

`createDepartment`

This cloud function creates and returns new department.

### Parameters

| Parameter | Required | Type   | Description                           |
| --------- | -------- | ------ | ------------------------------------- |
| name      | \*       | string | Name of the department to be created. |

## Update Department

```javascript
import Parse from 'parse'

const res = await Parse.Cloud.run("updatedDepartment",
  { <PARAMETERS> })
```

> The above command returns JSON structured like this:

```json
[
  {
      "name": "NSFW",
      "createdAt": "2020-08-29T11:35:45.248Z",
      "updatedAt": "2020-08-29T11:35:45.248Z",
      "objectId": "dx3FBrIewC"
  }
];

```

### cloud function

`createDepartment`

This cloud function updates name of department and returns updated department.

### Parameters

| Parameter | Required | Type   | Description                                      |
| --------- | -------- | ------ | ------------------------------------------------ |
| objectId  | \*       | string | Unique objectId of the department to be created. |
| name      | \*       | string | Name of the department to be updated.            |
