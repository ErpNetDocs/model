---
uid: Production.Technologies.RecipeOperations
---
# Production.Technologies.RecipeOperations


Contains the routing (operation list) of the recipes.

## General
Namespace: [Production.Technologies](Production.Technologies.md)  
Repository: Production.Technologies.RecipeOperations  
Base Table: Prd_Recipe_Operations  
API access:  ReadWrite  

## Visualization
Display Format: {Recipe.Name}  
Search Members: Recipe.Name  
Name Member: Recipe.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Technologies.Recipes](Production.Technologies.Recipes.md)  
Aggregate Root:  
[Production.Technologies.Recipes](Production.Technologies.Recipes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LineOrd](Production.Technologies.RecipeOperations.md#lineord) | int32 | Order of the operation within the recipe`Required` 
| [MinimumConcurrent<br />StartTimeMinutes](Production.Technologies.RecipeOperations.md#minimumconcurrentstarttimeminutes) | int32 __nullable__ | How many minutes after the start of this operation can the next operation start. NULL means that the next operation should wait this operation to finish before starting 
| [MoveTimeMinutes](Production.Technologies.RecipeOperations.md#movetimeminutes) | int32 | Time to move the lot to the next operation in minutes`Required` `Default(0)` 
| [Notes](Production.Technologies.RecipeOperations.md#notes) | string (254) __nullable__ | Notes for this RecipeOperation. 
| [OperationDescription](Production.Technologies.RecipeOperations.md#operationdescription) | string (max) __nullable__ | The description of the operation. 
| [<s>RoutingOperationId</s>](Production.Technologies.RecipeOperations.md#routingoperationid) | guid __nullable__ | **OBSOLETE! Do not use!** Not used. `Obsolete` `Filter(multi eq)` `Obsoleted in version 22.1.6.61` 
| [RunTimeMinutes](Production.Technologies.RecipeOperations.md#runtimeminutes) | int32 | Duration of the operation for standard lot of the product`Required` `Default(0)` 
| [ScrapRate](Production.Technologies.RecipeOperations.md#scraprate) | decimal (7, 6) | Standard rate of scrap during the operation`Required` `Default(0)` 
| [SetupTimeMinutes](Production.Technologies.RecipeOperations.md#setuptimeminutes) | int32 | Time needed to setup the equipment`Required` `Default(0)` 
| [StandardCostPerHour](Production.Technologies.RecipeOperations.md#standardcostperhour) | [Amount (18, 6)](../data-types.md#amount) __nullable__ | Standard cost per hour for this operation. It participates in the calculation of standard cost for production for the whole recipe.`Currency: Recipe.Product.CostingCurrency` 
| [StandardPricePerHour](Production.Technologies.RecipeOperations.md#standardpriceperhour) | [Amount (18, 6)](../data-types.md#amount) | Standard price for 1 hour work`Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` 
| [Tooling](Production.Technologies.RecipeOperations.md#tooling) | string (max) __nullable__ | The tools needed for the routing step 
| [UseQuantity](Production.Technologies.RecipeOperations.md#usequantity) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity of the workgroup resource that should be allocated for the operation`Unit: UseQuantityUnit` `Required` `Default(1)` 
| [WaitTimeMinutes](Production.Technologies.RecipeOperations.md#waittimeminutes) | int32 | Wait time (drying, cooling, etc.) after the operation in minutes`Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Operation](Production.Technologies.RecipeOperations.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | Standard operation Id. If not NULL used to load the details. If NULL the details (times, scrap rates, etc.) must be entered manually |
| [OperationInstruction](Production.Technologies.RecipeOperations.md#operationinstruction) | [OperationInstructions](Production.Resources.OperationInstructions.md) (nullable) | Link to additional data, containing instructions in external format |
| [Recipe](Production.Technologies.RecipeOperations.md#recipe) | [Recipes](Production.Technologies.Recipes.md) | The <see cref="Recipe"/> to which this RecipeOperation belongs. `Required` `Filter(multi eq)` `Owner` |
| [UseQuantityUnit](Production.Technologies.RecipeOperations.md#usequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Use_Quantity |
| [WorkgroupResource](Production.Technologies.RecipeOperations.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) | The exact workgroup resource that is engaged in the operation. NULL means that no resource is needed or it will be specfied at a later stage |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Technologies.RecipeOperations.md#id) | guid |  
| [ObjectVersion](Production.Technologies.RecipeOperations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Technologies.RecipeOperations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### LineOrd

Order of the operation within the recipe`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Recipe.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.Recipe.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### MinimumConcurrentStartTimeMinutes

How many minutes after the start of this operation can the next operation start. NULL means that the next operation should wait this operation to finish before starting

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MoveTimeMinutes

Time to move the lot to the next operation in minutes`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this RecipeOperation.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### OperationDescription

The description of the operation.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RoutingOperationId

**OBSOLETE! Do not use!** Not used. `Obsolete` `Filter(multi eq)` `Obsoleted in version 22.1.6.61`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### RunTimeMinutes

Duration of the operation for standard lot of the product`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ScrapRate

Standard rate of scrap during the operation`Required` `Default(0)`

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### SetupTimeMinutes

Time needed to setup the equipment`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### StandardCostPerHour

Standard cost per hour for this operation. It participates in the calculation of standard cost for production for the whole recipe.`Currency: Recipe.Product.CostingCurrency`

Type: **[Amount (18, 6)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StandardPricePerHour

Standard price for 1 hour work`Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)`

Type: **[Amount (18, 6)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### Tooling

The tools needed for the routing step

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### UseQuantity

Quantity of the workgroup resource that should be allocated for the operation`Unit: UseQuantityUnit` `Required` `Default(1)`

Type: **[Quantity (9, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### WaitTimeMinutes

Wait time (drying, cooling, etc.) after the operation in minutes`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### Operation

Standard operation Id. If not NULL used to load the details. If NULL the details (times, scrap rates, etc.) must be entered manually

Type: **[Operations](Production.Resources.Operations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OperationInstruction

Link to additional data, containing instructions in external format

Type: **[OperationInstructions](Production.Resources.OperationInstructions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### Recipe

The <see cref="Recipe"/> to which this RecipeOperation belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Recipes](Production.Technologies.Recipes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### UseQuantityUnit

The measurement unit of Use_Quantity

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WorkgroupResource

The exact workgroup resource that is engaged in the operation. NULL means that no resource is needed or it will be specfied at a later stage

Type: **[WorkgroupResources](Production.Resources.WorkgroupResources.md)**  
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

[!list limit=1000 erp.entity=Production.Technologies.RecipeOperations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Technologies.RecipeOperations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Technologies_RecipeOperations

Domain API Entity Type: 
Production_Technologies_RecipeOperation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Technologies_RecipeOperations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Technologies_RecipeOperations?$top=10>

