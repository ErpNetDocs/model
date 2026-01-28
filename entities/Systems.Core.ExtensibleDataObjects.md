---
uid: Systems.Core.ExtensibleDataObjects
---
# Systems.Core.ExtensibleDataObjects


Extends data in other tables with attached files, custom properties, etc. Each row is an object, bound to exactly one row in the primary table. Each object can be bound to a row in a different primary table, specified in Entity_Type.

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.ExtensibleDataObjects  
Base Table: Sys_Objects  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {EntityType}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)  
  * [Systems.Core.ObjectVersions](Systems.Core.ObjectVersions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Systems.Core.ExtensibleDataObjects.md#creationtimeutc) | datetime __nullable__ | The exact server time (in UTC) when the object represented by this system object was created. null means that it is unknown. `Filter(ge;le)` `ORD` `Introduced in version 19.1` 
| [EntityItemId](Systems.Core.ExtensibleDataObjects.md#entityitemid) | guid | The Id of the primary row to which the object is bound. `Required` `Filter(multi eq)` 
| [EntityType](Systems.Core.ExtensibleDataObjects.md#entitytype) | string (64) | The entity type of the row to which the object is bound. `Required` `Default(" ")` `Filter(eq)` 
| [ExternalId](Systems.Core.ExtensibleDataObjects.md#externalid) | string (254) __nullable__ | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. `Filter(multi eq)` `ORD` `Introduced in version 24.1.0.89` 
| [ExternalSystem](Systems.Core.ExtensibleDataObjects.md#externalsystem) | string (64) __nullable__ | The name of the external system from which the object is imported/synchronized. `Filter(multi eq)` `Introduced in version 24.1.0.89` 
| [IsDeleted](Systems.Core.ExtensibleDataObjects.md#isdeleted) | boolean | Specifies whether the object represented by this system object is deleted. After deletion of the original object, the system object remains in the system, but can be purged later by some cleanup processes. `Required` `Default(false)` `Filter(eq)` `Introduced in version 19.1` 
| [LastUpdateTimeUtc](Systems.Core.ExtensibleDataObjects.md#lastupdatetimeutc) | datetime __nullable__ | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. `Filter(ge;le)` `ORD` `Introduced in version 19.1` 
| [LatestVersion](Systems.Core.ExtensibleDataObjects.md#latestversion) | int32 | The latest saved version of the object. Starts from 1 and increments with 1 for each new version. `Required` `Default(1)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Systems.Core.ExtensibleDataObjects.md#creationuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who created the object represented by this system object . null means that it is unknown. `Filter(multi eq)` `Introduced in version 19.1` |
| [Folder](Systems.Core.ExtensibleDataObjects.md#folder) | [Folders](General.Files.Folders.md) (nullable) | The owner folder of the object. `Filter(multi eq)` `Introduced in version 26.2.0.13` |
| [LastUpdateUser](Systems.Core.ExtensibleDataObjects.md#lastupdateuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who made the last modification of the object represented by this system object . null means that it is unknown. `Filter(multi eq)` `Introduced in version 19.1` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Core.ExtensibleDataObjects.md#id) | guid |  
| [ObjectVersion](Systems.Core.ExtensibleDataObjects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Core.ExtensibleDataObjects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Versions | [ObjectVersions](Systems.Core.ObjectVersions.md) | List of `ObjectVersion`(Systems.Core.ObjectVersions.md) child objects, based on the `Systems.Core.ObjectVersion.Object`(Systems.Core.ObjectVersions.md#object) back reference 


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC) when the object represented by this system object was created. null means that it is unknown. `Filter(ge;le)` `ORD` `Introduced in version 19.1`

Type: **datetime __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### EntityItemId

The Id of the primary row to which the object is bound. `Required` `Filter(multi eq)`

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EntityType

The entity type of the row to which the object is bound. `Required` `Default(" ")` `Filter(eq)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Default Value: ** **  
Show in UI: **ShownByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. `Filter(multi eq)` `ORD` `Introduced in version 24.1.0.89`

Type: **string (254) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. `Filter(multi eq)` `Introduced in version 24.1.0.89`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### IsDeleted

Specifies whether the object represented by this system object is deleted. After deletion of the original object, the system object remains in the system, but can be purged later by some cleanup processes. `Required` `Default(false)` `Filter(eq)` `Introduced in version 19.1`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. `Filter(ge;le)` `ORD` `Introduced in version 19.1`

Type: **datetime __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### LatestVersion

The latest saved version of the object. Starts from 1 and increments with 1 for each new version. `Required` `Default(1)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
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

### CreationUser

The user, who created the object represented by this system object . null means that it is unknown. `Filter(multi eq)` `Introduced in version 19.1`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Folder

The owner folder of the object. `Filter(multi eq)` `Introduced in version 26.2.0.13`

Type: **[Folders](General.Files.Folders.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LastUpdateUser

The user, who made the last modification of the object represented by this system object . null means that it is unknown. `Filter(multi eq)` `Introduced in version 19.1`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### ChangeFolder

Changes the folder of the object to the specified folder.             This method saves immediately the changes.  
Return Type: **void**  
Declaring Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Domain API Request: **POST**  

**Parameters**  
  * **folder**  
      
    Type: [Folders](General.Files.Folders.md)  


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

[!list limit=1000 erp.entity=Systems.Core.ExtensibleDataObjects erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.ExtensibleDataObjects erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Core_ExtensibleDataObjects

Domain API Entity Type: 
Systems_Core_ExtensibleDataObject

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_ExtensibleDataObjects?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_ExtensibleDataObjects?$top=10>

