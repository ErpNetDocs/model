---
uid: Crm.Pricing.PromotionalPackageLines
---
# Crm.Pricing.PromotionalPackageLines Entity

**Namespace:** [Crm.Pricing](Crm.Pricing.md)  

Detail records (lines) of promotional package definition. Entity: Crm_Promotional_Package_Lines

## Renames

Old name: **Crm.PromotionalPackageLines**  
New name: **Crm.Pricing.PromotionalPackageLines**  
Version: **25.1.1.36**  
Case: **37717**  



## Default Visualization
Default Display Text Format:  
_{PromotionalPackage.Name}_  
Default Search Members:  
_PromotionalPackage.Name_  
Name Data Member:  
_PromotionalPackage.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pricing.PromotionalPackages](Crm.Pricing.PromotionalPackages.md)  
Aggregate Root:  
[Crm.Pricing.PromotionalPackages](Crm.Pricing.PromotionalPackages.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Crm.Pricing.PromotionalPackageLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Pricing.PromotionalPackageLines.md#id) | guid |  
| [LineNumber](Crm.Pricing.PromotionalPackageLines.md#linenumber) | int32 | Consecutive line number. `Required` 
| [ObjectVersion](Crm.Pricing.PromotionalPackageLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Crm.Pricing.PromotionalPackageLines.md#quantity) | [Quantity (9, 3)](../data-types.md#quantity) | The quantity of the product in the package in the base measurement unit of the Product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(1)` `Filter(ge;le)` 
| [StandardDiscount<br />AdjustOrReplace](Crm.Pricing.PromotionalPackageLines.md#standarddiscountadjustorreplace) | [StandardDiscount<br />AdjustOrReplace](Crm.Pricing.PromotionalPackageLines.md#standarddiscountadjustorreplace) | Specifies standard discount change action: A=ADD, M=Mark down - apply after standard discount; R=REPLACE the standard discount. `Required` `Default("R")` 
| [StandardDiscount<br />PercentAdjust](Crm.Pricing.PromotionalPackageLines.md#standarddiscountpercentadjust) | decimal (7, 6) | The value of change (in percents) for the standard discount. `Required` `Default(0)` 
| [UnitPrice](Crm.Pricing.PromotionalPackageLines.md#unitprice) | [Amount (13, 5)](../data-types.md#amount) __nullable__ | When not null specifies directly unit price for the product. When null, the package specifies only discount. `Currency: UnitPriceCurrency` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Lot](Crm.Pricing.PromotionalPackageLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The Product lot number in the promotional package. `Filter(multi eq)` `Introduced in version 19.1` |
| [Product](Crm.Pricing.PromotionalPackageLines.md#product) | [Products](General.Products.Products.md) | The product, which is included in the promotional package. `Required` `Filter(multi eq)` |
| [PromotionalPackage](Crm.Pricing.PromotionalPackageLines.md#promotionalpackage) | [PromotionalPackages](Crm.Pricing.PromotionalPackages.md) | The <see cref="Promotional<br />Package"/> to which this PromotionalPackageLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [UnitPriceCurrency](Crm.Pricing.PromotionalPackageLines.md#unitpricecurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Currency of the unit price. null if the package specifies only discount. `Filter(multi eq)` |


## Attribute Details

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

### LineNumber

Consecutive line number. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.PromotionalPackage.Lines.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.PromotionalPackage.Lines.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The quantity of the product in the package in the base measurement unit of the Product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(1)` `Filter(ge;le)`

_Type_: **[Quantity (9, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### StandardDiscountAdjustOrReplace

Specifies standard discount change action: A=ADD, M=Mark down - apply after standard discount; R=REPLACE the standard discount. `Required` `Default("R")`

_Type_: **[StandardDiscount<br />AdjustOrReplace](Crm.Pricing.PromotionalPackageLines.md#standarddiscountadjustorreplace)**  
_Category_: **System**  
Allowed values for the `StandardDiscountAdjustOrReplace`(Crm.Pricing.PromotionalPackageLines.md#standarddiscountadjustorreplace) data attribute  
_Allowed Values (Crm.Pricing.PromotionalPackageLinesRepository.StandardDiscountAdjustOrReplace Enum Members)_  

| Value | Description |
| ---- | --- |
| Add | Add value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Add' |
| Replace | Replace value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Replace' |
| MarkDown | MarkDown value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'MarkDown' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Replace**  
_Show in UI_: **ShownByDefault**  

### StandardDiscountPercentAdjust

The value of change (in percents) for the standard discount. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### UnitPrice

When not null specifies directly unit price for the product. When null, the package specifies only discount. `Currency: UnitPriceCurrency`

_Type_: **[Amount (13, 5)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Lot

The Product lot number in the promotional package. `Filter(multi eq)` `Introduced in version 19.1`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product, which is included in the promotional package. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PromotionalPackage

The <see cref="PromotionalPackage"/> to which this PromotionalPackageLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[PromotionalPackages](Crm.Pricing.PromotionalPackages.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### UnitPriceCurrency

Currency of the unit price. null if the package specifies only discount. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pricing.PromotionalPackageLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.PromotionalPackageLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pricing_PromotionalPackageLines

Domain API Entity Type: 
Crm_Pricing_PromotionalPackageLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pricing_PromotionalPackageLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pricing_PromotionalPackageLines?$top=10>

