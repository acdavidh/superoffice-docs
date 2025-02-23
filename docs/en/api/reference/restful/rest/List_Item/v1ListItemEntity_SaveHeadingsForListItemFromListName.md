---
title: PUT List/{udListDefinitionName}/Items/{id}/Headings
uid: v1ListItemEntity_SaveHeadingsForListItemFromListName
generated: true
---

# PUT List/{udListDefinitionName}/Items/{id}/Headings

```http
PUT /api/v1/List/{udListDefinitionName}/Items/{listItemId}/Headings
```

Saves the headings for the list item.






| Path Part | Type | Description |
|-----------|------|-------------|
| udListDefinitionName | string | The name of the list definition, indicating which list to update. **Required** |
| listItemId | int32 | The identity of the list item **Required** |



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

## Request Body: headings 

The headings to save. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| Id | Integer | The Id of the ListItem |
| Name | String | The name of the ListItem |
| ToolTip | String | The tooltip of the ListItem |
| Deleted | Boolean | The deleted status of the ListItem |
| Rank | Integer | The rank of the ListItem |
| Type | String | The type of the ListItem. Custom field. |
| ColorBlock | Integer | The color indicator of the ListItem color block |
| IconHint | String | The Icon hint of the ListItem. Custom field. |
| Selected | Boolean | True if the ListItem is selected |
| LastChanged | String | Time of last change. |
| ChildItems | Array | The child items of the SelectableMDOListItem |
| ExtraInfo | String | Extra information added to the ListItem. Could be information such as sort order etc or other meta data. Custom field. |
| StyleHint | String | Style hint indicating, information such as background color etc. Custom field. |
| Hidden | Boolean | True if the ListItem is hidden |
| FullName | String | The name of the ListItem in its context |

## Response:array

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: array

| Property Name | Type |  Description |
|----------------|------|--------------|
| Id | int32 | The Id of the ListItem |
| Name | string | The name of the ListItem |
| ToolTip | string | The tooltip of the ListItem |
| Deleted | bool | The deleted status of the ListItem |
| Rank | int32 | The rank of the ListItem |
| Type | string | The type of the ListItem. Custom field. |
| ColorBlock | int32 | The color indicator of the ListItem color block |
| IconHint | string | The Icon hint of the ListItem. Custom field. |
| Selected | bool | True if the ListItem is selected |
| LastChanged | date-time | Time of last change. |
| ChildItems | array | The child items of the SelectableMDOListItem |
| ExtraInfo | string | Extra information added to the ListItem. Could be information such as sort order etc or other meta data. Custom field. |
| StyleHint | string | Style hint indicating, information such as background color etc. Custom field. |
| Hidden | bool | True if the ListItem is hidden |
| FullName | string | The name of the ListItem in its context |
| TableRight | TableRight | The carrier's table right |
| FieldProperties | object | Field property dictionary mapping field names to field access rights. |

## Sample request

```http!
PUT /api/v1/List/{udListDefinitionName}/Items/{listItemId}/Headings
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 973,
    "Name": "Yost-Hoeger",
    "ToolTip": "Et et.",
    "Deleted": false,
    "Rank": 264,
    "Type": "sed",
    "ColorBlock": 759,
    "IconHint": "distinctio",
    "Selected": true,
    "LastChanged": "2018-02-26T10:30:32.8425633+01:00",
    "ChildItems": [
      {
        "Id": 319,
        "Name": "Zemlak LLC",
        "ToolTip": "Cumque et hic.",
        "Deleted": false,
        "Rank": 195,
        "Type": "quia",
        "ColorBlock": 744,
        "IconHint": "aliquam",
        "Selected": false,
        "LastChanged": "2021-12-08T10:30:32.8425633+01:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "repudiandae",
        "StyleHint": "et",
        "Hidden": false,
        "FullName": "Prof. Dillan Zulauf"
      }
    ],
    "ExtraInfo": "sit",
    "StyleHint": "inventore",
    "Hidden": false,
    "FullName": "Maia Homenick"
  }
]
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 593,
    "Name": "Bauch, Bosco and Crooks",
    "ToolTip": "Nostrum incidunt ea qui voluptatum ut doloremque.",
    "Deleted": false,
    "Rank": 229,
    "Type": "accusantium",
    "ColorBlock": 204,
    "IconHint": "aspernatur",
    "Selected": false,
    "LastChanged": "2006-09-19T10:30:32.8425633+02:00",
    "ChildItems": [
      {
        "Id": 909,
        "Name": "Predovic, Harris and Torphy",
        "ToolTip": "Corrupti debitis animi eligendi inventore praesentium consequatur nesciunt.",
        "Deleted": false,
        "Rank": 980,
        "Type": "placeat",
        "ColorBlock": 397,
        "IconHint": "voluptatem",
        "Selected": false,
        "LastChanged": "2003-07-14T10:30:32.8425633+02:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "tempora",
        "StyleHint": "quisquam",
        "Hidden": false,
        "FullName": "Reta Beer",
        "TableRight": null,
        "FieldProperties": {
          "fieldName": {
            "FieldRight": null,
            "FieldType": "System.Int32",
            "FieldLength": 851
          }
        }
      }
    ],
    "ExtraInfo": "et",
    "StyleHint": "cumque",
    "Hidden": true,
    "FullName": "Ashleigh Rau",
    "TableRight": null,
    "FieldProperties": {
      "fieldName": {
        "FieldRight": null,
        "FieldType": "System.String",
        "FieldLength": 602
      }
    }
  }
]
```