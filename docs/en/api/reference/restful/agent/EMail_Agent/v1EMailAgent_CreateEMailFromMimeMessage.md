---
title: POST Agents/EMail/CreateEMailFromMimeMessage
uid: v1EMailAgent_CreateEMailFromMimeMessage
generated: true
---

# POST Agents/EMail/CreateEMailFromMimeMessage

```http
POST /api/v1/Agents/EMail/CreateEMailFromMimeMessage
```

Get an e-mail based on the provided MIME-message


## Online Restricted: ## The EMail agent is not available in Online by default. Access must be requested specifically when app is registered.






## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/EMail/CreateEMailFromMimeMessage?$select=name,department,category/id
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

MimeMessage 

| Property Name | Type |  Description |
|----------------|------|--------------|
| MimeMessage | String |  |

## Response:

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: EMailEntity

| Property Name | Type |  Description |
|----------------|------|--------------|
| To | array | To recipients of e-mail |
| Cc | array | Cc recipients of e-mail |
| Bcc | array | Bcc recipient of e-mail |
| Subject | string | Subject of the e-mail |
| HTMLBody | string | Body formatted in HTML |
| From | EMailAddress | Who did the e-mail originate from |
| Sent | date-time | When was the e-mail sent |
| Size | int32 | Total size of the e-mail |
| Priority | string | Importance of the e-mail |
| Flags | string | Flag status of this mail (unread, replied, deleted ) |
| MessageID | string | Unique id of e-mails |
| PlainBody | string | Body formatted in plain text |
| IsSent | bool | Is this a sent e-mail (not new) |
| EMailSOInfo | EMailSOInfo | Glue between SuperOffice data and an e-mail. |
| ServerId | int32 | Unique id for the e-mail on the server |
| Attachments | array |  |
| CustomHeaderList | array | Non standard e-mail headers |
| FolderName | string | Name of folder the e-mail belongs in |
| EmailItemId | int32 | Primary key |
| AccountId | int32 | Account Id |
| ReceivedAt | date-time | Received date time |
| InReplyTo | EMailEnvelope | The envelope of the email this email is a reply to, if it exists |
| RepliedAt | date-time | When this email was replied at |
| HasCalendarData | bool | If this email contains exactly one iCal appointment |
| CalMethod | string | Method stored in the associated iCal appointment. Indicates if the iCal data is a reply, counter proposal etc. |
| CalReplyStatus | string | Reply status stored in calendar data for the ical method is REPLY |
| TableRight | TableRight | The carrier's table right |
| FieldProperties | object | Field property dictionary mapping field names to field access rights. |

## Sample request

```http!
POST /api/v1/Agents/EMail/CreateEMailFromMimeMessage
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

{
  "MimeMessage": "non"
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "To": [
    {
      "ContactId": 743,
      "ContactName": "Langworth-Pfeffer",
      "PersonId": 131,
      "PersonName": "Tremblay, Lebsack and Conroy",
      "AssociateId": 213,
      "Address": "atque",
      "EmailId": 584,
      "DuplicatePersonIds": [
        435,
        186
      ],
      "Name": "Olson Inc and Sons",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.String",
          "FieldLength": 971
        }
      }
    }
  ],
  "Cc": [
    {
      "ContactId": 646,
      "ContactName": "Heathcote Group",
      "PersonId": 538,
      "PersonName": "Stroman-Krajcik",
      "AssociateId": 472,
      "Address": "tempore",
      "EmailId": 577,
      "DuplicatePersonIds": [
        1000,
        88
      ],
      "Name": "Bartoletti, Kulas and Okuneva",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 570
        }
      }
    }
  ],
  "Bcc": [
    {
      "ContactId": 89,
      "ContactName": "Wolff Group",
      "PersonId": 875,
      "PersonName": "Hand-Zboncak",
      "AssociateId": 262,
      "Address": "facilis",
      "EmailId": 196,
      "DuplicatePersonIds": [
        486,
        964
      ],
      "Name": "Bednar, Harber and Douglas",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 974
        }
      }
    }
  ],
  "Subject": "voluptatem",
  "HTMLBody": "ut",
  "From": null,
  "Sent": "2002-07-05T10:30:23.8293034+02:00",
  "Size": 296,
  "Priority": "High",
  "Flags": "Answered",
  "MessageID": "sed",
  "PlainBody": "architecto",
  "IsSent": true,
  "EMailSOInfo": null,
  "ServerId": 593,
  "Attachments": [
    {
      "Description": "Customizable discrete info-mediaries",
      "Filename": "quis",
      "Size": 978,
      "Type": "accusantium",
      "Encoding": "voluptate",
      "Id": "maiores",
      "Disposition": "in",
      "IsSafeFileExtension": true,
      "Stream": "GIF89....File contents as raw bytes...",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.String",
          "FieldLength": 74
        }
      }
    }
  ],
  "CustomHeaderList": [
    {
      "Name": "Ritchie Inc and Sons",
      "Values": [
        "dicta",
        "autem"
      ],
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 178
        }
      }
    },
    {
      "Name": "Ritchie Inc and Sons",
      "Values": [
        "dicta",
        "autem"
      ],
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 178
        }
      }
    }
  ],
  "FolderName": "Schneider, Paucek and Boyle",
  "EmailItemId": 754,
  "AccountId": 400,
  "ReceivedAt": "2024-02-11T10:30:23.8293034+01:00",
  "InReplyTo": null,
  "RepliedAt": "2008-03-20T10:30:23.8293034+01:00",
  "HasCalendarData": false,
  "CalMethod": "Add",
  "CalReplyStatus": "Accepted",
  "TableRight": null,
  "FieldProperties": {
    "fieldName": {
      "FieldRight": null,
      "FieldType": "System.Int32",
      "FieldLength": 372
    }
  }
}
```