---
title: PUT Webhook/{id}
uid: v1Webhook_PutWebhook
generated: true
---

# PUT Webhook/{id}

```http
PUT /api/v1/Webhook/{id}
```

Updates the existing Webhook


## Online Restricted: ## The Webhook agent is not available in Online by default. Access must be requested specifically when app is registered.





| Path Part | Type | Description |
|-----------|------|-------------|
| id | int32 | The Webhook id to update. **Required** |


## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category" Default = show all fields. |

```http
PUT /api/v1/Webhook/{id}?$select=name,department,category/id
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

## Request Body: entity 

The Webhook to be saved. 

| Property Name | Type |  Description |
|----------------|------|--------------|
| WebhookId | Integer | Primary Key. Unique id for this webhook. |
| Name | String | Name to identify this webhook. Does not have to be unique. |
| Events | Array | Array of event names that trigger this webhook: ['contact.created', 'sale.changed'] |
| TargetUrl | String | Destination to POST event info to. URL for webhooks. Id for CRM scripts |
| Secret | String | Shared secret key used for generating SHA256 HMAC signature, so that receiver can verify that call came from this server |
| State | String | Webhook status - should we post events to the URL? 1=Active, 2=Stopped or 3=TooManyErrors |
| Type | String | Name of plugin that handles this webhook. 'webhook' for HTTP POST notifications, 'crmscript' for script invocations. |
| Headers | Object | Custom HTTP Headers to add to webhook requests. |
| Properties | Object | Custom values to inject into JSON body of webhook call. |
| Registered | String | Registered when  in UTC. |
| RegisteredAssociate | Associate | The user that created the webhook. |
| Updated | String | Last updated when  in UTC. |
| UpdatedAssociate | Associate | The user that last updated the webhook. |
| ErrorsEmail | String | Email address to send error message to when this webhook state changes to too-many errors. |

## Response:

Webhook updated.

| Response | Description |
|----------------|-------------|
| 200 | Webhook updated. |
| 400 | Bad request. Entity to save is not in request body. |

### Response body: WebhookWithLinks

| Property Name | Type |  Description |
|----------------|------|--------------|
| WebhookId | int32 | Primary Key. Unique id for this webhook. |
| Name | string | Name to identify this webhook. Does not have to be unique. |
| Events | array | Array of event names that trigger this webhook: ['contact.created', 'sale.changed'] |
| TargetUrl | string | Destination to POST event info to. URL for webhooks. Id for CRM scripts |
| Secret | string | Shared secret key used for generating SHA256 HMAC signature, so that receiver can verify that call came from this server |
| State | string | Webhook status - should we post events to the URL? 1=Active, 2=Stopped or 3=TooManyErrors |
| Type | string | Name of plugin that handles this webhook. 'webhook' for HTTP POST notifications, 'crmscript' for script invocations. |
| Headers | object | Custom HTTP Headers to add to webhook requests. |
| Properties | object | Custom values to inject into JSON body of webhook call. |
| Registered | date-time | Registered when  in UTC. |
| RegisteredAssociate | Associate | The user that created the webhook. |
| Updated | date-time | Last updated when  in UTC. |
| UpdatedAssociate | Associate | The user that last updated the webhook. |
| ErrorsEmail | string | Email address to send error message to when this webhook state changes to too-many errors. |
| _Links | object |  |

## Sample request

```http!
PUT /api/v1/Webhook/{id}
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: sv
Content-Type: application/json; charset=utf-8

{
  "WebhookId": 535,
  "Name": "Ullrich-Robel",
  "Events": [
    "recusandae",
    "aut"
  ],
  "TargetUrl": "http://www.example.com/",
  "Secret": "voluptas",
  "State": "Active",
  "Type": "qui",
  "Headers": {
    "Headers1": "laborum",
    "Headers2": "dolor"
  },
  "Properties": {
    "fieldName": {}
  },
  "Registered": "2016-12-06T10:30:32.8113095+01:00",
  "RegisteredAssociate": null,
  "Updated": "2005-08-28T10:30:32.8113095+02:00",
  "UpdatedAssociate": null,
  "ErrorsEmail": "irma_denesik@greenweimann.uk"
}
```

## Sample response

```http_
HTTP/1.1 200 Webhook updated.
Content-Type: application/json; charset=utf-8

{
  "WebhookId": 96,
  "Name": "Crona LLC",
  "Events": [
    "perferendis",
    "accusamus"
  ],
  "TargetUrl": "http://www.example.com/",
  "Secret": "eum",
  "State": "Active",
  "Type": "aut",
  "Headers": {
    "Headers1": "maxime",
    "Headers2": "nisi"
  },
  "Properties": {
    "fieldName": {}
  },
  "Registered": "2007-07-23T10:30:32.8113095+02:00",
  "RegisteredAssociate": null,
  "Updated": "2008-05-12T10:30:32.8113095+02:00",
  "UpdatedAssociate": null,
  "ErrorsEmail": "arnulfo_collins@jewesskshlerin.com",
  "_Links": {
    "Self": "https://www.example.com/api/v1/project/321",
    "Archive": "https://www.example.com/api/v1/project"
  }
}
```