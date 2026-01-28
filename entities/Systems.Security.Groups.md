---
uid: Systems.Security.Groups
---
# Systems.Security.Groups


Groups of users. Used for providing group access to secured data.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.Groups  
Base Table: Sec_Groups  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.Groups](Systems.Security.Groups.md)  
  * [Systems.Security.GroupAccessKeys](Systems.Security.GroupAccessKeys.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EditPeriodDays](Systems.Security.Groups.md#editperioddays) | int32 __nullable__ | The number of days before which the documents can not be corrected, released or voided. 
| [GroupType](Systems.Security.Groups.md#grouptype) | [GroupType](Systems.Security.Groups.md#grouptype) | Group type. G=Normal user-definable group; U=System group for 1 user; A=Admin; E=Everybody. `Required` `Default("G")` `Filter(eq)` `ReadOnly` 
| [Name](Systems.Security.Groups.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this Group. `Required` `Filter(like)` `ORD` 
| [Notes](Systems.Security.Groups.md#notes) | string (254) __nullable__ | Notes for this Group. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [GroupForUser](Systems.Security.Groups.md#groupforuser) | [Users](Systems.Security.Users.md) (nullable) | When Group_Type=U, contains the user for which the group is defined, null otherwise. `Filter(multi eq)` `ReadOnly` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.Groups.md#id) | guid |  
| [ObjectVersion](Systems.Security.Groups.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Security.Groups.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.Groups.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Security.Groups.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Security.Groups.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| AccessKeys | [GroupAccessKeys](Systems.Security.GroupAccessKeys.md) | List of `GroupAccessKey`(Systems.Security.GroupAccessKeys.md) child objects, based on the `Systems.Security.GroupAccessKey.Group`(Systems.Security.GroupAccessKeys.md#group) back reference 


## Attribute Details

### EditPeriodDays

The number of days before which the documents can not be corrected, released or voided.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### GroupType

Group type. G=Normal user-definable group; U=System group for 1 user; A=Admin; E=Everybody. `Required` `Default("G")` `Filter(eq)` `ReadOnly`

Type: **[GroupType](Systems.Security.Groups.md#grouptype)**  
Category: **System**  
Allowed values for the `GroupType`(Systems.Security.Groups.md#grouptype) data attribute  
Allowed Values (Systems.Security.GroupsRepository.GroupType Enum Members)  

| Value | Description |
| ---- | --- |
| NormalUserDefinableGroup | NormalUserDefinableGroup value. Stored as 'G'. <br /> Database Value: 'G' <br /> Model Value: 0 <br /> Domain API Value: 'NormalUserDefinableGroup' |
| SystemGroupForOneUser | SystemGroupForOneUser value. Stored as 'U'. <br /> Database Value: 'U' <br /> Model Value: 1 <br /> Domain API Value: 'SystemGroupForOneUser' |
| Administrators | Administrators value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 2 <br /> Domain API Value: 'Administrators' |
| Everybody | Everybody value. Stored as 'E'. <br /> Database Value: 'E' <br /> Model Value: 3 <br /> Domain API Value: 'Everybody' |
| PowerUsers | PowerUsers value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 4 <br /> Domain API Value: 'PowerUsers' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **NormalUserDefinableGroup**  
Show in UI: **ShownByDefault**  

### Name

The name of this Group. `Required` `Filter(like)` `ORD`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Group.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
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

### GroupForUser

When Group_Type=U, contains the user for which the group is defined, null otherwise. `Filter(multi eq)` `ReadOnly`

Type: **[Users](Systems.Security.Users.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Systems.Security.Groups erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.Groups erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_Groups

Domain API Entity Type: 
Systems_Security_Group

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_Groups?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_Groups?$top=10>

