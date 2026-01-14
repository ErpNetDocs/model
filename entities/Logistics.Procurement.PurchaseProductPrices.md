---
uid: Logistics.Procurement.PurchaseProductPrices
---
# Logistics.Procurement.PurchaseProductPrices Entity

**Namespace:** [Logistics.Procurement](Logistics.Procurement.md)  

Contains purchase prices of the products. Used for automatically loading unit prices in the purchase documents. Entity: Scm_Purchase_Product_Prices

## Default Visualization
Default Display Text Format:  
_{Price} - {FromDate}_  
Default Search Members:  
__  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Procurement.PurchaseProductPrices](Logistics.Procurement.PurchaseProductPrices.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Logistics.Procurement.PurchaseProductPrices.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Procurement.PurchaseProductPrices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Logistics.Procurement.PurchaseProductPrices.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Procurement.PurchaseProductPrices.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FromDate](Logistics.Procurement.PurchaseProductPrices.md#fromdate) | datetime __nullable__ | Starting date of validity of the price. `Filter(eq;ge;le)` 
| [Id](Logistics.Procurement.PurchaseProductPrices.md#id) | guid |  
| [MaxQuantity](Logistics.Procurement.PurchaseProductPrices.md#maxquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Maximum quantity for which this price is valid in the Price_Quantity_<br />Measurement_Unit. `Unit: PriceQuantityMeasurement<br />Unit` `Filter(eq)` 
| [MinQuantity](Logistics.Procurement.PurchaseProductPrices.md#minquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | Minimal quantity required to use this price (in the Price_Quantity_Measurement_Unit). `Unit: PriceQuantityMeasurement<br />Unit` `Filter(eq)` 
| [Notes](Logistics.Procurement.PurchaseProductPrices.md#notes) | string (254) __nullable__ | Notes for this PurchaseProductPrice. 
| [ObjectVersion](Logistics.Procurement.PurchaseProductPrices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Price](Logistics.Procurement.PurchaseProductPrices.md#price) | [Amount (13, 5)](../data-types.md#amount) | Price in the specified currency and for the specified quantity. `Currency: Currency` `Required` `Default(0)` 
| [PriceQuantity](Logistics.Procurement.PurchaseProductPrices.md#pricequantity) | [Quantity (10, 3)](../data-types.md#quantity) | The quantity of the product for which the price is specified. `Unit: PriceQuantityMeasurement<br />Unit` `Required` `Default(1)` 
| [Priority](Logistics.Procurement.PurchaseProductPrices.md#priority) | [Priority](Logistics.Procurement.PurchaseProductPrices.md#priority) | Priority of the price comparative to other prices. `Required` `Default(2)` `Filter(multi eq)` 
| [ThruDate](Logistics.Procurement.PurchaseProductPrices.md#thrudate) | datetime __nullable__ | Ending date (inclusive) of the validity of the price. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Currency](Logistics.Procurement.PurchaseProductPrices.md#currency) | [Currencies](General.Currencies.Currencies.md) | The currency of the price. `Required` `Filter(multi eq)` |
| [EnterpriseCompany](Logistics.Procurement.PurchaseProductPrices.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Determines for which enterprise company this price is used. If not specified the price is used for all enterprise companies. `Filter(multi eq)` |
| [EnterpriseCompanyLocation](Logistics.Procurement.PurchaseProductPrices.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | Specifies the Enterprise Company Location for which the price is valid for. If the field is blank, the price is valid for all Enterprise Company Locations. `Filter(multi eq)` `Introduced in version 24.1.4.35` |
| [PriceQuantityMeasurement<br />Unit](Logistics.Procurement.PurchaseProductPrices.md#pricequantitymeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Price_Quantity. `Required` `Filter(multi eq)` |
| [Product](Logistics.Procurement.PurchaseProductPrices.md#product) | [Products](General.Products.Products.md) | The product for which a purchase price will be defined. `Required` `Filter(multi eq)` |
| [PurchasePriceList](Logistics.Procurement.PurchaseProductPrices.md#purchasepricelist) | [PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable) | When not null, specifies that this price is valid only when the purchase document is set to work with the specified price list. `Filter(multi eq)` |
| [Supplier](Logistics.Procurement.PurchaseProductPrices.md#supplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | When not null, specifies that the price is valid only for the specified supplier. `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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

### FromDate

Starting date of validity of the price. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### MaxQuantity

Maximum quantity for which this price is valid in the Price_Quantity_Measurement_Unit. `Unit: PriceQuantityMeasurementUnit` `Filter(eq)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### MinQuantity

Minimal quantity required to use this price (in the Price_Quantity_Measurement_Unit). `Unit: PriceQuantityMeasurementUnit` `Filter(eq)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Notes

Notes for this PurchaseProductPrice.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Price

Price in the specified currency and for the specified quantity. `Currency: Currency` `Required` `Default(0)`

_Type_: **[Amount (13, 5)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### PriceQuantity

The quantity of the product for which the price is specified. `Unit: PriceQuantityMeasurementUnit` `Required` `Default(1)`

_Type_: **[Quantity (10, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

### Priority

Priority of the price comparative to other prices. `Required` `Default(2)` `Filter(multi eq)`

_Type_: **[Priority](Logistics.Procurement.PurchaseProductPrices.md#priority)**  
_Category_: **System**  
Allowed values for the `Priority`(Logistics.Procurement.PurchaseProductPrices.md#priority) data attribute  
_Allowed Values (Logistics.Procurement.PurchaseProductPricesRepository.Priority Enum Members)_  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Lowest' |
| Two | Two value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Two' |
| Three | Three value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Three' |
| Four | Four value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Four' |
| Highest | Highest value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Highest' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **2**  
_Show in UI_: **ShownByDefault**  

### ThruDate

Ending date (inclusive) of the validity of the price. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Currency

The currency of the price. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

Determines for which enterprise company this price is used. If not specified the price is used for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### EnterpriseCompanyLocation

Specifies the Enterprise Company Location for which the price is valid for. If the field is blank, the price is valid for all Enterprise Company Locations. `Filter(multi eq)` `Introduced in version 24.1.4.35`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PriceQuantityMeasurementUnit

The measurement unit of Price_Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.BaseUnit.IfNullThen( obj.PriceQuantityMeasurementUnit)`
### Product

The product for which a purchase price will be defined. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PurchasePriceList

When not null, specifies that this price is valid only when the purchase document is set to work with the specified price list. `Filter(multi eq)`

_Type_: **[PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Supplier

When not null, specifies that the price is valid only for the specified supplier. `Filter(multi eq)`

_Type_: **[Suppliers](Logistics.Procurement.Suppliers.md) (nullable)**  
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

