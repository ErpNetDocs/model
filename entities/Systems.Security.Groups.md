---
uid: Systems.Security.Groups
---
# Systems.Security.Groups Entity

**Namespace:** [Systems.Security](Systems.Security.md)  

Groups of users. Used for providing group access to secured data. Entity: Sec_Groups

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _3 - Track object and attribute changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Security.Groups](Systems.Security.Groups.md)  
  * [Systems.Security.GroupAccessKeys](Systems.Security.GroupAccessKeys.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Security.Groups.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EditPeriodDays](Systems.Security.Groups.md#editperioddays) | int32 __nullable__ | The number of days before which the documents can not be corrected, released or voided. 
| [ExternalId](Systems.Security.Groups.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Security.Groups.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [GroupType](Systems.Security.Groups.md#grouptype) | [GroupType](Systems.Security.Groups.md#grouptype) | Group type. G=Normal user-definable group; U=System group for 1 user; A=Admin; E=Everybody. `Required` `Default("G")` `Filter(eq)` `ReadOnly` 
| [Id](Systems.Security.Groups.md#id) | guid |  
| [Name](Systems.Security.Groups.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this Group. `Required` `Filter(like)` `ORD` 
| [Notes](Systems.Security.Groups.md#notes) | string (254) __nullable__ | Notes for this Group. 
| [ObjectVersion](Systems.Security.Groups.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [GroupForUser](Systems.Security.Groups.md#groupforuser) | [Users](Systems.Security.Users.md) (nullable) | When Group_Type=U, contains the user for which the group is defined, null otherwise. `Filter(multi eq)` `ReadOnly` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| AccessKeys | [GroupAccessKeys](Systems.Security.GroupAccessKeys.md) | List of `GroupAccessKey`(Systems.Security.GroupAccessKeys.md) child objects, based on the `Systems.Security.GroupAccessKey.Group`(Systems.Security.GroupAccessKeys.md#group) back reference 


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EditPeriodDays

The number of days before which the documents can not be corrected, released or voided.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### GroupType

Group type. G=Normal user-definable group; U=System group for 1 user; A=Admin; E=Everybody. `Required` `Default("G")` `Filter(eq)` `ReadOnly`

_Type_: **[GroupType](Systems.Security.Groups.md#grouptype)**  
_Category_: **System**  
Allowed values for the `GroupType`(Systems.Security.Groups.md#grouptype) data attribute  
_Allowed Values (Systems.Security.GroupsRepository.GroupType Enum Members)_  

| Value | Description |
| ---- | --- |
| NormalUserDefinableGroup | NormalUserDefinableGroup value. Stored as 'G'. <br /> _Database Value:_ 'G' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'NormalUserDefinableGroup' |
| SystemGroupForOneUser | SystemGroupForOneUser value. Stored as 'U'. <br /> _Database Value:_ 'U' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'SystemGroupForOneUser' |
| Administrators | Administrators value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Administrators' |
| Everybody | Everybody value. Stored as 'E'. <br /> _Database Value:_ 'E' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Everybody' |
| PowerUsers | PowerUsers value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'PowerUsers' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **NormalUserDefinableGroup**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Name

The name of this Group. `Required` `Filter(like)` `ORD`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Group.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### GroupForUser

When Group_Type=U, contains the user for which the group is defined, null otherwise. `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
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

