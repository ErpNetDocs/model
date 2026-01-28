---
uid: Projects.Agile.Sprints
---
# Projects.Agile.Sprints


Stores the definition, schedule, and metrics for each Agile sprint (iteration) within a project or team (social group). A sprint is a fixed timebox used to deliver a defined set of backlog items (Cases) toward a sprint goal. It supports sprint planning, execution tracking, and historical reporting.

## General
Namespace: [Projects.Agile](Projects.Agile.md)  
Repository: Projects.Agile.Sprints  
Base Table: Apm_Sprints  
Introduced In Version: 26.1.4.32  
API access:  ReadWrite  

## Visualization
Display Format: {Project}: {Name:T} ({StartDate:d} - {EndDate:d})  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Agile.Sprints](Projects.Agile.Sprints.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActivatedAt](Projects.Agile.Sprints.md#activatedat) | datetime __nullable__ | Timestamp when the sprint was activated. `Filter(eq;ge;le)` 
| [EndDate](Projects.Agile.Sprints.md#enddate) | date | End date of the sprint’s timebox. `Required` `Filter(eq;ge;le)` 
| [Goal](Projects.Agile.Sprints.md#goal) | string (500) __nullable__ | Short description of the main objectives or focus for the sprint. `Filter(eq;like)` 
| [Name](Projects.Agile.Sprints.md#name) | string (100) | Human-readable sprint name, e.g. “Sprint 14”. `Required` `Filter(eq;like)` 
| [StartDate](Projects.Agile.Sprints.md#startdate) | date | Start date of the sprint’s timebox. `Required` `Filter(eq;ge;le)` 
| [State](Projects.Agile.Sprints.md#state) | [State](Projects.Agile.Sprints.md#state) | Current sprint status: Planned, Active, Completed, Cancelled. `Required` `Default("PLN")` `Filter(multi eq)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Project](Projects.Agile.Sprints.md#project) | [Projects](Projects.Agile.Projects.md) | Project to which this sprint belongs. `Required` `Filter(multi eq)` |
| [SocialGroup](Projects.Agile.Sprints.md#socialgroup) | [Groups](Communities.Social.Groups.md) (nullable) | Team (social group) responsible for the sprint. null if the sprint applies to the entire project without team distinction. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Agile.Sprints.md#id) | guid |  
| [ObjectVersion](Projects.Agile.Sprints.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Agile.Sprints.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Agile.Sprints.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Agile.Sprints.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Agile.Sprints.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ActivatedAt

Timestamp when the sprint was activated. `Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EndDate

End date of the sprint’s timebox. `Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Goal

Short description of the main objectives or focus for the sprint. `Filter(eq;like)`

Type: **string (500) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **500**  
Show in UI: **ShownByDefault**  

### Name

Human-readable sprint name, e.g. “Sprint 14”. `Required` `Filter(eq;like)`

Type: **string (100)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **100**  
Show in UI: **ShownByDefault**  

### StartDate

Start date of the sprint’s timebox. `Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### State

Current sprint status: Planned, Active, Completed, Cancelled. `Required` `Default("PLN")` `Filter(multi eq)` `ReadOnly`

Type: **[State](Projects.Agile.Sprints.md#state)**  
Category: **System**  
Allowed values for the `State`(Projects.Agile.Sprints.md#state) data attribute  
Allowed Values (Projects.Agile.SprintsRepository.State Enum Members)  

| Value | Description |
| ---- | --- |
| Planned | Planned. Stored as 'PLN'. <br /> Database Value: 'PLN' <br /> Model Value: 0 <br /> Domain API Value: 'Planned' |
| Active | Active. Stored as 'ACT'. <br /> Database Value: 'ACT' <br /> Model Value: 1 <br /> Domain API Value: 'Active' |
| Completed | Completed. Stored as 'CMP'. <br /> Database Value: 'CMP' <br /> Model Value: 2 <br /> Domain API Value: 'Completed' |
| Cancelled | Cancelled. Stored as 'CNC'. <br /> Database Value: 'CNC' <br /> Model Value: 3 <br /> Domain API Value: 'Cancelled' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Planned**  
Show in UI: **HiddenByDefault**  

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

### Project

Project to which this sprint belongs. `Required` `Filter(multi eq)`

Type: **[Projects](Projects.Agile.Projects.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SocialGroup

Team (social group) responsible for the sprint. null if the sprint applies to the entire project without team distinction. `Filter(multi eq)`

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

[!list limit=1000 erp.entity=Projects.Agile.Sprints erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Agile.Sprints erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Agile_Sprints

Domain API Entity Type: 
Projects_Agile_Sprint

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Agile_Sprints?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Agile_Sprints?$top=10>

