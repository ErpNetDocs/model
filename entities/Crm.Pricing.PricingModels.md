---
uid: Crm.Pricing.PricingModels
---
# Crm.Pricing.PricingModels Entity

**Namespace:** [Crm.Pricing](Crm.Pricing.md)  

Pricing models are assigned to product groups and are used to automate creation of standard costs and prices and related price records. Entity: Crm_Pricing_Models

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pricing.PricingModels](Crm.Pricing.PricingModels.md)  
  * [Crm.Pricing.PricingModelCosts](Crm.Pricing.PricingModelCosts.md)  
  * [Crm.Pricing.PricingModelPriceLists](Crm.Pricing.PricingModelPriceLists.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultMarginPercent](Crm.Pricing.PricingModels.md#defaultmarginpercent) | decimal (6, 5) | Default margin between standard cost and standard price. The margin is applied to the products when calculating standard price. `Required` `Default(0)` 
| [DisplayText](Crm.Pricing.PricingModels.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Crm.Pricing.PricingModels.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pricing.PricingModels.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Crm.Pricing.PricingModels.md#id) | guid |  
| [IsActive](Crm.Pricing.PricingModels.md#isactive) | boolean | Indicates whether the current Pricing model is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18` 
| [Name](Crm.Pricing.PricingModels.md#name) | string (254) | The name of the pricing model. `Required` `Filter(eq;like)` 
| [ObjectVersion](Crm.Pricing.PricingModels.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Currency](Crm.Pricing.PricingModels.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency in which the prices will be calculated. `Required` `Filter(multi eq)` |
| [PurchasePriceList](Crm.Pricing.PricingModels.md#purchasepricelist) | [PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) | Purchase price list Id, which will be used to get the purchase price of the products. `Required` `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Costs | [PricingModelCosts](Crm.Pricing.PricingModelCosts.md) | List of `PricingModelCost`(Crm.Pricing.PricingModelCosts.md) child objects, based on the `Crm.Pricing.PricingModelCost.PricingModel`(Crm.Pricing.PricingModelCosts.md#pricingmodel) back reference 
| PriceLists | [PricingModelPriceLists](Crm.Pricing.PricingModelPriceLists.md) | List of `PricingModelPriceList`(Crm.Pricing.PricingModelPriceLists.md) child objects, based on the `Crm.Pricing.PricingModelPriceList.PricingModel`(Crm.Pricing.PricingModelPriceLists.md#pricingmodel) back reference 


## Attribute Details

### DefaultMarginPercent

Default margin between standard cost and standard price. The margin is applied to the products when calculating standard price. `Required` `Default(0)`

_Type_: **decimal (6, 5)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
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
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the current Pricing model is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

The name of the pricing model. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
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


## Reference Details

### Currency

The currency in which the prices will be calculated. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchasePriceList

Purchase price list Id, which will be used to get the purchase price of the products. `Required` `Filter(multi eq)`

_Type_: **[PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md)**  
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

