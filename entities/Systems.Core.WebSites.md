---
uid: Systems.Core.WebSites
---
# Systems.Core.WebSites Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains the web sites, which are hosted for the database. Entity: Sys_Web_Sites (Introduced in version 19.1)
## Renamed
**New name:** [Systems.Config.WebSites](Systems.Config.WebSites.md)  



## Default Visualization
Default Display Text Format:  
_{RelativeUrl}: {WebSiteType}_  
Default Search Members:  
__  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.WebSites](Systems.Core.WebSites.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Core.WebSites.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Core.WebSites.md#id) | guid |  
| [IsActive](Systems.Core.WebSites.md#isactive) | boolean | Indicates whether the web site is active and will be instantiated upon next web server restart. `Required` `Default(true)` `Filter(eq)` 
| [IsPrivate](Systems.Core.WebSites.md#isprivate) | boolean | Specifies that the web site address will not be publicly listed. The web site itself will still be publicly accessible; only its URL would not be listed in the auto-discovery service. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.0.8` 
| [Notes](Systems.Core.WebSites.md#notes) | string (max) __nullable__ | Notes for this WebSite. 
| [ObjectVersion](Systems.Core.WebSites.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RelativeUrl](Systems.Core.WebSites.md#relativeurl) | string (254) __nullable__ | The relative Url of the site. This is the text after the first slash after the protocol and host name. The text should not include the protocol and host name. null means that the site will be hosted as the root site in the speicified web host. 
| [SettingsJson](Systems.Core.WebSites.md#settingsjson) | string (max) __nullable__ | The field specifies the JSON settings for this website. null means that there are no specific settings for this website. `Introduced in version 23.1.0.37` 
| [WebSiteType](Systems.Core.WebSites.md#websitetype) | [WebSiteType](Systems.Core.WebSites.md#websitetype) | The type of web site - Api, Client Center, Id, etc. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Systems.Core.WebSites.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The enterprise company, for which is the site. null means, that the web site should not be enterprise company specific. `Filter(multi eq)` |
| [TrustedApplication](Systems.Core.WebSites.md#trustedapplication) | [TrustedApplications](Systems.Security.TrustedApplications.md) (nullable) | The trusted application related to this web site. `Filter(multi eq)` `Introduced in version 20.1` |
| [WebHost](Systems.Core.WebSites.md#webhost) | [WebHosts](Systems.Core.WebHosts.md) (nullable) | The web host in which to host the site. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

The relative Url of the site. This is the text after the first slash after the protocol and host name. The text should not include the protocol and host name. null means that the site will be hosted as the root site in the speicified web host.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

### WebSiteType

The type of web site - Api, Client Center, Id, etc. `Required` `Filter(multi eq)`

_Type_: **[WebSiteType](Systems.Core.WebSites.md#websitetype)**  
_Category_: **System**  
Allowed values for the `WebSiteType`(Systems.Core.WebSites.md#websitetype) data attribute  
_Allowed Values (Systems.Core.WebSitesRepository.WebSiteType Enum Members)_  

| Value | Description |
| ---- | --- |
| API | Allows external applications to access the ERP resources using REST API.. Stored as 'API'. <br /> _Database Value:_ 'API' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'API' |
| ClientCenter | Allows community users to access ERP resources. Requires working ID site.. Stored as 'CC'. <br /> _Database Value:_ 'CC' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ClientCenter' |
| ECommerce | ECommerce value. Stored as 'EC'. <br /> _Database Value:_ 'EC' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ECommerce' |
| LEGALBG | LEGALBG value. Stored as 'LEG'. <br /> _Database Value:_ 'LEG' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'LEGALBG' |
| SocialInteractions | SocialInteractions value. Stored as 'SI'. <br /> _Database Value:_ 'SI' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'SocialInteractions' |
| DigitalMarketplace | DigitalMarketplace value. Stored as 'DM'. <br /> _Database Value:_ 'DM' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'DigitalMarketplace' |
| WebClientApplication | WebClientApplication value. Stored as 'APP'. <br /> _Database Value:_ 'APP' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'WebClientApplication' |
| TableAPI | TableAPI value. Stored as 'TAP'. <br /> _Database Value:_ 'TAP' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'TableAPI' |
| DataAccessAPI | DataAccessAPI value. Stored as 'DAP'. <br /> _Database Value:_ 'DAP' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'DataAccessAPI' |
| LEGALUK | LEGALUK value. Stored as 'LUK'. <br /> _Database Value:_ 'LUK' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'LEGALUK' |
| OLAP | OLAP value. Stored as 'OLP'. <br /> _Database Value:_ 'OLP' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'OLAP' |
| MicrosoftSync | MicrosoftSync value. Stored as 'MSS'. <br /> _Database Value:_ 'MSS' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'MicrosoftSync' |

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

_Type_: **[WebHosts](Systems.Core.WebHosts.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Core.WebSites erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.WebSites erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_WebSites?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_WebSites?$top=10>

