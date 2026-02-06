---
uid: Projects.Classic.ProjectTaskDependancies
---
# Projects.Classic.ProjectTaskDependancies


Represents dependancy between project tasks.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.ProjectTaskDependancies  
Base Table: Prj_Project_Task_Dependancies  
API access:  ReadWrite  

## Visualization
Display Format: {ProjectTask.TaskName}  
Search Members: ProjectTask.TaskName  
Name Member: ProjectTask.TaskName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Classic.ProjectTasks](Projects.Classic.ProjectTasks.md)  
Aggregate Root:  
[Projects.Classic.ProjectTasks](Projects.Classic.ProjectTasks.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DependancyType](Projects.Classic.ProjectTaskDependancies.md#dependancytype) | [DependancyType](Projects.Classic.ProjectTaskDependancies.md#dependancytype) | FS=Finish-to-Start;SS=Start-to-Start;FF=Finish-to-Finish;SF=Start-to-Finish;SY=Sync (all types in the same time)[Required] [Default(&quot;FS&quot;)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DependsOnTask](Projects.Classic.ProjectTaskDependancies.md#dependsontask) | [ProjectTasks](Projects.Classic.ProjectTasks.md) | The task on which Project_Task depends |
| [ProjectTask](Projects.Classic.ProjectTaskDependancies.md#projecttask) | [ProjectTasks](Projects.Classic.ProjectTasks.md) | The task which depends on another task |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.ProjectTaskDependancies.md#id) | guid |  
| [ObjectVersion](Projects.Classic.ProjectTaskDependancies.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Classic.ProjectTaskDependancies.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DependancyType

FS=Finish-to-Start;SS=Start-to-Start;FF=Finish-to-Finish;SF=Start-to-Finish;SY=Sync (all types in the same time)[Required] [Default(&quot;FS&quot;)]

Type: **[DependancyType](Projects.Classic.ProjectTaskDependancies.md#dependancytype)**  
Category: **System**  
Allowed values for the `DependancyType`(Projects.Classic.ProjectTaskDependancies.md#dependancytype) data attribute  
Allowed Values (Projects.Classic.ProjectTaskDependanciesRepository.DependancyType Enum Members)  

| Value | Description |
| ---- | --- |
| FinishToStart | FinishToStart value. Stored as 'FS'. <br /> Database Value: 'FS' <br /> Model Value: 0 <br /> Domain API Value: 'FinishToStart' |
| StartToStart | StartToStart value. Stored as 'SS'. <br /> Database Value: 'SS' <br /> Model Value: 1 <br /> Domain API Value: 'StartToStart' |
| FinishToFinish | FinishToFinish value. Stored as 'FF'. <br /> Database Value: 'FF' <br /> Model Value: 2 <br /> Domain API Value: 'FinishToFinish' |
| StartToFinish | StartToFinish value. Stored as 'SF'. <br /> Database Value: 'SF' <br /> Model Value: 3 <br /> Domain API Value: 'StartToFinish' |
| SyncAllTypesInTheSameTime | SyncAllTypesInTheSameTime value. Stored as 'SY'. <br /> Database Value: 'SY' <br /> Model Value: 4 <br /> Domain API Value: 'SyncAllTypesInTheSameTime' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **FinishToStart**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### DependsOnTask

The task on which Project_Task depends

Type: **[ProjectTasks](Projects.Classic.ProjectTasks.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectTask

The task which depends on another task

Type: **[ProjectTasks](Projects.Classic.ProjectTasks.md)**  
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

[!list limit=1000 erp.entity=Projects.Classic.ProjectTaskDependancies erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.ProjectTaskDependancies erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_ProjectTaskDependancies

Domain API Entity Type: 
Projects_Classic_ProjectTaskDependancy

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_ProjectTaskDependancies?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_ProjectTaskDependancies?$top=10>

