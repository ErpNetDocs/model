---
uid: Crm.Pricing.PricingModels
---
# Crm.Pricing.PricingModels


Pricing models are assigned to product groups and are used to automate creation of standard costs and prices and related price records

## General
Namespace: [Crm.Pricing](Crm.Pricing.md)  
Repository: Crm.Pricing.PricingModels  
Base Table: Crm_Pricing_Models  
API access:  ReadWrite  

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
* [Crm.Pricing.PricingModels](Crm.Pricing.PricingModels.md)  
  * [Crm.Pricing.PricingModelCosts](Crm.Pricing.PricingModelCosts.md)  
  * [Crm.Pricing.PricingModelPriceLists](Crm.Pricing.PricingModelPriceLists.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultMarginPercent](Crm.Pricing.PricingModels.md#defaultmarginpercent) | decimal (6, 5) | Default margin between standard cost and standard price. The margin is applied to the products when calculating standard price`Required` `Default(0)` 
| [IsActive](Crm.Pricing.PricingModels.md#isactive) | boolean | Indicates whether the current Pricing model is active.`Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18` 
| [Name](Crm.Pricing.PricingModels.md#name) | string (254) | The name of the pricing model`Required` `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Currency](Crm.Pricing.PricingModels.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency in which the prices will be calculated |
| [PurchasePriceList](Crm.Pricing.PricingModels.md#purchasepricelist) | [PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) | Purchase price list Id, which will be used to get the purchase price of the products |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.PricingModels.md#id) | guid |  
| [ObjectVersion](Crm.Pricing.PricingModels.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pricing.PricingModels.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pricing.PricingModels.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pricing.PricingModels.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pricing.PricingModels.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Costs | [PricingModelCosts](Crm.Pricing.PricingModelCosts.md) | List of `PricingModelCost`(Crm.Pricing.PricingModelCosts.md) child objects, based on the `Crm.Pricing.PricingModelCost.PricingModel`(Crm.Pricing.PricingModelCosts.md#pricingmodel) back reference 
| PriceLists | [PricingModelPriceLists](Crm.Pricing.PricingModelPriceLists.md) | List of `PricingModelPriceList`(Crm.Pricing.PricingModelPriceLists.md) child objects, based on the `Crm.Pricing.PricingModelPriceList.PricingModel`(Crm.Pricing.PricingModelPriceLists.md#pricingmodel) back reference 


## Attribute Details

### DefaultMarginPercent

Default margin between standard cost and standard price. The margin is applied to the products when calculating standard price`Required` `Default(0)`

Type: **decimal (6, 5)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current Pricing model is active.`Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

The name of the pricing model`Required` `Filter(eq;like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
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

### Currency

The currency in which the prices will be calculated

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchasePriceList

Purchase price list Id, which will be used to get the purchase price of the products

Type: **[PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md)**  
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

[!list limit=1000 erp.entity=Crm.Pricing.PricingModels erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.PricingModels erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pricing_PricingModels

Domain API Entity Type: 
Crm_Pricing_PricingModel

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pricing_PricingModels?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pricing_PricingModels?$top=10>

