---
uid: Production.Technologies.Recipes
---
# Production.Technologies.Recipes


Contains the characteristics of operations used to create products

## General
Namespace: [Production.Technologies](Production.Technologies.md)  
Repository: Production.Technologies.Recipes  
Base Table: Prd_Recipes  
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

Aggregate Tree  
* [Production.Technologies.Recipes](Production.Technologies.Recipes.md)  
  * [Production.Technologies.RecipeIngredients](Production.Technologies.RecipeIngredients.md)  
  * [Production.Technologies.RecipeOperations](Production.Technologies.RecipeOperations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTime](Production.Technologies.Recipes.md#creationtime) | datetime __nullable__ | Date and time when the Recipe was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](Production.Technologies.Recipes.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Recipe. `Filter(like)` `ReadOnly` 
| [ExpiryDate](Production.Technologies.Recipes.md#expirydate) | datetime __nullable__ | The last date, when the recipe should be used. NULL means that the recipe might still be in use 
| [IsDefault](Production.Technologies.Recipes.md#isdefault) | boolean | Default for period: Release_Date - Expiry_Date 
| [Name](Production.Technologies.Recipes.md#name) | string (64) | The name of the recipe. When there is only 1 recipe, it is often equal to the product name. However, when there are multiple recipes for one product, the name is used for diferentiation. 
| [Notes](Production.Technologies.Recipes.md#notes) | string (254) __nullable__ | User comments for the recipe 
| [Price](Production.Technologies.Recipes.md#price) | [Amount (18, 4)](../data-types.md#amount) | The price for the specified Produce_Quantity 
| [PricePerLot](Production.Technologies.Recipes.md#priceperlot) | [Amount (18, 4)](../data-types.md#amount) | Price for one lot of the product (according to Lot_Size_Quantity_Base) 
| [ProduceQuantity](Production.Technologies.Recipes.md#producequantity) | [Quantity (18, 3)](../data-types.md#quantity) | Lot size. This is the produced quantity in one production run. The quantity is measured in the primary unit of Product_Id 
| [ReleaseDate](Production.Technologies.Recipes.md#releasedate) | datetime | The date, when the recipe was released to production 
| [ScrapRate](Production.Technologies.Recipes.md#scraprate) | decimal (7, 6) | The percentage (0..1) of scrap usually occurring during the operation. Specifying this leads to inflated requirements of all raw materials for this recipe 
| [UpdateTime](Production.Technologies.Recipes.md#updatetime) | datetime __nullable__ | Date and time when the Recipe was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](Production.Technologies.Recipes.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Recipe. `Filter(like)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrencyDirectory](Production.Technologies.Recipes.md#currencydirectory) | [CurrencyDirectories](General.Currencies.CurrencyDirectories.md) (nullable) | Currency directory, which is used to convert the costs and prices of materials, operations and resources into the currency of the product. |
| [PrincipalRecipe](Production.Technologies.Recipes.md#principalrecipe) | [PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) (nullable) | The prinicipal recipe, used to create this recipe. NULL means that this recipe was created without the help of principal recipe |
| [Product](Production.Technologies.Recipes.md#product) | [Products](General.Products.Products.md) (nullable) | The Id of the produced product |
| [Store](Production.Technologies.Recipes.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store for which this technology is valid. The store is matched with the output store specified in the production order. When NULL, the technology is valid for all stores. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Technologies.Recipes.md#id) | guid | Unique recipe Id 
| [ObjectVersion](Production.Technologies.Recipes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Production.Technologies.Recipes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Production.Technologies.Recipes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Production.Technologies.Recipes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Production.Technologies.Recipes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Ingredients | [RecipeIngredients](Production.Technologies.RecipeIngredients.md) | List of `RecipeIngredient`(Production.Technologies.RecipeIngredients.md) child objects, based on the `Production.Technologies.RecipeIngredient.Recipe`(Production.Technologies.RecipeIngredients.md#recipe) back reference 
| Operations | [RecipeOperations](Production.Technologies.RecipeOperations.md) | List of `RecipeOperation`(Production.Technologies.RecipeOperations.md) child objects, based on the `Production.Technologies.RecipeOperation.Recipe`(Production.Technologies.RecipeOperations.md#recipe) back reference 


## Attribute Details

### CreationTime

Date and time when the Recipe was created. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Recipe. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### ExpiryDate

The last date, when the recipe should be used. NULL means that the recipe might still be in use

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsDefault

Default for period: Release_Date - Expiry_Date

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

The name of the recipe. When there is only 1 recipe, it is often equal to the product name. However, when there are multiple recipes for one product, the name is used for diferentiation.

Type: **string (64)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Notes

User comments for the recipe

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Price

The price for the specified Produce_Quantity

Type: **[Amount (18, 4)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### PricePerLot

Price for one lot of the product (according to Lot_Size_Quantity_Base)

Type: **[Amount (18, 4)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ProduceQuantity

Lot size. This is the produced quantity in one production run. The quantity is measured in the primary unit of Product_Id

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ReleaseDate

The date, when the recipe was released to production

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### ScrapRate

The percentage (0..1) of scrap usually occurring during the operation. Specifying this leads to inflated requirements of all raw materials for this recipe

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### UpdateTime

Date and time when the Recipe was last updated. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Recipe. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### Id

Unique recipe Id

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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### CurrencyDirectory

Currency directory, which is used to convert the costs and prices of materials, operations and resources into the currency of the product.

Type: **[CurrencyDirectories](General.Currencies.CurrencyDirectories.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PrincipalRecipe

The prinicipal recipe, used to create this recipe. NULL means that this recipe was created without the help of principal recipe

Type: **[PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The Id of the produced product

Type: **[Products](General.Products.Products.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Store

The store for which this technology is valid. The store is matched with the output store specified in the production order. When NULL, the technology is valid for all stores.

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
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

