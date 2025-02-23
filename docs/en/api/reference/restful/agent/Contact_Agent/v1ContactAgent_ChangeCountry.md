---
title: POST Agents/Contact/ChangeCountry
uid: v1ContactAgent_ChangeCountry
generated: true
---

# POST Agents/Contact/ChangeCountry

```http
POST /api/v1/Agents/Contact/ChangeCountry
```

Change country regenerates the default values and localized information such as phone number and address format







## Query String Parameters

| Parameter Name | Type |  Description |
|----------------|------|--------------|
| $select | string |  Optional comma separated list of properties to include in the result. Other fields are then nulled out to reduce payload size: "Name,department,category". Default = show all fields. |

```http
POST /api/v1/Agents/Contact/ChangeCountry?$select=name,department,category/id
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

ContactEntity, ToCountryId 

| Property Name | Type |  Description |
|----------------|------|--------------|
| ContactEntity | ContactEntity | The Contact Service. The service implements all services working with the Contact object <para /> Carrier object for ContactEntity. Services for the ContactEntity Carrier is available from the <see cref="T:SuperOffice.CRM.Services.IContactAgent">Contact Agent</see>. |
| ToCountryId | Integer |  |

## Response:

OK

| Response | Description |
|----------------|-------------|
| 200 | OK |

### Response body: ContactEntity

| Property Name | Type |  Description |
|----------------|------|--------------|
| ContactId | int32 | Primary key |
| Name | string | Contact name |
| Department | string | Department |
| OrgNr | string | VAT number or similar |
| Number1 | string | Alphanumeric user field |
| Number2 | string | Alphanumeric user field |
| UpdatedDate | date-time | Date last updated  in UTC. |
| CreatedDate | date-time | Date registered  in UTC. |
| Emails | array | The contact's email |
| Interests | array | The contact's available and selected interests.  Use MDO List name "contint" to get list items. |
| Urls | array | The contact's internet adresses |
| Phones | array | The contact's phone numbers |
| Faxes | array | The contact's fax numbers |
| Description | string | Description of the contact. Usually shown as a postit note. |
| UpdatedBy | Associate | The user that last updated the contact |
| CreatedBy | Associate | The user that created the contact |
| Associate | Associate | The user that owns this contact.  Use MDO List name "associate" to get list items. |
| Business | Business | The business that the contact is associated with. The GUI forces the user to enter a business type.  Use MDO List name "business" to get list items. |
| Category | Category | The category that is set on the company. The GUI forces the user to enter a category type  Use MDO List name "category" to get list items. |
| Country | Country | The country this contact is located in. The country a contact is saved with, affects the phone number format, and the address layout.  Use MDO List name "country" to get list items. |
| Persons | array | The persons belonging to the contact. |
| NoMailing | bool | Spam filter. Indicates if this contact should retrieve advertising. |
| Kananame | string | Contact kana name, used in Japanese versions only |
| Xstop | bool | STOP flag |
| ActiveInterests | int32 | The number of active interests. |
| GroupId | int32 | Group id of original owning associate, semantics like appnt.grp_id |
| ActiveStatusMonitorId | int32 | Active status monitor identity with the lowest rank for contact |
| SupportAssociate | Associate | Use MDO List name "associate" to get list items. |
| TicketPriority | TicketPriority | Use MDO List name "ticketpriority" to get list items. |
| CustomerLanguage | CustomerLanguage | customerlanguage |
| Deleted | int32 | If nonzero, then this contact is 'deleted' and should generally not be shown |
| DbiAgentId | int32 | Integration agent (eJournal) |
| DbiLastSyncronized | date-time | Last external syncronization. |
| DbiKey | string | The primary key for the integrated entry in the external datasource. |
| DbiLastModified | date-time | When the entry was last modified. |
| SupportPerson | Person | Carrier object for Person. Services for the Person Carrier is available from the Person Agent. |
| Address | Address | Street and/or Postal address, in both formatted and structured forms. You only need to modify one of the two for the change to be registered.  Carrier object for Address. |
| Source | int32 | How did we get this contact? For future integration needs |
| ActiveErpLinks | int32 | The number of active erp links |
| BounceEmails | array | Email addresses with a positive bounce counter. |
| Domains | array | Web domains for this contact, ordered in array by rank |
| UserDefinedFields | object | Deprecated: Use {SuperOffice.CRM.Services.ContactEntity.CustomFields} instead. Dictionary of user defined field data. The key string is the ProgId of the UdefField, or if the ProgId is empty it is a string of the format "SuperOffice:[UdefFieldIdentity]", e.g. "SuperOffice:1234" |
| ExtraFields | object | Deprecated: Use {SuperOffice.CRM.Services.ContactEntity.CustomFields} instead. Extra fields added to the carrier. This could be data from Plug-ins, the foreign key system, external applications, etc. |
| CustomFields | object | Udef + Extra fields added to the carrier. Extra fields as defined by changes to database schema + user-defined fields as defined by admin. Custom fields combines user defined fields and extra fields into one bucket.  The individual {SuperOffice.CRM.Services.ContactEntity.ExtraFields} and UserDefinedFields properties are deprecated in favor of this combined collection. |
| TableRight | TableRight | The carrier's table right |
| FieldProperties | object | Field property dictionary mapping field names to field access rights. |

## Sample request

```http!
POST /api/v1/Agents/Contact/ChangeCountry
Authorization: Basic dGplMDpUamUw
Accept: application/json; charset=utf-8
Accept-Language: en
Content-Type: application/json; charset=utf-8

