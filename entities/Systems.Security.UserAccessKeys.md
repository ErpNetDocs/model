---
uid: Systems.Security.UserAccessKeys
---
# Systems.Security.UserAccessKeys


Obsolete. Not used.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.UserAccessKeys  
Base Table: Sec_User_Access_Keys  
API access:  ReadWrite  

> [!NOTE]  
> **OBSOLETE! Do not use!**   


## Visualization
Display Format: {User.Name:T}  
Search Members: User.Name  
Name Member: User.Name  
Category:  Definitions  
Show in UI:  CannotBeShown  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.Users](Systems.Security.Users.md)  
Aggregate Root:  
[Systems.Security.Users](Systems.Security.Users.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CanDelete](Systems.Security.UserAccessKeys.md#candelete) | boolean | Obsolete. Not used.[Required] 
| [CanUpdate](Systems.Security.UserAccessKeys.md#canupdate) | boolean | Obsolete. Not used.[Required] 
| [Permission1](Systems.Security.UserAccessKeys.md#permission1) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission10](Systems.Security.UserAccessKeys.md#permission10) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission2](Systems.Security.UserAccessKeys.md#permission2) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission3](Systems.Security.UserAccessKeys.md#permission3) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission4](Systems.Security.UserAccessKeys.md#permission4) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission5](Systems.Security.UserAccessKeys.md#permission5) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission6](Systems.Security.UserAccessKeys.md#permission6) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission7](Systems.Security.UserAccessKeys.md#permission7) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission8](Systems.Security.UserAccessKeys.md#permission8) | boolean | Obsolete. Not used.[Required] [Default(false)] 
| [Permission9](Systems.Security.UserAccessKeys.md#permission9) | boolean | Obsolete. Not used.[Required] [Default(false)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Systems.Security.UserAccessKeys.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) | The access key, containing the permissions for this UserAccessKey. An empty value means that all users have unlimited permissions. `Required` `Filter(multi eq)` |
| [User](Systems.Security.UserAccessKeys.md#user) | [Users](Systems.Security.Users.md) | Obsolete. Not used. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.UserAccessKeys.md#id) | guid |  
| [ObjectVersion](Systems.Security.UserAccessKeys.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Security.UserAccessKeys.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CanDelete

Obsolete. Not used.[Required]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CanUpdate

Obsolete. Not used.[Required]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Permission1

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission10

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission2

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission3

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission4

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission5

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission6

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission7

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission8

Obsolete. Not used.[Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Permission9

Obsolete. Not used.[Required] [Default(false)]

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

The access key, containing the permissions for this UserAccessKey. An empty value means that all users have unlimited permissions. `Required` `Filter(multi eq)`

Type: **[AccessKeys](Systems.Security.AccessKeys.md)**  
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
### User

Obsolete. Not used.

Type: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Systems.Security.UserAccessKeys erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.UserAccessKeys erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_UserAccessKeys

Domain API Entity Type: 
Systems_Security_UserAccessKey

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_UserAccessKeys?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_UserAccessKeys?$top=10>

