---
uid: Crm.Sales.DiscountTypes
---
# Crm.Sales.DiscountTypes


Discount Types define the classification and application rules for line discounts in sales documents. This data type specifies discount types that can be applied to sales order lines, including the discount level used in multi-level discounting. For each discount level, ERP.net selects one applicable discount and applies it to the line, while discounts from different levels can be combined (cascaded) to form the effective line discount.

## General
Namespace: [Crm.Sales](Crm.Sales.md)  
Repository: Crm.Sales.DiscountTypes  
Base Table: Crm_Discount_Types  
API access:  ReadWrite  

## Renames

Old name: Crm.DiscountTypes  
New name: Crm.Sales.DiscountTypes  
Version: 25.1.2.28  
Case: 38176  



## Visualization
Display Format: {Name}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  CannotBeShown  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Sales.DiscountTypes](Crm.Sales.DiscountTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActionType](Crm.Sales.DiscountTypes.md#actiontype) | [ActionType](Crm.Sales.DiscountTypes.md#actiontype) | Specifies the way the discount is applied over the previous discounts. `Required` `Default("A")` `Filter(multi eq)` 
| [CalculationMethod](Crm.Sales.DiscountTypes.md#calculationmethod) | [CalculationMethod](Crm.Sales.DiscountTypes.md#calculationmethod) | Specifies whether the calculation method of the discount is based on a standard discount, promotional package, bonus program, etc. `Required` `Filter(multi eq)` 
| [Code](Crm.Sales.DiscountTypes.md#code) | string (32) | The unique code of the DiscountType. `Required` `Filter(eq)` 
| [IsSystem](Crm.Sales.DiscountTypes.md#issystem) | boolean | Specifies whether this discount type is created and managed by the system. `Required` `Default(false)` `Filter(multi eq)` 
| [Name](Crm.Sales.DiscountTypes.md#name) | string (254) | The name of this DiscountType. `Required` `Filter(like)` 
| [Notes](Crm.Sales.DiscountTypes.md#notes) | string (max) __nullable__ | Notes for this DiscountType. 
| [Ord](Crm.Sales.DiscountTypes.md#ord) | int32 | Determines the order in which the discounts are applied. The discounts with smaller Ord are applied first. `Required` `Default(1)` `Filter(ge;le)` 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Sales.DiscountTypes.md#id) | guid |  
| [ObjectVersion](Crm.Sales.DiscountTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Sales.DiscountTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Sales.DiscountTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Sales.DiscountTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Sales.DiscountTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ActionType

Specifies the way the discount is applied over the previous discounts. `Required` `Default("A")` `Filter(multi eq)`

Type: **[ActionType](Crm.Sales.DiscountTypes.md#actiontype)**  
Category: **System**  
Allowed values for the `ActionType`(Crm.Sales.DiscountTypes.md#actiontype) data attribute  
Allowed Values (Crm.Sales.DiscountTypesRepository.ActionType Enum Members)  

| Value | Description |
| ---- | --- |
| Add | Add value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'Add' |
| Replace | Replace value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Replace' |
| MarkDown | MarkDown value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 2 <br /> Domain API Value: 'MarkDown' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Add**  
Show in UI: **ShownByDefault**  

### CalculationMethod

Specifies whether the calculation method of the discount is based on a standard discount, promotional package, bonus program, etc. `Required` `Filter(multi eq)`

Type: **[CalculationMethod](Crm.Sales.DiscountTypes.md#calculationmethod)**  
Category: **System**  
Allowed values for the `CalculationMethod`(Crm.Sales.DiscountTypes.md#calculationmethod) data attribute  
Allowed Values (Crm.Sales.DiscountTypesRepository.CalculationMethod Enum Members)  

| Value | Description |
| ---- | --- |
| StandardDiscount | StandardDiscount value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'StandardDiscount' |
| PromotionalPackage | PromotionalPackage value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'PromotionalPackage' |
| BonusProgram | BonusProgram value. Stored as 'B'. <br /> Database Value: 'B' <br /> Model Value: 2 <br /> Domain API Value: 'BonusProgram' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Code

The unique code of the DiscountType. `Required` `Filter(eq)`

Type: **string (32)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### IsSystem

Specifies whether this discount type is created and managed by the system. `Required` `Default(false)` `Filter(multi eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

The name of this DiscountType. `Required` `Filter(like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this DiscountType.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Ord

Determines the order in which the discounts are applied. The discounts with smaller Ord are applied first. `Required` `Default(1)` `Filter(ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

[!list limit=1000 erp.entity=Crm.Sales.DiscountTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Sales.DiscountTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Sales_DiscountTypes

Domain API Entity Type: 
Crm_Sales_DiscountType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Sales_DiscountTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Sales_DiscountTypes?$top=10>