{
  "ContactEntity": null,
  "ToCountryId": 268
}
```

## Sample response

```http_
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "ContactId": 668,
  "Name": "Tromp, Quitzon and Shanahan",
  "Department": "",
  "OrgNr": "527494",
  "Number1": "1125953",
  "Number2": "663484",
  "UpdatedDate": "1997-01-06T10:30:23.3511906+01:00",
  "CreatedDate": "2007-10-26T10:30:23.3511906+02:00",
  "Emails": [
    {
      "Value": "omnis",
      "StrippedValue": "ipsum",
      "Description": "Reverse-engineered actuating hardware",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 721
        }
      }
    },
    {
      "Value": "omnis",
      "StrippedValue": "ipsum",
      "Description": "Reverse-engineered actuating hardware",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 721
        }
      }
    }
  ],
  "Interests": [
    {
      "Id": 84,
      "Name": "Lockman, Spencer and O'Conner",
      "ToolTip": "Et nam quis dolor ab rerum.",
      "Deleted": true,
      "Rank": 730,
      "Type": "mollitia",
      "ColorBlock": 730,
      "IconHint": "impedit",
      "Selected": true,
      "LastChanged": "2006-05-31T10:30:23.3511906+02:00",
      "ChildItems": [
        {},
        {}
      ],
      "ExtraInfo": "voluptatibus",
      "StyleHint": "corporis",
      "Hidden": false,
      "FullName": "Ms. Reid Laurianne Walker IV",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 437
        }
      }
    }
  ],
  "Urls": [
    {
      "Value": "repellat",
      "StrippedValue": "veniam",
      "Description": "Realigned clear-thinking focus group",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 429
        }
      }
    },
    {
      "Value": "repellat",
      "StrippedValue": "veniam",
      "Description": "Realigned clear-thinking focus group",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 429
        }
      }
    }
  ],
  "Phones": [
    {
      "Value": "velit",
      "StrippedValue": "voluptate",
      "Description": "Monitored mission-critical contingency",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 768
        }
      }
    },
    {
      "Value": "velit",
      "StrippedValue": "voluptate",
      "Description": "Monitored mission-critical contingency",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 768
        }
      }
    }
  ],
  "Faxes": [
    {
      "Value": "ut",
      "StrippedValue": "esse",
      "Description": "Enterprise-wide value-added implementation",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 323
        }
      }
    },
    {
      "Value": "ut",
      "StrippedValue": "esse",
      "Description": "Enterprise-wide value-added implementation",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.Int32",
          "FieldLength": 323
        }
      }
    }
  ],
  "Description": "Organized modular open architecture",
  "UpdatedBy": null,
  "CreatedBy": null,
  "Associate": null,
  "Business": null,
  "Category": null,
  "Country": null,
  "Persons": [
    {
      "Position": "optio",
      "PersonId": 683,
      "Mrmrs": "omnis",
      "Firstname": "Brionna",
      "Lastname": "Walsh",
      "MiddleName": "Volkman Group",
      "Title": "sit",
      "Description": "Synergized human-resource portal",
      "Email": "jarrett_heller@orn.com",
      "FullName": "Rosetta Feeney III",
      "DirectPhone": "707-258-0226",
      "FormalName": "Hintz-Gibson",
      "CountryId": 450,
      "ContactId": 631,
      "ContactName": "Renner Inc and Sons",
      "Retired": 865,
      "Rank": 970,
      "ActiveInterests": 415,
      "ContactDepartment": "",
      "ContactCountryId": 732,
      "ContactOrgNr": "551089",
      "FaxPhone": "416.655.0077",
      "MobilePhone": "551.544.7903",
      "ContactPhone": "895-033-1810 x1348",
      "AssociateName": "Cassin, Grant and Renner",
      "AssociateId": 853,
      "UsePersonAddress": true,
      "ContactFax": "commodi",
      "Kanafname": "est",
      "Kanalname": "voluptates",
      "Post1": "quia",
      "Post2": "dolorem",
      "Post3": "veniam",
      "EmailName": "daisha.collier@bergnaumherman.com",
      "ContactFullName": "Miss Omer Deanna Stamm",
      "ActiveErpLinks": 270,
      "TicketPriorityId": 169,
      "SupportLanguageId": 561,
      "SupportAssociateId": 129,
      "CategoryName": "VIP Customer",
      "TableRight": null,
      "FieldProperties": {
        "fieldName": {
          "FieldRight": null,
          "FieldType": "System.String",
          "FieldLength": 103
        }
      }
    }
  ],
  "NoMailing": true,
  "Kananame": "consequatur",
  "Xstop": false,
  "ActiveInterests": 158,
  "GroupId": 360,
  "ActiveStatusMonitorId": 264,
  "SupportAssociate": null,
  "TicketPriority": null,
  "CustomerLanguage": null,
  "Deleted": 706,
  "DbiAgentId": 976,
  "DbiLastSyncronized": "2023-05-08T10:30:23.3511906+02:00",
  "DbiKey": "est",
  "DbiLastModified": "2023-04-18T10:30:23.3511906+02:00",
  "SupportPerson": null,
  "Address": null,
  "Source": 37,
  "ActiveErpLinks": 750,
  "BounceEmails": [
    "darron@barton.info",
    "jaqueline@gulgowski.us"
  ],
  "Domains": [
    "est",
    "reiciendis"
  ],
  "UserDefinedFields": {
    "SuperOffice:1": "Jeffrey Abshire",
    "SuperOffice:2": "Jena Keira Bernhard IV"
  },
  "ExtraFields": {
    "ExtraFields1": "veniam",
    "ExtraFields2": "perspiciatis"
  },
  "CustomFields": {
    "CustomFields1": "eligendi",
    "CustomFields2": "omnis"
  },
  "TableRight": null,
  "FieldProperties": {
    "fieldName": {
      "FieldRight": null,
      "FieldType": "System.String",
      "FieldLength": 873
    }
  }
}
```