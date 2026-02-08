---
uid: Logistics.Procurement.PurchaseProductPrices
---
# Logistics.Procurement.PurchaseProductPrices


Contains purchase prices of the products. Used for automatically loading unit prices in the purchase documents.

## General
Namespace: [Logistics.Procurement](Logistics.Procurement.md)  
Repository: Logistics.Procurement.PurchaseProductPrices  
Base Table: Scm_Purchase_Product_Prices  
API access:  ReadWrite  

## Visualization
Display Format: {Price} - {FromDate}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Procurement.PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FromDate](Logistics.Procurement.PurchaseProductPrices.md#fromdate) | datetime __nullable__ | Starting date of validity of the price. Usually used for temporary promotions.`Filter(eq;ge;le)` 
| [MaxQuantity](Logistics.Procurement.PurchaseProductPrices.md#maxquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Maximum quantity for which is valid this price (in the price quantity measurement unit).`Unit: PriceQuantityMeasurement<br />Unit` `Filter(eq)` 
| [MinQuantity](Logistics.Procurement.PurchaseProductPrices.md#minquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Minimal quantity required to use this price (in the price quantity measurement unit).`Unit: PriceQuantityMeasurement<br />Unit` `Filter(eq)` 
| [Notes](Logistics.Procurement.PurchaseProductPrices.md#notes) | string (254) __nullable__ | Notes for this PurchaseProductPrice. 
| [Price](Logistics.Procurement.PurchaseProductPrices.md#price) | [Amount (13, 5)](../data-types.md#amount) | Price in the specified currency and for the specified quantity. This price is used only when the other conditions in this record are satisfied.`Currency: Currency` `Required` `Default(0)` 
| [PriceQuantity](Logistics.Procurement.PurchaseProductPrices.md#pricequantity) | [Quantity (10, 3)](../data-types.md#quantity) | The quantity of the product for which the price is specified.`Unit: PriceQuantityMeasurement<br />Unit` `Required` `Default(1)` 
| [Priority](Logistics.Procurement.PurchaseProductPrices.md#priority) | [Priority](Logistics.Procurement.PurchaseProductPrices.md#priority) | Priority of the price comparative to other prices valid for current document.`Required` `Default(2)` `Filter(multi eq)` 
| [ThruDate](Logistics.Procurement.PurchaseProductPrices.md#thrudate) | datetime __nullable__ | Ending date (inclusive) of the validity of the price. Usually used for temporary promotions.`Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Currency](Logistics.Procurement.PurchaseProductPrices.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency of the specified price. |
| [EnterpriseCompany](Logistics.Procurement.PurchaseProductPrices.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Determines for which enterprise company this price is used. If not specified the price is used for all enterprise companies. |
| [EnterpriseCompanyLocation](Logistics.Procurement.PurchaseProductPrices.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | Specifies the Enterprise Company Location for which the price is valid for. If the field is blank, the price is valid for all Enterprise Company Locations. |
| [PriceQuantityMeasurement<br />Unit](Logistics.Procurement.PurchaseProductPrices.md#pricequantitymeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the price quantity. |
| [Product](Logistics.Procurement.PurchaseProductPrices.md#product) | [Products](General.Products.Products.md) | The product for which a purchase price will be defined. |
| [PurchasePriceList](Logistics.Procurement.PurchaseProductPrices.md#purchasepricelist) | [PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable) | Specifies in which purchase price list this price is included. This price is used only when the purchase price list is specified in the current document. |
| [Supplier](Logistics.Procurement.PurchaseProductPrices.md#supplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | The price is used only for this supplier if specified. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Procurement.PurchaseProductPrices.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.PurchaseProductPrices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Procurement.PurchaseProductPrices.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Procurement.PurchaseProductPrices.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Procurement.PurchaseProductPrices.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Procurement.PurchaseProductPrices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### FromDate

Starting date of validity of the price. Usually used for temporary promotions.`Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### MaxQuantity

Maximum quantity for which is valid this price (in the price quantity measurement unit).`Unit: PriceQuantityMeasurementUnit` `Filter(eq)`

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### MinQuantity

Minimal quantity required to use this price (in the price quantity measurement unit).`Unit: PriceQuantityMeasurementUnit` `Filter(eq)`

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Notes

Notes for this PurchaseProductPrice.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### Price

Price in the specified currency and for the specified quantity. This price is used only when the other conditions in this record are satisfied.`Currency: Currency` `Required` `Default(0)`

Type: **[Amount (13, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### PriceQuantity

The quantity of the product for which the price is specified.`Unit: PriceQuantityMeasurementUnit` `Required` `Default(1)`

Type: **[Quantity (10, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### Priority

Priority of the price comparative to other prices valid for current document.`Required` `Default(2)` `Filter(multi eq)`

Type: **[Priority](Logistics.Procurement.PurchaseProductPrices.md#priority)**  
Category: **System**  
Allowed values for the `Priority`(Logistics.Procurement.PurchaseProductPrices.md#priority) data attribute  
Allowed Values (Logistics.Procurement.PurchaseProductPricesRepository.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Lowest' |
| Two | Two value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Two' |
| Three | Three value. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Three' |
| Four | Four value. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'Four' |
| Highest | Highest value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Highest' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **2**  
Show in UI: **ShownByDefault**  

### ThruDate

Ending date (inclusive) of the validity of the price. Usually used for temporary promotions.`Filter(eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

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

The currency of the specified price.

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Determines for which enterprise company this price is used. If not specified the price is used for all enterprise companies.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompanyLocation

Specifies the Enterprise Company Location for which the price is valid for. If the field is blank, the price is valid for all Enterprise Company Locations.

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PriceQuantityMeasurementUnit

The measurement unit of the price quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product.BaseUnit.IfNullThen( obj.PriceQuantityMeasurementUnit)`
### Product

The product for which a purchase price will be defined.

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PurchasePriceList

Specifies in which purchase price list this price is included. This price is used only when the purchase price list is specified in the current document.

Type: **[PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Supplier

The price is used only for this supplier if specified.

Type: **[Suppliers](Logistics.Procurement.Suppliers.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseProductPrices erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseProductPrices erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_PurchaseProductPrices

Domain API Entity Type: 
Logistics_Procurement_PurchaseProductPrice

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_PurchaseProductPrices?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_PurchaseProductPrices?$top=10>

