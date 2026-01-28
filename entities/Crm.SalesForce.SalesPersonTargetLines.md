---
uid: Crm.SalesForce.SalesPersonTargetLines
---
# Crm.SalesForce.SalesPersonTargetLines


Detail records (lines) of targets for sales persons.

## General
Namespace: [Crm.SalesForce](Crm.SalesForce.md)  
Repository: Crm.SalesForce.SalesPersonTargetLines  
Base Table: Crm_Sales_Person_Target_Lines  
API access:  ReadWrite  

## Renames

Old name: Crm.Distribution.SalesPersonTargetLines  
New name: Crm.SalesForce.SalesPersonTargetLines  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {PeriodYear}-{PeriodMonth} {TargetType}  
Search Members: SalesPersonTarget.DocumentNo  
Name Member: SalesPersonTarget.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.SalesForce.SalesPersonTargets](Crm.SalesForce.SalesPersonTargets.md)  
Aggregate Root:  
[Crm.SalesForce.SalesPersonTargets](Crm.SalesForce.SalesPersonTargets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [PeriodDate](Crm.SalesForce.SalesPersonTargetLines.md#perioddate) | datetime | Calculated date representation of the target period (used for grouping, filtering and other auxiliary purposes). `Required` `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.1.43` 
| [PeriodMonth](Crm.SalesForce.SalesPersonTargetLines.md#periodmonth) | byte | Month of the period in which the target must be fulfilled (the period is determined by specifying a month and an year). `Required` `Filter(ge;le)` 
| [PeriodYear](Crm.SalesForce.SalesPersonTargetLines.md#periodyear) | int16 | Year of the period in which the target must be fulfilled (the period is determined by specifying a month and an year). `Required` `Filter(ge;le)` 
| [TargetAmount](Crm.SalesForce.SalesPersonTargetLines.md#targetamount) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | Target amount to be fulfilled by the specified sales person. Deprecated - use Target_Value. `Currency: TargetAmountCurrency` 
| [TargetType](Crm.SalesForce.SalesPersonTargetLines.md#targettype) | [TargetType](Crm.SalesForce.SalesPersonTargetLines.md#targettype) | Type of target. Defines the meaning of Target_Value. SALES-sales amount, BONUS-count of bonus progs, PACK-count of promo packs. `Required` `Default("SALES")` `Filter(multi eq)` 
| [TargetValue](Crm.SalesForce.SalesPersonTargetLines.md#targetvalue) | decimal (9, 2) | Value of target. Meaning depends on target type. `Required` `Default(0)` 
| [TargetWeight](Crm.SalesForce.SalesPersonTargetLines.md#targetweight) | decimal (5, 2) | Relative weight of target, comparatively to other targets. `Required` `Default(1)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BonusProgram](Crm.SalesForce.SalesPersonTargetLines.md#bonusprogram) | [BonusPrograms](Crm.Pricing.BonusPrograms.md) (nullable) | Bonus program Id when the target type is BONUS, null otherwise. `Filter(multi eq)` |
| [Document](Crm.SalesForce.SalesPersonTargetLines.md#document) | [SalesPersonTargets](Crm.SalesForce.SalesPersonTargets.md) | The owner document. The <see cref="SalesPersonTarget"/> to which this SalesPersonTargetLine belongs. `Required` `Filter(multi eq)` |
| [ProductGroup](Crm.SalesForce.SalesPersonTargetLines.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | Product group for which the target is defined. `Filter(multi eq)` |
| [PromotionalPackage](Crm.SalesForce.SalesPersonTargetLines.md#promotionalpackage) | [PromotionalPackages](Crm.Pricing.PromotionalPackages.md) (nullable) | Promotional Package Id when the target type is PROMO, null otherwise. `Filter(multi eq)` |
| [SalesPerson](Crm.SalesForce.SalesPersonTargetLines.md#salesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) | Sales person to whom the target is assigned. `Required` `Filter(multi eq)` |
| [SalesPersonTarget](Crm.SalesForce.SalesPersonTargetLines.md#salespersontarget) | [SalesPersonTargets](Crm.SalesForce.SalesPersonTargets.md) | The <see cref="SalesPersonTarget"/> to which this SalesPersonTargetLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [TargetAmountCurrency](Crm.SalesForce.SalesPersonTargetLines.md#targetamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Deprecated - use currency in document header. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.SalesForce.SalesPersonTargetLines.md#id) | guid |  
| [ObjectVersion](Crm.SalesForce.SalesPersonTargetLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.SalesForce.SalesPersonTargetLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### PeriodDate

Calculated date representation of the target period (used for grouping, filtering and other auxiliary purposes). `Required` `Filter(ge;le)` `ReadOnly` `Introduced in version 25.1.1.43`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PeriodMonth

Month of the period in which the target must be fulfilled (the period is determined by specifying a month and an year). `Required` `Filter(ge;le)`

Type: **byte**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PeriodYear

Year of the period in which the target must be fulfilled (the period is determined by specifying a month and an year). `Required` `Filter(ge;le)`

Type: **int16**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TargetAmount

Target amount to be fulfilled by the specified sales person. Deprecated - use Target_Value. `Currency: TargetAmountCurrency`

Type: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### TargetType

Type of target. Defines the meaning of Target_Value. SALES-sales amount, BONUS-count of bonus progs, PACK-count of promo packs. `Required` `Default("SALES")` `Filter(multi eq)`

Type: **[TargetType](Crm.SalesForce.SalesPersonTargetLines.md#targettype)**  
Category: **System**  
Allowed values for the `TargetType`(Crm.SalesForce.SalesPersonTargetLines.md#targettype) data attribute  
Allowed Values (Crm.SalesForce.SalesPersonTargetLinesRepository.TargetType Enum Members)  

| Value | Description |
| ---- | --- |
| SalesAmount | SalesAmount value. Stored as 'SALES'. <br /> Database Value: 'SALES' <br /> Model Value: 0 <br /> Domain API Value: 'SalesAmount' |
| NumberOfApplied<br />BonusPrograms | NumberOfApplied<br />BonusPrograms value. Stored as 'BONUS'. <br /> Database Value: 'BONUS' <br /> Model Value: 1 <br /> Domain API Value: 'NumberOfApplied<br />BonusPrograms' |
| NumberOfPromotional<br />Packages | NumberOfPromotional<br />Packages value. Stored as 'PROMO'. <br /> Database Value: 'PROMO' <br /> Model Value: 2 <br /> Domain API Value: 'NumberOfPromotional<br />Packages' |
| LocationsCount | LocationsCount value. Stored as 'LOCNT'. <br /> Database Value: 'LOCNT' <br /> Model Value: 3 <br /> Domain API Value: 'LocationsCount' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **SalesAmount**  
Show in UI: **ShownByDefault**  

### TargetValue

Value of target. Meaning depends on target type. `Required` `Default(0)`

Type: **decimal (9, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### TargetWeight

Relative weight of target, comparatively to other targets. `Required` `Default(1)`

Type: **decimal (5, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
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

### BonusProgram

Bonus program Id when the target type is BONUS, null otherwise. `Filter(multi eq)`

Type: **[BonusPrograms](Crm.Pricing.BonusPrograms.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Document

The owner document. The <see cref="SalesPersonTarget"/> to which this SalesPersonTargetLine belongs. `Required` `Filter(multi eq)`

Type: **[SalesPersonTargets](Crm.SalesForce.SalesPersonTargets.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductGroup

Product group for which the target is defined. `Filter(multi eq)`

Type: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SalesPersonTarget.ProductGroup`

Front-End Recalc Expressions:  
`obj.SalesPersonTarget.ProductGroup`
### PromotionalPackage

Promotional Package Id when the target type is PROMO, null otherwise. `Filter(multi eq)`

Type: **[PromotionalPackages](Crm.Pricing.PromotionalPackages.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SalesPerson

Sales person to whom the target is assigned. `Required` `Filter(multi eq)`

Type: **[SalesPersons](Crm.SalesForce.SalesPersons.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SalesPersonTarget.SalesPerson`

Front-End Recalc Expressions:  
`obj.SalesPersonTarget.SalesPerson`
### SalesPersonTarget

The <see cref="SalesPersonTarget"/> to which this SalesPersonTargetLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[SalesPersonTargets](Crm.SalesForce.SalesPersonTargets.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### TargetAmountCurrency

Deprecated - use currency in document header. `Filter(multi eq)`

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SalesPersonTarget.TargetCurrency`

Front-End Recalc Expressions:  
`obj.SalesPersonTarget.TargetCurrency`

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

[!list limit=1000 erp.entity=Crm.SalesForce.SalesPersonTargetLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.SalesForce.SalesPersonTargetLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_SalesForce_SalesPersonTargetLines

Domain API Entity Type: 
Crm_SalesForce_SalesPersonTargetLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_SalesForce_SalesPersonTargetLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_SalesForce_SalesPersonTargetLines?$top=10>

