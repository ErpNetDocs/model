---
uid: Systems.Security.DomainProviders
---
# Systems.Security.DomainProviders


The external authentication providers, linked to the domain. Contains data about registration, usually the app id or app key.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.DomainProviders  
Base Table: Sec_Domain_Providers  
Introduced In Version: 20.1  
API access:  ReadWrite  

## Visualization
Display Format: {DisplayName:T}  
Search Members: DisplayName  
Name Member: DisplayName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.Domains](Systems.Security.Domains.md)  
Aggregate Root:  
[Systems.Security.Domains](Systems.Security.Domains.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ClientID](Systems.Security.DomainProviders.md#clientid) | string (254) __nullable__ | This is the Client_ID of our registration within the provider. 
| [ClientSecret](Systems.Security.DomainProviders.md#clientsecret) | string (254) __nullable__ | This is the password, which we, as a client app, use to access the authentication provider. 
| [DisplayName](Systems.Security.DomainProviders.md#displayname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Specifies the (multi-language) display name of the button in the login form. Especially useful for multi-tenant providers. 
| [IsActive](Systems.Security.DomainProviders.md#isactive) | boolean | Specifies whether the provider is currently active for the domain.`Required` `Default(true)` `Filter(eq)` 
| [Notes](Systems.Security.DomainProviders.md#notes) | string (max) __nullable__ | Notes for this DomainProvider. 
| [ProviderName](Systems.Security.DomainProviders.md#providername) | [ProviderName](Systems.Security.DomainProviders.md#providername) | The system name of the user authentication provider. For example GOOGLE, FACEBOOK, MICROSOFT, AZUREAD, ERPNET, etc.`Required` `Filter(eq)` 
| [TenantID](Systems.Security.DomainProviders.md#tenantid) | string (254) __nullable__ | When the authentication provider is multi-tenant, this specifies the tenant ID. For example, Google, Facebook and Microsoft are singe-tenant, while AzureAD is multi-tenant. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Domain](Systems.Security.DomainProviders.md#domain) | [Domains](Systems.Security.Domains.md) | The domain for which the provider is setup. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.DomainProviders.md#id) | guid |  
| [ObjectVersion](Systems.Security.DomainProviders.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Security.DomainProviders.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ClientID

This is the Client_ID of our registration within the provider.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ClientSecret

This is the password, which we, as a client app, use to access the authentication provider.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### DisplayName

Specifies the (multi-language) display name of the button in the login form. Especially useful for multi-tenant providers.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the provider is currently active for the domain.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this DomainProvider.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ProviderName

The system name of the user authentication provider. For example GOOGLE, FACEBOOK, MICROSOFT, AZUREAD, ERPNET, etc.`Required` `Filter(eq)`

Type: **[ProviderName](Systems.Security.DomainProviders.md#providername)**  
Category: **System**  
Allowed values for the `ProviderName`(Systems.Security.DomainProviders.md#providername) data attribute  
Allowed Values (Systems.Security.DomainProvidersRepository.ProviderName Enum Members)  

| Value | Description |
| ---- | --- |
| ERPNET | ERPNET value. Stored as 'ERPNET'. <br /> Database Value: 'ERPNET' <br /> Model Value: 0 <br /> Domain API Value: 'ERPNET' |
| AZUREAD | AZUREAD value. Stored as 'AZUREAD'. <br /> Database Value: 'AZUREAD' <br /> Model Value: 1 <br /> Domain API Value: 'AZUREAD' |
| GOOGLE | GOOGLE value. Stored as 'GOOGLE'. <br /> Database Value: 'GOOGLE' <br /> Model Value: 2 <br /> Domain API Value: 'GOOGLE' |
| FACEBOOK | FACEBOOK value. Stored as 'FACEBOOK'. <br /> Database Value: 'FACEBOOK' <br /> Model Value: 3 <br /> Domain API Value: 'FACEBOOK' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TenantID

When the authentication provider is multi-tenant, this specifies the tenant ID. For example, Google, Facebook and Microsoft are singe-tenant, while AzureAD is multi-tenant.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Domain

The domain for which the provider is setup.

Type: **[Domains](Systems.Security.Domains.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Systems.Security.DomainProviders erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.DomainProviders erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_DomainProviders

Domain API Entity Type: 
Systems_Security_DomainProvider

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_DomainProviders?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_DomainProviders?$top=10>

