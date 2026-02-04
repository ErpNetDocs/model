---
uid: Projects.Classic.ProjectTasks
---
# Projects.Classic.ProjectTasks


Represents one task of a project.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.ProjectTasks  
Base Table: Prj_Project_Tasks  
API access:  ReadWrite  

## Visualization
Display Format: {TaskName}  
Search Members: TaskName  
Name Member: TaskName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Projects.Classic.ProjectTasks](Projects.Classic.ProjectTasks.md)  
  * [Projects.Classic.ProjectTaskDependancies](Projects.Classic.ProjectTaskDependancies.md)  
  * [Projects.Classic.ProjectTaskMaterials](Projects.Classic.ProjectTaskMaterials.md)  
  * [Projects.Classic.ProjectTaskParticipants](Projects.Classic.ProjectTaskParticipants.md)  
  * [Projects.Classic.ProjectTaskResources](Projects.Classic.ProjectTaskResources.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BudgetLaborAmount](Projects.Classic.ProjectTasks.md#budgetlaboramount) | [Amount (12, 2)](../data-types.md#amount) __nullable__ | Budgeted amount for the labor for the task in the currency of the project. The material is calculated separately. NULL means that budgeting for the item is not calculated 
| [FinishDateTime](Projects.Classic.ProjectTasks.md#finishdatetime) | datetime | The date and time when the task is planned to finish. 
| [Notes](Projects.Classic.ProjectTasks.md#notes) | string (max) __nullable__ | Notes for this ProjectTask. 
| [PlannedDurationHours](Projects.Classic.ProjectTasks.md#planneddurationhours) | decimal (8, 2) | Planned duration of the task in hours. The hours are allocated in the time interval between Start Date Time and Finish Date Time. 
| [ProjectTaskNo](Projects.Classic.ProjectTasks.md#projecttaskno) | int32 | Consecutive task number, unique within the project. 
| [StartDateTime](Projects.Classic.ProjectTasks.md#startdatetime) | datetime | The date and time when the task is planned to start. 
| [TaskName](Projects.Classic.ProjectTasks.md#taskname) | string (254) | The short name of the task. It is best practice to contain the target of the task. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Activity](Projects.Classic.ProjectTasks.md#activity) | [Activities](General.Activities.Activities.md) (nullable) | The Id of the Cm_Activity created for this task. NULL means that activity is still not created |
| [Project](Projects.Classic.ProjectTasks.md#project) | [Projects](Projects.Classic.Projects.md) | The project, to which this task belongs. |
| [ProjectWorkElement](Projects.Classic.ProjectTasks.md#projectworkelement) | [ProjectWorkElements](Projects.Classic.ProjectWorkElements.md) | The work element under which the task is filed. |
| [Resource](Projects.Classic.ProjectTasks.md#resource) | [Resources](Projects.Classic.Resources.md) (nullable) | The resource, which is required for the task. NULL means - do not plan any resource |
| [ResponsibleParty](Projects.Classic.ProjectTasks.md#responsibleparty) | [Parties](General.Contacts.Parties.md) (nullable) | The responsible party. Usually a person and usually one of the project participants. NULL means that responsible is not yet determined |
| [TaskType](Projects.Classic.ProjectTasks.md#tasktype) | [TaskTypes](Projects.Classic.TaskTypes.md) | The type of the task. Determines the work type of the tasks, default billing rules, etc. |
| [WorkType](Projects.Classic.ProjectTasks.md#worktype) | [TypeWorkTypes](Projects.Classic.TypeWorkTypes.md) (nullable) | Type of work to be done. NULL means that type of work is undetermined yet. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.ProjectTasks.md#id) | guid |  
| [ObjectVersion](Projects.Classic.ProjectTasks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Projects.Classic.ProjectTasks.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Projects.Classic.ProjectTasks.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Projects.Classic.ProjectTasks.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Projects.Classic.ProjectTasks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Dependancies | [ProjectTaskDependancies](Projects.Classic.ProjectTaskDependancies.md) | List of `ProjectTaskDependancy`(Projects.Classic.ProjectTaskDependancies.md) child objects, based on the `Projects.Classic.ProjectTaskDependancy.ProjectTask`(Projects.Classic.ProjectTaskDependancies.md#projecttask) back reference 
| Materials | [ProjectTaskMaterials](Projects.Classic.ProjectTaskMaterials.md) | List of `ProjectTaskMaterial`(Projects.Classic.ProjectTaskMaterials.md) child objects, based on the `Projects.Classic.ProjectTaskMaterial.ProjectTask`(Projects.Classic.ProjectTaskMaterials.md#projecttask) back reference 
| Participants | [ProjectTaskParticipants](Projects.Classic.ProjectTaskParticipants.md) | List of `ProjectTaskParticipant`(Projects.Classic.ProjectTaskParticipants.md) child objects, based on the `Projects.Classic.ProjectTaskParticipant.ProjectTask`(Projects.Classic.ProjectTaskParticipants.md#projecttask) back reference 
| Resources | [ProjectTaskResources](Projects.Classic.ProjectTaskResources.md) | List of `ProjectTaskResource`(Projects.Classic.ProjectTaskResources.md) child objects, based on the `Projects.Classic.ProjectTaskResource.ProjectTask`(Projects.Classic.ProjectTaskResources.md#projecttask) back reference 


## Attribute Details

### BudgetLaborAmount

Budgeted amount for the labor for the task in the currency of the project. The material is calculated separately. NULL means that budgeting for the item is not calculated

Type: **[Amount (12, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.PlannedDurationHours != 0) AndAlso ( obj.WorkType != null)), obj.CalculateBudgetLaborAmount( ), new Amount( 0, obj.Project.BudgetingCurrency))`
### FinishDateTime

The date and time when the task is planned to finish.

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ProjectTask.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PlannedDurationHours

Planned duration of the task in hours. The hours are allocated in the time interval between Start Date Time and Finish Date Time.

Type: **decimal (8, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ProjectTaskNo

Consecutive task number, unique within the project.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StartDateTime

The date and time when the task is planned to start.

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### TaskName

The short name of the task. It is best practice to contain the target of the task.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
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

### Activity

The Id of the Cm_Activity created for this task. NULL means that activity is still not created

Type: **[Activities](General.Activities.Activities.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### Project

The project, to which this task belongs.

Type: **[Projects](Projects.Classic.Projects.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectWorkElement

The work element under which the task is filed.

Type: **[ProjectWorkElements](Projects.Classic.ProjectWorkElements.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Resource

The resource, which is required for the task. NULL means - do not plan any resource

Type: **[Resources](Projects.Classic.Resources.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### ResponsibleParty

The responsible party. Usually a person and usually one of the project participants. NULL means that responsible is not yet determined

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TaskType

The type of the task. Determines the work type of the tasks, default billing rules, etc.

Type: **[TaskTypes](Projects.Classic.TaskTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WorkType

Type of work to be done. NULL means that type of work is undetermined yet.

Type: **[TypeWorkTypes](Projects.Classic.TypeWorkTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


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

[!list limit=1000 erp.entity=Projects.Classic.ProjectTasks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.ProjectTasks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_ProjectTasks

Domain API Entity Type: 
Projects_Classic_ProjectTask

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_ProjectTasks?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_ProjectTasks?$top=10>

