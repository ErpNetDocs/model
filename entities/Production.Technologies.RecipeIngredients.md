---
uid: Production.Technologies.RecipeIngredients
---
# Production.Technologies.RecipeIngredients


Contains the materials of a recipe that make up the product

## General
Namespace: [Production.Technologies](Production.Technologies.md)  
Repository: Production.Technologies.RecipeIngredients  
Base Table: Prd_Recipe_Ingredients  
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
| [Cost](Production.Technologies.RecipeIngredients.md#cost) | [Amount (18, 4)](../data-types.md#amount) | The cost of the specified quantity of the ingredient 
| [FixedScrapQuantity](Production.Technologies.RecipeIngredients.md#fixedscrapquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Fixed scrap quantity for setup. 
| [LineOrd](Production.Technologies.RecipeIngredients.md#lineord) | int32 | The order of this line in the recipe. 
| [Notes](Production.Technologies.RecipeIngredients.md#notes) | string (254) __nullable__ | Notes for this RecipeIngredient. 
| [Price](Production.Technologies.RecipeIngredients.md#price) | [Amount (18, 4)](../data-types.md#amount) | Total price of the ingredient 
| [ScrapRate](Production.Technologies.RecipeIngredients.md#scraprate) | decimal (7, 6) | The usual percentage (0..1) of scrap of the raw material; inflates the requirements of this material for this recipe 
| [UnitCost](Production.Technologies.RecipeIngredients.md#unitcost) | [Amount (18, 6)](../data-types.md#amount) | Cost of 1 of Usage_Unit_Id 
| [UnitPrice](Production.Technologies.RecipeIngredients.md#unitprice) | [Amount (18, 6)](../data-types.md#amount) | Price for 1 of Usage_Unit_Id 
| [UsageQuantity](Production.Technologies.RecipeIngredients.md#usagequantity) | [Quantity (18, 6)](../data-types.md#quantity) __nullable__ | Quantity of the material, consumed in the operation. The measurement unit is the primary unit of Material_Item_Id. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Material](Production.Technologies.RecipeIngredients.md#material) | [Products](General.Products.Products.md) | The Id of the consumed material (Gen_Products_Table) |
| [Operation](Production.Technologies.RecipeIngredients.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | Specifies for which operation this ingredient will be used. |
| [PrincipalRecipeIngredient](Production.Technologies.RecipeIngredients.md#principalrecipeingredient) | [PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) (nullable) | The principal recipe ingredient which was used to create this recipe ingredient. NULL means that this ingredient is standalone, not created with principal recipe ingredient |
| [Recipe](Production.Technologies.RecipeIngredients.md#recipe) | [Recipes](Production.Technologies.Recipes.md) | The <see cref="Recipe"/> to which this RecipeIngredient belongs. `Required` `Filter(multi eq)` `Owner` |
| [Store](Production.Technologies.RecipeIngredients.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store from which to retrieve the material. |
| [UsageUnit](Production.Technologies.RecipeIngredients.md#usageunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Usage_Quantity. The selected item must support the specified unit |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Technologies.RecipeIngredients.md#id) | guid |  
| [ObjectVersion](Production.Technologies.RecipeIngredients.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Technologies.RecipeIngredients.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Cost

The cost of the specified quantity of the ingredient

Type: **[Amount (18, 4)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### FixedScrapQuantity

Fixed scrap quantity for setup.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### LineOrd

The order of this line in the recipe.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Recipe.Ingredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.Recipe.Ingredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this RecipeIngredient.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### Price

Total price of the ingredient

Type: **[Amount (18, 4)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ScrapRate

The usual percentage (0..1) of scrap of the raw material; inflates the requirements of this material for this recipe

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### UnitCost

Cost of 1 of Usage_Unit_Id

Type: **[Amount (18, 6)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### UnitPrice

Price for 1 of Usage_Unit_Id

Type: **[Amount (18, 6)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### UsageQuantity

Quantity of the material, consumed in the operation. The measurement unit is the primary unit of Material_Item_Id.

Type: **[Quantity (18, 6)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
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

### Material

The Id of the consumed material (Gen_Products_Table)

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Operation

Specifies for which operation this ingredient will be used.

Type: **[Operations](Production.Resources.Operations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PrincipalRecipeIngredient

The principal recipe ingredient which was used to create this recipe ingredient. NULL means that this ingredient is standalone, not created with principal recipe ingredient

Type: **[PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### Recipe

The <see cref="Recipe"/> to which this RecipeIngredient belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Recipes](Production.Technologies.Recipes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Store

The store from which to retrieve the material.

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### UsageUnit

The measurement unit of Usage_Quantity. The selected item must support the specified unit

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

[!list limit=1000 erp.entity=Production.Technologies.RecipeIngredients erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Technologies.RecipeIngredients erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Technologies_RecipeIngredients

Domain API Entity Type: 
Production_Technologies_RecipeIngredient

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Technologies_RecipeIngredients?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Technologies_RecipeIngredients?$top=10>

