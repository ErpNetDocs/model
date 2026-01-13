---
uid: Production.Technologies.PrincipalRecipes
---
# Production.Technologies.PrincipalRecipes Entity

**Namespace:** [Production.Technologies](Production.Technologies.md)  

List of base recipe models. Recipe models are used by the Product Configurator to create specific recipes. Entity: Prd_Principal_Recipes

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

Aggregate Parent:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  
Aggregate Root:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Production.Technologies.PrincipalRecipes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DurationHour](Production.Technologies.PrincipalRecipes.md#durationhour) | decimal (10, 0) | The approximate duration of the operation (for the specified quantities) in seconds. This is pure operation time and excludes setup time. `Required` `Default(0)` 
| [ExpiryDate](Production.Technologies.PrincipalRecipes.md#expirydate) | datetime __nullable__ | The last date, when the recipe should be used. null means that there is no expiry date yet and the recipe model is still active. `Filter(ge;le)` 
| [Id](Production.Technologies.PrincipalRecipes.md#id) | guid |  
| [Name](Production.Technologies.PrincipalRecipes.md#name) | string (64) | Name of the principal recipe. `Required` `Filter(like)` 
| [Notes](Production.Technologies.PrincipalRecipes.md#notes) | string (254) __nullable__ | User comments for the principal recipe. 
| [ObjectVersion](Production.Technologies.PrincipalRecipes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProduceQuantity](Production.Technologies.PrincipalRecipes.md#producequantity) | [Quantity (18, 3)](../data-types.md#quantity) | Suggested quantity to produce. Usually it is equal to 1. `Unit: ProduceUnit` `Required` `Default(1)` `Filter(ge;le)` 
| [ReleaseDate](Production.Technologies.PrincipalRecipes.md#releasedate) | datetime | The date, when the recipe model is released for use. `Required` `Default(Today)` `Filter(ge;le)` 
| [ScrapRate](Production.Technologies.PrincipalRecipes.md#scraprate) | decimal (7, 6) | The percentage (0..1) of scrap usually occurring during the production operations. Specifying this leads to inflated requirements of all raw materials for the recipe. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProduceUnit](Production.Technologies.PrincipalRecipes.md#produceunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Produce_Quantity. The selected item must support the specified unit. `Required` `Filter(multi eq)` |
| [ProductGroup](Production.Technologies.PrincipalRecipes.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) | The production group, whose production is defined by the principal recipe . `Required` `Filter(multi eq)` `Owner` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Ingredients | [PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) | List of `PrincipalRecipe<br />Ingredient`(Production.Technologies.PrincipalRecipeIngredients.md) child objects, based on the `Production.Technologies.PrincipalRecipeIngredient.PrincipalRecipe`(Production.Technologies.PrincipalRecipeIngredients.md#principalrecipe) back reference 
| Operations | [PrincipalRecipeOperations](Production.Technologies.PrincipalRecipeOperations.md) | List of `PrincipalRecipeOperation`(Production.Technologies.PrincipalRecipeOperations.md) child objects, based on the `Production.Technologies.PrincipalRecipeOperation.PrincipalRecipe`(Production.Technologies.PrincipalRecipeOperations.md#principalrecipe) back reference 


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DurationHour

The approximate duration of the operation (for the specified quantities) in seconds. This is pure operation time and excludes setup time. `Required` `Default(0)`

_Type_: **decimal (10, 0)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **CannotBeShown**  

### ExpiryDate

The last date, when the recipe should be used. null means that there is no expiry date yet and the recipe model is still active. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Name

Name of the principal recipe. `Required` `Filter(like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Notes

User comments for the principal recipe.

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

### ProduceQuantity

Suggested quantity to produce. Usually it is equal to 1. `Unit: ProduceUnit` `Required` `Default(1)` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ReleaseDate

The date, when the recipe model is released for use. `Required` `Default(Today)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  
_Show in UI_: **ShownByDefault**  

### ScrapRate

The percentage (0..1) of scrap usually occurring during the production operations. Specifying this leads to inflated requirements of all raw materials for the recipe. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ProduceUnit

The measurement unit of Produce_Quantity. The selected item must support the specified unit. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductGroup

The production group, whose production is defined by the principal recipe . `Required` `Filter(multi eq)` `Owner`

_Type_: **[ProductGroups](General.Products.ProductGroups.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

