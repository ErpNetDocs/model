---
uid: Systems.Bpm.CustomEntities
---
# Systems.Bpm.CustomEntities


Stores the instances of user-defined aggregate root entities.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.CustomEntities  
Base Table: Sys_Custom_Entities  
Introduced In Version: 27.1.1.41  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.CustomEntities](Systems.Bpm.CustomEntities.md)  
  * [Systems.Bpm.CustomSubEntities](Systems.Bpm.CustomSubEntities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Systems.Bpm.CustomEntities.md#active) | boolean | Indicates whether the custom entity instance is active and available for use. `Required` `Default(true)` `Filter(eq)` |
| [Code](Systems.Bpm.CustomEntities.md#code) | string (64) __nullable__ | Optional business identifier of the custom entity instance. Unique within the entity type. `Filter(eq;like)` |
| [Name](Systems.Bpm.CustomEntities.md#name) | string (254) __nullable__ | Name of the custom entity instance. `Filter(like)` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EntityType](Systems.Bpm.CustomEntities.md#entitytype) | [CustomEntityTypes](Systems.Bpm.CustomEntityTypes.md) | Reference to the custom entity type. The referenced type must be an aggregate root type. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.CustomEntities.md#id) | guid |  |
| [ObjectVersion](Systems.Bpm.CustomEntities.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [ExternalId](Systems.Bpm.CustomEntities.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] |
| [ExternalSystem](Systems.Bpm.CustomEntities.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] |
| [AggregateLastUpdateTimeUtc](Systems.Bpm.CustomEntities.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] |
| [AdditionalDataJson](Systems.Bpm.CustomEntities.md#additionaldatajson) | string | Extensible JSON object for storing this entity&apos;s custom or optional attributes. Each application or service must store its data in a separate top-level object identified by the owning application, service, or functional domain. Applications must preserve top-level objects owned by other applications or services. Maximum length: 32,000 characters. [Introduced in version 26.3.100.4] |
| [DisplayText](Systems.Bpm.CustomEntities.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| CustomSubEntities | [CustomSubEntities](Systems.Bpm.CustomSubEntities.md) | List of `CustomSubEntity`(Systems.Bpm.CustomSubEntities.md) child objects, based on the `Systems.Bpm.CustomSubEntity.RootEntity`(Systems.Bpm.CustomSubEntities.md#rootentity) back reference 


## Attribute Details

### Active

Indicates whether the custom entity instance is active and available for use. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Code

Optional business identifier of the custom entity instance. Unique within the entity type. `Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Name

Name of the custom entity instance. `Filter(like)`

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
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

### EntityType

Reference to the custom entity type. The referenced type must be an aggregate root type. `Required` `Filter(multi eq)`

Type: **[CustomEntityTypes](Systems.Bpm.CustomEntityTypes.md)**  
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

[!list limit=1000 erp.entity=Systems.Bpm.CustomEntities erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.CustomEntities erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_CustomEntities

Domain API Entity Type: 
Systems_Bpm_CustomEntity

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_CustomEntities?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_CustomEntities?$top=10>

