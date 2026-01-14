---
uid: Production.Technologies.Recipes
---
# Production.Technologies.Recipes Entity

**Namespace:** [Production.Technologies](Production.Technologies.md)  

Contains the characteristics of operations used to create products. Entity: Prd_Recipes

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Production.Technologies.Recipes](Production.Technologies.Recipes.md)  
  * [Production.Technologies.RecipeIngredients](Production.Technologies.RecipeIngredients.md)  
  * [Production.Technologies.RecipeOperations](Production.Technologies.RecipeOperations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Production.Technologies.Recipes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [CreationTime](Production.Technologies.Recipes.md#creationtime) | datetime __nullable__ | Date and time when the Recipe was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](Production.Technologies.Recipes.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Recipe. `Filter(like)` `ReadOnly` 
| [DisplayText](Production.Technologies.Recipes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExpiryDate](Production.Technologies.Recipes.md#expirydate) | datetime __nullable__ | The last date, when the recipe should be used. null means that the recipe might still be in use. `Filter(ge;le)` 
| [ExternalId](Production.Technologies.Recipes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Production.Technologies.Recipes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Production.Technologies.Recipes.md#id) | guid |  
| [IsDefault](Production.Technologies.Recipes.md#isdefault) | boolean | Default for period: Release_Date - Expiry_Date. `Required` `Default(false)` `Filter(eq)` 
| [Name](Production.Technologies.Recipes.md#name) | string (64) | The name of the recipe. When there is only 1 recipe, it is often equal to the product name. However, when there are multiple recipes for one product, the name is used for diferentiation. `Required` `Filter(like)` 
| [Notes](Production.Technologies.Recipes.md#notes) | string (254) __nullable__ | User comments for the recipe. 
| [ObjectVersion](Production.Technologies.Recipes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Price](Production.Technologies.Recipes.md#price) | [Amount (18, 4)](../data-types.md#amount) | The price for the specified Produce_Quantity. `Currency: Product.CostingCurrency` `Required` `Default(0)` 
| [PricePerLot](Production.Technologies.Recipes.md#priceperlot) | [Amount (18, 4)](../data-types.md#amount) | Price for one lot of the product (according to Lot_Size_Quantity_Base). `Currency: Product.CostingCurrency` `Required` `Default(0)` 
| [ProduceQuantity](Production.Technologies.Recipes.md#producequantity) | [Quantity (18, 3)](../data-types.md#quantity) | Lot size. This is the produced quantity in one production run. The quantity is measured in the primary unit of Product_Id. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(1)` 
| [ReleaseDate](Production.Technologies.Recipes.md#releasedate) | datetime | The date, when the recipe was released to production. `Required` `Default(Today)` `Filter(ge;le)` 
| [ScrapRate](Production.Technologies.Recipes.md#scraprate) | decimal (7, 6) | The percentage (0..1) of scrap usually occurring during the operation. Specifying this leads to inflated requirements of all raw materials for this recipe. `Required` `Default(0)` 
| [UpdateTime](Production.Technologies.Recipes.md#updatetime) | datetime __nullable__ | Date and time when the Recipe was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](Production.Technologies.Recipes.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Recipe. `Filter(like)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrencyDirectory](Production.Technologies.Recipes.md#currencydirectory) | [CurrencyDirectories](General.Currencies.CurrencyDirectories.md) (nullable) | Currency directory, which is used to convert the costs and prices of materials, operations and resources into the currency of the product. `Filter(multi eq)` |
| [PrincipalRecipe](Production.Technologies.Recipes.md#principalrecipe) | [PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) (nullable) | The prinicipal recipe, used to create this recipe. null means that this recipe was created without the help of principal recipe. `Filter(multi eq)` |
| [Product](Production.Technologies.Recipes.md#product) | [Products](General.Products.Products.md) (nullable) | The Id of the produced product. `Filter(multi eq)` |
| [Store](Production.Technologies.Recipes.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store for which this technology is valid. The store is matched with the output store specified in the production order. When null, the technology is valid for all stores. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Ingredients | [RecipeIngredients](Production.Technologies.RecipeIngredients.md) | List of `RecipeIngredient`(Production.Technologies.RecipeIngredients.md) child objects, based on the `Production.Technologies.RecipeIngredient.Recipe`(Production.Technologies.RecipeIngredients.md#recipe) back reference 
| Operations | [RecipeOperations](Production.Technologies.RecipeOperations.md) | List of `RecipeOperation`(Production.Technologies.RecipeOperations.md) child objects, based on the `Production.Technologies.RecipeOperation.Recipe`(Production.Technologies.RecipeOperations.md#recipe) back reference 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### CreationTime

Date and time when the Recipe was created. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Recipe. `Filter(like)` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExpiryDate

The last date, when the recipe should be used. null means that the recipe might still be in use. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
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

### IsDefault

Default for period: Release_Date - Expiry_Date. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

The name of the recipe. When there is only 1 recipe, it is often equal to the product name. However, when there are multiple recipes for one product, the name is used for diferentiation. `Required` `Filter(like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Notes

User comments for the recipe.

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

### Price

The price for the specified Produce_Quantity. `Currency: Product.CostingCurrency` `Required` `Default(0)`

_Type_: **[Amount (18, 4)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### PricePerLot

Price for one lot of the product (according to Lot_Size_Quantity_Base). `Currency: Product.CostingCurrency` `Required` `Default(0)`

_Type_: **[Amount (18, 4)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ProduceQuantity

Lot size. This is the produced quantity in one production run. The quantity is measured in the primary unit of Product_Id. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(1)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ReleaseDate

The date, when the recipe was released to production. `Required` `Default(Today)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  
_Show in UI_: **ShownByDefault**  

### ScrapRate

The percentage (0..1) of scrap usually occurring during the operation. Specifying this leads to inflated requirements of all raw materials for this recipe. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### UpdateTime

Date and time when the Recipe was last updated. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Recipe. `Filter(like)` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### CurrencyDirectory

Currency directory, which is used to convert the costs and prices of materials, operations and resources into the currency of the product. `Filter(multi eq)`

_Type_: **[CurrencyDirectories](General.Currencies.CurrencyDirectories.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PrincipalRecipe

The prinicipal recipe, used to create this recipe. null means that this recipe was created without the help of principal recipe. `Filter(multi eq)`

_Type_: **[PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The Id of the produced product. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Store

The store for which this technology is valid. The store is matched with the output store specified in the production order. When null, the technology is valid for all stores. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
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

[!list limit=1000 erp.entity=Production.Technologies.Recipes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Technologies.Recipes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Technologies_Recipes

Domain API Entity Type: 
Production_Technologies_Recipe

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Technologies_Recipes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Technologies_Recipes?$top=10>

