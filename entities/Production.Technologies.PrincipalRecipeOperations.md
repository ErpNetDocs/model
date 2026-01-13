---
uid: Production.Technologies.PrincipalRecipeOperations
---
# Production.Technologies.PrincipalRecipeOperations Entity

**Namespace:** [Production.Technologies](Production.Technologies.md)  

Contains the operations within a principal recipe. Entity: Prd_Principal_Recipe_Operations

## Default Visualization
Default Display Text Format:  
_{PrincipalRecipe.Name}_  
Default Search Members:  
_PrincipalRecipe.Name_  
Name Data Member:  
_PrincipalRecipe.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Technologies.PrincipalRecipes](Production.Technologies.PrincipalRecipes.md)  
Aggregate Root:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionalProperty<br />Description](Production.Technologies.PrincipalRecipeOperations.md#conditionalpropertydescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The desired description of the Conditional Property. . 
| [ConditionalPropertyValue](Production.Technologies.PrincipalRecipeOperations.md#conditionalpropertyvalue) | string (254) __nullable__ | The desired value of the Conditional Property. . 
| [DisplayText](Production.Technologies.PrincipalRecipeOperations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.Technologies.PrincipalRecipeOperations.md#id) | guid |  
| [LineOrd](Production.Technologies.PrincipalRecipeOperations.md#lineord) | int32 | Consecutive line number within the principal recipe. `Required` 
| [MinimumConcurrent<br />StartTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#minimumconcurrentstarttimeminutes) | int32 __nullable__ | How many minutes after the start of the previous operation can this operation start. null means that this operation should wait the previous operation to finish before starting. 
| [MoveTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#movetimeminutes) | int32 | Time to move the lot to the next operation in minutes. `Required` `Default(0)` `Filter(ge;le)` 
| [Notes](Production.Technologies.PrincipalRecipeOperations.md#notes) | string (254) __nullable__ | Notes for this PrincipalRecipeOperation. 
| [ObjectVersion](Production.Technologies.PrincipalRecipeOperations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OperationDescription](Production.Technologies.PrincipalRecipeOperations.md#operationdescription) | string (max) __nullable__ | The description of the operation. Initially copied from the generic operation definition. 
| [RunTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#runtimeminutes) | int32 | Duration of the operation for one piece in the standard measurement unit of the product. `Required` `Default(0)` `Filter(ge;le)` 
| [ScrapRate](Production.Technologies.PrincipalRecipeOperations.md#scraprate) | decimal (7, 6) | Standard rate of scrap during the operation. `Required` `Default(0)` 
| [SetupTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#setuptimeminutes) | int32 | Time needed to setup the equipment. `Required` `Default(0)` `Filter(ge;le)` 
| [Tooling](Production.Technologies.PrincipalRecipeOperations.md#tooling) | string (254) __nullable__ | The tools needed for the routing step. 
| [UseQuantity](Production.Technologies.PrincipalRecipeOperations.md#usequantity) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity of the workgroup resource that should be allocated for the operation. `Unit: UseQuantityUnit` `Required` `Default(1)` `Filter(ge;le)` 
| [WaitTimeMinutes](Production.Technologies.PrincipalRecipeOperations.md#waittimeminutes) | int32 | Wait time (drying, cooling, etc.) after the operation in minutes. `Required` `Default(0)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionalProperty](Production.Technologies.PrincipalRecipeOperations.md#conditionalproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | When not null, specifies that, when creating recipe, the operation will be added only if this property is set for the main product. `Filter(multi eq)` |
| [Operation](Production.Technologies.PrincipalRecipeOperations.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | The generic operation definition. The data is copied locally and can be modified for this specific record. `Filter(multi eq)` |
| [OperationInstruction](Production.Technologies.PrincipalRecipeOperations.md#operationinstruction) | [OperationInstructions](Production.Resources.OperationInstructions.md) (nullable) | Link to additional data, containing instructions in external format. `Filter(multi eq)` |
| [PrincipalRecipe](Production.Technologies.PrincipalRecipeOperations.md#principalrecipe) | [PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) | The <see cref="PrincipalRecipe"/> to which this PrincipalRecipeOperation belongs. `Required` `Filter(multi eq)` `Owner` |
| [UseQuantityUnit](Production.Technologies.PrincipalRecipeOperations.md#usequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Use_Quantity. `Required` `Filter(multi eq)` |
| [WorkgroupResource](Production.Technologies.PrincipalRecipeOperations.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) | Required workgroup resource for the operation. null means that no resource is required or the resource will be specified later. `Required` `Filter(multi eq)` |


## Attribute Details

### ConditionalPropertyDescription

The desired description of the Conditional Property. .

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ConditionalPropertyValue

The desired value of the Conditional Property. .

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

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

### LineOrd

Consecutive line number within the principal recipe. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.PrincipalRecipe.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.PrincipalRecipe.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### MinimumConcurrentStartTimeMinutes

How many minutes after the start of the previous operation can this operation start. null means that this operation should wait the previous operation to finish before starting.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MoveTimeMinutes

Time to move the lot to the next operation in minutes. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Operation.MoveTimeMinutes`
### Notes

Notes for this PrincipalRecipeOperation.

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

### OperationDescription

The description of the operation. Initially copied from the generic operation definition.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Operation.Description`
### RunTimeMinutes

Duration of the operation for one piece in the standard measurement unit of the product. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Operation.RunTimeMinutes`
### ScrapRate

Standard rate of scrap during the operation. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### SetupTimeMinutes

Time needed to setup the equipment. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Operation.SetupTimeMinutes`
### Tooling

The tools needed for the routing step.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### UseQuantity

Quantity of the workgroup resource that should be allocated for the operation. `Unit: UseQuantityUnit` `Required` `Default(1)` `Filter(ge;le)`

_Type_: **[Quantity (9, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Operation.UseQuantityBase`
### WaitTimeMinutes

Wait time (drying, cooling, etc.) after the operation in minutes. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Operation.WaitTimeMinutes`

## Reference Details

### ConditionalProperty

When not null, specifies that, when creating recipe, the operation will be added only if this property is set for the main product. `Filter(multi eq)`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Operation

The generic operation definition. The data is copied locally and can be modified for this specific record. `Filter(multi eq)`

_Type_: **[Operations](Production.Resources.Operations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OperationInstruction

Link to additional data, containing instructions in external format. `Filter(multi eq)`

_Type_: **[OperationInstructions](Production.Resources.OperationInstructions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### PrincipalRecipe

The <see cref="PrincipalRecipe"/> to which this PrincipalRecipeOperation belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[PrincipalRecipes](Production.Technologies.PrincipalRecipes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### UseQuantityUnit

The measurement unit of Use_Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.WorkgroupResource.Resource != null), obj.WorkgroupResource.Resource.PrimaryUnit, obj.UseQuantityUnit)`
### WorkgroupResource

Required workgroup resource for the operation. null means that no resource is required or the resource will be specified later. `Required` `Filter(multi eq)`

_Type_: **[WorkgroupResources](Production.Resources.WorkgroupResources.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Operation.WorkgroupResource`

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

