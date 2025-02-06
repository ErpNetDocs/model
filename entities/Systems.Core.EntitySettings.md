---
uid: Systems.Core.EntitySettings
---
# Systems.Core.EntitySettings Entity

**Namespace:** [Systems.Core](Systems.Core.md)  

Contains entities, which have secured access. Entity: Sys_Entities
## Renamed
**New name:** [Systems.Security.EntitySettings](Systems.Security.EntitySettings.md)  



## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Core.EntitySettings](Systems.Core.EntitySettings.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Core.EntitySettings.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DisplayTextFormat](Systems.Core.EntitySettings.md#displaytextformat) | string (128) __nullable__ | Interpolated string, containing the default format for displaying values of the entity. null means to use the system-wide default. `Introduced in version 22.1.4.18` 
| [Id](Systems.Core.EntitySettings.md#id) | guid |  
| [LogCreate](Systems.Core.EntitySettings.md#logcreate) | boolean | Specifies whether to log every insert for this entity. `Required` `Default(false)` `Introduced in version 18.2` 
| [LogDelete](Systems.Core.EntitySettings.md#logdelete) | boolean | Specifies whether to log every delete for this entity. `Required` `Default(false)` `Introduced in version 18.2` 
| [LogReadById](Systems.Core.EntitySettings.md#logreadbyid) | boolean | Specifies whether to log every load by Id for this entity. `Required` `Default(false)` `Introduced in version 18.2` 
| [LogReadMany](Systems.Core.EntitySettings.md#logreadmany) | boolean | Specifies whether to log every load of many records for this entity. `Required` `Default(false)` `Introduced in version 18.2` 
| [LogUpdate](Systems.Core.EntitySettings.md#logupdate) | boolean | Specifies whether to log every update for this entity. `Required` `Default(false)` `Introduced in version 18.2` 
| [Name](Systems.Core.EntitySettings.md#name) | string (64) | The system name of the entity, which is being secured. `Required` `Filter(eq;like)` `ORD` 
| [ObjectVersion](Systems.Core.EntitySettings.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [TrackChangesLevel](Systems.Core.EntitySettings.md#trackchangeslevel) | [TrackChangesLevel](Systems.Core.EntitySettings.md#trackchangeslevel) | The track changes level for the entity. `Required` `Default(0)` `Filter(multi eq)` `Introduced in version 19.1` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Core.EntitySettings.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, required to access the secured entity. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DisplayTextFormat

Interpolated string, containing the default format for displaying values of the entity. null means to use the system-wide default. `Introduced in version 22.1.4.18`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LogCreate

Specifies whether to log every insert for this entity. `Required` `Default(false)` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LogDelete

Specifies whether to log every delete for this entity. `Required` `Default(false)` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LogReadById

Specifies whether to log every load by Id for this entity. `Required` `Default(false)` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LogReadMany

Specifies whether to log every load of many records for this entity. `Required` `Default(false)` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LogUpdate

Specifies whether to log every update for this entity. `Required` `Default(false)` `Introduced in version 18.2`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

The system name of the entity, which is being secured. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### TrackChangesLevel

The track changes level for the entity. `Required` `Default(0)` `Filter(multi eq)` `Introduced in version 19.1`

_Type_: **[TrackChangesLevel](Systems.Core.EntitySettings.md#trackchangeslevel)**  
_Category_: **System**  
Represents the different levels of tracking changes for a specific entity.  
_Allowed Values (Systems.Core.TrackChangesLevel Enum Members)_  

| Value | Description |
| ---- | --- |
| DoNotTrackChanges | The do not track changes for this entity. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'DoNotTrackChanges' |
| TrackLastChangesOnly | The track last changes only: creation time, creation user, last update time, last update user. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'TrackLastChangesOnly' |
| TrackObjectChanges | Only object changes are tracked. The changed attributes are not tracked. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'TrackObjectChanges' |
| TrackObjectAnd<br />AttributeChanges | Object and attribute changes are tracked excluding BLOB attributes. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'TrackObjectAnd<br />AttributeChanges' |
| TrackObjectAttribute<br />AndBlobChanges | Object and attribute changes are tracked including BLOB attributes. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'TrackObjectAttribute<br />AndBlobChanges' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AccessKey

The access key, required to access the secured entity. `Filter(multi eq)`

_Type_: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  


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

[!list limit=1000 erp.entity=Systems.Core.EntitySettings erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Core.EntitySettings erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Core_EntitySettings?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Core_EntitySettings?$top=10>

