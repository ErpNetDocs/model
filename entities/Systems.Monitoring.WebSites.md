---
uid: Systems.Monitoring.WebSites
---
# Systems.Monitoring.WebSites (View)


Web sites dynamic management view

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.WebSites  
Introduced In Version: 23.1.1.43  
API access:  ReadWrite  

## Renames

Old name: Systems.Dmv.WebSites  
New name: Systems.Monitoring.WebSites  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {RootUrl}: {Type}  
Search Members:   
Category:  DynamicViews  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.WebSites](Systems.Monitoring.WebSites.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsSystemSite](Systems.Monitoring.WebSites.md#issystemsite) | boolean | Indicates whether this website is a system website[Required] [Introduced in version 24.1.0.3] 
| [RootUrl](Systems.Monitoring.WebSites.md#rooturl) | string (256) | The root URL of the web site.[Required] [Filter(eq;like)] [ORD] 
| [Status](Systems.Monitoring.WebSites.md#status) | string (10) | The current status of the web site.[Required] [Filter(like)] [ORD] 
| [Type](Systems.Monitoring.WebSites.md#type) | string (64) | The site type.[Required] [Filter(eq;like)] [ORD] 


## Attribute Details

### IsSystemSite

Indicates whether this website is a system website[Required] [Introduced in version 24.1.0.3]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### RootUrl

The root URL of the web site.[Required] [Filter(eq;like)] [ORD]

Type: **string (256)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### Status

The current status of the web site.[Required] [Filter(like)] [ORD]

Type: **string (10)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **True**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### Type

The site type.[Required] [Filter(eq;like)] [ORD]

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### Start

Start web site  
Return Type: **void**  
Declaring Type: **[WebSites](Systems.Monitoring.WebSites.md)**  
Domain API Request: **POST**  

### Stop

Stop web site  
Return Type: **void**  
Declaring Type: **[WebSites](Systems.Monitoring.WebSites.md)**  
Domain API Request: **POST**  

### Restart

Restart web site  
Return Type: **void**  
Declaring Type: **[WebSites](Systems.Monitoring.WebSites.md)**  
Domain API Request: **POST**  

## API

Domain API Entity Set: 
Systems_Monitoring_WebSites

Domain API Entity Type: 
Systems_Monitoring_WebSitesEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_WebSites?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_WebSites?$top=10>

