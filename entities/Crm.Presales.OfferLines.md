---
uid: Crm.Presales.OfferLines
---
# Crm.Presales.OfferLines


Detail records (lines) of Offers

## General
Namespace: [Crm.Presales](Crm.Presales.md)  
Repository: Crm.Presales.OfferLines  
Base Table: Crm_Offer_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {Offer.DocumentNo} {Offer.DocumentType.TypeName:T}  
Search Members: Offer.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Presales.Offers](Crm.Presales.Offers.md)  
Aggregate Root:  
[Crm.Presales.Offers](Crm.Presales.Offers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ChoiceGroupName](Crm.Presales.OfferLines.md#choicegroupname) | string (60) __nullable__ | Name of a group of alternative lines, only one of which can be selected for ordering. Lines are grouped based on the exact name of the Choice Group. 
| [CurrentBalanceBase](Crm.Presales.OfferLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DeliveryTermDays](Crm.Presales.OfferLines.md#deliverytermdays) | int32 | Delivery term in days. When Required Delivery Date is specified (not null), it takes precedence and this is ignored. `Required` `Default(0)` 
| [GuaranteePeriodDays](Crm.Presales.OfferLines.md#guaranteeperioddays) | int32 __nullable__ | Guarantee period in days for the offered product. null for non-serviced products. 
| [IsSelected](Crm.Presales.OfferLines.md#isselected) | boolean | True when the line is selected for further processing (ordering), false otherwise. `Required` `Default(true)` 
| [LineAmount](Crm.Presales.OfferLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount. `Currency: Offer.DocumentCurrency` `Required` `Default(0)` 
| [LineCustomDiscountPercent](Crm.Presales.OfferLines.md#linecustomdiscountpercent) | decimal (7, 6) | Operator defined discount percentage, specified for this line. `Required` `Default(0)` 
| [LineNo](Crm.Presales.OfferLines.md#lineno) | int32 | Line number, unique within the Offer. Usually is increasing number like 10, 20, 30, ... when initially entering the Offer (in order to allow insertions with adjustment documents). `Required` `Filter(eq)` 
| [LineStandardDiscount<br />Percent](Crm.Presales.OfferLines.md#linestandarddiscountpercent) | decimal (7, 6) | The discount percentage, applied through the standard discount policy. `Required` `Default(0)` `ReadOnly` 
| [Notes](Crm.Presales.OfferLines.md#notes) | string (max) __nullable__ | Notes for this OfferLine. 
| [ProductDescription](Crm.Presales.OfferLines.md#productdescription) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The description of the offered product. Initially copied from the name of the offered product. `Required` `Filter(like)` 
| [Quantity](Crm.Presales.OfferLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | Quantity offered. `Unit: QuantityUnit` `Required` `Default(1)` 
| [QuantityBase](Crm.Presales.OfferLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalent of Quantity in the base measurement unit of the Product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [RequiredDeliveryDate](Crm.Presales.OfferLines.md#requireddeliverydate) | date __nullable__ | Date, when the delivery is required. Alternative to Delivery Term Days. When null, Delivery Term Days is used. `Filter(ge;le)` 
| [StandardQuantityBase](Crm.Presales.OfferLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [UnitPrice](Crm.Presales.OfferLines.md#unitprice) | [Amount (14, 5)](../data-types.md#amount) | The unit price of the offered product. It is specified in the measurement unit of Quantity. `Currency: Offer.DocumentCurrency` `Required` `Default(0)` 
| [Variant](Crm.Presales.OfferLines.md#variant) | string (60) __nullable__ | Name or number of variant of the whole offer. When multiple lines have the same variant, they are selected for ordering together. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Crm.Presales.OfferLines.md#document) | [Offers](Crm.Presales.Offers.md) | The owner document. The <see cref="Offer"/> to which this OfferLine belongs. `Required` `Filter(multi eq)` |
| [LineDiscount](Crm.Presales.OfferLines.md#linediscount) | [LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable) | When not null, contains the discount policy selected for this line. `Filter(multi eq)` |
| [LineEndCustomerParty](Crm.Presales.OfferLines.md#lineendcustomerparty) | [Parties](General.Contacts.Parties.md) (nullable) | The end customer is the customer of the dealer. It is stored for information purposes only. The end customer may not have customer definition, just party. `Filter(multi eq)` `Introduced in version 21.1.2.96` |
| [Offer](Crm.Presales.OfferLines.md#offer) | [Offers](Crm.Presales.Offers.md) | The <see cref="Offer"/> to which this OfferLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [Product](Crm.Presales.OfferLines.md#product) | [Products](General.Products.Products.md) | The offered product. `Required` `Filter(multi eq)` |
| [ProductCode](Crm.Presales.OfferLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Not null, when the product is selected using a coding system code. `Filter(multi eq)` |
| [ProductPrice](Crm.Presales.OfferLines.md#productprice) | [ProductPrices](Crm.Pricing.ProductPrices.md) (nullable) | Not null when the price has been selected from the list of valid standard prices. `Filter(multi eq)` |
| [QuantityUnit](Crm.Presales.OfferLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Presales.OfferLines.md#id) | guid |  
| [ObjectVersion](Crm.Presales.OfferLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Presales.OfferLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ChoiceGroupName

Name of a group of alternative lines, only one of which can be selected for ordering. Lines are grouped based on the exact name of the Choice Group.

Type: **string (60) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **60**  
Show in UI: **HiddenByDefault**  

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DeliveryTermDays

Delivery term in days. When Required Delivery Date is specified (not null), it takes precedence and this is ignored. `Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **HiddenByDefault**  

### GuaranteePeriodDays

Guarantee period in days for the offered product. null for non-serviced products.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product.GuaranteePeriodDays`
### IsSelected

True when the line is selected for further processing (ordering), false otherwise. `Required` `Default(true)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **HiddenByDefault**  

### LineAmount

Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount. `Currency: Offer.DocumentCurrency` `Required` `Default(0)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.UnitPrice == null)) OrElse ( ( obj.Quantity.Value == 0) AndAlso ( obj.UnitPrice.Value == 0))), obj.LineAmount, ( ( ( obj.Quantity.Value * obj.UnitPrice) * ( 1 - obj.LineStandardDiscountPercent)) * ( 1 - obj.LineCustomDiscountPercent)).Round( ))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.UnitPrice == null)) OrElse ( ( obj.Quantity.Value == 0) AndAlso ( obj.UnitPrice.Value == 0))), obj.LineAmount, ( ( ( obj.Quantity.Value * obj.UnitPrice) * ( 1 - obj.LineStandardDiscountPercent)) * ( 1 - obj.LineCustomDiscountPercent)).Round( ))`
### LineCustomDiscountPercent

Operator defined discount percentage, specified for this line. `Required` `Default(0)`

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### LineNo

Line number, unique within the Offer. Usually is increasing number like 10, 20, 30, ... when initially entering the Offer (in order to allow insertions with adjustment documents). `Required` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Offer.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.Offer.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineStandardDiscountPercent

The discount percentage, applied through the standard discount policy. `Required` `Default(0)` `ReadOnly`

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.LineDiscount.DiscountPercent`

Front-End Recalc Expressions:  
`IIF( ( obj.LineDiscount == null), 0, obj.LineDiscount.DiscountPercent)`
### Notes

Notes for this OfferLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### ProductDescription

The description of the offered product. Initially copied from the name of the offered product. `Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Product.Name`

Front-End Recalc Expressions:  
`obj.Product.Name`
### Quantity

Quantity offered. `Unit: QuantityUnit` `Required` `Default(1)`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The equivalent of Quantity in the base measurement unit of the Product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### RequiredDeliveryDate

Date, when the delivery is required. Alternative to Delivery Term Days. When null, Delivery Term Days is used. `Filter(ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Offer.RequiredDeliveryDate`

Front-End Recalc Expressions:  
`IIF( ( obj.DeliveryTermDays == 0), obj.RequiredDeliveryDate, null)`
`obj.Offer.RequiredDeliveryDate`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### UnitPrice

The unit price of the offered product. It is specified in the measurement unit of Quantity. `Currency: Offer.DocumentCurrency` `Required` `Default(0)`

Type: **[Amount (14, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( CalculateUnitPriceFromLineAmount( obj.LineAmount, obj.Quantity, obj.LineStandardDiscountPercent, obj.LineCustomDiscountPercent) ?? obj.UnitPrice)`

Front-End Recalc Expressions:  
`obj.CalculateUnitPrice( obj.Product, obj.ProductPrice, obj.QuantityUnit, obj.Offer)`
### Variant

Name or number of variant of the whole offer. When multiple lines have the same variant, they are selected for ordering together.

Type: **string (60) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **60**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Document

The owner document. The <see cref="Offer"/> to which this OfferLine belongs. `Required` `Filter(multi eq)`

Type: **[Offers](Crm.Presales.Offers.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LineDiscount

When not null, contains the discount policy selected for this line. `Filter(multi eq)`

Type: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.DetermineLineDiscount( obj.RequiredDeliveryDate, obj.Offer.Customer, obj.Offer.ShipToCustomer, obj.Product, obj.Quantity, obj.QuantityUnit, obj.Offer.EnterpriseCompany, obj.Offer.EnterpriseCompanyLocation, obj.Offer.PriceList, obj.LineDiscount)`
### LineEndCustomerParty

The end customer is the customer of the dealer. It is stored for information purposes only. The end customer may not have customer definition, just party. `Filter(multi eq)` `Introduced in version 21.1.2.96`

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Offer.EndCustomerParty`

Front-End Recalc Expressions:  
`obj.Offer.EndCustomerParty`
### Offer

The <see cref="Offer"/> to which this OfferLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Offers](Crm.Presales.Offers.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Product

The offered product. `Required` `Filter(multi eq)`

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( obj.ProductCode.Product == null), obj.Product, obj.ProductCode.Product)`

Front-End Recalc Expressions:  
`IIF( ( obj.ProductCode.Product == null), obj.Product, obj.ProductCode.Product)`
### ProductCode

Not null, when the product is selected using a coding system code. `Filter(multi eq)`

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ProductPrice

Not null when the price has been selected from the list of valid standard prices. `Filter(multi eq)`

Type: **[ProductPrices](Crm.Pricing.ProductPrices.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`DetermineProductPrice( obj.Product, obj.Quantity, obj.QuantityUnit, obj.RequiredDeliveryDate, obj.Offer.Customer, obj.Offer.ShipToCustomer, obj.Offer.EnterpriseCompany, obj.Offer.EnterpriseCompanyLocation, null, obj.Offer.PriceList, obj.ProductPrice)`
### QuantityUnit

The measurement unit of Quantity. `Required` `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit)`

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit)`

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

[!list limit=1000 erp.entity=Crm.Presales.OfferLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Presales.OfferLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Presales_OfferLines

Domain API Entity Type: 
Crm_Presales_OfferLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Presales_OfferLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Presales_OfferLines?$top=10>

