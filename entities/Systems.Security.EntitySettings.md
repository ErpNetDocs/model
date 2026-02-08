---
uid: Systems.Security.EntitySettings
---
# Systems.Security.EntitySettings


Contains entities, which have secured access.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.EntitySettings  
Base Table: Sys_Entities  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.EntitySettings  
New name: Systems.Security.EntitySettings  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.EntitySettings](Systems.Security.EntitySettings.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayTextFormat](Systems.Security.EntitySettings.md#displaytextformat) | string (128) __nullable__ | Interpolated string, containing the default format for displaying values of the entity. NULL means to use the system-wide default.`Introduced in version 22.1.4.18` 
| [LogCreate](Systems.Security.EntitySettings.md#logcreate) | boolean | Specifies whether to log every insert for this entity.`Required` `Default(false)` `Introduced in version 18.2` 
| [LogDelete](Systems.Security.EntitySettings.md#logdelete) | boolean | Specifies whether to log every delete for this entity.`Required` `Default(false)` `Introduced in version 18.2` 
| [LogReadById](Systems.Security.EntitySettings.md#logreadbyid) | boolean | Specifies whether to log every load by Id for this entity.`Required` `Default(false)` `Introduced in version 18.2` 
| [LogReadMany](Systems.Security.EntitySettings.md#logreadmany) | boolean | Specifies whether to log every load of many records for this entity.`Required` `Default(false)` `Introduced in version 18.2` 
| [LogUpdate](Systems.Security.EntitySettings.md#logupdate) | boolean | Specifies whether to log every update for this entity.`Required` `Default(false)` `Introduced in version 18.2` 
| [Name](Systems.Security.EntitySettings.md#name) | string (64) | The system name of the entity, which is being secured.`Required` `Filter(eq;like)` `ORD` 
| [TrackChangesLevel](Systems.Security.EntitySettings.md#trackchangeslevel) | [TrackChangesLevel](Systems.Security.EntitySettings.md#trackchangeslevel) | The track changes level for the entity`Required` `Default(0)` `Filter(multi eq)` `Introduced in version 19.1` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Security.EntitySettings.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, required to access the secured entity. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.EntitySettings.md#id) | guid |  
| [ObjectVersion](Systems.Security.EntitySettings.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Security.EntitySettings.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.EntitySettings.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Security.EntitySettings.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Security.EntitySettings.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DisplayTextFormat

Interpolated string, containing the default format for displaying values of the entity. NULL means to use the system-wide default.`Introduced in version 22.1.4.18`

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### LogCreate

Specifies whether to log every insert for this entity.`Required` `Default(false)` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LogDelete

Specifies whether to log every delete for this entity.`Required` `Default(false)` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LogReadById

Specifies whether to log every load by Id for this entity.`Required` `Default(false)` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LogReadMany

Specifies whether to log every load of many records for this entity.`Required` `Default(false)` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LogUpdate

Specifies whether to log every update for this entity.`Required` `Default(false)` `Introduced in version 18.2`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

The system name of the entity, which is being secured.`Required` `Filter(eq;like)` `ORD`

Type: **string (64)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### TrackChangesLevel

The track changes level for the entity`Required` `Default(0)` `Filter(multi eq)` `Introduced in version 19.1`

Type: **[TrackChangesLevel](Systems.Security.EntitySettings.md#trackchangeslevel)**  
Category: **System**  
Represents the different levels of tracking changes for a specific entity.  
Allowed Values (Core.TrackChangesLevel Enum Members)  

| Value | Description |
| ---- | --- |
| DoNotTrackChanges | The do not track changes for this entity. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'DoNotTrackChanges' |
| TrackLastChangesOnly | The track last changes only: creation time, creation user, last update time, last update user. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'TrackLastChangesOnly' |
| TrackObjectChanges | Only object changes are tracked. The changed attributes are not tracked. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'TrackObjectChanges' |
| TrackObjectAnd<br />AttributeChanges | Object and attribute changes are tracked excluding BLOB attributes. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'TrackObjectAnd<br />AttributeChanges' |
| TrackObjectAttribute<br />AndBlobChanges | Object and attribute changes are tracked including BLOB attributes. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'TrackObjectAttribute<br />AndBlobChanges' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **0**  
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

### AccessKey

The access key, required to access the secured entity.

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
| Open a form | Permission1 |
| Opena a navigator | Permission2 |

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

[!list limit=1000 erp.entity=Systems.Security.EntitySettings erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.EntitySettings erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_EntitySettings

Domain API Entity Type: 
Systems_Security_EntitySetting

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_EntitySettings?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_EntitySettings?$top=10>

