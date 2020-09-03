---
title: taxArea resource type | Microsoft Docs
description: A tax area.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# taxArea resource type
Represents a tax area resource type in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[GET taxArea](../api/dynamics_taxarea_get.md)|taxArea|Gets a tax area object.|
|[POST taxArea](../api/dynamics_create_taxarea.md)|taxArea|Creates a tax area object.|
|[PATCH taxArea](../api/dynamics_taxarea_update.md)|taxArea|Updates a tax area object.|
|[DELETE taxArea](../api/dynamics_taxarea_delete.md)|none|Deletes a tax area object.|

## Properties

| Property     | Type   |Description|
|:---------------|:--------|:----------|
|id|GUID|The unique ID of the tax area. Non-editable.|
|code|string, maximum size 20| The code of the tax area.|
|displayName|string, maximum size 50| The display name of the tax area.|
|lastModifiedDateTime|datetime|The last datetime the tax area was modified. Read-Only.|

## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "code": "string",
   "displayName": "string",
   "taxType": "NAV.taxBufferType",
   "lastModifiedDateTime": "datetime"
}
```

## See also

[Get Tax Area](../api/dynamics_taxarea_get.md)  
[Create Tax Area](../api/dynamics_create_taxarea.md)  
[Update Tax Area](../api/dynamics_taxarea_update.md)  
[Delete Tax Area](../api/dynamics_taxarea_delete.md)  