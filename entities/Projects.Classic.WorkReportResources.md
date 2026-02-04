---
uid: Projects.Classic.WorkReportResources
---
# Projects.Classic.WorkReportResources


Each record contains usage of resource, reported by the related Work Report.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.WorkReportResources  
Base Table: Prj_Work_Report_Resources  
API access:  ReadWrite  

## Visualization
Display Format: {WorkReport.EntityName}  
Search Members: WorkReport.EntityName  
Name Member: WorkReport.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Classic.WorkReports](Projects.Classic.WorkReports.md)  
Aggregate Root:  
[Projects.Classic.WorkReports](Projects.Classic.WorkReports.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActualEndTime](Projects.Classic.WorkReportResources.md#actualendtime) | datetime __nullable__ | Optionally, specifies the actual date and time when the resource usage ended. 
| [ActualStartTime](Projects.Classic.WorkReportResources.md#actualstarttime) | datetime __nullable__ | Optionally, specifies the actual date and time when the resource usage began. 
| [TotalResourceUsageHours](Projects.Classic.WorkReportResources.md#totalresourceusagehours) | decimal (18, 2) | The total number of resource-hours, which are actually consumed. Equals to the duration of the task, multiplied by the average resource usage. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectTask](Projects.Classic.WorkReportResources.md#projecttask) | [ProjectTasks](Projects.Classic.ProjectTasks.md) | The project task for which the work is reported. |
| [Resource](Projects.Classic.WorkReportResources.md#resource) | [Resources](General.Resources.Resources.md) | The resource, for which usage is reported. |
| [ResourceInstance](Projects.Classic.WorkReportResources.md#resourceinstance) | [ResourceInstances](General.Resources.ResourceInstances.md) (nullable) | The concrete resource instance used. NULL when no concrete resource was used or there is no data whether concrete resource was used. |
| [WorkReport](Projects.Classic.WorkReportResources.md#workreport) | [WorkReports](Projects.Classic.WorkReports.md) | The <see cref="WorkReport"/> to which this WorkReportResource belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.WorkReportResources.md#id) | guid |  
| [ObjectVersion](Projects.Classic.WorkReportResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Classic.WorkReportResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ActualEndTime

Optionally, specifies the actual date and time when the resource usage ended.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ActualStartTime

Optionally, specifies the actual date and time when the resource usage began.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalResourceUsageHours

The total number of resource-hours, which are actually consumed. Equals to the duration of the task, multiplied by the average resource usage.

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Default Value: **0**  
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

### ProjectTask

The project task for which the work is reported.

Type: **[ProjectTasks](Projects.Classic.ProjectTasks.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.WorkReport.ProjectTask`

Front-End Recalc Expressions:  
`obj.WorkReport.ProjectTask`
### Resource

The resource, for which usage is reported.

Type: **[Resources](General.Resources.Resources.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ResourceInstance

The concrete resource instance used. NULL when no concrete resource was used or there is no data whether concrete resource was used.

Type: **[ResourceInstances](General.Resources.ResourceInstances.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.ResourceInstance != null) AndAlso ( obj.ResourceInstance.Resource != obj.Resource)), null, obj.ResourceInstance)`
### WorkReport

The <see cref="WorkReport"/> to which this WorkReportResource belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[WorkReports](Projects.Classic.WorkReports.md)**  
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

[!list limit=1000 erp.entity=Projects.Classic.WorkReportResources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.WorkReportResources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_WorkReportResources

Domain API Entity Type: 
Projects_Classic_WorkReportResource

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_WorkReportResources?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_WorkReportResources?$top=10>

