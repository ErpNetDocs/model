---
uid: Crm.Sales.DiscountTypes
---
# Crm.Sales.DiscountTypes Entity

**Namespace:** [Crm.Sales](Crm.Sales.md)  

Contains the different types of discounts, which can be applied to sales lines. Different types of discounts can be combined for a single sales line. Entity: Crm_Discount_Types

## Renames

Old name: **Crm.DiscountTypes**  
New name: **Crm.Sales.DiscountTypes**  
Version: **25.1.2.28**  
Case: **38176**  



## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Crm.Sales.DiscountTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Crm.Sales.DiscountTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Sales.DiscountTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Crm.Sales.DiscountTypes.md#id) | guid |  
| [IsSystem](Crm.Sales.DiscountTypes.md#issystem) | boolean | Specifies whether this discount type is created and managed by the system. `Required` `Default(false)` `Filter(multi eq)` 
| [Name](Crm.Sales.DiscountTypes.md#name) | string (254) | The name of this DiscountType. `Required` `Filter(like)` 
| [Notes](Crm.Sales.DiscountTypes.md#notes) | string (max) __nullable__ | Notes for this DiscountType. 
| [ObjectVersion](Crm.Sales.DiscountTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Ord](Crm.Sales.DiscountTypes.md#ord) | int32 | Determines the order in which the discounts are applied. The discounts with smaller Ord are applied first. `Required` `Default(1)` `Filter(ge;le)` 


## Attribute Details

### ActionType

Specifies the way the discount is applied over the previous discounts. `Required` `Default("A")` `Filter(multi eq)`

_Type_: **[ActionType](Crm.Sales.DiscountTypes.md#actiontype)**  
_Category_: **System**  
Allowed values for the `ActionType`(Crm.Sales.DiscountTypes.md#actiontype) data attribute  
_Allowed Values (Crm.Sales.DiscountTypesRepository.ActionType Enum Members)_  

| Value | Description |
| ---- | --- |
| Add | Add value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Add' |
| Replace | Replace value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Replace' |
| MarkDown | MarkDown value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'MarkDown' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Add**  
_Show in UI_: **ShownByDefault**  

### CalculationMethod

Specifies whether the calculation method of the discount is based on a standard discount, promotional package, bonus program, etc. `Required` `Filter(multi eq)`

_Type_: **[CalculationMethod](Crm.Sales.DiscountTypes.md#calculationmethod)**  
_Category_: **System**  
Allowed values for the `CalculationMethod`(Crm.Sales.DiscountTypes.md#calculationmethod) data attribute  
_Allowed Values (Crm.Sales.DiscountTypesRepository.CalculationMethod Enum Members)_  

| Value | Description |
| ---- | --- |
| StandardDiscount | StandardDiscount value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'StandardDiscount' |
| PromotionalPackage | PromotionalPackage value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'PromotionalPackage' |
| BonusProgram | BonusProgram value. Stored as 'B'. <br /> _Database Value:_ 'B' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'BonusProgram' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Code

The unique code of the DiscountType. `Required` `Filter(eq)`

_Type_: **string (32)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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
_Show in UI_: **ShownByDefault**  

### IsSystem

Specifies whether this discount type is created and managed by the system. `Required` `Default(false)` `Filter(multi eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

The name of this DiscountType. `Required` `Filter(like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this DiscountType.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Ord

Determines the order in which the discounts are applied. The discounts with smaller Ord are applied first. `Required` `Default(1)` `Filter(ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **1**  
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

