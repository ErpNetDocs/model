---
uid: Projects.Classic.ProjectTaskResources
---
# Projects.Classic.ProjectTaskResources


Contains the resources, required by the project tasks.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.ProjectTaskResources  
Base Table: Prj_Project_Task_Resources  
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
| [BillingPricePerHour](Projects.Classic.ProjectTaskResources.md#billingpriceperhour) | decimal (12, 5) __nullable__ | When not null, specifies the price per hour (in the currency of the Project) of resource usage which will be used for billing. null means that the item will be billed in another way. This way of billing is mutually exclusive with Fixed Total Price. `Filter(eq)` 
| [BillingTotalAmount](Projects.Classic.ProjectTaskResources.md#billingtotalamount) | decimal (14, 2) __nullable__ | When not null, specifies that this item will be billed for the specified fixed total price (in the currency of the Project). null means that this item will be billed in another way. This way of billing is mutually exclusive with Billing Price Per Hour. `Filter(eq)` 
| [CostPerHour](Projects.Classic.ProjectTaskResources.md#costperhour) | decimal (12, 5) | Cost per hour for the resource usage for this task (in the currency of the project). `Required` `Default(0)` `Filter(eq)` 
| [Notes](Projects.Classic.ProjectTaskResources.md#notes) | string (254) __nullable__ | Notes for this ProjectTaskResource. 
| [PerUseCost](Projects.Classic.ProjectTaskResources.md#perusecost) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | One time cost for each resource usage, specified in the projects currency. `Currency: ProjectTask.Project.BudgetingCurrency` 
| [ResourceUsageHours](Projects.Classic.ProjectTaskResources.md#resourceusagehours) | decimal (10, 2) | The total number of resource-hours, which are planned for this task. Equals to the length of the task, multiplied by the resource usage. `Required` `Default(0)` `Filter(eq)` 
| [ResourceUsagePercent](Projects.Classic.ProjectTaskResources.md#resourceusagepercent) | decimal (18, 4) | The planned resource usage for this activity in percents. Values of more than 100% are allowed when more than 1 resource is required. `Required` `Default(1)` `Filter(eq)` 
| [TaskTotalCost](Projects.Classic.ProjectTaskResources.md#tasktotalcost) | decimal (14, 2) | Total cost for this task (in the currency of the project). `Required` `Default(0)` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectTask](Projects.Classic.ProjectTaskResources.md#projecttask) | [ProjectTasks](Projects.Classic.ProjectTasks.md) | The task for which the resource is planned. `Required` `Filter(multi eq)` `Owner` |
| [Resource](Projects.Classic.ProjectTaskResources.md#resource) | [Resources](General.Resources.Resources.md) | The planned resource. `Required` `Filter(multi eq)` |
| [ResourceInstance](Projects.Classic.ProjectTaskResources.md#resourceinstance) | [ResourceInstances](General.Resources.ResourceInstances.md) (nullable) | The concrete resource instance, which should be used. null when no specific resource instance is required. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.ProjectTaskResources.md#id) | guid |  
| [ObjectVersion](Projects.Classic.ProjectTaskResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Classic.ProjectTaskResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BillingPricePerHour

When not null, specifies the price per hour (in the currency of the Project) of resource usage which will be used for billing. null means that the item will be billed in another way. This way of billing is mutually exclusive with Fixed Total Price. `Filter(eq)`

Type: **decimal (12, 5) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.BillingTotalAmount != null) AndAlso ( obj.BillingPricePerHour != null)), null, obj.BillingPricePerHour)`
### BillingTotalAmount

When not null, specifies that this item will be billed for the specified fixed total price (in the currency of the Project). null means that this item will be billed in another way. This way of billing is mutually exclusive with Billing Price Per Hour. `Filter(eq)`

Type: **decimal (14, 2) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.BillingTotalAmount != null) AndAlso ( obj.BillingPricePerHour != null)), null, obj.BillingTotalAmount)`
### CostPerHour

Cost per hour for the resource usage for this task (in the currency of the project). `Required` `Default(0)` `Filter(eq)`

Type: **decimal (12, 5)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.PerUseCost != null) AndAlso ( obj.ResourceUsageHours != 0)), ( ( obj.TaskTotalCost - obj.PerUseCost.Value) / obj.ResourceUsageHours), obj.CostPerHour)`
### Notes

Notes for this ProjectTaskResource.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### PerUseCost

One time cost for each resource usage, specified in the projects currency. `Currency: ProjectTask.Project.BudgetingCurrency`

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ResourceUsageHours

The total number of resource-hours, which are planned for this task. Equals to the length of the task, multiplied by the resource usage. `Required` `Default(0)` `Filter(eq)`

Type: **decimal (10, 2)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ProjectTask != null), ( obj.ProjectTask.PlannedDurationHours * obj.ResourceUsagePercent), obj.ResourceUsageHours)`
### ResourceUsagePercent

The planned resource usage for this activity in percents. Values of more than 100% are allowed when more than 1 resource is required. `Required` `Default(1)` `Filter(eq)`

Type: **decimal (18, 4)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ProjectTask.PlannedDurationHours == 0), 0, ( obj.ResourceUsageHours / obj.ProjectTask.PlannedDurationHours))`
### TaskTotalCost

Total cost for this task (in the currency of the project). `Required` `Default(0)` `Filter(eq)`

Type: **decimal (14, 2)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( ( obj.ResourceUsageHours * obj.CostPerHour) + obj.PerUseCost.Value)`

Front-End Recalc Expressions:  
`IIF( ( obj.PerUseCost != null), ( ( obj.ResourceUsageHours * obj.CostPerHour) + obj.PerUseCost.Value), obj.TaskTotalCost)`
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

The task for which the resource is planned. `Required` `Filter(multi eq)` `Owner`

Type: **[ProjectTasks](Projects.Classic.ProjectTasks.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Resource

The planned resource. `Required` `Filter(multi eq)`

Type: **[Resources](General.Resources.Resources.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ResourceInstance

The concrete resource instance, which should be used. null when no specific resource instance is required. `Filter(multi eq)`

Type: **[ResourceInstances](General.Resources.ResourceInstances.md) (nullable)**  
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

[!list limit=1000 erp.entity=Projects.Classic.ProjectTaskResources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.ProjectTaskResources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_ProjectTaskResources

Domain API Entity Type: 
Projects_Classic_ProjectTaskResource

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_ProjectTaskResources?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_ProjectTaskResources?$top=10>

