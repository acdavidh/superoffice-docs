---
title: POST Agents/EMail/SaveEMail
uid: v1EMailAgent_SaveEMail
generated: true
---

# POST Agents/EMail/SaveEMail

```http
POST /api/v1/Agents/EMail/SaveEMail
```

Save the passed e-mail back to the server


## Online Restricted: ## The EMail agent is not available in Online by default. Access must be requested specifically when app is registered.






## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/EMail/SaveEMail?$select=name,department,category/id
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

ConnectionInfo, Email 

| Property Name | Type |  Description |
|----------------|------|--------------|
| ConnectionInfo | EMailConnectionInfo | All information needed to connect to a mailserver <para /> Carrier object for EMailConnectionInfo. Services for the EMailConnectionInfo Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IEMailAgent">EMail Agent</see>. |
| Email | EMailEntity | All information about an e-mail <para /> Carrier object for EMailEntity. Services for the EMailEntity Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IEMailAgent">EMail Agent</see>. |

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
POST /api/v1/Agents/EMail/SaveEMail
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

{
  "ConnectionInfo": null,
  "Email": null
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "To": [
    {
      "ContactId": 81,
      "ContactName": "Hegmann-Konopelski",
      "PersonId": 579,
      "PersonName": "Ortiz, Crona and White",
      "AssociateId": 369,
      "Address": "a",
      "EmailId": 403,
      "DuplicatePersonIds": [
        63,
        160
      ],
      "Name": "Parker, Purdy and Hermann",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 638
        }
      }
    }
  ],
  "Cc": [
    {
      "ContactId": 485,
      "ContactName": "Casper-Lynch",
      "PersonId": 527,
      "PersonName": "Gibson, Von and Harber",
      "AssociateId": 253,
      "Address": "vero",
      "EmailId": 28,
      "DuplicatePersonIds": [
        909,
        614
      ],
      "Name": "Quitzon Group",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 847
        }
      }
    }
  ],
  "Bcc": [
    {
      "ContactId": 997,
      "ContactName": "Jacobson, Spencer and Greenfelder",
      "PersonId": 939,
      "PersonName": "Morissette, Hettinger and Towne",
      "AssociateId": 972,
      "Address": "sapiente",
      "EmailId": 230,
      "DuplicatePersonIds": [
        402,
        905
      ],
      "Name": "Bogisich-Bradtke",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.String",
          "FieldLength": 520
        }
      }
    }
  ],
  "Subject": "alias",
  "HTMLBody": "commodi",
  "From": null,
  "Sent": "2016-09-15T10:30:23.798054+02:00",
  "Size": 41,
  "Priority": "High",
  "Flags": "Answered",
  "MessageID": "omnis",
  "PlainBody": "omnis",
  "IsSent": false,
  "EMailSOInfo": null,
  "ServerId": 554,
  "Attachments": [
    {
      "Description": "Self-enabling background productivity",
      "Filename": "tempore",
      "Size": 979,
      "Type": "impedit",
      "Encoding": "quas",
      "Id": "maxime",
      "Disposition": "libero",
      "IsSafeFileExtension": false,
      "Stream": "GIF89....File contents as raw bytes...",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 357
        }
      }
    }
  ],
  "CustomHeaderList": [
    {
      "Name": "Wisozk, West and Hermiston",
      "Values": [
        "nemo",
        "est"
      ],
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 769
        }
      }
    },
    {
      "Name": "Wisozk, West and Hermiston",
      "Values": [
        "nemo",
        "est"
      ],
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 769
        }
      }
    }
  ],
  "FolderName": "Monahan-Gleichner",
  "EmailItemId": 878,
  "AccountId": 361,
  "ReceivedAt": "2004-11-18T10:30:23.798054+01:00",
  "InReplyTo": null,
  "RepliedAt": "1999-02-11T10:30:23.798054+01:00",
  "HasCalendarData": false,
  "CalMethod": "Add",
  "CalReplyStatus": "Accepted",
  "TableRight": null,
  "FieldProperties": {
    "fieldName": {
      "FieldRight": null,
      "FieldType": "System.Int32",
      "FieldLength": 392
    }
  }
}
```