---
uid: Systems.Security.GroupAccessKeys
---
# Systems.Security.GroupAccessKeys Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

Specifies the access keys for which the user groups have permissions. The existance of a record grants read permission. Additional permissions are granted through specialized fields. Entity: Sec_Group_Access_Keys

## Default Visualization
Default Display Text Format:  
_{Group.Name:T}_  
Default Search Members:  
_Group.Name_  
Name Data Member:  
_Group.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _3 - Track object and attribute changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.Groups](Systems.Security.Groups.md)  
Aggregate Root:  
[Systems.Security.Groups](Systems.Security.Groups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CanAdminister](Systems.Security.GroupAccessKeys.md#canadminister) | boolean | When true, the group is granted with administrative permission (allowance to change access key) for the entity, protected by the access key. `Required` `Default(false)` 
| [CanDelete](Systems.Security.GroupAccessKeys.md#candelete) | boolean | When true, the group is granted with delete permission for the entity, protected by the access key. `Required` 
| [CanUpdate](Systems.Security.GroupAccessKeys.md#canupdate) | boolean | When true, the group is granted with update permission for the entity, protected by the access key. `Required` 
| [DisplayText](Systems.Security.GroupAccessKeys.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Security.GroupAccessKeys.md#id) | guid |  
| [ObjectVersion](Systems.Security.GroupAccessKeys.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Permission1](Systems.Security.GroupAccessKeys.md#permission1) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission10](Systems.Security.GroupAccessKeys.md#permission10) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission2](Systems.Security.GroupAccessKeys.md#permission2) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission3](Systems.Security.GroupAccessKeys.md#permission3) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission4](Systems.Security.GroupAccessKeys.md#permission4) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission5](Systems.Security.GroupAccessKeys.md#permission5) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission6](Systems.Security.GroupAccessKeys.md#permission6) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission7](Systems.Security.GroupAccessKeys.md#permission7) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission8](Systems.Security.GroupAccessKeys.md#permission8) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 
| [Permission9](Systems.Security.GroupAccessKeys.md#permission9) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Security.GroupAccessKeys.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) | This access key, to which we are granting access permissions. `Required` `Filter(multi eq)` |
| [Group](Systems.Security.GroupAccessKeys.md#group) | [Groups](Systems.Security.Groups.md) | The group, which is granted with access permission. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### CanAdminister

When true, the group is granted with administrative permission (allowance to change access key) for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### CanDelete

When true, the group is granted with delete permission for the entity, protected by the access key. `Required`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CanUpdate

When true, the group is granted with update permission for the entity, protected by the access key. `Required`

_Type_: **boolean**  
_Category_: **System**  
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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Permission1

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission10

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission2

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission3

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission4

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission5

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission6

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission7

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission8

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Permission9

When true, the group is granted with entity-specific permission for the entity, protected by the access key. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AccessKey

This access key, to which we are granting access permissions. `Required` `Filter(multi eq)`

_Type_: **[AccessKeys](Systems.Security.AccessKeys.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


_Remarks_  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### Group

The group, which is granted with access permission. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Groups](Systems.Security.Groups.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

[!list limit=1000 erp.entity=Systems.Security.GroupAccessKeys erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.GroupAccessKeys erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_GroupAccessKeys

Domain API Entity Type: 
Systems_Security_GroupAccessKey

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_GroupAccessKeys?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_GroupAccessKeys?$top=10>

