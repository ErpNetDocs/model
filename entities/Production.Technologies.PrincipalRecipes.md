---
uid: Production.Technologies.PrincipalRecipes
---
# Production.Technologies.PrincipalRecipes


List of base recipe models. Recipe models are used by the Product Configurator to create specific recipes.

## General
Namespace: [Production.Technologies](Production.Technologies.md)  
Repository: Production.Technologies.PrincipalRecipes  
Base Table: Prd_Principal_Recipes  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  
Aggregate Root:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DurationHour](Production.Technologies.PrincipalRecipes.md#durationhour) | decimal (10, 0) | The approximate duration of the operation (for the specified quantities) in seconds. This is pure operation time and excludes setup time. `Required` `Default(0)` 
| [ExpiryDate](Production.Technologies.PrincipalRecipes.md#expirydate) | datetime __nullable__ | The last date, when the recipe should be used. null means that there is no expiry date yet and the recipe model is still active. `Filter(ge;le)` 
| [Name](Production.Technologies.PrincipalRecipes.md#name) | string (64) | Name of the principal recipe. `Required` `Filter(like)` 
| [Notes](Production.Technologies.PrincipalRecipes.md#notes) | string (254) __nullable__ | User comments for the principal recipe. 
| [ProduceQuantity](Production.Technologies.PrincipalRecipes.md#producequantity) | [Quantity (18, 3)](../data-types.md#quantity) | Suggested quantity to produce. Usually it is equal to 1. `Unit: ProduceUnit` `Required` `Default(1)` `Filter(ge;le)` 
| [ReleaseDate](Production.Technologies.PrincipalRecipes.md#releasedate) | datetime | The date, when the recipe model is released for use. `Required` `Default(Today)` `Filter(ge;le)` 
| [ScrapRate](Production.Technologies.PrincipalRecipes.md#scraprate) | decimal (7, 6) | The percentage (0..1) of scrap usually occurring during the production operations. Specifying this leads to inflated requirements of all raw materials for the recipe. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProduceUnit](Production.Technologies.PrincipalRecipes.md#produceunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Produce_Quantity. The selected item must support the specified unit. `Required` `Filter(multi eq)` |
| [ProductGroup](Production.Technologies.PrincipalRecipes.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) | The production group, whose production is defined by the principal recipe . `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Technologies.PrincipalRecipes.md#id) | guid |  
| [ObjectVersion](Production.Technologies.PrincipalRecipes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Technologies.PrincipalRecipes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Ingredients | [PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) | List of `PrincipalRecipe<br />Ingredient`(Production.Technologies.PrincipalRecipeIngredients.md) child objects, based on the `Production.Technologies.PrincipalRecipeIngredient.PrincipalRecipe`(Production.Technologies.PrincipalRecipeIngredients.md#principalrecipe) back reference 
| Operations | [PrincipalRecipeOperations](Production.Technologies.PrincipalRecipeOperations.md) | List of `PrincipalRecipeOperation`(Production.Technologies.PrincipalRecipeOperations.md) child objects, based on the `Production.Technologies.PrincipalRecipeOperation.PrincipalRecipe`(Production.Technologies.PrincipalRecipeOperations.md#principalrecipe) back reference 


## Attribute Details

### DurationHour

The approximate duration of the operation (for the specified quantities) in seconds. This is pure operation time and excludes setup time. `Required` `Default(0)`

Type: **decimal (10, 0)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **CannotBeShown**  

### ExpiryDate

The last date, when the recipe should be used. null means that there is no expiry date yet and the recipe model is still active. `Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Name

Name of the principal recipe. `Required` `Filter(like)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Notes

User comments for the principal recipe.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ProduceQuantity

Suggested quantity to produce. Usually it is equal to 1. `Unit: ProduceUnit` `Required` `Default(1)` `Filter(ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ReleaseDate

The date, when the recipe model is released for use. `Required` `Default(Today)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### ScrapRate

The percentage (0..1) of scrap usually occurring during the production operations. Specifying this leads to inflated requirements of all raw materials for the recipe. `Required` `Default(0)`

Type: **decimal (7, 6)**  
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

### ProduceUnit

The measurement unit of Produce_Quantity. The selected item must support the specified unit. `Required` `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductGroup

The production group, whose production is defined by the principal recipe . `Required` `Filter(multi eq)` `Owner`

Type: **[ProductGroups](General.Products.ProductGroups.md)**  
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

[!list limit=1000 erp.entity=Production.Technologies.PrincipalRecipes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Technologies.PrincipalRecipes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Technologies_PrincipalRecipes

Domain API Entity Type: 
Production_Technologies_PrincipalRecipe

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Technologies_PrincipalRecipes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Technologies_PrincipalRecipes?$top=10>

