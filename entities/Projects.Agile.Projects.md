---
uid: Projects.Agile.Projects
---
# Projects.Agile.Projects Entity

**Namespace:** [Projects.Agile](Projects.Agile.md)  

Agile project, used to logically group cases. Entity: Apm_Projects (Introduced in version 24.1.1.66)

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
Layout category attribute:  _ProjectTypeId_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.Projects](Projects.Agile.Projects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsiderWipLimit](Projects.Agile.Projects.md#considerwiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to CONSIDER state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38` 
| [Description](Projects.Agile.Projects.md#description) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Description of the project. `Filter(like)` `Introduced in version 25.1.1.48` 
| [DisplayText](Projects.Agile.Projects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Projects.Agile.Projects.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.Projects.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Projects.Agile.Projects.md#id) | guid |  
| [InProgressWipLimit](Projects.Agile.Projects.md#inprogresswiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to IN PROGRESS state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38` 
| [IsActive](Projects.Agile.Projects.md#isactive) | boolean | Is the project active for new cases?. `Required` `Default(true)` `Filter(eq)` 
| [IsTemplate](Projects.Agile.Projects.md#istemplate) | boolean | Specifies whether the project is template for new projects of the same type. Template projects can be managed as normal projects. Only one project can be template for any given project type. Cases and other data are copied from the template project when creating a new project. `Required` `Default(false)` `Filter(eq)` 
| [Name](Projects.Agile.Projects.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Multi-language name of the project. `Required` `Filter(like)` 
| [ObjectVersion](Projects.Agile.Projects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ReadyWipLimit](Projects.Agile.Projects.md#readywiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to READY state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38` 
| [<s>WipLimit</s>](Projects.Agile.Projects.md#wiplimit) | int32 __nullable__ | **OBSOLETE! Do not use!** When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to Active state. `Obsolete` `Filter(eq)` `Obsoleted in version 25.1.1.38` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Projects.Agile.Projects.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this Project. An empty value means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.3.39` |
| [Customer](Projects.Agile.Projects.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | Specified, when the project is for a customer. `Filter(multi eq)` |
| [PrimaryUser](Projects.Agile.Projects.md#primaryuser) | [Users](Systems.Security.Users.md) | The primary responsible user for the project. `Required` `Filter(multi eq)` |
| [ProjectGroup](Projects.Agile.Projects.md#projectgroup) | [ProjectGroups](Projects.Agile.ProjectGroups.md) (nullable) | The project group to which the project belongs. null means the project is not assigned to any group. `Filter(multi eq)` `Introduced in version 26.1.4.49` |
| [ProjectType](Projects.Agile.Projects.md#projecttype) | [ProjectTypes](Projects.Agile.ProjectTypes.md) | Specifies what kind of project is this. `Required` `Filter(multi eq)` |
| [SocialGroup](Projects.Agile.Projects.md#socialgroup) | [Groups](Communities.Social.Groups.md) (nullable) | The working group responsible for discussing and collaborating on this project. `Filter(multi eq)` `Introduced in version 25.1.2.63` |


## Attribute Details

### ConsiderWipLimit

When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to CONSIDER state. `Filter(eq;ge;le)` `Introduced in version 25.1.1.38`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Description

Description of the project. `Filter(like)` `Introduced in version 25.1.1.48`

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

Is the project active for new cases?. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### IsTemplate

Specifies whether the project is template for new projects of the same type. Template projects can be managed as normal projects. Only one project can be template for any given project type. Cases and other data are copied from the template project when creating a new project. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

Multi-language name of the project. `Required` `Filter(like)`

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

### WipLimit

**OBSOLETE! Do not use!** When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to Active state. `Obsolete` `Filter(eq)` `Obsoleted in version 25.1.1.38`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **CannotBeShown**  


## Reference Details

### AccessKey

The access key, containing the permissions for this Project. An empty value means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.3.39`

_Type_: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  


_Remarks_  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### Customer

Specified, when the project is for a customer. `Filter(multi eq)`

_Type_: **[Customers](Crm.Sales.Customers.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PrimaryUser

The primary responsible user for the project. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectGroup

The project group to which the project belongs. null means the project is not assigned to any group. `Filter(multi eq)` `Introduced in version 26.1.4.49`

_Type_: **[ProjectGroups](Projects.Agile.ProjectGroups.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectType

Specifies what kind of project is this. `Required` `Filter(multi eq)`

_Type_: **[ProjectTypes](Projects.Agile.ProjectTypes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SocialGroup

The working group responsible for discussing and collaborating on this project. `Filter(multi eq)` `Introduced in version 25.1.2.63`

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

[!list limit=1000 erp.entity=Projects.Agile.Projects erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.Projects erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_Projects

Domain API Entity Type: 
Projects_Agile_Project

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_Projects?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_Projects?$top=10>

