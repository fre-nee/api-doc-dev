---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript (React)

toc_footers:
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to Exactt API! This is documentation about various cloud code fucntions which can consumed to make exactt client app work. For more information about code checkout <a href=' https://docs.parseplatform.org/cloudcode/guide/#cloud-functions'>Parse Server Cloud Code</a>

Document is authored by Freddy Thobhani <thobhani.freddy@gmail.com> and it it currently maintained by
Freddy Thobhani and Neel Patel <hello@ineelpatel.com>. Feel free to contact Freddy or Neel if something is not clear or you see any mistake.

For any new cloud code function request create a [issue](https://github.com/fre-nee/exactt-backend/issues)

# Authentication

> To configure Parse on client side:

```javascript
import Parse from 'parse'

Parse.initialize("YOUR_APP_ID", "YOUR_JAVASCRIPT_KEY");
Parse.serverURL = 'http://YOUR_PARSE_SERVER:1337/api'
```

> Make sure to replace `YOUR_APP_ID` with your APP key.

> Make sure to replace `YOUR_JAVASCRIPT_KEY` with your JAVASCRIPT key.

> Make sure to replace `YOUR_PARSE_SERVER` with your API SERVER url.

To see detailed docs about configuring Parse on client side for consuing exactt backend check [Parse JS Guide](https://docs.parseplatform.org/js/guide/).


# Organization

## Get Organization Status

```javascript
import Parse from 'parse'

const res = await Parse.Cloud.run("getOrganizationStatus");
```

> The above command returns NUMBER as a status which can 0,1 or 2:

```number
1
```

### cloud function

`getOrganizationStatus`

This cloud function returns the status of organization. 

Status is a number which can be 0, 1 or 2. 

Status | Description 
--------- | ---------|------|-------------
0 | There is no Admin User or Organization information.
1 | There is a Admin user but no Organization information.
2 | There is a Admin user andOrganization information (Organization onboarding successful).


### Parameters

NOT REQUIRED


## Get Organization

```javascript
import Parse from 'parse'

const res = await Parse.Cloud.run("getOrganizationStatus");
```

> The above command returns JSON structured like this:

```json
{
  "address": {
      "line1": "201-202, Sahaj Arcade, Above Vimal Hospital",
      "line2": "Opposite Lincoln Healthcare, Near Sola Gam, Science City Road",
      "state": "Gujarat",
      "city": "Ahmedabad",
      "zip": "380060"
  },
  "bank": {
      "name": "Kotak",
      "acc_name": "Hitech",
      "acc_number": "1234567890",
      "branch": "Maninagar",
      "ifsc": "KKBK00091"
  },
  "contact": {
      "name": "Neel Patel",
      "phone": "9825866927",
      "email": "info@hitech.com"
  },
  "name": "Hitech Healthcare Laboratory and Research Centre",
  "email": "info@hitech.com",
  "prefix": "HTL",
  "gst": "24ABCDE1234F2Z5",
  "logo": {
      "__type": "File",
      "name": "9ea584fcfe5e72fc379d53af00158f6a_companyLogo.png",
      "url": "http://exactt-dev.herokuapp.com/api/files/exactt-backend/9ea584fcfe5e72fc379d53af00158f6a_companyLogo.png"
  },
  "createdAt": "2020-08-26T15:40:04.698Z",
  "updatedAt": "2020-08-26T15:40:04.698Z",
  "objectId": "UPiSW6hpvi"
}
```

This cloud function returns organization information.

### Cloud Function

`getOrganization`

### Parameters

NOT REQUIRED

## Create Organization

```javascript
import Parse from 'parse'

const res = await Parse.Cloud.run("createOrganization",
  { <PARAMETERS> });
```

> The above command returns JSON structured like this:

```json
{
  "address": {
      "line1": "201-202, Sahaj Arcade, Above Vimal Hospital",
      "line2": "Opposite Lincoln Healthcare, Near Sola Gam, Science City Road",
      "state": "Gujarat",
      "city": "Ahmedabad",
      "zip": "380060"
  },
  "bank": {
      "name": "Kotak",
      "acc_name": "Hitech",
      "acc_number": "1234567890",
      "branch": "Maninagar",
      "ifsc": "KKBK00091"
  },
  "contact": {
      "name": "Neel Patel",
      "phone": "9825866927",
      "email": "info@hitech.com"
  },
  "name": "Hitech Healthcare Laboratory and Research Centre",
  "email": "info@hitech.com",
  "prefix": "HTL",
  "gst": "24ABCDE1234F2Z5",
  "logo": {
      "__type": "File",
      "name": "9ea584fcfe5e72fc379d53af00158f6a_companyLogo.png",
      "url": "http://exactt-dev.herokuapp.com/api/files/exactt-backend/9ea584fcfe5e72fc379d53af00158f6a_companyLogo.png"
  },
  "createdAt": "2020-08-26T15:40:04.698Z",
  "updatedAt": "2020-08-26T15:40:04.698Z",
  "objectId": "UPiSW6hpvi"
}
```

This cloud function creates a new organisation.

Ideally should be using when `getOrganizationStatus` cloud functions returns status `1`

### Cloud Function

`createOrganization`

### Parameters

Parameter | Required | Type | Description
--------- | ---------|------|-------------
name | * | string  | Name of the organization.
email | * | string  | Email of the organization.
prefix | * | string | Prefix of the organization.
address | * | object - Address | Full address of the organization.
bank | | bank - Bank | Bank details of the organization.
gst | * | string | GST number of the organization.
contact | * | Object - Contact | Contact details of the organization.
logo | * | Parse File | Organization Logo.


# Role

## Get Role Access Permissions

```javascript
import Parse from 'parse'

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

Parameter | Required | Type | Description
--------- | ---------|------|-------------
roleName | * | string  | Name of the role to be created.

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

Parameter | Required | Type | Description
--------- | ---------|------|-------------
name | * | string  | Name of the role to be updated.
permission | * | Object - Permission | Access permission object.

# Department

## Get Departments

```javascript
import Parse from 'parse'

const res = await Parse.Cloud.run("getDepartments")
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

Parameter | Required | Type | Description
--------- | ---------|------|-------------
name | * | string  | Name of the department to be created.

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

Parameter | Required | Type | Description
--------- | ---------|------|-------------
objectId | * | string  | Unique objectId of the department to be created.
name | * | string  | Name of the department to be updated.