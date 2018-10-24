---
title: Get employee defaultDimensions | Microsoft Docs
description: Gets a employee default dimensions in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen

ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/20/2018
ms.author: solsen
---

# Get employee defaultDimensions
Gets the default dimensions of the employee in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

## HTTP request 
The following example gets the default dimensions of the employee entity in the response body.

```
GET /businesscentral/companies({companyId})/employees({employeeId})/defaultDimensions
```
## Request header
|Header|Value|
|------|-----|
|Authorization|	Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response 

If successful, this method returns a `200 OK` response code and the **default dimensions** in the response body.

## Example 
**Request**

```json
GET https://api.businesscentral.dynamics.com/v1.0/api/beta/companies({companyId})/employees({employeeId})/defaultDimensions
```
**Response**  
Here is an example of the response.

> [!NOTE]  
> The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

```json
{
    "@odata.context":"http://api.businesscentral.dynamics.com/v1.0/api/beta/$metadata#companies(5106c77d-af37-4e2d-bb88-45d87aba1033)/employees(b3fbe87a-61b8-4a6c-85de-0555f1627a67)/defaultDimensions",
    "value":
    [
        {
            "@odata.etag":"W/\"JzQ0OzNPaHFuS0ZQdk5oc3ZkSW9KdzVkdXk2LytjcmNqeHJJOU05SjZ1aFBYVjQ9MTswMDsn\"",
            "parentId":"b3fbe87a-61b8-4a6c-85de-0555f1627a67","dimensionId":"d5fc81ea-8687-4e9d-9c49-7fde28ccdb1a",
            "dimensionCode":"DEPARTMENT",
            "dimensionValueId":"1045a902-070a-4d31-b2b1-b9431e9e5b26",
            "dimensionValueCode":"PROD",
            "postingValidation":"Same Code"
        }
    ]
} 
```

## See Also
[Graph Reference](../api/dynamics_graph_reference.md)  
[Working with [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)] in Microsoft Graph](../resources/dynamics_overview.md)  
[Enabling the APIs for Microsoft Dynamics NAV](../../enabling-apis-for-dynamics-nav.md)  
[Endpoints for the APIs](../../endpoints-apis-for-dynamics.md)  
[Error Codes](../dynamics_error_codes.md)  
[Employees](../resources/dynamics_employee.md)  
[Create employee defaultDimensions](dynamics_employee_create_defaultdimensions.md)  
[Update employee defaultDimensions](dynamics_employee_update_defaultdimensions.md)  
[Delete employee defaultDimensions](dynamics_employee_delete_defaultdimensions.md)  
