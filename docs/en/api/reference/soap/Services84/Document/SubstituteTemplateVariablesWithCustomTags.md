---
title: Services84.DocumentAgent.SubstituteTemplateVariablesWithCustomTags SOAP
generated: 1
uid: Services84-Document-SubstituteTemplateVariablesWithCustomTags
---

# Services84 Document SubstituteTemplateVariablesWithCustomTags

SOAP request and response examples **Remote/Services84/Document.svc**
Implemented by the <see cref="M:SuperOffice.Services84.IDocumentAgent.SubstituteTemplateVariablesWithCustomTags">SuperOffice.Services84.IDocumentAgent.SubstituteTemplateVariablesWithCustomTags</see> method.

## SubstituteTemplateVariablesWithCustomTags





[WSDL file for Services84/Document](../Services84-Document.md)

Obtain a ticket from the [Services84/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## SubstituteTemplateVariablesWithCustomTags Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices842="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Document="http://www.superoffice.net/ws/crm/NetServer/Services84">
  <Document:ApplicationToken>1234567-1234-9876</Document:ApplicationToken>
  <Document:Credentials>
    <Document:Ticket>7T:1234abcxyzExample==</Document:Ticket>
  </Document:Credentials>
 <SOAP-ENV:Body>
   <Document:SubstituteTemplateVariablesWithCustomTags>
    <Document:Source xsi:type="xsd:string"></Document:Source>
    <Document:GeneratorEncoding xsi:type="Document:GeneratorEncoding">Text</Document:GeneratorEncoding>
    <Document:CustomTags xsi:type="NetServerServices842:ArrayOfstring">
     <NetServerServices842:string xsi:type="xsd:string"></NetServerServices842:string>
    </Document:CustomTags>
    <Document:CustomValues xsi:type="NetServerServices842:ArrayOfstring">
     <NetServerServices842:string xsi:type="xsd:string"></NetServerServices842:string>
    </Document:CustomValues>
    <Document:ContactId xsi:type="xsd:int">0</Document:ContactId>
    <Document:PersonId xsi:type="xsd:int">0</Document:PersonId>
    <Document:AppointmentId xsi:type="xsd:int">0</Document:AppointmentId>
    <Document:DocumentId xsi:type="xsd:int">0</Document:DocumentId>
    <Document:SaleId xsi:type="xsd:int">0</Document:SaleId>
    <Document:SelectionId xsi:type="xsd:int">0</Document:SelectionId>
    <Document:ProjectId xsi:type="xsd:int">0</Document:ProjectId>
    <Document:CultureName xsi:type="xsd:string"></Document:CultureName>
   </Document:SubstituteTemplateVariablesWithCustomTags>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## SubstituteTemplateVariablesWithCustomTags Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices842="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Document="http://www.superoffice.net/ws/crm/NetServer/Services84">
 <SOAP-ENV:Body>
  <Document:SubstituteTemplateVariablesWithCustomTagsResponse>
   <Document:Response xsi:type="xsd:string"></Document:Response>
  </Document:SubstituteTemplateVariablesWithCustomTagsResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```

