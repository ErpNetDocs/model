---
uid: Crm.Pricing.PromotionalPackageLines
---
# Crm.Pricing.PromotionalPackageLines


Detail records (lines) of promotional package definition

## General
Namespace: [Crm.Pricing](Crm.Pricing.md)  
Repository: Crm.Pricing.PromotionalPackageLines  
Base Table: Crm_Promotional_Package_Lines  
API access:  ReadWrite  

## Renames

Old name: Crm.PromotionalPackageLines  
New name: Crm.Pricing.PromotionalPackageLines  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {PromotionalPackage.Name}  
Search Members: PromotionalPackage.Name  
Name Member: PromotionalPackage.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Pricing.PromotionalPackages](Crm.Pricing.PromotionalPackages.md)  
Aggregate Root:  
[Crm.Pricing.PromotionalPackages](Crm.Pricing.PromotionalPackages.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [LineNumber](Crm.Pricing.PromotionalPackageLines.md#linenumber) | int32 | Consecutive line number 
| [Quantity](Crm.Pricing.PromotionalPackageLines.md#quantity) | [Quantity (9, 3)](../data-types.md#quantity) | The quantity of the product in the package in the base measurement unit of the Product. 
| [StandardDiscount<br />AdjustOrReplace](Crm.Pricing.PromotionalPackageLines.md#standarddiscountadjustorreplace) | [StandardDiscount<br />AdjustOrReplace](Crm.Pricing.PromotionalPackageLines.md#standarddiscountadjustorreplace) | Specifies the way in which to change the standard discount 
| [StandardDiscount<br />PercentAdjust](Crm.Pricing.PromotionalPackageLines.md#standarddiscountpercentadjust) | decimal (7, 6) | Specifies the amount of change (in percent) for the standard discount 
| [UnitPrice](Crm.Pricing.PromotionalPackageLines.md#unitprice) | [Amount (13, 5)](../data-types.md#amount) __nullable__ | When not null specifies directly unit price for the product. When NULL, the package specifies only discount 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Lot](Crm.Pricing.PromotionalPackageLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The Product lot number in the promotional package. |
| [Product](Crm.Pricing.PromotionalPackageLines.md#product) | [Products](General.Products.Products.md) | The product, which is included in the promotional package |
| [PromotionalPackage](Crm.Pricing.PromotionalPackageLines.md#promotionalpackage) | [PromotionalPackages](Crm.Pricing.PromotionalPackages.md) | The <see cref="Promotional<br />Package"/> to which this PromotionalPackageLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [UnitPriceCurrency](Crm.Pricing.PromotionalPackageLines.md#unitpricecurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Currency of the unit price. NULL if the package specifies only discount |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.PromotionalPackageLines.md#id) | guid |  
| [ObjectVersion](Crm.Pricing.PromotionalPackageLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Pricing.PromotionalPackageLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### LineNumber

Consecutive line number

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.PromotionalPackage.Lines.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.PromotionalPackage.Lines.Select( c => c.LineNumber).DefaultIfEmpty( 0).Max( ) + 1)`
### Quantity

The quantity of the product in the package in the base measurement unit of the Product.

Type: **[Quantity (9, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### StandardDiscountAdjustOrReplace

Specifies the way in which to change the standard discount

Type: **[StandardDiscount<br />AdjustOrReplace](Crm.Pricing.PromotionalPackageLines.md#standarddiscountadjustorreplace)**  
Category: **System**  
Allowed values for the `StandardDiscountAdjustOrReplace`(Crm.Pricing.PromotionalPackageLines.md#standarddiscountadjustorreplace) data attribute  
Allowed Values (Crm.Pricing.PromotionalPackageLinesRepository.StandardDiscountAdjustOrReplace Enum Members)  

| Value | Description |
| ---- | --- |
| Add | Add value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'Add' |
| Replace | Replace value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Replace' |
| MarkDown | MarkDown value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 2 <br /> Domain API Value: 'MarkDown' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Replace**  
Show in UI: **ShownByDefault**  

### StandardDiscountPercentAdjust

Specifies the amount of change (in percent) for the standard discount

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### UnitPrice

When not null specifies directly unit price for the product. When NULL, the package specifies only discount

Type: **[Amount (13, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
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

### Lot

The Product lot number in the promotional package.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product, which is included in the promotional package

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PromotionalPackage

The <see cref="PromotionalPackage"/> to which this PromotionalPackageLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[PromotionalPackages](Crm.Pricing.PromotionalPackages.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### UnitPriceCurrency

Currency of the unit price. NULL if the package specifies only discount

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
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

