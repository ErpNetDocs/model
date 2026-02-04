---
uid: Systems.Security.GroupAccessKeys
---
# Systems.Security.GroupAccessKeys


Specifies the access keys for which the user groups have permissions. The existance of a record grants read permission. Additional permissions are granted through specialized fields.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.GroupAccessKeys  
Base Table: Sec_Group_Access_Keys  
API access:  ReadWrite  

## Visualization
Display Format: {Group.Name:T}  
Search Members: Group.Name  
Name Member: Group.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.Groups](Systems.Security.Groups.md)  
Aggregate Root:  
[Systems.Security.Groups](Systems.Security.Groups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CanAdminister](Systems.Security.GroupAccessKeys.md#canadminister) | boolean | When true, the group is granted with administrative permission (allowance to change access key) for the entity, protected by the access key. 
| [CanDelete](Systems.Security.GroupAccessKeys.md#candelete) | boolean | When true, the group is granted with delete permission for the entity, protected by the access key. 
| [CanUpdate](Systems.Security.GroupAccessKeys.md#canupdate) | boolean | When true, the group is granted with update permission for the entity, protected by the access key. 
| [Permission1](Systems.Security.GroupAccessKeys.md#permission1) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission10](Systems.Security.GroupAccessKeys.md#permission10) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission2](Systems.Security.GroupAccessKeys.md#permission2) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission3](Systems.Security.GroupAccessKeys.md#permission3) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission4](Systems.Security.GroupAccessKeys.md#permission4) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission5](Systems.Security.GroupAccessKeys.md#permission5) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission6](Systems.Security.GroupAccessKeys.md#permission6) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission7](Systems.Security.GroupAccessKeys.md#permission7) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission8](Systems.Security.GroupAccessKeys.md#permission8) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 
| [Permission9](Systems.Security.GroupAccessKeys.md#permission9) | boolean | When true, the group is granted with entity-specific permission for the entity, protected by the access key. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Security.GroupAccessKeys.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) | This access key, to which we are granting access permissions. |
| [Group](Systems.Security.GroupAccessKeys.md#group) | [Groups](Systems.Security.Groups.md) | The group, which is granted with access permission. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.GroupAccessKeys.md#id) | guid |  
| [ObjectVersion](Systems.Security.GroupAccessKeys.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Security.GroupAccessKeys.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CanAdminister

When true, the group is granted with administrative permission (allowance to change access key) for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### CanDelete

When true, the group is granted with delete permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CanUpdate

When true, the group is granted with update permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Permission1

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission10

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission2

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission3

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission4

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission5

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission6

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission7

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission8

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission9

When true, the group is granted with entity-specific permission for the entity, protected by the access key.

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

### AccessKey

This access key, to which we are granting access permissions.

Type: **[AccessKeys](Systems.Security.AccessKeys.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### Group

The group, which is granted with access permission.

Type: **[Groups](Systems.Security.Groups.md)**  
Indexed: **True**  
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

