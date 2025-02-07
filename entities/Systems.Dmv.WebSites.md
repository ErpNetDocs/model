---
uid: Systems.Dmv.WebSites
---
# Systems.Dmv.WebSites View

**Namespace:** [Systems.Dmv](Systems.Dmv.md)  

Web sites dynamic management view. Entity: Dmv_Web_Sites (Introduced in version 23.1.1.43)
## Renamed
**New name:** [Systems.Monitoring.WebSites](Systems.Monitoring.WebSites.md)  



## Default Visualization
Default Display Text Format:  
_{RootUrl}: {Type}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Dmv.WebSites](Systems.Dmv.WebSites.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsSystemSite](Systems.Dmv.WebSites.md#issystemsite) | boolean | Indicates whether this website is a system website. `Required` `Introduced in version 24.1.0.3` 
| [RootUrl](Systems.Dmv.WebSites.md#rooturl) | string (256) | The root URL of the web site. `Required` `Filter(eq;like)` `ORD` 
| [Status](Systems.Dmv.WebSites.md#status) | string (10) | The current status of the web site. `Required` `Filter(like)` `ORD` 
| [Type](Systems.Dmv.WebSites.md#type) | string (64) | The site type. `Required` `Filter(eq;like)` `ORD` 


## Attribute Details

### IsSystemSite

Indicates whether this website is a system website. `Required` `Introduced in version 24.1.0.3`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### RootUrl

The root URL of the web site. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (256)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### Status

The current status of the web site. `Required` `Filter(like)` `ORD`

_Type_: **string (10)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **True**  
_Maximum Length_: **10**  
_Show in UI_: **ShownByDefault**  

### Type

The site type. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### Start

Start web site  
_Return Type_: **void**  
_Declaring Type_: **[WebSites](Systems.Dmv.WebSites.md)**  
_Domain API Request_: **POST**  

### Stop

Stop web site  
_Return Type_: **void**  
_Declaring Type_: **[WebSites](Systems.Dmv.WebSites.md)**  
_Domain API Request_: **POST**  

### Restart

Restart web site  
_Return Type_: **void**  
_Declaring Type_: **[WebSites](Systems.Dmv.WebSites.md)**  
_Domain API Request_: **POST**  

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Dmv_WebSites?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Dmv_WebSites?$top=10>

