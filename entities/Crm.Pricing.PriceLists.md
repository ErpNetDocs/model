---
uid: Crm.Pricing.PriceLists
---
# Crm.Pricing.PriceLists


Price Lists are used to manage multiple price records, assign to customers, etc.

## General
Namespace: [Crm.Pricing](Crm.Pricing.md)  
Repository: Crm.Pricing.PriceLists  
Base Table: Crm_Price_Lists  
API access:  ReadWrite  

## Renames

Old name: Crm.PriceLists  
New name: Crm.Pricing.PriceLists  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pricing.PriceLists](Crm.Pricing.PriceLists.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AutoApplyDiscountLevel](Crm.Pricing.PriceLists.md#autoapplydiscountlevel) | [DiscountLevel](Crm.Pricing.PriceLists.md#autoapplydiscountlevel) | Indicates the level to which discounts are applied automatically. Increasing the level has performance implications. Discounts, higher than the specified level can also be applied, but must be selected manually by the users. Level 1 discounts are always calculated. 
| [Description](Crm.Pricing.PriceLists.md#description) | string (max) __nullable__ | The description of this PriceList. 
| [FromDate](Crm.Pricing.PriceLists.md#fromdate) | datetime __nullable__ | Starting validity of the price list 
| [IsActive](Crm.Pricing.PriceLists.md#isactive) | boolean | Indicates whether the current Price List is active. 
| [Name](Crm.Pricing.PriceLists.md#name) | string (50) | The name of this PriceList. `Required` `Filter(eq;like)` `ORD` 
| [ThruDate](Crm.Pricing.PriceLists.md#thrudate) | datetime __nullable__ | Ending validity of the price list 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Crm.Pricing.PriceLists.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this PriceList applies, or null if it is for all enterprise companies. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.PriceLists.md#id) | guid |  
| [ObjectVersion](Crm.Pricing.PriceLists.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pricing.PriceLists.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pricing.PriceLists.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pricing.PriceLists.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pricing.PriceLists.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AutoApplyDiscountLevel

Indicates the level to which discounts are applied automatically. Increasing the level has performance implications. Discounts, higher than the specified level can also be applied, but must be selected manually by the users. Level 1 discounts are always calculated.

Type: **[DiscountLevel](Crm.Pricing.PriceLists.md#autoapplydiscountlevel)**  
Category: **System**  
Allowed values for the `DiscountLevel`(Crm.Pricing.LineDiscounts.md#discountlevel) data attribute  
Allowed Values (Crm.Pricing.LineDiscountsRepository.DiscountLevel Enum Members)  

| Value | Description |
| ---- | --- |
| One | One value. Stored as '1'. <br /> Database Value: '1' <br /> Model Value: 0 <br /> Domain API Value: 'One' |
| Two | Two value. Stored as '2'. <br /> Database Value: '2' <br /> Model Value: 1 <br /> Domain API Value: 'Two' |
| Three | Three value. Stored as '3'. <br /> Database Value: '3' <br /> Model Value: 2 <br /> Domain API Value: 'Three' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **One**  
Show in UI: **ShownByDefault**  

### Description

The description of this PriceList.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### FromDate

Starting validity of the price list

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current Price List is active.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The name of this PriceList. `Required` `Filter(eq;like)` `ORD`

Type: **string (50)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### ThruDate

Ending validity of the price list

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### EnterpriseCompany

The Enterprise Company to which this PriceList applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Crm.Pricing.PriceLists erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.PriceLists erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pricing_PriceLists

Domain API Entity Type: 
Crm_Pricing_PriceList

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pricing_PriceLists?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pricing_PriceLists?$top=10>

