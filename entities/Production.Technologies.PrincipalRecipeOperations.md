---
uid: Production.Technologies.PrincipalRecipeOperations
---
# Production.Technologies.PrincipalRecipeOperations


Contains the operations within a principal recipe.

## General
Namespace: [Production.Technologies](Production.Technologies.md)  
Repository: Production.Technologies.PrincipalRecipeOperations  
Base Table: Prd_Principal_Recipe_Operations  
API access:  ReadWrite  

## Visualization
Display Format: {PrincipalRecipe.Name}  
Search Members: PrincipalRecipe.Name  
Name Member: PrincipalRecipe.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Technologies.PrincipalRecipes](Production.Technologies.PrincipalRecipes.md)  
Aggregate Root:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionalProperty<br />Description](Production.Technologies.PrincipalRecipeOperations.md#conditionalpropertydescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The desired description of the Conditional Property.  
| [ConditionalPropertyValue](Production.Technologies.PrincipalRecipeOperations.md#conditionalpropertyvalue) | string (254) __nullable__ | The desired value of the Conditional Property.  
| [LineOrd](Production.Technologies.PrincipalRecipeOperations.md#lineord) | int32 | Consecutive line number within the principal recipe.`Required` 
| [MinimumConcurrent<br />StartTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#minimumconcurrentstarttimeminutes) | int32 __nullable__ | How many minutes after the start of the previous operation can this operation start. NULL means that this operation should wait the previous operation to finish before starting 
| [MoveTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#movetimeminutes) | int32 | Time to move the lot to the next operation in minutes`Required` `Default(0)` `Filter(ge;le)` 
| [Notes](Production.Technologies.PrincipalRecipeOperations.md#notes) | string (254) __nullable__ | Notes for this PrincipalRecipeOperation. 
| [OperationDescription](Production.Technologies.PrincipalRecipeOperations.md#operationdescription) | string (max) __nullable__ | The description of the operation. Initially copied from the generic operation definition. 
| [RunTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#runtimeminutes) | int32 | Duration of the operation for one piece in the standard measurement unit of the product`Required` `Default(0)` `Filter(ge;le)` 
| [ScrapRate](Production.Technologies.PrincipalRecipeOperations.md#scraprate) | decimal (7, 6) | Standard rate of scrap during the operation`Required` `Default(0)` 
| [SetupTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#setuptimeminutes) | int32 | Time needed to setup the equipment`Required` `Default(0)` `Filter(ge;le)` 
| [Tooling](Production.Technologies.PrincipalRecipeOperations.md#tooling) | string (254) __nullable__ | The tools needed for the routing step 
| [UseQuantity](Production.Technologies.PrincipalRecipeOperations.md#usequantity) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity of the workgroup resource that should be allocated for the operation`Unit: UseQuantityUnit` `Required` `Default(1)` `Filter(ge;le)` 
| [WaitTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#waittimeminutes) | int32 | Wait time (drying, cooling, etc.) after the operation in minutes`Required` `Default(0)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionalProperty](Production.Technologies.PrincipalRecipeOperations.md#conditionalproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | When not NULL, specifies that, when creating recipe, the operation will be added only if this property is set for the main product |
| [Operation](Production.Technologies.PrincipalRecipeOperations.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | The generic operation definition. The data is copied locally and can be modified for this specific record. |
| [OperationInstruction](Production.Technologies.PrincipalRecipeOperations.md#operationinstruction) | [OperationInstructions](Production.Resources.OperationInstructions.md) (nullable) | Link to additional data, containing instructions in external format |
| [PrincipalRecipe](Production.Technologies.PrincipalRecipeOperations.md#principalrecipe) | [PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) | The <see cref="PrincipalRecipe"/> to which this PrincipalRecipeOperation belongs. `Required` `Filter(multi eq)` `Owner` |
| [UseQuantityUnit](Production.Technologies.PrincipalRecipeOperations.md#usequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Use_Quantity |
| [WorkgroupResource](Production.Technologies.PrincipalRecipeOperations.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) | Required workgroup resource for the operation. NULL means that no resource is required or the resource will be specified later |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Technologies.PrincipalRecipeOperations.md#id) | guid |  
| [ObjectVersion](Production.Technologies.PrincipalRecipeOperations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Technologies.PrincipalRecipeOperations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConditionalPropertyDescription

The desired description of the Conditional Property.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionalPropertyValue

The desired value of the Conditional Property.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### LineOrd

Consecutive line number within the principal recipe.`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.PrincipalRecipe.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.PrincipalRecipe.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### MinimumConcurrentStartTimeMinutes

How many minutes after the start of the previous operation can this operation start. NULL means that this operation should wait the previous operation to finish before starting

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MoveTimeMinutes

Time to move the lot to the next operation in minutes`Required` `Default(0)` `Filter(ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Operation.MoveTimeMinutes`
### Notes

Notes for this PrincipalRecipeOperation.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### OperationDescription

The description of the operation. Initially copied from the generic operation definition.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Operation.Description`
### RunTimeMinutes

Duration of the operation for one piece in the standard measurement unit of the product`Required` `Default(0)` `Filter(ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Operation.RunTimeMinutes`
### ScrapRate

Standard rate of scrap during the operation`Required` `Default(0)`

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### SetupTimeMinutes

Time needed to setup the equipment`Required` `Default(0)` `Filter(ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Operation.SetupTimeMinutes`
### Tooling

The tools needed for the routing step

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### UseQuantity

Quantity of the workgroup resource that should be allocated for the operation`Unit: UseQuantityUnit` `Required` `Default(1)` `Filter(ge;le)`

Type: **[Quantity (9, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Operation.UseQuantityBase`
### WaitTimeMinutes

Wait time (drying, cooling, etc.) after the operation in minutes`Required` `Default(0)` `Filter(ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Operation.WaitTimeMinutes`
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

### ConditionalProperty

When not NULL, specifies that, when creating recipe, the operation will be added only if this property is set for the main product

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Operation

The generic operation definition. The data is copied locally and can be modified for this specific record.

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

### PrincipalRecipe

The <see cref="PrincipalRecipe"/> to which this PrincipalRecipeOperation belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[PrincipalRecipes](Production.Technologies.PrincipalRecipes.md)**  
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

Front-End Recalc Expressions:  
`IIF( ( obj.WorkgroupResource.Resource != null), obj.WorkgroupResource.Resource.PrimaryUnit, obj.UseQuantityUnit)`
### WorkgroupResource

Required workgroup resource for the operation. NULL means that no resource is required or the resource will be specified later

Type: **[WorkgroupResources](Production.Resources.WorkgroupResources.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Operation.WorkgroupResource`

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

[!list limit=1000 erp.entity=Production.Technologies.PrincipalRecipeOperations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Technologies.PrincipalRecipeOperations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Technologies_PrincipalRecipeOperations

Domain API Entity Type: 
Production_Technologies_PrincipalRecipeOperation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Technologies_PrincipalRecipeOperations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Technologies_PrincipalRecipeOperations?$top=10>

