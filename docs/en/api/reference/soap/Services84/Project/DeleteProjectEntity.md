---
title: Services84.ProjectAgent.DeleteProjectEntity SOAP
generated: 1
uid: Services84-Project-DeleteProjectEntity
---

# Services84 Project DeleteProjectEntity

SOAP request and response examples **Remote/Services84/Project.svc**
Implemented by the <see cref="M:SuperOffice.Services84.IProjectAgent.DeleteProjectEntity">SuperOffice.Services84.IProjectAgent.DeleteProjectEntity</see> method.

## DeleteProjectEntity





[WSDL file for Services84/Project](../Services84-Project.md)

Obtain a ticket from the [Services84/SoPrincipal.svc](../SoPrincipal/index.md)

Application tokens must be specified if calling an Online installation. ApplicationTokens are not checked for on-site installations.

## DeleteProjectEntity Request

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices842="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services84">
  <Project:ApplicationToken>1234567-1234-9876</Project:ApplicationToken>
  <Project:Credentials>
    <Project:Ticket>7T:1234abcxyzExample==</Project:Ticket>
  </Project:Credentials>
 <SOAP-ENV:Body>
   <Project:DeleteProjectEntity>
    <Project:ProjectEntityId xsi:type="xsd:int">0</Project:ProjectEntityId>
   </Project:DeleteProjectEntity>

 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```


## DeleteProjectEntity Response

```xml
<?xml version="1.0" encoding="UTF-8"?>
<SOAP-ENV:Envelope
 xmlns:SOAP-ENV="http://www.w3.org/2003/05/soap-envelope"
 xmlns:SOAP-ENC="http://www.w3.org/2003/05/soap-encoding"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
 xmlns:NetServerServices842="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
 xmlns:NetServerServices841="http://schemas.microsoft.com/2003/10/Serialization/"
 xmlns:Project="http://www.superoffice.net/ws/crm/NetServer/Services84">
 <SOAP-ENV:Body>
  <Project:DeleteProjectEntityResponse>
  </Project:DeleteProjectEntityResponse>
 </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```

