---
title: POST Agents/BulkUpdate/GetAvailableFields
uid: v1BulkUpdateAgent_GetAvailableFields
generated: true
---

# POST Agents/BulkUpdate/GetAvailableFields

```http
POST /api/v1/Agents/BulkUpdate/GetAvailableFields
```

Get all available fields for a given tablename/entity







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/BulkUpdate/GetAvailableFields?$select=name,department,category/id
```


## Request Headers

| Parameter Name | Description |
|----------------|-------------|
| Authorization  | Supports 'Basic', 'SoTicket' and 'Bearer' schemes, depending on installation type. |
| X-XSRF-TOKEN   | If not using Authorization header, you must provide XSRF value from cookie or hidden input field |
| Content-Type | Content-type of the request body: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/x-www-form-urlencoded`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept         | Content-type(s) you would like the response in: `application/json`, `text/json`, `application/xml`, `text/xml`, `application/json-patch+json`, `application/merge-patch+json` |
| Accept-Language | Convert string references and multi-language values into a specified language (iso2) code. |
| SO-Language | Convert string references and multi-language values into a specified language (iso2) code. Overrides Accept-Language value. |
| SO-Culture | Number, date formatting in a specified culture (iso2 language) code. Partially overrides SO-Language/Accept-Language value. Ignored if no Language set. |
| SO-TimeZone | Specify the timezone code that you would like date/time responses converted to. |
| SO-AppToken | The application token that identifies the partner app. Used when calling Online WebAPI from a server. |

## Request Body: request 

Tablename 

| Property Name | Type |  Description |
|----------------|------|--------------|
| Tablename | String |  |

## Response:array

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: array

| Property Name | Type |  Description |
|----------------|------|--------------|
| CanSupportMultiUse | bool | Can the field support multi use? |
| DefaultShowInGui | bool | Default show in Gui? |
| DefaultShowInSelector | bool | Default show in selector? |
| IsActive | bool | True if the field and operations will be used in the bulk update |
| Key | string | The unique key on the field |
| ValueType | string | Describes the expected value array |
| Mandatory | bool | True if this is a mandatory field |
| EncodedDisplayName | string | The displayname of the field |
| EncodedDisplayDescription | string | The description of the field |
| IconHint | string | The iconhint of the field |
| ControlInfos | array | Array of the controlinfos |
| EncodedDataCaption | string |  |
| EncodedDataCaptionDescription | string |  |
| CurrentOperationType | string | The selected operation to execute on this field |
| Values | array | The values to be set on this field on this bulkupdate |
| DisplayValues | array | The displayvalues to be set on this field on this bulkupdate, used to resolve when values array contains ids |
| OperationInfos | array | Array of the available operations for this field |

## Sample request

```http!
POST /api/v1/Agents/BulkUpdate/GetAvailableFields
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: sv
Content-Type: application/json; charset=utf-8

{
  "Tablename": "project"
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "CanSupportMultiUse": false,
    "DefaultShowInGui": true,
    "DefaultShowInSelector": false,
    "IsActive": false,
    "Key": "porro",
    "ValueType": "voluptates",
    "Mandatory": false,
    "EncodedDisplayName": "West LLC",
    "EncodedDisplayDescription": "Adaptive methodical synergy",
    "IconHint": "fugiat",
    "ControlInfos": [
      {
        "Type": "magnam",
        "Label": "qui",
        "Dimension": 555,
        "ListProviderName": "Baumbach Group",
        "ListProviderExtraInfo": "ea",
        "ListProviderPrimaryKeyName": "Wehner-Bartell",
        "ListLeadText": "ipsum",
        "TableRight": null,
        "FieldProperties": {
          "fieldName": {
            "FieldRight": null,
            "FieldType": "System.Int32",
            "FieldLength": 39
          }
        }
      }
    ],
    "EncodedDataCaption": "temporibus",
    "EncodedDataCaptionDescription": "Object-based modular archive",
    "CurrentOperationType": "accusantium",
    "Values": [
      "doloribus",
      "ab"
    ],
    "DisplayValues": [
      "repellendus",
      "aut"
    ],
    "OperationInfos": [
      {
        "Key": "accusantium",
        "EncodedDisplayName": "Borer LLC",
        "EncodedLeadTexts": [
          "ratione",
          "dicta"
        ],
        "TableRight": null,
        "FieldProperties": {
          "fieldName": {
            "FieldRight": null,
            "FieldType": "System.String",
            "FieldLength": 519
          }
        }
      },
      {
        "Key": "accusantium",
        "EncodedDisplayName": "Borer LLC",
        "EncodedLeadTexts": [
          "ratione",
          "dicta"
        ],
        "TableRight": null,
        "FieldProperties": {
          "fieldName": {
            "FieldRight": null,
            "FieldType": "System.String",
            "FieldLength": 519
          }
        }
      }
    ]
  }
]
```