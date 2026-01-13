---
uid: Production.Technologies.RecipeIngredients
---
# Production.Technologies.RecipeIngredients Entity

**Namespace:** [Production.Technologies](Production.Technologies.md)  

Contains the materials of a recipe that make up the product. Entity: Prd_Recipe_Ingredients

## Default Visualization
Default Display Text Format:  
_{Recipe.Name}_  
Default Search Members:  
_Recipe.Name_  
Name Data Member:  
_Recipe.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Technologies.Recipes](Production.Technologies.Recipes.md)  
Aggregate Root:  
[Production.Technologies.Recipes](Production.Technologies.Recipes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Cost](Production.Technologies.RecipeIngredients.md#cost) | [Amount (18, 4)](../data-types.md#amount) | The cost of the specified quantity of the ingredient. `Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` `Filter(ge;le)` 
| [DisplayText](Production.Technologies.RecipeIngredients.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FixedScrapQuantity](Production.Technologies.RecipeIngredients.md#fixedscrapquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Fixed scrap quantity of the material, needed for setup. `Unit: UsageUnit` `Required` `Default(0)` 
| [Id](Production.Technologies.RecipeIngredients.md#id) | guid |  
| [LineOrd](Production.Technologies.RecipeIngredients.md#lineord) | int32 | The order of this line in the recipe. `Required` 
| [Notes](Production.Technologies.RecipeIngredients.md#notes) | string (254) __nullable__ | Notes for this RecipeIngredient. 
| [ObjectVersion](Production.Technologies.RecipeIngredients.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Price](Production.Technologies.RecipeIngredients.md#price) | [Amount (18, 4)](../data-types.md#amount) | Total price of the ingredient. `Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` `Filter(ge;le)` 
| [ScrapRate](Production.Technologies.RecipeIngredients.md#scraprate) | decimal (7, 6) | The usual percentage (0..1) of scrap of the raw material; inflates the requirements of this material for this recipe. `Required` `Default(0)` 
| [UnitCost](Production.Technologies.RecipeIngredients.md#unitcost) | [Amount (18, 6)](../data-types.md#amount) | Cost of 1 of Usage_Unit_Id. `Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` `Filter(ge;le)` 
| [UnitPrice](Production.Technologies.RecipeIngredients.md#unitprice) | [Amount (18, 6)](../data-types.md#amount) | Price for 1 of Usage_Unit_Id. `Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` `Filter(ge;le)` 
| [UsageQuantity](Production.Technologies.RecipeIngredients.md#usagequantity) | [Quantity (18, 6)](../data-types.md#quantity) __nullable__ | Quantity of the material, consumed in the operation. The measurement unit is the primary unit of Material_Item_Id. `Unit: UsageUnit` `Default(1.000)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Material](Production.Technologies.RecipeIngredients.md#material) | [Products](General.Products.Products.md) | The Id of the consumed material (Gen_Products_Table). `Required` `Filter(multi eq)` |
| [Operation](Production.Technologies.RecipeIngredients.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | Specifies for which operation this ingredient will be used. `Filter(multi eq)` |
| [PrincipalRecipeIngredient](Production.Technologies.RecipeIngredients.md#principalrecipeingredient) | [PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) (nullable) | The principal recipe ingredient which was used to create this recipe ingredient. null means that this ingredient is standalone, not created with principal recipe ingredient. `Filter(multi eq)` |
| [Recipe](Production.Technologies.RecipeIngredients.md#recipe) | [Recipes](Production.Technologies.Recipes.md) | The <see cref="Recipe"/> to which this RecipeIngredient belongs. `Required` `Filter(multi eq)` `Owner` |
| [Store](Production.Technologies.RecipeIngredients.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store from which to retrieve the material. `Filter(multi eq)` |
| [UsageUnit](Production.Technologies.RecipeIngredients.md#usageunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Usage_Quantity. The selected item must support the specified unit. `Required` `Filter(multi eq)` |


## Attribute Details

### Cost

The cost of the specified quantity of the ingredient. `Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` `Filter(ge;le)`

_Type_: **[Amount (18, 4)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FixedScrapQuantity

Fixed scrap quantity of the material, needed for setup. `Unit: UsageUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineOrd

The order of this line in the recipe. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Recipe.Ingredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.Recipe.Ingredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this RecipeIngredient.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Price

Total price of the ingredient. `Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` `Filter(ge;le)`

_Type_: **[Amount (18, 4)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ScrapRate

The usual percentage (0..1) of scrap of the raw material; inflates the requirements of this material for this recipe. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### UnitCost

Cost of 1 of Usage_Unit_Id. `Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` `Filter(ge;le)`

_Type_: **[Amount (18, 6)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### UnitPrice

Price for 1 of Usage_Unit_Id. `Currency: Recipe.Product.CostingCurrency` `Required` `Default(0)` `Filter(ge;le)`

_Type_: **[Amount (18, 6)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### UsageQuantity

Quantity of the material, consumed in the operation. The measurement unit is the primary unit of Material_Item_Id. `Unit: UsageUnit` `Default(1.000)` `Filter(ge;le)`

_Type_: **[Quantity (18, 6)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Material

The Id of the consumed material (Gen_Products_Table). `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Operation

Specifies for which operation this ingredient will be used. `Filter(multi eq)`

_Type_: **[Operations](Production.Resources.Operations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PrincipalRecipeIngredient

The principal recipe ingredient which was used to create this recipe ingredient. null means that this ingredient is standalone, not created with principal recipe ingredient. `Filter(multi eq)`

_Type_: **[PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### Recipe

The <see cref="Recipe"/> to which this RecipeIngredient belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Recipes](Production.Technologies.Recipes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Store

The store from which to retrieve the material. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### UsageUnit

The measurement unit of Usage_Quantity. The selected item must support the specified unit. `Required` `Filter(multi eq)`

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

