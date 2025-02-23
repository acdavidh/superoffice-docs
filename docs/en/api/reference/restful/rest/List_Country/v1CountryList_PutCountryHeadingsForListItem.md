---
title: PUT List/Country/Items/{id}/Headings
uid: v1CountryList_PutCountryHeadingsForListItem
generated: true
---

# PUT List/Country/Items/{id}/Headings

```http
PUT /api/v1/List/Country/Items/{itemId}/Headings
```

Saves headings for the Country list's item.


Calls the List agent service SaveHeadingsForListItemFromListDefinition.





| Path Part | Type | Description |
|-----------|------|-------------|
| itemId | int32 | The ID of the headings to be saved. **Required** |



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

## Request Body: entities 

The headings to be saved. 

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
PUT /api/v1/List/Country/Items/{itemId}/Headings
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: fr,de,ru,zh
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 476,
    "Name": "Abbott-Langosh",
    "ToolTip": "Tempore illum in.",
    "Deleted": false,
    "Rank": 937,
    "Type": "qui",
    "ColorBlock": 124,
    "IconHint": "non",
    "Selected": true,
    "LastChanged": "2019-05-09T10:30:32.9274257+02:00",
    "ChildItems": [
      {
        "Id": 57,
        "Name": "Koepp Inc and Sons",
        "ToolTip": "Voluptatem et ea beatae ad dolorem architecto.",
        "Deleted": false,
        "Rank": 364,
        "Type": "et",
        "ColorBlock": 517,
        "IconHint": "assumenda",
        "Selected": true,
        "LastChanged": "2019-04-04T10:30:32.9274257+02:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "sunt",
        "StyleHint": "quo",
        "Hidden": false,
        "FullName": "Dr. Fay Abernathy II"
      }
    ],
    "ExtraInfo": "minima",
    "StyleHint": "dolorem",
    "Hidden": false,
    "FullName": "Mr. Aurelio Kattie Blanda"
  }
]
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

[
  {
    "Id": 909,
    "Name": "O'Hara Group",
    "ToolTip": "Ex provident voluptatum.",
    "Deleted": false,
    "Rank": 257,
    "Type": "est",
    "ColorBlock": 429,
    "IconHint": "eveniet",
    "Selected": false,
    "LastChanged": "2019-06-01T10:30:32.9430827+02:00",
    "ChildItems": [
      {
        "Id": 213,
        "Name": "Reinger, Steuber and Rutherford",
        "ToolTip": "Vel et ut quo mollitia est.",
        "Deleted": false,
        "Rank": 809,
        "Type": "libero",
        "ColorBlock": 74,
        "IconHint": "natus",
        "Selected": false,
        "LastChanged": "2004-01-15T10:30:32.9430827+01:00",
        "ChildItems": [
          {},
          {}
        ],
        "ExtraInfo": "ut",
        "StyleHint": "eveniet",
        "Hidden": true,
        "FullName": "Merle Aufderhar",
        "TableRight": null,
        "FieldProperties": {
          "fieldName": {
            "FieldRight": null,
            "FieldType": "System.String",
            "FieldLength": 357
          }
        }
      }
    ],
    "ExtraInfo": "et",
    "StyleHint": "quia",
    "Hidden": false,
    "FullName": "Nathan Kunze",
    "TableRight": null,
    "FieldProperties": {
      "fieldName": {
        "FieldRight": null,
        "FieldType": "System.Int32",
        "FieldLength": 699
      }
    }
  }
]
```