---
uid: Crm.Pos.ServiceProfiles
---
# Crm.Pos.ServiceProfiles


Defines user-configurable service profiles, such as dine-in, pickup, or a specific delivery platform, that can be selected for POS sales. Each profile belongs to a predefined service kind.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.ServiceProfiles  
Base Table: Pos_Service_Profiles  
Introduced In Version: 27.1.1.75  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.ServiceProfiles](Crm.Pos.ServiceProfiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Crm.Pos.ServiceProfiles.md#code) | string (16) | Unique short code of the service profile. Used for integration settings, display constrained devices, import/export matching, etc.`Required` `Filter(eq;like)` `ORD` |
| [IsActive](Crm.Pos.ServiceProfiles.md#isactive) | boolean | Indicates whether the profile is active and can be selected for new sales. Deactivation does not affect existing sales.`Required` `Default(true)` `Filter(eq)` |
| [Name](Crm.Pos.ServiceProfiles.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the service profile, as shown to the operator in POS, for example Dine-in or Glovo delivery.`Required` `Filter(eq;like)` |
| [Notes](Crm.Pos.ServiceProfiles.md#notes) | string (max) __nullable__ | Notes for the service profile.`Filter(like)` |
| [Ord](Crm.Pos.ServiceProfiles.md#ord) | int32 | The display order of the profile in POS.`Required` `Filter(eq;ge;le)` `ORD` |
| [ServiceKind](Crm.Pos.ServiceProfiles.md#servicekind) | [ServiceKind](Crm.Pos.ServiceProfiles.md#servicekind) | The predefined kind of service associated with the profile.`Required` `Default(&quot;DIN&quot;)` `Filter(multi eq)` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Crm.Pos.ServiceProfiles.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When specified, the profile applies only to the specified enterprise company. NULL means there is no enterprise company restriction. Location and location group restrictions also apply. |
| [Location](Crm.Pos.ServiceProfiles.md#location) | [Locations](Crm.Pos.Locations.md) (nullable) | When specified, the profile applies only to the specified POS location. NULL means there is no individual location restriction. Enterprise company and location group restrictions also apply. |
| [LocationGroup](Crm.Pos.ServiceProfiles.md#locationgroup) | [LocationGroups](Crm.Pos.LocationGroups.md) (nullable) | When specified, the profile applies only to POS locations belonging to the specified location group. NULL means there is no location group restriction. Enterprise company and individual location restrictions also apply. When Location is specified, it must belong to this group. |
| [Partner](Crm.Pos.ServiceProfiles.md#partner) | [Parties](General.Contacts.Parties.md) (nullable) | The external partner, such as a delivery platform or aggregator, through which sales with this profile are received. NULL when the sales are received directly. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.ServiceProfiles.md#id) | guid |  |
| [ObjectVersion](Crm.Pos.ServiceProfiles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [ExternalId](Crm.Pos.ServiceProfiles.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] |
| [ExternalSystem](Crm.Pos.ServiceProfiles.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] |
| [AggregateLastUpdateTimeUtc](Crm.Pos.ServiceProfiles.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] |
| [AdditionalDataJson](Crm.Pos.ServiceProfiles.md#additionaldatajson) | string | Extensible JSON object for storing this entity&apos;s custom or optional attributes. Each application or service must store its data in a separate top-level object identified by the owning application, service, or functional domain. Applications must preserve top-level objects owned by other applications or services. Maximum length: 32,000 characters. [Introduced in version 26.3.100.4] |
| [DisplayText](Crm.Pos.ServiceProfiles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### Code

Unique short code of the service profile. Used for integration settings, display constrained devices, import/export matching, etc.`Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the profile is active and can be selected for new sales. Deactivation does not affect existing sales.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Name of the service profile, as shown to the operator in POS, for example Dine-in or Glovo delivery.`Required` `Filter(eq;like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for the service profile.`Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Ord

The display order of the profile in POS.`Required` `Filter(eq;ge;le)` `ORD`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### ServiceKind

The predefined kind of service associated with the profile.`Required` `Default(&quot;DIN&quot;)` `Filter(multi eq)`

Type: **[ServiceKind](Crm.Pos.ServiceProfiles.md#servicekind)**  
Category: **System**  
Allowed values for the `ServiceKind`(Crm.Pos.ServiceProfiles.md#servicekind) data attribute  
Allowed Values (Crm.Pos.ServiceProfilesRepository.ServiceKind Enum Members)  

| Value | Description |
| ---- | --- |
| DineIn | DineIn value. Stored as 'DIN'. <br /> Database Value: 'DIN' <br /> Model Value: 0 <br /> Domain API Value: 'DineIn' |
| Pickup | Pickup value. Stored as 'PCK'. <br /> Database Value: 'PCK' <br /> Model Value: 1 <br /> Domain API Value: 'Pickup' |
| Delivery | Delivery value. Stored as 'DLV'. <br /> Database Value: 'DLV' <br /> Model Value: 2 <br /> Domain API Value: 'Delivery' |
| Other | Other value. Stored as 'OTH'. <br /> Database Value: 'OTH' <br /> Model Value: 3 <br /> Domain API Value: 'Other' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **DineIn**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

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

### AdditionalDataJson

Extensible JSON object for storing this entity&apos;s custom or optional attributes. Each application or service must store its data in a separate top-level object identified by the owning application, service, or functional domain. Applications must preserve top-level objects owned by other applications or services. Maximum length: 32,000 characters. [Introduced in version 26.3.100.4]

Type: **string**  
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

When specified, the profile applies only to the specified enterprise company. NULL means there is no enterprise company restriction. Location and location group restrictions also apply.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Location

When specified, the profile applies only to the specified POS location. NULL means there is no individual location restriction. Enterprise company and location group restrictions also apply.

Type: **[Locations](Crm.Pos.Locations.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LocationGroup

When specified, the profile applies only to POS locations belonging to the specified location group. NULL means there is no location group restriction. Enterprise company and individual location restrictions also apply. When Location is specified, it must belong to this group.

Type: **[LocationGroups](Crm.Pos.LocationGroups.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Partner

The external partner, such as a delivery platform or aggregator, through which sales with this profile are received. NULL when the sales are received directly.

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Crm.Pos.ServiceProfiles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.ServiceProfiles erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_ServiceProfiles

Domain API Entity Type: 
Crm_Pos_ServiceProfile

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_ServiceProfiles?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_ServiceProfiles?$top=10>

