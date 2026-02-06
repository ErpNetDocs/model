---
uid: Systems.Security.AccessKeys
---
# Systems.Security.AccessKeys


An Access key defines a set of access permissions to one or more entities. Access keys can be private, securing only one entity, or shared between more entities (of the same data type). The actual permissions are specified for security groups. Each group can have different specific permissions.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.AccessKeys  
Base Table: Sec_Access_Keys  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  SystemData  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.AccessKeys](Systems.Security.AccessKeys.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Systems.Security.AccessKeys.md#code) | string (16) __nullable__ | Unique code for the access key. The codes can be null for legacy keys or entities that do not support codes. The codes are unique only among non-null entries[Filter(eq;like)] [ORD] 
| [EntityId](Systems.Security.AccessKeys.md#entityid) | guid __nullable__ | The field stores the Id of the entity that the key was created from. `Filter(multi eq)` `Introduced in version 25.1.1.32` 
| [EntityName](Systems.Security.AccessKeys.md#entityname) | string (64) __nullable__ | What entitity the key secures. Can be null for private, legacy keys[Filter(eq;like)] [ORD] 
| [Name](Systems.Security.AccessKeys.md#name) | [MultilanguageString (1024)](../data-types.md#multilanguagestring) __nullable__ | Multilanguage descriptive name of the security key. Can be null for legacy keys[Filter(eq;like)] 
| [ShareLevel](Systems.Security.AccessKeys.md#sharelevel) | [ShareLevel](Systems.Security.AccessKeys.md#sharelevel) | Specifies the extent to which the key can be shared among multiple entities.[Required] [Default(&quot;PRI&quot;)] [Filter(eq)] [Introduced in version 25.1.1.32] 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.AccessKeys.md#id) | guid |  
| [ObjectVersion](Systems.Security.AccessKeys.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Security.AccessKeys.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.AccessKeys.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Security.AccessKeys.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Security.AccessKeys.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

Unique code for the access key. The codes can be null for legacy keys or entities that do not support codes. The codes are unique only among non-null entries[Filter(eq;like)] [ORD]

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Code, o => ( o.EntityName == obj.EntityName), "00000")`

### EntityId

The field stores the Id of the entity that the key was created from. `Filter(multi eq)` `Introduced in version 25.1.1.32`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EntityName

What entitity the key secures. Can be null for private, legacy keys[Filter(eq;like)] [ORD]

Type: **string (64) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Name

Multilanguage descriptive name of the security key. Can be null for legacy keys[Filter(eq;like)]

Type: **[MultilanguageString (1024)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ShareLevel

Specifies the extent to which the key can be shared among multiple entities.[Required] [Default(&quot;PRI&quot;)] [Filter(eq)] [Introduced in version 25.1.1.32]

Type: **[ShareLevel](Systems.Security.AccessKeys.md#sharelevel)**  
Category: **System**  
Allowed values for the `ShareLevel`(Systems.Security.AccessKeys.md#sharelevel) data attribute  
Allowed Values (Systems.Security.AccessKeysRepository.ShareLevel Enum Members)  

| Value | Description |
| ---- | --- |
| Private | The key is private to the entity.. Stored as 'PRI'. <br /> Database Value: 'PRI' <br /> Model Value: 0 <br /> Domain API Value: 'Private' |
| Referenceable | The key can be referenced from other entities.. Stored as 'RFA'. <br /> Database Value: 'RFA' <br /> Model Value: 1 <br /> Domain API Value: 'Referenceable' |
| Referencing | The access permissions of the selected object are applied.. Stored as 'RFI'. <br /> Database Value: 'RFI' <br /> Model Value: 2 <br /> Domain API Value: 'Referencing' |
| Inheriting | The access permissions of the parent object are inherited.. Stored as 'IHI'. <br /> Database Value: 'IHI' <br /> Model Value: 3 <br /> Domain API Value: 'Inheriting' |
| Shared | The key is not specific to any entity.. Stored as 'SHA'. <br /> Database Value: 'SHA' <br /> Model Value: 4 <br /> Domain API Value: 'Shared' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Private**  
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

[!list limit=1000 erp.entity=Systems.Security.AccessKeys erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.AccessKeys erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_AccessKeys

Domain API Entity Type: 
Systems_Security_AccessKey

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_AccessKeys?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_AccessKeys?$top=10>

