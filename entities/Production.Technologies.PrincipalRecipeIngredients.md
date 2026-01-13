---
uid: Production.Technologies.PrincipalRecipeIngredients
---
# Production.Technologies.PrincipalRecipeIngredients Entity

**Namespace:** [Production.Technologies](Production.Technologies.md)  

Template for material usage of a principal recipe. Entity: Prd_Principal_Recipe_Ingredients

## Default Visualization
Default Display Text Format:  
_{IngredientName}_  
Default Search Members:  
_IngredientName_  
Name Data Member:  
_IngredientName_  
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
| [ConditionalProperty<br />Description](Production.Technologies.PrincipalRecipeIngredients.md#conditionalpropertydescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The desired description of Conditional Property in order for the template line to match. 
| [ConditionalPropertyValue](Production.Technologies.PrincipalRecipeIngredients.md#conditionalpropertyvalue) | string (254) __nullable__ | The desired value of Conditional Property in order for the template line to match. 
| [DisplayText](Production.Technologies.PrincipalRecipeIngredients.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FixedScrapQuantity](Production.Technologies.PrincipalRecipeIngredients.md#fixedscrapquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Fixed scrap quantity for setup. `Unit: UsageUnit` `Required` `Default(0)` 
| [Id](Production.Technologies.PrincipalRecipeIngredients.md#id) | guid |  
| [<s>IngredientId</s>](Production.Technologies.PrincipalRecipeIngredients.md#ingredientid) | guid | **OBSOLETE! Do not use!** The Id of the ingredient. When copying principal recipes, this Id remains the same for the new principal recipe to provide upgrade path for old recipes. `Obsolete` `Required` `Default(New Guid)` `Filter(multi eq)` `Obsoleted in version 22.1.6.61` 
| [IngredientName](Production.Technologies.PrincipalRecipeIngredients.md#ingredientname) | string (254) | The principal name of the ingredient. `Required` `Filter(like)` 
| [LineOrd](Production.Technologies.PrincipalRecipeIngredients.md#lineord) | int32 | The position of the line in the recipe model. `Required` 
| [ObjectVersion](Production.Technologies.PrincipalRecipeIngredients.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ScrapRate](Production.Technologies.PrincipalRecipeIngredients.md#scraprate) | decimal (7, 6) | The usual percentage (0..1) of scrap of the raw material; inflates the requirements of this material for this recipe. `Required` `Default(0)` `Filter(ge;le)` 
| [UsageQuantity](Production.Technologies.PrincipalRecipeIngredients.md#usagequantity) | [Quantity (18, 6)](../data-types.md#quantity) __nullable__ | Quantity to be consumed from the material. null means that the quantity is specified with formula. `Unit: UsageUnit` `Default(1)` `Filter(ge;le)` 
| [UsageQuantityFormula](Production.Technologies.PrincipalRecipeIngredients.md#usagequantityformula) | string (max) __nullable__ | Specifies formula for the usage quantity. The formula can reference properties in `&lt;Prop_Name&gt;` style, just like products name and description mask. The formula can contain *, /, + and - operators. The formula can also be simple number, directly specifying quantity. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConditionalProperty](Production.Technologies.PrincipalRecipeIngredients.md#conditionalproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | When not null, specifies that, when creating recipe, the ingredient will be added only if this property is set for the main product. `Filter(multi eq)` |
| [ConditionalProperty<br />AllowedValue](Production.Technologies.PrincipalRecipeIngredients.md#conditionalpropertyallowedvalue) | [CustomPropertyAllowedValues](Systems.Bpm.CustomPropertyAllowedValues.md) (nullable) | When not null, specifies that, when creating recipe, the ingredient will be added only if the main product property, specified in Conditional_Property_Id equals the specified value. `Filter(multi eq)` |
| [DefaultMaterial](Production.Technologies.PrincipalRecipeIngredients.md#defaultmaterial) | [Products](General.Products.Products.md) (nullable) | If not null, points to default product for this ingredient. `Filter(multi eq)` |
| [DefaultStore](Production.Technologies.PrincipalRecipeIngredients.md#defaultstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The default store from which to retrieve the material. `Filter(multi eq)` |
| [MaterialFromProperty](Production.Technologies.PrincipalRecipeIngredients.md#materialfromproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | When not null, specifies that the material will be obtained from the value of the specified property. The property must have allowed values in the Products domain. `Filter(multi eq)` |
| [MaterialGroup](Production.Technologies.PrincipalRecipeIngredients.md#materialgroup) | [ProductGroups](General.Products.ProductGroups.md) | Filter for choosing specific material in the recipe (Gen_Product_Groups_Table). `Required` `Filter(multi eq)` |
| [Operation](Production.Technologies.PrincipalRecipeIngredients.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | Specifies for which operation this ingredient will be used. `Filter(multi eq)` |
| [PrincipalRecipe](Production.Technologies.PrincipalRecipeIngredients.md#principalrecipe) | [PrincipalRecipes](Production.Technologies.PrincipalRecipes.md) | The <see cref="PrincipalRecipe"/> to which this PrincipalRecipeIngredient belongs. `Required` `Filter(multi eq)` `Owner` |
| [UsageUnit](Production.Technologies.PrincipalRecipeIngredients.md#usageunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Usage_Quantity. The selected item must support the specified unit. `Required` `Filter(multi eq)` |


## Attribute Details

### ConditionalPropertyDescription

The desired description of Conditional Property in order for the template line to match.

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ConditionalPropertyValue

The desired value of Conditional Property in order for the template line to match.

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

### FixedScrapQuantity

Fixed scrap quantity for setup. `Unit: UsageUnit` `Required` `Default(0)`

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

### IngredientId

**OBSOLETE! Do not use!** The Id of the ingredient. When copying principal recipes, this Id remains the same for the new principal recipe to provide upgrade path for old recipes. `Obsolete` `Required` `Default(New Guid)` `Filter(multi eq)` `Obsoleted in version 22.1.6.61`

_Type_: **guid**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IngredientName

The principal name of the ingredient. `Required` `Filter(like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.DefaultMaterial.Name`
### LineOrd

The position of the line in the recipe model. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.PrincipalRecipe.Ingredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.PrincipalRecipe.Ingredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ScrapRate

The usual percentage (0..1) of scrap of the raw material; inflates the requirements of this material for this recipe. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### UsageQuantity

Quantity to be consumed from the material. null means that the quantity is specified with formula. `Unit: UsageUnit` `Default(1)` `Filter(ge;le)`

_Type_: **[Quantity (18, 6)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.UsageQuantityFormula != null), null, obj.UsageQuantity)`
### UsageQuantityFormula

Specifies formula for the usage quantity. The formula can reference properties in `&lt;Prop_Name&gt;` style, just like products name and description mask. The formula can contain *, /, + and - operators. The formula can also be simple number, directly specifying quantity.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.UsageQuantity != null), null, obj.UsageQuantityFormula)`

## Reference Details

### ConditionalProperty

When not null, specifies that, when creating recipe, the ingredient will be added only if this property is set for the main product. `Filter(multi eq)`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ConditionalPropertyAllowedValue

When not null, specifies that, when creating recipe, the ingredient will be added only if the main product property, specified in Conditional_Property_Id equals the specified value. `Filter(multi eq)`

_Type_: **[CustomPropertyAllowedValues](Systems.Bpm.CustomPropertyAllowedValues.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### DefaultMaterial

If not null, points to default product for this ingredient. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DefaultStore

The default store from which to retrieve the material. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MaterialFromProperty

When not null, specifies that the material will be obtained from the value of the specified property. The property must have allowed values in the Products domain. `Filter(multi eq)`

_Type_: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MaterialGroup

Filter for choosing specific material in the recipe (Gen_Product_Groups_Table). `Required` `Filter(multi eq)`

_Type_: **[ProductGroups](General.Products.ProductGroups.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Operation

Specifies for which operation this ingredient will be used. `Filter(multi eq)`

_Type_: **[Operations](Production.Resources.Operations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PrincipalRecipe

The <see cref="PrincipalRecipe"/> to which this PrincipalRecipeIngredient belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[PrincipalRecipes](Production.Technologies.PrincipalRecipes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### UsageUnit

The measurement unit of Usage_Quantity. The selected item must support the specified unit. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.DefaultMaterial.BaseUnit`

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

