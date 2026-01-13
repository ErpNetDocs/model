---
uid: Systems.Core.ExtensibleDataObjects
---
# Systems.Core.ExtensibleDataObjects Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Extends data in other tables with attached files, custom properties, etc. Each row is an object, bound to exactly one row in the primary table. Each object can be bound to a row in a different primary table, specified in Entity_Type. Entity: Sys_Objects

## Default Visualization
Default Display Text Format:  
_{Id}: {EntityType}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)  
  * [Systems.Core.ObjectVersions](Systems.Core.ObjectVersions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Systems.Core.ExtensibleDataObjects.md#creationtimeutc) | datetime __nullable__ | The exact server time (in UTC) when the object represented by this system object was created. null means that it is unknown. `Filter(ge;le)` `ORD` `Introduced in version 19.1` 
| [DisplayText](Systems.Core.ExtensibleDataObjects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityItemId](Systems.Core.ExtensibleDataObjects.md#entityitemid) | guid | The Id of the primary row to which the object is bound. `Required` `Filter(multi eq)` 
| [EntityType](Systems.Core.ExtensibleDataObjects.md#entitytype) | string (64) | The entity type of the row to which the object is bound. `Required` `Default(" ")` `Filter(eq)` 
| [ExternalId](Systems.Core.ExtensibleDataObjects.md#externalid) | string (254) __nullable__ | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. `Filter(multi eq)` `ORD` `Introduced in version 24.1.0.89` 
| [ExternalSystem](Systems.Core.ExtensibleDataObjects.md#externalsystem) | string (64) __nullable__ | The name of the external system from which the object is imported/synchronized. `Filter(multi eq)` `Introduced in version 24.1.0.89` 
| [Id](Systems.Core.ExtensibleDataObjects.md#id) | guid |  
| [IsDeleted](Systems.Core.ExtensibleDataObjects.md#isdeleted) | boolean | Specifies whether the object represented by this system object is deleted. After deletion of the original object, the system object remains in the system, but can be purged later by some cleanup processes. `Required` `Default(false)` `Filter(eq)` `Introduced in version 19.1` 
| [LastUpdateTimeUtc](Systems.Core.ExtensibleDataObjects.md#lastupdatetimeutc) | datetime __nullable__ | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. `Filter(ge;le)` `ORD` `Introduced in version 19.1` 
| [LatestVersion](Systems.Core.ExtensibleDataObjects.md#latestversion) | int32 | The latest saved version of the object. Starts from 1 and increments with 1 for each new version. `Required` `Default(1)` 
| [ObjectVersion](Systems.Core.ExtensibleDataObjects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Systems.Core.ExtensibleDataObjects.md#creationuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who created the object represented by this system object . null means that it is unknown. `Filter(multi eq)` `Introduced in version 19.1` |
| [Folder](Systems.Core.ExtensibleDataObjects.md#folder) | [Folders](General.Files.Folders.md) (nullable) | The owner folder of the object. `Filter(multi eq)` `Introduced in version 26.2.0.13` |
| [LastUpdateUser](Systems.Core.ExtensibleDataObjects.md#lastupdateuser) | [Users](Systems.Security.Users.md) (nullable) | The user, who made the last modification of the object represented by this system object . null means that it is unknown. `Filter(multi eq)` `Introduced in version 19.1` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Versions | [ObjectVersions](Systems.Core.ObjectVersions.md) | List of `ObjectVersion`(Systems.Core.ObjectVersions.md) child objects, based on the `Systems.Core.ObjectVersion.Object`(Systems.Core.ObjectVersions.md#object) back reference 


## Attribute Details

### CreationTimeUtc

The exact server time (in UTC) when the object represented by this system object was created. null means that it is unknown. `Filter(ge;le)` `ORD` `Introduced in version 19.1`

_Type_: **datetime __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityItemId

The Id of the primary row to which the object is bound. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EntityType

The entity type of the row to which the object is bound. `Required` `Default(" ")` `Filter(eq)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Default Value_: ** **  
_Show in UI_: **ShownByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. `Filter(multi eq)` `ORD` `Introduced in version 24.1.0.89`

_Type_: **string (254) __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. `Filter(multi eq)` `Introduced in version 24.1.0.89`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsDeleted

Specifies whether the object represented by this system object is deleted. After deletion of the original object, the system object remains in the system, but can be purged later by some cleanup processes. `Required` `Default(false)` `Filter(eq)` `Introduced in version 19.1`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. `Filter(ge;le)` `ORD` `Introduced in version 19.1`

_Type_: **datetime __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### LatestVersion

The latest saved version of the object. Starts from 1 and increments with 1 for each new version. `Required` `Default(1)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### CreationUser

The user, who created the object represented by this system object . null means that it is unknown. `Filter(multi eq)` `Introduced in version 19.1`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Folder

The owner folder of the object. `Filter(multi eq)` `Introduced in version 26.2.0.13`

_Type_: **[Folders](General.Files.Folders.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LastUpdateUser

The user, who made the last modification of the object represented by this system object . null means that it is unknown. `Filter(multi eq)` `Introduced in version 19.1`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### ChangeFolder

Changes the folder of the object to the specified folder.             This method saves immediately the changes.  
_Return Type_: **void**  
_Declaring Type_: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
_Domain API Request_: **POST**  

**Parameters**  
  * **folder**  
      
    _Type_: [Folders](General.Files.Folders.md)  


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

