# Role

## Get Role Access Permissions

```javascript
import Parse from "parse";

const res = await Parse.Cloud.run("getRoleAccessPermission");
```

> The above command returns JSON structured like this:

```json
{
  "admin": {
    "role": {
        "read": true,
        "write": true
    },
    "user": {
        "read": true,
        "write": true
    },
    "customer": {
        "read": true,
        "write": true
    },
    "department": {
        "read": true,
        "write": true
    },
    ...
  }
};

```

### cloud function

`getRoleAccessPermission`

This cloud function returns the access permission for each role.

### Parameters

NOT REQUIRED

## Get Role List

```javascript
import Parse from "parse";

const res = await Parse.Cloud.run("getAvailableRoles");
```

> The above command returns JSON structured like this:

```json
[
    {
        "name": "admin",
        "objectId": "gGYz6fgKCC"
    },
    {
        "name": "hod",
        "objectId": "185Cjy9yX7"
    },
    {
        "name": "account",
        "objectId": "1r65a7ENKS"
    },
    {
        "name": "chemist",
        "objectId": "0PJiOoCFeg"
    },
    {
        "name": "Receptionist",
        "objectId": "PGIEP5lnZK"
    },
    {
        "name": "test",
        "objectId": "GwKC5JAhc4"
    }
];
```

### cloud function

`getAvailableRoles`

This cloud function returns list of available roles.

### Parameters

NOT REQUIRED

## Create Role

```javascript
import Parse from 'parse'

const res = await Parse.Cloud.run("createRole",
  { <PARAMETERS> });
```

> The above command returns JSON structured like this:

```json
{
  "test": {
    "role": {
        "read": false,
        "write": false
    },
    "user": {
        "read": false,
        "write": false
    },
    "customer": {
        "read": false,
        "write": false
    },
    "department": {
        "read": false,
        "write": false
    },
    ...
  }
};

```

### cloud function

`createRole`

This cloud function creates and returns new role.

### Parameters

| Parameter | Required | Type   | Description                     |
| --------- | -------- | ------ | ------------------------------- |
| roleName  | \*       | string | Name of the role to be created. |

## Update Role

```javascript
import Parse from 'parse'

const res = await Parse.Cloud.run("updateRole",
  { <PARAMETERS> });
```

> The above command returns JSON structured like this:

```json
{
  "test": {
    "role": {
        "read": false,
        "write": false
    },
    "user": {
        "read": false,
        "write": false
    },
    "customer": {
        "read": false,
        "write": false
    },
    "department": {
        "read": false,
        "write": false
    },
    ...
  }
};

```

### cloud function

`updateRole`

This cloud function updates and returns updated role.

### Parameters
