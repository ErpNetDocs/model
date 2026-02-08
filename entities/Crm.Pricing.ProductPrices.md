---
uid: Crm.Pricing.ProductPrices
---
# Crm.Pricing.ProductPrices


Specific prices of products. A price is applied after matching the specified criteria.

## General
Namespace: [Crm.Pricing](Crm.Pricing.md)  
Repository: Crm.Pricing.ProductPrices  
Base Table: Crm_Product_Prices  
API access:  ReadWrite  

## Renames

Old name: Crm.ProductPrices  
New name: Crm.Pricing.ProductPrices  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {Price} - {FromDate}  
Search Members: Notes  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pricing.ProductPrices](Crm.Pricing.ProductPrices.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FromDate](Crm.Pricing.ProductPrices.md#fromdate) | date __nullable__ | Starting date of validity of the price`Filter(eq;ge;le)` 
| [IsActive](Crm.Pricing.ProductPrices.md#isactive) | boolean | Indicates whether the current Product price is active.`Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18` 
| [MaxQuantity](Crm.Pricing.ProductPrices.md#maxquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Maximum quantity for which this price is valid in the Price_Quantity_<br />Measurement_Unit`<br />Unit: PriceQuantityMeasurement<br />Unit` `Filter(eq;ge;le)` 
| [MinQuantity](Crm.Pricing.ProductPrices.md#minquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Minimal quantity required to use this price (in the Price_Quantity_Measurement_Unit)`Unit: PriceQuantityMeasurement<br />Unit` `Filter(eq;ge;le)` 
| [Notes](Crm.Pricing.ProductPrices.md#notes) | string (254) __nullable__ | Notes for this ProductPrice. `Filter(like)` 
| [Price](Crm.Pricing.ProductPrices.md#price) | [Amount (13, 5)](../data-types.md#amount) | Price in the specified currency and for the specified quantity`Currency: Currency` `Required` `Default(0)` `Filter(eq;ge;le)` 
| [PriceQuantity](Crm.Pricing.ProductPrices.md#pricequantity) | [Quantity (10, 3)](../data-types.md#quantity) | The quantity of the product for which the price is specified`Unit: PriceQuantityMeasurement<br />Unit` `Required` `Default(1)` `Filter(ge;le)` 
| [Priority](Crm.Pricing.ProductPrices.md#priority) | [Priority](Crm.Pricing.ProductPrices.md#priority) | Priority of the price comparative to other prices. Only the highest priority price is applied.`Required` `Default(2)` `Filter(multi eq)` 
| [ThruDate](Crm.Pricing.ProductPrices.md#thrudate) | date __nullable__ | Ending date (inclusive) of the validity of the price`Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Campaign](Crm.Pricing.ProductPrices.md#campaign) | [Campaigns](Crm.Marketing.Campaigns.md) (nullable) | Тhe marketing campaign to which the current definition belongs. |
| [Currency](Crm.Pricing.ProductPrices.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency of the price |
| [Customer](Crm.Pricing.ProductPrices.md#customer) | [Customers](Crm.Sales.Customers.md) (nullable) | When not NULL, specifies that the customer of the sales document must be the specified customer. |
| [DistributionChannel](Crm.Pricing.ProductPrices.md#distributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable) | Use the price only when selling through the specified channel |
| [EnterpriseCompany](Crm.Pricing.ProductPrices.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not NULL, specifies that the sales document must be in the specified enterprise company. |
| [EnterpriseCompanyLocation](Crm.Pricing.ProductPrices.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | When set, specifies that the sales document must be of the specified enterprise company location. |
| [PriceList](Crm.Pricing.ProductPrices.md#pricelist) | [PriceLists](Crm.Pricing.PriceLists.md) (nullable) | When not NULL, specifies that the sales document must have the specified price list. |
| [PriceQuantityMeasurement<br />Unit](Crm.Pricing.ProductPrices.md#pricequantitymeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Price_Quantity |
| [PriceType](Crm.Pricing.ProductPrices.md#pricetype) | [PriceTypes](Crm.Pricing.PriceTypes.md) (nullable) | Price type of the current product price. The price types are used to set additional priority condition for the prices. |
| [Product](Crm.Pricing.ProductPrices.md#product) | [Products](General.Products.Products.md) | The product for which a price will be defined |
| [ShipToCustomer](Crm.Pricing.ProductPrices.md#shiptocustomer) | [Customers](Crm.Sales.Customers.md) (nullable) | When not null, specifies that the price will be applied only when the sales document has the specified Ship-To-Customer. |
| [TargetGroup](Crm.Pricing.ProductPrices.md#targetgroup) | [TargetGroups](Crm.Marketing.TargetGroups.md) (nullable) | When not NULL, specifies a criteria, which is matched only when the customer of the sales document is included in the group. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.ProductPrices.md#id) | guid |  
| [ObjectVersion](Crm.Pricing.ProductPrices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pricing.ProductPrices.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pricing.ProductPrices.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pricing.ProductPrices.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pricing.ProductPrices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### FromDate

Starting date of validity of the price`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### IsActive

Indicates whether the current Product price is active.`Required` `Default(true)` `Filter(eq)` `Introduced in version 25.1.0.18`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### MaxQuantity

Maximum quantity for which this price is valid in the Price_Quantity_Measurement_Unit`Unit: PriceQuantityMeasurementUnit` `Filter(eq;ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### MinQuantity

Minimal quantity required to use this price (in the Price_Quantity_Measurement_Unit)`Unit: PriceQuantityMeasurementUnit` `Filter(eq;ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Notes

Notes for this ProductPrice. `Filter(like)`

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### Price

Price in the specified currency and for the specified quantity`Currency: Currency` `Required` `Default(0)` `Filter(eq;ge;le)`

Type: **[Amount (13, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### PriceQuantity

The quantity of the product for which the price is specified`Unit: PriceQuantityMeasurementUnit` `Required` `Default(1)` `Filter(ge;le)`

Type: **[Quantity (10, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### Priority

Priority of the price comparative to other prices. Only the highest priority price is applied.`Required` `Default(2)` `Filter(multi eq)`

Type: **[Priority](Crm.Pricing.ProductPrices.md#priority)**  
Category: **System**  
Generic enum type for Priority properties  
Allowed Values (General.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Lowest' |
| Low | Low value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
| Medium | Medium value. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Medium' |
| High | High value. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'High' |
| Highest | Highest value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Highest' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **2**  
Show in UI: **ShownByDefault**  

### ThruDate

Ending date (inclusive) of the validity of the price`Filter(eq;ge;le)`

Type: **date __nullable__**  
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

### Campaign

Тhe marketing campaign to which the current definition belongs.

Type: **[Campaigns](Crm.Marketing.Campaigns.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Currency

The currency of the price

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Customer

When not NULL, specifies that the customer of the sales document must be the specified customer.

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DistributionChannel

Use the price only when selling through the specified channel

Type: **[DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

When not NULL, specifies that the sales document must be in the specified enterprise company.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompanyLocation

When set, specifies that the sales document must be of the specified enterprise company location.

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.EnterpriseCompanyLocation != null) AndAlso ( obj.EnterpriseCompanyLocation.Company != obj.EnterpriseCompany)), null, obj.EnterpriseCompanyLocation.Company)`
### PriceList

When not NULL, specifies that the sales document must have the specified price list.

Type: **[PriceLists](Crm.Pricing.PriceLists.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PriceQuantityMeasurementUnit

The measurement unit of Price_Quantity

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.Product != null), obj.Product.MeasurementUnit, obj.PriceQuantityMeasurementUnit)`
### PriceType

Price type of the current product price. The price types are used to set additional priority condition for the prices.

Type: **[PriceTypes](Crm.Pricing.PriceTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product for which a price will be defined

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ShipToCustomer

When not null, specifies that the price will be applied only when the sales document has the specified Ship-To-Customer.

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ShipToCustomer.Party.ParentParty != obj.Customer), null, obj.ShipToCustomer)`
### TargetGroup

When not NULL, specifies a criteria, which is matched only when the customer of the sales document is included in the group.

Type: **[TargetGroups](Crm.Marketing.TargetGroups.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pricing.ProductPrices erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.ProductPrices erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pricing_ProductPrices

Domain API Entity Type: 
Crm_Pricing_ProductPrice

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pricing_ProductPrices?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pricing_ProductPrices?$top=10>

