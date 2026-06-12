---
uid: Projects.ProjectTaskResources
---
# Projects.ProjectTaskResources Entity

**Namespace:** [Projects](Projects.md)  

Contains the resources, required by the project tasks. Entity: Prj_Project_Task_Resources

## Default Visualization
Default Display Text Format:  
_{ProjectTask.TaskName}_  
Default Search Members:  
_ProjectTask.TaskName_  
Name Data Member:  
_ProjectTask.TaskName_  
Category:  _Definitions_  
Show in UI:  _CannotBeShown_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.ProjectTasks](Projects.ProjectTasks.md)  
Aggregate Root:  
[Projects.ProjectTasks](Projects.ProjectTasks.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BillingPricePerHour](Projects.ProjectTaskResources.md#billingpriceperhour) | decimal (12, 5) __nullable__ | When not null, specifies the price per hour (in the currency of the Project) of resource usage which will be used for billing. null means that the item will be billed in another way. This way of billing is mutually exclusive with Fixed Total Price. `Filter(eq)` 
| [BillingTotalAmount](Projects.ProjectTaskResources.md#billingtotalamount) | decimal (14, 2) __nullable__ | When not null, specifies that this item will be billed for the specified fixed total price (in the currency of the Project). null means that this item will be billed in another way. This way of billing is mutually exclusive with Billing Price Per Hour. `Filter(eq)` 
| [CostPerHour](Projects.ProjectTaskResources.md#costperhour) | decimal (12, 5) | Cost per hour for the resource usage for this task (in the currency of the project). `Required` `Default(0)` `Filter(eq)` 
| [DisplayText](Projects.ProjectTaskResources.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.ProjectTaskResources.md#id) | guid |  
| [Notes](Projects.ProjectTaskResources.md#notes) | string (254) __nullable__ | Notes for this ProjectTaskResource. 
| [ObjectVersion](Projects.ProjectTaskResources.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PerUseCost](Projects.ProjectTaskResources.md#perusecost) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | One time cost for each resource usage, specified in the projects currency. `Currency: ProjectTask.Project.BudgetingCurrency` 
| [ResourceUsageHours](Projects.ProjectTaskResources.md#resourceusagehours) | decimal (10, 2) | The total number of resource-hours, which are planned for this task. Equals to the length of the task, multiplied by the resource usage. `Required` `Default(0)` `Filter(eq)` 
| [ResourceUsagePercent](Projects.ProjectTaskResources.md#resourceusagepercent) | decimal (18, 4) | The planned resource usage for this activity in percents. Values of more than 100% are allowed when more than 1 resource is required. `Required` `Default(1)` `Filter(eq)` 
| [TaskTotalCost](Projects.ProjectTaskResources.md#tasktotalcost) | decimal (14, 2) | Total cost for this task (in the currency of the project). `Required` `Default(0)` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProjectTask](Projects.ProjectTaskResources.md#projecttask) | [ProjectTasks](Projects.ProjectTasks.md) | The task for which the resource is planned. `Required` `Filter(multi eq)` `Owner` |
| [Resource](Projects.ProjectTaskResources.md#resource) | [Resources](General.Resources.Resources.md) | The planned resource. `Required` `Filter(multi eq)` |
| [ResourceInstance](Projects.ProjectTaskResources.md#resourceinstance) | [ResourceInstances](General.Resources.ResourceInstances.md) (nullable) | The concrete resource instance, which should be used. null when no specific resource instance is required. `Filter(multi eq)` |


## Attribute Details

### BillingPricePerHour

When not null, specifies the price per hour (in the currency of the Project) of resource usage which will be used for billing. null means that the item will be billed in another way. This way of billing is mutually exclusive with Fixed Total Price. `Filter(eq)`

_Type_: **decimal (12, 5) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.BillingTotalAmount != null) AndAlso ( obj.BillingPricePerHour != null)), null, obj.BillingPricePerHour)`
### BillingTotalAmount

When not null, specifies that this item will be billed for the specified fixed total price (in the currency of the Project). null means that this item will be billed in another way. This way of billing is mutually exclusive with Billing Price Per Hour. `Filter(eq)`

_Type_: **decimal (14, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.BillingTotalAmount != null) AndAlso ( obj.BillingPricePerHour != null)), null, obj.BillingTotalAmount)`
### CostPerHour

Cost per hour for the resource usage for this task (in the currency of the project). `Required` `Default(0)` `Filter(eq)`

_Type_: **decimal (12, 5)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.PerUseCost != null) AndAlso ( obj.ResourceUsageHours != 0)), ( ( obj.TaskTotalCost - obj.PerUseCost.Value) / obj.ResourceUsageHours), obj.CostPerHour)`
### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Notes for this ProjectTaskResource.

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

### PerUseCost

One time cost for each resource usage, specified in the projects currency. `Currency: ProjectTask.Project.BudgetingCurrency`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ResourceUsageHours

The total number of resource-hours, which are planned for this task. Equals to the length of the task, multiplied by the resource usage. `Required` `Default(0)` `Filter(eq)`

_Type_: **decimal (10, 2)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.ProjectTask != null), ( obj.ProjectTask.PlannedDurationHours * obj.ResourceUsagePercent), obj.ResourceUsageHours)`
### ResourceUsagePercent

The planned resource usage for this activity in percents. Values of more than 100% are allowed when more than 1 resource is required. `Required` `Default(1)` `Filter(eq)`

_Type_: **decimal (18, 4)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.ProjectTask.PlannedDurationHours == 0), 0, ( obj.ResourceUsageHours / obj.ProjectTask.PlannedDurationHours))`
### TaskTotalCost

Total cost for this task (in the currency of the project). `Required` `Default(0)` `Filter(eq)`

_Type_: **decimal (14, 2)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( ( obj.ResourceUsageHours * obj.CostPerHour) + obj.PerUseCost.Value)`

_Front-End Recalc Expressions:_  
`IIF( ( obj.PerUseCost != null), ( ( obj.ResourceUsageHours * obj.CostPerHour) + obj.PerUseCost.Value), obj.TaskTotalCost)`

## Reference Details

### ProjectTask

The task for which the resource is planned. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ProjectTasks](Projects.ProjectTasks.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Resource

The planned resource. `Required` `Filter(multi eq)`

_Type_: **[Resources](General.Resources.Resources.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ResourceInstance

The concrete resource instance, which should be used. null when no specific resource instance is required. `Filter(multi eq)`

_Type_: **[ResourceInstances](General.Resources.ResourceInstances.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Projects.ProjectTaskResources erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.ProjectTaskResources erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Projects_ProjectTaskResources?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Projects_ProjectTaskResources?$top=10>

