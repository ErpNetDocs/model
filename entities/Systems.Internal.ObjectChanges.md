---
uid: Systems.Internal.ObjectChanges
---
# Systems.Internal.ObjectChanges Entity

**Namespace:** [Systems.Internal](Systems.Internal.md)  

Actual tracked changes to one object. Entity: Sys_Object_Changes (Introduced in version 19.1)

## Renames

Old name: **Systems.Core.ObjectChanges**  
New name: **Systems.Internal.ObjectChanges**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{RepositoryName}_  
Default Search Members:  
_RepositoryName_  
Name Data Member:  
_RepositoryName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Internal.ObjectChangesets](Systems.Internal.ObjectChangesets.md)  
Aggregate Root:  
[Systems.Internal.ObjectChangesets](Systems.Internal.ObjectChangesets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ChangesJsonCompressed](Systems.Internal.ObjectChanges.md#changesjsoncompressed) | byte[] __nullable__ | Contains JSON formatted attribute values. GZip compressed. `Introduced in version 24.1.4.29` 
| [ChangeType](Systems.Internal.ObjectChanges.md#changetype) | [ChangeType](Systems.Internal.ObjectChanges.md#changetype) | Type of change - Create, Update or Delete. `Required` 
| [DisplayText](Systems.Internal.ObjectChanges.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntityItemId](Systems.Internal.ObjectChanges.md#entityitemid) | guid | The id of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. `Required` `Filter(multi eq)` 
| [Id](Systems.Internal.ObjectChanges.md#id) | guid |  
| [ObjectVersion](Systems.Internal.ObjectChanges.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [<s>OldValuesJson</s>](Systems.Internal.ObjectChanges.md#oldvaluesjson) | string (max) __nullable__ | **OBSOLETE! Do not use!** Old values in a name-value Json format. Only changed data attributes are recorded. Old values are recorded for update and delete. `Obsolete` `Obsoleted in version 22.1.6.61` 
| [RepositoryName](Systems.Internal.ObjectChanges.md#repositoryname) | string (64) | The repository of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. `Required` `Filter(multi eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ObjectChangeset](Systems.Internal.ObjectChanges.md#objectchangeset) | [ObjectChangesets](Systems.Internal.ObjectChangesets.md) | The changeset containing this change. `Required` `Filter(multi eq)` `Owner` |
| [RootObject](Systems.Internal.ObjectChanges.md#rootobject) | [ExtensibleDataObjects](Systems.Internal.ExtensibleDataObjects.md) | The root object in the aggregate of the object, which has been changed. Each change is recorded at the aggregate root level. `Required` `Filter(multi eq)` |


## Attribute Details

### ChangesJsonCompressed

Contains JSON formatted attribute values. GZip compressed. `Introduced in version 24.1.4.29`

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ChangeType

Type of change - Create, Update or Delete. `Required`

_Type_: **[ChangeType](Systems.Internal.ObjectChanges.md#changetype)**  
_Category_: **System**  
Allowed values for the `ChangeType`(Systems.Internal.ObjectChanges.md#changetype) data attribute  
_Allowed Values (Systems.Internal.ObjectChangesRepository.ChangeType Enum Members)_  

| Value | Description |
| ---- | --- |
| Create | Create value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Create' |
| Update | Update value. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Update' |
| Delete | Delete value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Delete' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntityItemId

The id of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. `Required` `Filter(multi eq)`

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OldValuesJson

**OBSOLETE! Do not use!** Old values in a name-value Json format. Only changed data attributes are recorded. Old values are recorded for update and delete. `Obsolete` `Obsoleted in version 22.1.6.61`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **HiddenByDefault**  

### RepositoryName

The repository of the actual changed object, described by this change. This is different than the aggregate root, which is pointed by Root Object. `Required` `Filter(multi eq;like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ObjectChangeset

The changeset containing this change. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ObjectChangesets](Systems.Internal.ObjectChangesets.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### RootObject

The root object in the aggregate of the object, which has been changed. Each change is recorded at the aggregate root level. `Required` `Filter(multi eq)`

_Type_: **[ExtensibleDataObjects](Systems.Internal.ExtensibleDataObjects.md)**  
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

[!list limit=1000 erp.entity=Systems.Internal.ObjectChanges erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Internal.ObjectChanges erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Internal_ObjectChanges?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Internal_ObjectChanges?$top=10>

