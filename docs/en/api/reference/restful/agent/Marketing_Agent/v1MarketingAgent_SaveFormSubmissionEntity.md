---
title: POST Agents/Marketing/SaveFormSubmissionEntity
uid: v1MarketingAgent_SaveFormSubmissionEntity
generated: true
---

# POST Agents/Marketing/SaveFormSubmissionEntity

```http
POST /api/v1/Agents/Marketing/SaveFormSubmissionEntity
```

Updates the existing FormSubmissionEntity or creates a new FormSubmissionEntity if the id parameter is empty








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

## Request Body: entity 

The FormSubmissionEntity to be saved. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| FormSubmissionId | Integer | Primary key |
| FormId | Integer | The id of the parent form. |
| WhenSubmitted | String | The time of the submit. |
| ContactId | Integer | The optional id of the contact of the person who submitted. |
| PersonId | Integer | The optional id of the person who submitted. |
| EmailAddress | String | The email address of the person who submitted |
| ResponseShipmentAddrId | Integer | The id of the s_shipment_addr that is the response mail |
| Response | String | The JSON-formatted response from this form |
| Status | String | What is the status of this submission |
| ProcessingLog | String | A log of what happened during processing |

## Response:

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: FormSubmissionEntity

| Property Name | Type |  Description |
|----------------|------|--------------|
| FormSubmissionId | int32 | Primary key |
| FormId | int32 | The id of the parent form. |
| WhenSubmitted | date-time | The time of the submit. |
| ContactId | int32 | The optional id of the contact of the person who submitted. |
| PersonId | int32 | The optional id of the person who submitted. |
| EmailAddress | string | The email address of the person who submitted |
| ResponseShipmentAddrId | int32 | The id of the s_shipment_addr that is the response mail |
| Response | string | The JSON-formatted response from this form |
| Status | string | What is the status of this submission |
| ProcessingLog | string | A log of what happened during processing |
| TableRight | TableRight | The carrier's table right |
| FieldProperties | object | Field property dictionary mapping field names to field access rights. |

## Sample request

```http!
POST /api/v1/Agents/Marketing/SaveFormSubmissionEntity
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: *
Content-Type: application/json; charset=utf-8

{
  "FormSubmissionId": 127,
  "FormId": 632,
  "WhenSubmitted": "2021-03-14T10:30:24.1037706+01:00",
  "ContactId": 92,
  "PersonId": 784,
  "EmailAddress": "mafalda.dickens@hoppearmstrong.ca",
  "ResponseShipmentAddrId": 54,
  "Response": "possimus",
  "Status": "EmailVerification",
  "ProcessingLog": "iste"
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "FormSubmissionId": 547,
  "FormId": 886,
  "WhenSubmitted": "2003-05-22T10:30:24.1037706+02:00",
  "ContactId": 980,
  "PersonId": 109,
  "EmailAddress": "lavada@kleinthompson.name",
  "ResponseShipmentAddrId": 553,
  "Response": "quidem",
  "Status": "EmailVerification",
  "ProcessingLog": "in",
  "TableRight": null,
  "FieldProperties": {
    "fieldName": {
      "FieldRight": null,
      "FieldType": "System.Int32",
      "FieldLength": 355
    }
  }
}
```