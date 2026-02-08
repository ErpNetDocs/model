---
uid: Projects.Classic.ProjectTaskMaterials
---
# Projects.Classic.ProjectTaskMaterials


Contains the materials, which are required for a project task.

## General
Namespace: [Projects.Classic](Projects.Classic.md)  
Repository: Projects.Classic.ProjectTaskMaterials  
Base Table: Prj_Project_Task_Materials  
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
| [BudgetedMaterialAmount](Projects.Classic.ProjectTaskMaterials.md#budgetedmaterialamount) | [Amount (12, 2)](../data-types.md#amount) __nullable__ | Budgeted amount for the material in the currency of the project. NULL means there is still no budgeted amount`Currency: ProjectTask.Project.BudgetingCurrency` 
| [LineNumber](Projects.Classic.ProjectTaskMaterials.md#linenumber) | int32 | Line number within the task, increased in steps of 10. Used for sorting purposes`Required` `Default(0)` 
| [Quantity](Projects.Classic.ProjectTaskMaterials.md#quantity) | [Quantity (9, 3)](../data-types.md#quantity) | The required quantity of the material`Unit: QuantityUnit` `Required` `Default(1)` 
| [QuantityBase](Projects.Classic.ProjectTaskMaterials.md#quantitybase) | decimal (9, 3) | The equivalence of Quantity in the base measurement unit of the Material.`Required` `Default(0)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaterialProduct](Projects.Classic.ProjectTaskMaterials.md#materialproduct) | [Products](General.Products.Products.md) | The product Id of the required material |
| [ProjectTask](Projects.Classic.ProjectTaskMaterials.md#projecttask) | [ProjectTasks](Projects.Classic.ProjectTasks.md) | The task for which is the material requirement |
| [QuantityUnit](Projects.Classic.ProjectTaskMaterials.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the required quantity |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Projects.Classic.ProjectTaskMaterials.md#id) | guid |  
| [ObjectVersion](Projects.Classic.ProjectTaskMaterials.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Projects.Classic.ProjectTaskMaterials.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BudgetedMaterialAmount

Budgeted amount for the material in the currency of the project. NULL means there is still no budgeted amount`Currency: ProjectTask.Project.BudgetingCurrency`

Type: **[Amount (12, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.MaterialProduct != null), obj.CalculateBudgetMaterialAmount( obj.Quantity), new Amount( 0, obj.ProjectTask.Project.BudgetingCurrency))`
### LineNumber

Line number within the task, increased in steps of 10. Used for sorting purposes`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ProjectTask.Materials.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.ProjectTask.Materials.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### Quantity

The required quantity of the material`Unit: QuantityUnit` `Required` `Default(1)`

Type: **[Quantity (9, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The equivalence of Quantity in the base measurement unit of the Material.`Required` `Default(0)` `ReadOnly`

Type: **decimal (9, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.QuantityUnit != null) AndAlso ( obj.MaterialProduct != null)), obj.Quantity.ConvertTo( obj.MaterialProduct.BaseUnit, obj.MaterialProduct).Value, obj.QuantityBase)`
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

### MaterialProduct

The product Id of the required material

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProjectTask

The task for which is the material requirement

Type: **[ProjectTasks](Projects.Classic.ProjectTasks.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of the required quantity

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
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

[!list limit=1000 erp.entity=Projects.Classic.ProjectTaskMaterials erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.ProjectTaskMaterials erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_ProjectTaskMaterials

Domain API Entity Type: 
Projects_Classic_ProjectTaskMaterial

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_ProjectTaskMaterials?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_ProjectTaskMaterials?$top=10>

