---
uid: Projects.Classic.ProjectTaskMaterials
---
# Projects.Classic.ProjectTaskMaterials Entity

**Namespace:** [Projects.Classic](Projects.Classic.md)  

Contains the materials, which are required for a project task. Entity: Prj_Project_Task_Materials

## Default Visualization
Default Display Text Format:  
_{ProjectTask.TaskName}_  
Default Search Members:  
_ProjectTask.TaskName_  
Name Data Member:  
_ProjectTask.TaskName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Classic.ProjectTasks](Projects.Classic.ProjectTasks.md)  
Aggregate Root:  
[Projects.Classic.ProjectTasks](Projects.Classic.ProjectTasks.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BudgetedMaterialAmount](Projects.Classic.ProjectTaskMaterials.md#budgetedmaterialamount) | [Amount (12, 2)](../data-types.md#amount) __nullable__ | Budgeted amount for the material in the currency of the project. null means there is still no budgeted amount. `Currency: ProjectTask.Project.BudgetingCurrency` 
| [DisplayText](Projects.Classic.ProjectTaskMaterials.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.Classic.ProjectTaskMaterials.md#id) | guid |  
| [LineNumber](Projects.Classic.ProjectTaskMaterials.md#linenumber) | int32 | Line number within the task, increased in steps of 10. Used for sorting purposes. `Required` `Default(0)` 
| [ObjectVersion](Projects.Classic.ProjectTaskMaterials.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Projects.Classic.ProjectTaskMaterials.md#quantity) | [Quantity (9, 3)](../data-types.md#quantity) | The required quantity of the material. `Unit: QuantityUnit` `Required` `Default(1)` 
| [QuantityBase](Projects.Classic.ProjectTaskMaterials.md#quantitybase) | decimal (9, 3) | The equivalence of Quantity in the base measurement unit of the Material. `Required` `Default(0)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaterialProduct](Projects.Classic.ProjectTaskMaterials.md#materialproduct) | [Products](General.Products.Products.md) | The product Id of the required material. `Required` `Filter(multi eq)` |
| [ProjectTask](Projects.Classic.ProjectTaskMaterials.md#projecttask) | [ProjectTasks](Projects.Classic.ProjectTasks.md) | The task for which is the material requirement. `Required` `Filter(multi eq)` `Owner` |
| [QuantityUnit](Projects.Classic.ProjectTaskMaterials.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the required quantity. `Required` `Filter(multi eq)` |


## Attribute Details

### BudgetedMaterialAmount

Budgeted amount for the material in the currency of the project. null means there is still no budgeted amount. `Currency: ProjectTask.Project.BudgetingCurrency`

_Type_: **[Amount (12, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.MaterialProduct != null), obj.CalculateBudgetMaterialAmount( obj.Quantity), new Amount( 0, obj.ProjectTask.Project.BudgetingCurrency))`
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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNumber

Line number within the task, increased in steps of 10. Used for sorting purposes. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.ProjectTask.Materials.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.ProjectTask.Materials.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The required quantity of the material. `Unit: QuantityUnit` `Required` `Default(1)`

_Type_: **[Quantity (9, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The equivalence of Quantity in the base measurement unit of the Material. `Required` `Default(0)` `ReadOnly`

_Type_: **decimal (9, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.QuantityUnit != null) AndAlso ( obj.MaterialProduct != null)), obj.Quantity.ConvertTo( obj.MaterialProduct.BaseUnit, obj.MaterialProduct).Value, obj.QuantityBase)`

## Reference Details

### MaterialProduct

The product Id of the required material. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectTask

The task for which is the material requirement. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ProjectTasks](Projects.Classic.ProjectTasks.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit of the required quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
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

