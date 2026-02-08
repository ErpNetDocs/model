---
uid: Production.Technologies.PrincipalRecipeIngredients
---
# Production.Technologies.PrincipalRecipeIngredients


Template for material usage of a principal recipe.

## General
Namespace: [Production.Technologies](Production.Technologies.md)  
Repository: Production.Technologies.PrincipalRecipeIngredients  
Base Table: Prd_Principal_Recipe_Ingredients  
API access:  ReadWrite  

## Visualization
Display Format: {IngredientName}  
Search Members: IngredientName  
Name Member: IngredientName  
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
| [ConditionalProperty<br />Description](Production.Technologies.PrincipalRecipeIngredients.md#conditionalpropertydescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | Description of the chosen conditional property value 
| [ConditionalPropertyValue](Production.Technologies.PrincipalRecipeIngredients.md#conditionalpropertyvalue) | string (254) __nullable__ | When not NULL, specifies that, when creating recipe, the ingredient will be added only if the main product property, specified in "Conditional Property" equals the specified value 
| [FixedScrapQuantity](Production.Technologies.PrincipalRecipeIngredients.md#fixedscrapquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Fixed scrap quantity for setup.`Unit: UsageUnit` `Required` `Default(0)` 
| [<s>IngredientId</s>](Production.Technologies.PrincipalRecipeIngredients.md#ingredientid) | guid | **OBSOLETE! Do not use!** The Id of the ingredient. When copying principal recipes, this Id remains the same for the new principal recipe to provide upgrade path for old recipes. `Obsolete` `Required` `Default(New Guid)` `Filter(multi eq)` `Obsoleted in version 22.1.6.61` 
| [IngredientName](Production.Technologies.PrincipalRecipeIngredients.md#ingredientname) | string (254) | The principal name of the ingredient.`Required` `Filter(like)` 
| [LineOrd](Production.Technologies.PrincipalRecipeIngredients.md#lineord) | int32 | The position of the line in the recipe model`Required` 
| [ScrapRate](Production.Technologies.PrincipalRecipeIngredients.md#scraprate) | decimal (7, 6) | The usual percentage (0..1) of scrap of the raw material; inflates the requirements of this material for this recipe.`Required` `Default(0)` `Filter(ge;le)` 
| [UsageQuantity](Production.Technologies.PrincipalRecipeIngredients.md#usagequantity) | [Quantity (18, 6)](../data-types.md#quantity) __nullable__ | Quantity to be consumed from the material. NULL means that the quantity is specified with formula`Unit: UsageUnit` `Default(1)` `Filter(ge;le)` 
| [UsageQuantityFormula](Production.Technologies.PrincipalRecipeIngredients.md#usagequantityformula) | string (max) __nullable__ | Specifies formula for the usage quantity. The formula can reference properties in [Property_Code] style, just like products name and description mask. The formula can contain *, /, + and - operators. The formula can also be simple number, directly specifying quantity`&amp;lt;Prop_Name&amp;gt;` style, just like products name and description mask. The formula can contain *, /, + and - operators. The formula can also be simple number, directly specifying quantity. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionalProperty](Production.Technologies.PrincipalRecipeIngredients.md#conditionalproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | When not NULL, specifies that, when creating recipe, the ingredient will be added only if this property is set for the main product |
| [ConditionalProperty<br />AllowedValue](Production.Technologies.PrincipalRecipeIngredients.md#conditionalpropertyallowedvalue) | [CustomPropertyAllowedValues](Systems.Bpm.CustomPropertyAllowedValues.md) (nullable) | When not NULL, specifies that, when creating recipe, the ingredient will be added only if the main product property, specified in "Conditional Property" equals the specified value |
| [DefaultMaterial](Production.Technologies.PrincipalRecipeIngredients.md#defaultmaterial) | [Products](General.Products.Products.md) (nullable) | If not NULL, points to default product for this ingredient |
| [DefaultStore](Production.Technologies.PrincipalRecipeIngredients.md#defaultstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The default store from which to retrieve the material. |
| [MaterialFromProperty](Production.Technologies.PrincipalRecipeIngredients.md#materialfromproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | When not NULL, specifies that the material will be obtained from the value of the specified property. The property must have allowed values in the Products domain. |
| [MaterialGroup](Production.Technologies.PrincipalRecipeIngredients.md#materialgroup) | [ProductGroups](General.Products.ProductGroups.md) | Filter for choosing specific material in the recipe (Gen_Product_Groups_Table) |
| [Operation](Production.Technologies.PrincipalRecipeIngredients.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | Specifies for which operation this ingredient will be used. |
| [PrincipalRecipe](Production.Technologies.PrincipalRecipeIngredients.md#principalrecipe) | [PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) | The <see cref="PrincipalRecipe"/> to which this PrincipalRecipeIngredient belongs. `Required` `Filter(multi eq)` `Owner` |
| [UsageUnit](Production.Technologies.PrincipalRecipeIngredients.md#usageunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Usage_Quantity. The selected item must support the specified unit |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Technologies.PrincipalRecipeIngredients.md#id) | guid | The Id of the recipe ingredient. This changes for each different line of each different recipe in contrast to the ingredient id, which might be the same for many principal recipes 
| [ObjectVersion](Production.Technologies.PrincipalRecipeIngredients.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Technologies.PrincipalRecipeIngredients.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConditionalPropertyDescription

Description of the chosen conditional property value

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConditionalPropertyValue

When not NULL, specifies that, when creating recipe, the ingredient will be added only if the main product property, specified in "Conditional Property" equals the specified value

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### FixedScrapQuantity

Fixed scrap quantity for setup.`Unit: UsageUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### IngredientId

**OBSOLETE! Do not use!** The Id of the ingredient. When copying principal recipes, this Id remains the same for the new principal recipe to provide upgrade path for old recipes. `Obsolete` `Required` `Default(New Guid)` `Filter(multi eq)` `Obsoleted in version 22.1.6.61`

Type: **guid**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### IngredientName

The principal name of the ingredient.`Required` `Filter(like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DefaultMaterial.Name`
### LineOrd

The position of the line in the recipe model`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.PrincipalRecipe.Ingredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.PrincipalRecipe.Ingredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### ScrapRate

The usual percentage (0..1) of scrap of the raw material; inflates the requirements of this material for this recipe.`Required` `Default(0)` `Filter(ge;le)`

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### UsageQuantity

Quantity to be consumed from the material. NULL means that the quantity is specified with formula`Unit: UsageUnit` `Default(1)` `Filter(ge;le)`

Type: **[Quantity (18, 6)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.UsageQuantityFormula != null), null, obj.UsageQuantity)`
### UsageQuantityFormula

Specifies formula for the usage quantity. The formula can reference properties in [Property_Code] style, just like products name and description mask. The formula can contain *, /, + and - operators. The formula can also be simple number, directly specifying quantity`&amp;lt;Prop_Name&amp;gt;` style, just like products name and description mask. The formula can contain *, /, + and - operators. The formula can also be simple number, directly specifying quantity.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.UsageQuantity != null), null, obj.UsageQuantityFormula)`
### Id

The Id of the recipe ingredient. This changes for each different line of each different recipe in contrast to the ingredient id, which might be the same for many principal recipes

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

When not NULL, specifies that, when creating recipe, the ingredient will be added only if this property is set for the main product

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConditionalPropertyAllowedValue

When not NULL, specifies that, when creating recipe, the ingredient will be added only if the main product property, specified in "Conditional Property" equals the specified value

Type: **[CustomPropertyAllowedValues](Systems.Bpm.CustomPropertyAllowedValues.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### DefaultMaterial

If not NULL, points to default product for this ingredient

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultStore

The default store from which to retrieve the material.

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MaterialFromProperty

When not NULL, specifies that the material will be obtained from the value of the specified property. The property must have allowed values in the Products domain.

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MaterialGroup

Filter for choosing specific material in the recipe (Gen_Product_Groups_Table)

Type: **[ProductGroups](General.Products.ProductGroups.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Operation

Specifies for which operation this ingredient will be used.

Type: **[Operations](Production.Resources.Operations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PrincipalRecipe

The <see cref="PrincipalRecipe"/> to which this PrincipalRecipeIngredient belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[PrincipalRecipes](Production.Technologies.PrincipalRecipes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### UsageUnit

The measurement unit of Usage_Quantity. The selected item must support the specified unit

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DefaultMaterial.BaseUnit`

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

[!list limit=1000 erp.entity=Production.Technologies.PrincipalRecipeIngredients erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Technologies.PrincipalRecipeIngredients erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Technologies_PrincipalRecipeIngredients

Domain API Entity Type: 
Production_Technologies_PrincipalRecipeIngredient

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Technologies_PrincipalRecipeIngredients?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Technologies_PrincipalRecipeIngredients?$top=10>

