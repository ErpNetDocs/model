---
uid: Systems.Config.WebSites
---
# Systems.Config.WebSites


Contains the web sites, which are hosted for the database.

## General
Namespace: [Systems.Config](Systems.Config.md)  
Repository: Systems.Config.WebSites  
Base Table: Sys_Web_Sites  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.WebSites  
New name: Systems.Config.WebSites  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {RelativeUrl}: {WebSiteType}  
Search Members:   
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Config.WebSites](Systems.Config.WebSites.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Systems.Config.WebSites.md#isactive) | boolean | Indicates whether the web site is active and will be instantiated upon next web server restart. 
| [IsPrivate](Systems.Config.WebSites.md#isprivate) | boolean | Specifies that the web site address will not be publicly listed. The web site itself will still be publicly accessible; only its URL would not be listed in the auto-discovery service. 
| [Notes](Systems.Config.WebSites.md#notes) | string (max) __nullable__ | Notes for this WebSite. 
| [RelativeUrl](Systems.Config.WebSites.md#relativeurl) | string (254) __nullable__ | The relative Url of the site. This is the text after the first slash after the protocol and host name. The text should not include the protocol and host name. NULL means that the site will be hosted as the root site in the speicified web host. 
| [SettingsJson](Systems.Config.WebSites.md#settingsjson) | string (max) __nullable__ | The field specifies the JSON settings for this website. NULL means that there are no specific settings for this website. 
| [Uin](Systems.Config.WebSites.md#uin) | string (64) __nullable__ | For multi-instance databases, specifies the instance on which to start the web site. The instance is specified by its UIN (Unique Instance Name). When NULL (which is the default and suggested value), the site will be started on the primary instance.  
| [WebSiteType](Systems.Config.WebSites.md#websitetype) | [WebSiteType](Systems.Config.WebSites.md#websitetype) | The type of web site - Api, Client Center, Id, etc. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Systems.Config.WebSites.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company, for which is the site. NULL means, that the web site should not be enterprise company specific. |
| [TrustedApplication](Systems.Config.WebSites.md#trustedapplication) | [TrustedApplications](Systems.Security.TrustedApplications.md) (nullable) | The trusted application related to this web site |
| [WebHost](Systems.Config.WebSites.md#webhost) | [WebHosts](Systems.Config.WebHosts.md) (nullable) | The web host in which to host the site. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Config.WebSites.md#id) | guid |  
| [ObjectVersion](Systems.Config.WebSites.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Config.WebSites.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Config.WebSites.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Config.WebSites.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Config.WebSites.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### IsActive

Indicates whether the web site is active and will be instantiated upon next web server restart.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### IsPrivate

Specifies that the web site address will not be publicly listed. The web site itself will still be publicly accessible; only its URL would not be listed in the auto-discovery service.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this WebSite.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RelativeUrl

The relative Url of the site. This is the text after the first slash after the protocol and host name. The text should not include the protocol and host name. NULL means that the site will be hosted as the root site in the speicified web host.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### SettingsJson

The field specifies the JSON settings for this website. NULL means that there are no specific settings for this website.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Uin

For multi-instance databases, specifies the instance on which to start the web site. The instance is specified by its UIN (Unique Instance Name). When NULL (which is the default and suggested value), the site will be started on the primary instance.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### WebSiteType

The type of web site - Api, Client Center, Id, etc.

Type: **[WebSiteType](Systems.Config.WebSites.md#websitetype)**  
Category: **System**  
Allowed values for the `WebSiteType`(Systems.Config.WebSites.md#websitetype) data attribute  
Allowed Values (Systems.Config.WebSitesRepository.WebSiteType Enum Members)  

| Value | Description |
| ---- | --- |
| DomainAPI | DomainAPI value. Stored as 'API'. <br /> Database Value: 'API' <br /> Model Value: 0 <br /> Domain API Value: 'DomainAPI' |
| ClientCenter | Allows community users to access ERP resources. Requires working ID site.. Stored as 'CC'. <br /> Database Value: 'CC' <br /> Model Value: 1 <br /> Domain API Value: 'ClientCenter' |
| ECommerce | ECommerce value. Stored as 'EC'. <br /> Database Value: 'EC' <br /> Model Value: 2 <br /> Domain API Value: 'ECommerce' |
| LegalBG | LegalBG value. Stored as 'LEG'. <br /> Database Value: 'LEG' <br /> Model Value: 3 <br /> Domain API Value: 'LegalBG' |
| SocialInteractions | SocialInteractions value. Stored as 'SI'. <br /> Database Value: 'SI' <br /> Model Value: 4 <br /> Domain API Value: 'SocialInteractions' |
| DigitalMarketplace | DigitalMarketplace value. Stored as 'DM'. <br /> Database Value: 'DM' <br /> Model Value: 5 <br /> Domain API Value: 'DigitalMarketplace' |
| WebClient | WebClient value. Stored as 'APP'. <br /> Database Value: 'APP' <br /> Model Value: 6 <br /> Domain API Value: 'WebClient' |
| TableAPI | TableAPI value. Stored as 'TAP'. <br /> Database Value: 'TAP' <br /> Model Value: 7 <br /> Domain API Value: 'TableAPI' |
| DataAccessAPI | DataAccessAPI value. Stored as 'DAP'. <br /> Database Value: 'DAP' <br /> Model Value: 8 <br /> Domain API Value: 'DataAccessAPI' |
| LegalUK | LegalUK value. Stored as 'LUK'. <br /> Database Value: 'LUK' <br /> Model Value: 9 <br /> Domain API Value: 'LegalUK' |
| OLAP | OLAP value. Stored as 'OLP'. <br /> Database Value: 'OLP' <br /> Model Value: 10 <br /> Domain API Value: 'OLAP' |
| MicrosoftSync | MicrosoftSync value. Stored as 'MSS'. <br /> Database Value: 'MSS' <br /> Model Value: 11 <br /> Domain API Value: 'MicrosoftSync' |
| VideoConferencing | VideoConferencing value. Stored as 'VDC'. <br /> Database Value: 'VDC' <br /> Model Value: 12 <br /> Domain API Value: 'VideoConferencing' |
| AIServer | AIServer value. Stored as 'AIS'. <br /> Database Value: 'AIS' <br /> Model Value: 13 <br /> Domain API Value: 'AIServer' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company, for which is the site. NULL means, that the web site should not be enterprise company specific.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TrustedApplication

The trusted application related to this web site

Type: **[TrustedApplications](Systems.Security.TrustedApplications.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WebHost

The web host in which to host the site.

Type: **[WebHosts](Systems.Config.WebHosts.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
Return Type: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    Type: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    Type: string  
     Optional: True  
    Default Value: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **top**  
    The top clause - default is 10  
    Type: int32  
     Optional: True  
    Default Value: 10  

  * **skip**  
    The skip clause - default is 0  
    Type: int32  
     Optional: True  
    Default Value: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
Return Type: **void**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

**Parameters**  
  * **user**  
    The user.  
    Type: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    Type: string  

  * **subject**  
    The notification subject.  
    Type: string  

  * **priority**  
    The notification priority.  
    Type: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
    | Low | Low value. Stored as 2. <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
    | Normal | Normal value. Stored as 3. <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
    | High | High value. Stored as 4. <br /> Model Value: 4 <br /> Domain API Value: 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

     Optional: True  
    Default Value: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Config.WebSites erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Config.WebSites erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Config_WebSites

Domain API Entity Type: 
Systems_Config_WebSite

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Config_WebSites?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Config_WebSites?$top=10>

