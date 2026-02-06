---
uid: Projects.Agile.Projects
---
# Projects.Agile.Projects


Agile project, used to logically group cases.

## General
Namespace: [Projects.Agile](Projects.Agile.md)  
Repository: Projects.Agile.Projects  
Base Table: Apm_Projects  
Introduced In Version: 24.1.1.66  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  ProjectTypeId  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.Projects](Projects.Agile.Projects.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsiderWipLimit](Projects.Agile.Projects.md#considerwiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to CONSIDER state. 
| [Description](Projects.Agile.Projects.md#description) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Description of the project. 
| [InProgressWipLimit](Projects.Agile.Projects.md#inprogresswiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to IN PROGRESS state. 
| [IsActive](Projects.Agile.Projects.md#isactive) | boolean | Is the project active for new cases? 
| [IsTemplate](Projects.Agile.Projects.md#istemplate) | boolean | Specifies whether the project is template for new projects of the same type. Template projects can be managed as normal projects. Only one project can be template for any given project type. Cases and other data are copied from the template project when creating a new project. 
| [Name](Projects.Agile.Projects.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Multi-language name of the project 
| [ReadyWipLimit](Projects.Agile.Projects.md#readywiplimit) | int32 __nullable__ | When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to READY state. 
| [<s>WipLimit</s>](Projects.Agile.Projects.md#wiplimit) | int32 __nullable__ | **OBSOLETE! Do not use!** When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to Active state 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Projects.Agile.Projects.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this Project. An empty value means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.3.39` |
| [Customer](Projects.Agile.Projects.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | Specified, when the project is for a customer. |
| [PrimaryUser](Projects.Agile.Projects.md#primaryuser) | [Users](Systems.Security.Users.md) | The primary responsible user for the project. |
| [ProjectGroup](Projects.Agile.Projects.md#projectgroup) | [ProjectGroups](Projects.Agile.ProjectGroups.md) (nullable) | The project group to which the project belongs. NULL means the project is not assigned to any group. |
| [ProjectType](Projects.Agile.Projects.md#projecttype) | [ProjectTypes](Projects.Agile.ProjectTypes.md) | Specifies what kind of project is this. |
| [SocialGroup](Projects.Agile.Projects.md#socialgroup) | [Groups](Communities.Social.Groups.md) (nullable) | The working group responsible for discussing and collaborating on this project. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Agile.Projects.md#id) | guid |  
| [ObjectVersion](Projects.Agile.Projects.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Agile.Projects.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.Projects.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Agile.Projects.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Agile.Projects.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConsiderWipLimit

When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to CONSIDER state.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Description

Description of the project.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InProgressWipLimit

When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to IN PROGRESS state.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Is the project active for new cases?

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### IsTemplate

Specifies whether the project is template for new projects of the same type. Template projects can be managed as normal projects. Only one project can be template for any given project type. Cases and other data are copied from the template project when creating a new project.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

Multi-language name of the project

Type: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReadyWipLimit

When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to READY state.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### WipLimit

**OBSOLETE! Do not use!** When set, specifies the work-in-progress (WIP) limit. The limit is for number of cases, which can progress to Active state

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

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

### AccessKey

The access key, containing the permissions for this Project. An empty value means that all users have unlimited permissions. `Filter(multi eq)` `Introduced in version 25.1.3.39`

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### Customer

Specified, when the project is for a customer.

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PrimaryUser

The primary responsible user for the project.

Type: **[Users](Systems.Security.Users.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectGroup

The project group to which the project belongs. NULL means the project is not assigned to any group.

Type: **[ProjectGroups](Projects.Agile.ProjectGroups.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectType

Specifies what kind of project is this.

Type: **[ProjectTypes](Projects.Agile.ProjectTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SocialGroup

The working group responsible for discussing and collaborating on this project.

Type: **[Groups](Communities.Social.Groups.md) (nullable)**  
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

