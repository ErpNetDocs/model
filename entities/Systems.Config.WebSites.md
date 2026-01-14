---
uid: Systems.Config.WebSites
---
# Systems.Config.WebSites Entity

**Namespace:** [Systems.Config](Systems.Config.md)  

Contains the web sites, which are hosted for the database. Entity: Sys_Web_Sites (Introduced in version 19.1)

## Renames

Old name: **Systems.Core.WebSites**  
New name: **Systems.Config.WebSites**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{RelativeUrl}: {WebSiteType}_  
Default Search Members:  
__  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _3 - Track object and attribute changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Config.WebSites](Systems.Config.WebSites.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Systems.Config.WebSites.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Config.WebSites.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Systems.Config.WebSites.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Config.WebSites.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Config.WebSites.md#id) | guid |  
| [IsActive](Systems.Config.WebSites.md#isactive) | boolean | Indicates whether the web site is active and will be instantiated upon next web server restart. `Required` `Default(true)` `Filter(eq)` 
| [IsPrivate](Systems.Config.WebSites.md#isprivate) | boolean | Specifies that the web site address will not be publicly listed. The web site itself will still be publicly accessible; only its URL would not be listed in the auto-discovery service. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.0.8` 
| [Notes](Systems.Config.WebSites.md#notes) | string (max) __nullable__ | Notes for this WebSite. 
| [ObjectVersion](Systems.Config.WebSites.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RelativeUrl](Systems.Config.WebSites.md#relativeurl) | string (254) __nullable__ | The relative Url of the site. This is the text after the first slash after the protocol and host name. The text should not include the protocol and host name. null means that the site will be hosted as the root site in the speicified web host. `Filter(eq)` 
| [SettingsJson](Systems.Config.WebSites.md#settingsjson) | string (max) __nullable__ | The field specifies the JSON settings for this website. null means that there are no specific settings for this website. `Introduced in version 23.1.0.37` 
| [Uin](Systems.Config.WebSites.md#uin) | string (64) __nullable__ | For multi-instance databases, specifies the instance on which to start the web site. The instance is specified by its UIN (Unique Instance Name). When null (which is the default and suggested value), the site will be started on the primary instance. . `Introduced in version 24.1.5.42` 
| [WebSiteType](Systems.Config.WebSites.md#websitetype) | [WebSiteType](Systems.Config.WebSites.md#websitetype) | The type of web site - Api, Client Center, Id, etc. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Systems.Config.WebSites.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company, for which is the site. null means, that the web site should not be enterprise company specific. `Filter(multi eq)` |
| [TrustedApplication](Systems.Config.WebSites.md#trustedapplication) | [TrustedApplications](Systems.Security.TrustedApplications.md) (nullable) | The trusted application related to this web site. `Filter(multi eq)` `Introduced in version 20.1` |
| [WebHost](Systems.Config.WebSites.md#webhost) | [WebHosts](Systems.Config.WebHosts.md) (nullable) | The web host in which to host the site. `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the web site is active and will be instantiated upon next web server restart. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### IsPrivate

Specifies that the web site address will not be publicly listed. The web site itself will still be publicly accessible; only its URL would not be listed in the auto-discovery service. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.0.8`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this WebSite.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### RelativeUrl

The relative Url of the site. This is the text after the first slash after the protocol and host name. The text should not include the protocol and host name. null means that the site will be hosted as the root site in the speicified web host. `Filter(eq)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### SettingsJson

The field specifies the JSON settings for this website. null means that there are no specific settings for this website. `Introduced in version 23.1.0.37`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### Uin

For multi-instance databases, specifies the instance on which to start the web site. The instance is specified by its UIN (Unique Instance Name). When null (which is the default and suggested value), the site will be started on the primary instance. . `Introduced in version 24.1.5.42`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### WebSiteType

The type of web site - Api, Client Center, Id, etc. `Required` `Filter(multi eq)`

_Type_: **[WebSiteType](Systems.Config.WebSites.md#websitetype)**  
_Category_: **System**  
Allowed values for the `WebSiteType`(Systems.Config.WebSites.md#websitetype) data attribute  
_Allowed Values (Systems.Config.WebSitesRepository.WebSiteType Enum Members)_  

| Value | Description |
| ---- | --- |
| DomainAPI | DomainAPI value. Stored as 'API'. <br /> _Database Value:_ 'API' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'DomainAPI' |
| ClientCenter | Allows community users to access ERP resources. Requires working ID site.. Stored as 'CC'. <br /> _Database Value:_ 'CC' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ClientCenter' |
| ECommerce | ECommerce value. Stored as 'EC'. <br /> _Database Value:_ 'EC' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ECommerce' |
| LegalBG | LegalBG value. Stored as 'LEG'. <br /> _Database Value:_ 'LEG' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'LegalBG' |
| SocialInteractions | SocialInteractions value. Stored as 'SI'. <br /> _Database Value:_ 'SI' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'SocialInteractions' |
| DigitalMarketplace | DigitalMarketplace value. Stored as 'DM'. <br /> _Database Value:_ 'DM' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'DigitalMarketplace' |
| WebClient | WebClient value. Stored as 'APP'. <br /> _Database Value:_ 'APP' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'WebClient' |
| TableAPI | TableAPI value. Stored as 'TAP'. <br /> _Database Value:_ 'TAP' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'TableAPI' |
| DataAccessAPI | DataAccessAPI value. Stored as 'DAP'. <br /> _Database Value:_ 'DAP' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'DataAccessAPI' |
| LegalUK | LegalUK value. Stored as 'LUK'. <br /> _Database Value:_ 'LUK' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'LegalUK' |
| OLAP | OLAP value. Stored as 'OLP'. <br /> _Database Value:_ 'OLP' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'OLAP' |
| MicrosoftSync | MicrosoftSync value. Stored as 'MSS'. <br /> _Database Value:_ 'MSS' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'MicrosoftSync' |
| VideoConferencing | VideoConferencing value. Stored as 'VDC'. <br /> _Database Value:_ 'VDC' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'VideoConferencing' |
| AIServer | AIServer value. Stored as 'AIS'. <br /> _Database Value:_ 'AIS' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'AIServer' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company, for which is the site. null means, that the web site should not be enterprise company specific. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### TrustedApplication

The trusted application related to this web site. `Filter(multi eq)` `Introduced in version 20.1`

_Type_: **[TrustedApplications](Systems.Security.TrustedApplications.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WebHost

The web host in which to host the site. `Filter(multi eq)`

_Type_: **[WebHosts](Systems.Config.WebHosts.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


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

