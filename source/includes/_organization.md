# Organization

## Get Organization Status

```javascript
import Parse from "parse";

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

| Status | Description                                                                             |
| ------ | --------------------------------------------------------------------------------------- |
| 0      | There is no Admin User or Organization information.                                     |
| 1      | There is a Admin user but no Organization information.                                  |
| 2      | There is a Admin user andOrganization information (Organization onboarding successful). |

### Parameters

NOT REQUIRED

## Get Organization

```javascript
import Parse from "parse";

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

This cloud function will create and return a new organisation.

Ideally should be using when `getOrganizationStatus` cloud functions returns status `1`

### Cloud Function

`createOrganization`

### Parameters

| Parameter | Required | Type             | Description                          |
| --------- | -------- | ---------------- | ------------------------------------ |
| name      | \*       | string           | Name of the organization.            |
| email     | \*       | string           | Email of the organization.           |
| prefix    | \*       | string           | Prefix of the organization.          |
| address   | \*       | object - Address | Full address of the organization.    |
| bank      |          | bank - Bank      | Bank details of the organization.    |
| gst       | \*       | string           | GST number of the organization.      |
| contact   | \*       | Object - Contact | Contact details of the organization. |
| logo      | \*       | Parse File       | Organization Logo.                   |

| Parameter  | Required | Type                | Description                     |
| ---------- | -------- | ------------------- | ------------------------------- |
| name       | \*       | string              | Name of the role to be updated. |
| permission | \*       | Object - Permission | Access permission object.       |
