---
title: "Linking to the Microsoft Dynamics NAV Universal App"
ms.custom: na
ms.date: 19/04/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: d5d0499a-2770-4c7f-bbc8-ad2795656686
caps.latest.revision: 17
---
# Linking to the Microsoft Dynamics NAV Universal App
The protocol handler for the [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] lets you construct a URL for starting the [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] on a device. You can then distribute this URL by e-mail or from a Web page to the users.  

The [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] URL is based on the *ms-dynamicsnav* URI scheme, which is registered automatically when the app is installed. Invoking a URL based on this scheme will start the app with the provided parameters.   

> [!IMPORTANT]  
>  The *ms-dynamicsnav* scheme only translates to a secure server connection. Therefore the [!INCLUDE[nav_tablet](includes/nav_tablet_md.md)] and [!INCLUDE[nav_phone](includes/nav_phone_md.md)] must be exposed through an https connection. For more information, see [How to: Configure SSL to Secure the Connection to Microsoft Dynamics NAV Web Client](How-to--Configure-SSL-to-Secure-the-Connection-to-Microsoft-Dynamics-NAV-Web-Client.md).  
  
## Constructing the URL  
To construct a URL, start with `ms-dynamicsnav` scheme that points to your [!INCLUDE[nav_web_sever_instance_md](includes/nav_web_server_instance_md.md)], and then add additional parameters as needed.

The structure of a [!INCLUDE[nav_uni_app](includes/nav_uni_app_md.md)] link is very similar to links for the [!INCLUDE[nav_web](includes/nav_web_md.md)], and has the following syntax:  

```
ms-dynamicsnav://<hostname>[:<port>][/<instance>]/[?<parameter>=<value>[&<parameter>=<value>]]
```

`[]` indicates optional parameters; all other parameters are required.

`<>` indicates values that you must supply. Do not include the brackets in the address.


## Parameters
The following table describes the parameters for the main part of the URL, which are the parameters up to and including `[/<instance>]/`.

|Parameter|Description| Example |
|---------|-----------|---------|  
|hostname|The computer name, domain name, or IP address of the computer/server that hosts the [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance.| `ms-dynamicsnav://mywebservercomputer/`<br /><br />`ms-dynamicsnav://www.cronus.com/`<br /><br />`ms-dynamicsnav://192.168.0.254/`| 
|port|The port number for your [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance. If not provided, the standard SSL port \(443\) is used.| `ms-dynamicsnav://mywebservercomputer:80/`<br /><br />`ms-dynamicsnav://www.cronus.com:80/`<br /><br />`ms-dynamicsnav://192.168.0.254:80/` |
|instance|The [!INCLUDE[nav_web_server_instance_md](includes/nav_web_server_instance_md.md)] instance that you want to connect to.| `ms-dynamicsnav://mywebservercomputer:80/dynamicsnav110/`<br /><br />`ms-dynamicsnav://www.cronus.com:80/dynamicsnav110/`<br /><br />`ms-dynamicsnav://192.168.0.254:80/dynamicsnav110/`|

The following table describes the optional parameters that you can specify after `[/<instance>]/`. These parameters are referred to as the *query parameters*. The query parameters can be in any order. However, the first parameter must be preceded by the `?` symbol, and any additional parameters must be preceded by the `&` symbol, like `ms-dynamicsnav://mywebservercomputer/?page=21&mode=create`.

|Parameter|Description| Example |
|---------|-----------|---------|  
|page	|The ID of the page that you want to open directly.|`ms-dynamicsnav://mywebservercomputer:80/dynamicsnav110/?page=21`<br /><br />`ms-dynamicsnav://www.cronus.com/?page=21`|
|mode|Whether the page opens in view, edit, or create mode. `view` only lets you see the data on the page, not modify data. `edit` lets you to modify data on the page. `create` lets you to modify data on the page and add new entities. |`ms-dynamicsnav://mywebservercomputer/?page=21&mode=create`|
|profile|The name of the profile that you want to use in the client. This determines the Role Center that is opened. If not provided, the default profile is used. Business Manager	|`ms-dynamicsnav://mywebservercomputer/?profile=BUSINESS%20%MANAGER`|
|company|The company that you want to open in the client. If not provided, the default company is used. CRONUS%20International%20Ltd.|`ms-dynamicsnav://mywebservercomputer/?'company=CRONUS%20International%20Ltd.'`|
|tenant	|The ID of the tenant that you want to connect to. If not provided, the default tenant is used.|`ms-dynamicsnav://mywebservercomputer/?tenant=mytenant2-1`|
|filter	|The filter you want to apply to the page.<br /><br />The filter parameter enables you to display only records from the underlying table of the page that have specific values for one or more fields.	For more information about filters, see [Filtering Data on the Page](Opening-a-Page-in-the-Microsoft-Dynamics-NAV-Web-Client-by-Using-a-URL.md#Filtering).|`ms-dynamicsnav://mywebservercomputer/?page9305&filter='No.'%20IS%20'1001'`<br /><br />`ms-dynamicsnav://mywebservercomputer/?page9305&filter='Sell-to-Customer-No.'-IS-'10000'-AND-'Location-Code'-IS-'BLUE'`|
|bookmark|	The bookmark of the record you want to open. The value of a bookmark is an alphanumeric string of characters, for example, `19%3bGwAAAAJ7BDEAMAAwADA%3d`.<br /><br /> For the page types Card, CardPart, and Document, the bookmark specifies the record that is shown in the page. For page types List, ListPart, and Worksheet, the bookmark specifies the record that is selected in the list on the page.<br /><br /> **Important:**  Bookmarks are generated automatically. You can only determine a value for the bookmark by displaying the page in the client and looking at its address. Therefore, a bookmark is only relevant when the address you are working with has been copied from another instance of the page.|`ms-dynamicsnav://mywebservercomputer/?bookmark=19%3bGwAAAAJ7BDEAMAAwADA%3d`|
  
> [!NOTE]  
>  It is not possible to specify which client type to open up the URL in; the last used client will open up when clicking the URL.  The URL `ms-dynamicsnav:///?page=21` will open the server that you last connected to on the specified page. 

## Adding Username to the URL  
 The *ms-dynamicsnav* scheme also supports sending the user name in the URL for prefilling the user name. The password must be entered by the user. To send the user name, you must URL encode the value and prefix the server address by using *\<encoded username>@*. Examples are as follows:  
  
`ms-dynamicsnav://demouser%40mycompany.com@mywebservercomputer/myinstance/`  
  
`ms-dynamicsnav://user1:@mymywebservercomputer/myinstance/`  
  
> [!IMPORTANT]  
>  We recommend that you do not share a user name in the URL. This technique should only be used in demonstration scenarios and other instances where the accidental sharing of a URL will not compromise the system.  
  
## See Also  
[Developing for the Microsoft Dynamics NAV Universal App](Developing-for-the-Microsoft-Dynamics-NAV-Universal-App.md)   
[How to: Open the Microsoft Dynamics NAV Tablet or Phone Client from a Browser](How-to--Open-the-Microsoft-Dynamics-NAV-Tablet-or-Phone-Client-from-a-Browser.md)