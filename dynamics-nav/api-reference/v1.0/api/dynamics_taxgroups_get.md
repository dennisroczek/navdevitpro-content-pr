---
title: Get taxGroups | Microsoft Docs
description: Gets a tax groups method in Dynamics 365 Business Central. 
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/01/2019
ms.author: solsen
---

# Get taxGroups
Retrieve the properties and relationships of a tax groups object for [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request

```
GET /businesscentral/companies({id})/taxGroups({id})
```

## Request headers

|Header|Value|
|------|-----|
|Authorization  |Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a ```200 OK``` response code and a **taxGroups** object in the response body.

## Example

**Request**

Here is an example of the request.
```json
GET https://api.businesscentral.dynamics.com/v1.0/api/v1.0/companies({id})/taxGroups({id})
```

**Response**

Here is an example of the response. 

> [!NOTE]  
>   The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
  "id": "id-value",
  "code": "FURNITURE",
  "displayName": "Taxable Olympic Furniture",
  "lastModifiedDateTime": "2017-03-15T02:20:57.09Z"
}
```


## See Also

[Tax Groups](../resources/dynamics_taxgroups.md)  
[Create Tax groups](../api/dynamics_create_taxgroups.md)  
[Update Tax Groups](../api/dynamics_taxgroups_update.md)  
[Delete Tax Groups](../api/dynamics_taxgroups_delete.md)  