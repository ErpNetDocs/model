---
uid: Projects.Agile.ProjectAreas
---
# Projects.Agile.ProjectAreas Entity

**Namespace:** [Projects.Agile](Projects.Agile.md)  

Area of a project. Can be applicable to a single project or all projects. Entity: Apm_Project_Areas (Introduced in version 24.1.1.68)

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
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.ProjectAreas](Projects.Agile.ProjectAreas.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsiderWipLimit](Projects.Agile.ProjectAreas.md#considerwiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to CONSIDER state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38` 
| [Description](Projects.Agile.ProjectAreas.md#description) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Description of the project area. `Filter(like)` `Introduced in version 25.1.1.48` 
| [DisplayText](Projects.Agile.ProjectAreas.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Projects.Agile.ProjectAreas.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.ProjectAreas.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Projects.Agile.ProjectAreas.md#id) | guid |  
| [InProgressWipLimit](Projects.Agile.ProjectAreas.md#inprogresswiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to IN PROGRESS state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38` 
| [IsActive](Projects.Agile.ProjectAreas.md#isactive) | boolean | Specifies whether the project area is active for new projects. `Required` `Default(true)` `Filter(eq)` 
| [Name](Projects.Agile.ProjectAreas.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Multi-language name of the project area. `Required` `Filter(like)` 
| [ObjectVersion](Projects.Agile.ProjectAreas.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ReadyWipLimit](Projects.Agile.ProjectAreas.md#readywiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to READY state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PrimaryUser](Projects.Agile.ProjectAreas.md#primaryuser) | [Users](Systems.Security.Users.md) (nullable) | Specified, when there is a primary user for the area. `Filter(multi eq)` |
| [Project](Projects.Agile.ProjectAreas.md#project) | [Projects](Projects.Agile.Projects.md) (nullable) | Specified for local project areas. null means that the area is global and assignable for all projects. `Filter(multi eq)` |
| [ProjectGroup](Projects.Agile.ProjectAreas.md#projectgroup) | [ProjectGroups](Projects.Agile.ProjectGroups.md) (nullable) | Specified for areas that are applicable to all projects within the project group. null means the area is global, unless it is linked to a specific project. `Filter(multi eq)` `Introduced in version 26.1.4.49` |
| [SocialGroup](Projects.Agile.ProjectAreas.md#socialgroup) | [Groups](Communities.Social.Groups.md) (nullable) | The working group responsible for discussing and collaborating on this project area. `Filter(multi eq)` `Introduced in version 25.1.3.32` |


## Attribute Details

### ConsiderWipLimit

When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to CONSIDER state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Description

Description of the project area. `Filter(like)` `Introduced in version 25.1.1.48`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### InProgressWipLimit

When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to IN PROGRESS state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### IsActive

Specifies whether the project area is active for new projects. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

Multi-language name of the project area. `Required` `Filter(like)`

_Type_: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ReadyWipLimit

When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to READY state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### PrimaryUser

Specified, when there is a primary user for the area. `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Project

Specified for local project areas. null means that the area is global and assignable for all projects. `Filter(multi eq)`

_Type_: **[Projects](Projects.Agile.Projects.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectGroup

Specified for areas that are applicable to all projects within the project group. null means the area is global, unless it is linked to a specific project. `Filter(multi eq)` `Introduced in version 26.1.4.49`

_Type_: **[ProjectGroups](Projects.Agile.ProjectGroups.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SocialGroup

The working group responsible for discussing and collaborating on this project area. `Filter(multi eq)` `Introduced in version 25.1.3.32`

_Type_: **[Groups](Communities.Social.Groups.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.Agile.ProjectAreas erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.ProjectAreas erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_ProjectAreas

Domain API Entity Type: 
Projects_Agile_ProjectArea

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_ProjectAreas?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_ProjectAreas?$top=10>

