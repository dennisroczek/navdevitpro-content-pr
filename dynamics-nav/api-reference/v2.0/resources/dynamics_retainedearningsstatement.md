---
title: retainedEarningsStatement resource type | Microsoft Docs
description: A retained earnings statement object in Dynamics 365 Business Central.
 
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 8/26/2020
ms.author: solsen
---

# retainedEarningsStatement resource type
Represents an retained earnings statement in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods

| Method       | Return Type  |Description          |
|:-------------|:-------------|:--------------------|
|[GET retainedEarningsStatement](../api/dynamics_retainedearningsstatement_get.md)|retainedEarningsStatement|Get a retained earnings statement object.|

## Properties

| Property  | Type  |Description                                                           |
|:----------|:------|:---------------------------------------------------------------------|
|lineNumber |numeric|The retainedEarningsStatement item line number.                       |
|display    |string |The retainedEarningsStatement item display name.                      |
|netChange  |numeric|The retainedEarningsStatement item Net Change.                        |
|lineType   |string |The retainedEarningsStatement item line type can be: header, detail, total, or spacer.|
|indentation|numeric|The retainedEarningsStatement item indentation used in report layout. |
|dateFilter |date   |The date filter used to calculate the retainedEarningsStatement items.|


## JSON representation

Here is a JSON representation of the resource.


```json
{
   "id": "GUID",
   "lineNumber": "integer",
   "display": "string",
   "netChange": "decimal",
   "lineType": "NAV.invoiceLineAggLineType",
   "indentation": "integer",
   "dateFilter": "date"
}
```
## See also

[Get Retained Earnings Statement](../api/dynamics_retainedearningsstatement_get.md)  