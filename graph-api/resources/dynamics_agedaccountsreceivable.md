---
title: agedAccountsReceivable resource type | Microsoft Docs
description: An aged accounts receivable object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: dynamics365-businesscentral
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: solsen
---

# agedAccountsReceivable resource type
Represents an agedAccountsReceivable object in Dynamics 365 Business Central, which is showing the aging of a customer account.

## Methods

| Method         | Return Type  |Description|
|:---------------|:-------------|:----------|
|[GET agedAccountsReceivable](../api/dynamics_agedaccountsreceivable_get.md)|agedAccountsReceivable|Get agedAccountsReceivable object|

## Properties
| Property	     | Type    |Description                                  |
|:---------------|:--------|:--------------------------------------------|
|customerId      |GUID     |The unique ID of customer.                   |
|customerNumber  |string   |Specifies customer's number.                 |
|name            |string   |Specifies customer's name.                   |
|currencyCode    |string   |Specifies the currency.                      |
|balanceDue      |numeric  |Specifies the customer's total balance.      |
|currentAmount   |numeric  |Specifies balance for the current aging period.|
|period1Amount   |numeric  |Specifies balance in the first aging period. |
|period2Amount   |numeric  |Specifies balance in the second aging period.|
|period3Amount   |numeric  |Specifies balance in the third aging period. |
|agedAsOfDate    |date     |Specifies period start date used to calculate aging periods.|
|periodLengthFilter|string |Specifies the length of the periods. Acceptable time units include: D, WD, W, M, Q, and Y. C, meaning current time unit based on date, can be specified as a prefix to the time unit.|


## Relationships
None

## JSON representation

Here is a JSON representation of the resource.


```json
{
    "customerId": "GUID",
    "customerNumber": "string",
    "name": "string",
    "currencyCode": "string",
    "balanceDue": "decimal",
    "currentAmount": "decimal",
    "period1Amount": "decimal",
    "period2Amount": "decimal",
    "period3Amount": "decimal",
    "agedAsOfDate": "date",
    "periodLengthFilter": "string"
}

```
## See also
[Working with Dynamics 365 Business Central in Microsoft Graph](../resources/dynamics_overview.md)  
[Error Codes](../dynamics_error_codes.md)  
[Get Aged Accounts Receivable](../api/dynamics_agedaccountsreceivable_get.md)  
[Aged Accounts Payable](dynamics_agedaccountspayable.md)  
[Account](dynamics_account.md)  
