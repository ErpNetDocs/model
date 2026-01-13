---
uid: Crm.Presales.OfferLines
---
# Crm.Presales.OfferLines Entity

**Namespace:** [Crm.Presales](Crm.Presales.md)  

Detail records (lines) of Offers. Entity: Crm_Offer_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo}. {Offer.DocumentNo} {Offer.DocumentType.TypeName:T}_  
Default Search Members:  
_Offer.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Crm.Presales.OfferLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [GuaranteePeriodDays](Crm.Presales.OfferLines.md#guaranteeperioddays) | int32 __nullable__ | Guarantee period in days for the offered product. null for non-serviced products. 
| [Id](Crm.Presales.OfferLines.md#id) | guid |  
| [IsSelected](Crm.Presales.OfferLines.md#isselected) | boolean | True when the line is selected for further processing (ordering), false otherwise. `Required` `Default(true)` 
| [LineAmount](Crm.Presales.OfferLines.md#lineamount) | [Amount (14, 2)](../data-types.md#amount) | Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount. `Currency: Offer.DocumentCurrency` `Required` `Default(0)` 
| [LineCustomDiscountPercent](Crm.Presales.OfferLines.md#linecustomdiscountpercent) | decimal (7, 6) | Operator defined discount percentage, specified for this line. `Required` `Default(0)` 
| [LineNo](Crm.Presales.OfferLines.md#lineno) | int32 | Line number, unique within the Offer. Usually is increasing number like 10, 20, 30, ... when initially entering the Offer (in order to allow insertions with adjustment documents). `Required` `Filter(eq)` 
| [LineStandardDiscount<br />Percent](Crm.Presales.OfferLines.md#linestandarddiscountpercent) | decimal (7, 6) | The discount percentage, applied through the standard discount policy. `Required` `Default(0)` `ReadOnly` 
| [Notes](Crm.Presales.OfferLines.md#notes) | string (max) __nullable__ | Notes for this OfferLine. 
| [ObjectVersion](Crm.Presales.OfferLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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


## Attribute Details

### ChoiceGroupName

Name of a group of alternative lines, only one of which can be selected for ordering. Lines are grouped based on the exact name of the Choice Group.

_Type_: **string (60) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **60**  
_Show in UI_: **HiddenByDefault**  

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

_Type_: **[Quantity](../data-types.md#quantity)**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DeliveryTermDays

Delivery term in days. When Required Delivery Date is specified (not null), it takes precedence and this is ignored. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### GuaranteePeriodDays

Guarantee period in days for the offered product. null for non-serviced products.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.GuaranteePeriodDays`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsSelected

True when the line is selected for further processing (ordering), false otherwise. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **HiddenByDefault**  

### LineAmount

Amount for the line in the currency of the parent document. Usually equals Quantity * Unit_Price. When Quantity = 0, Unit Price is undefined and this contains the total line amount. `Currency: Offer.DocumentCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.UnitPrice == null)) OrElse ( ( obj.Quantity.Value == 0) AndAlso ( obj.UnitPrice.Value == 0))), obj.LineAmount, ( ( ( obj.Quantity.Value * obj.UnitPrice) * ( 1 - obj.LineStandardDiscountPercent)) * ( 1 - obj.LineCustomDiscountPercent)).Round( ))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.UnitPrice == null)) OrElse ( ( obj.Quantity.Value == 0) AndAlso ( obj.UnitPrice.Value == 0))), obj.LineAmount, ( ( ( obj.Quantity.Value * obj.UnitPrice) * ( 1 - obj.LineStandardDiscountPercent)) * ( 1 - obj.LineCustomDiscountPercent)).Round( ))`
### LineCustomDiscountPercent

Operator defined discount percentage, specified for this line. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### LineNo

Line number, unique within the Offer. Usually is increasing number like 10, 20, 30, ... when initially entering the Offer (in order to allow insertions with adjustment documents). `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Offer.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.Offer.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineStandardDiscountPercent

The discount percentage, applied through the standard discount policy. `Required` `Default(0)` `ReadOnly`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.LineDiscount.DiscountPercent`

_Front-End Recalc Expressions:_  
`IIF( ( obj.LineDiscount == null), 0, obj.LineDiscount.DiscountPercent)`
### Notes

Notes for this OfferLine.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ProductDescription

The description of the offered product. Initially copied from the name of the offered product. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.Product.Name`

_Front-End Recalc Expressions:_  
`obj.Product.Name`
### Quantity

Quantity offered. `Unit: QuantityUnit` `Required` `Default(1)`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The equivalent of Quantity in the base measurement unit of the Product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### RequiredDeliveryDate

Date, when the delivery is required. Alternative to Delivery Term Days. When null, Delivery Term Days is used. `Filter(ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.Offer.RequiredDeliveryDate`

_Front-End Recalc Expressions:_  
`IIF( ( obj.DeliveryTermDays == 0), obj.RequiredDeliveryDate, null)`
`obj.Offer.RequiredDeliveryDate`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### UnitPrice

The unit price of the offered product. It is specified in the measurement unit of Quantity. `Currency: Offer.DocumentCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 5)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( CalculateUnitPriceFromLineAmount( obj.LineAmount, obj.Quantity, obj.LineStandardDiscountPercent, obj.LineCustomDiscountPercent) ?? obj.UnitPrice)`

_Front-End Recalc Expressions:_  
`obj.CalculateUnitPrice( obj.Product, obj.ProductPrice, obj.QuantityUnit, obj.Offer)`
### Variant

Name or number of variant of the whole offer. When multiple lines have the same variant, they are selected for ordering together.

_Type_: **string (60) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **60**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The owner document. The <see cref="Offer"/> to which this OfferLine belongs. `Required` `Filter(multi eq)`

_Type_: **[Offers](Crm.Presales.Offers.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LineDiscount

When not null, contains the discount policy selected for this line. `Filter(multi eq)`

_Type_: **[LineDiscounts](Crm.Pricing.LineDiscounts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.DetermineLineDiscount( obj.RequiredDeliveryDate, obj.Offer.Customer, obj.Offer.ShipToCustomer, obj.Product, obj.Quantity, obj.QuantityUnit, obj.Offer.EnterpriseCompany, obj.Offer.EnterpriseCompanyLocation, obj.Offer.PriceList, obj.LineDiscount)`
### LineEndCustomerParty

The end customer is the customer of the dealer. It is stored for information purposes only. The end customer may not have customer definition, just party. `Filter(multi eq)` `Introduced in version 21.1.2.96`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.Offer.EndCustomerParty`

_Front-End Recalc Expressions:_  
`obj.Offer.EndCustomerParty`
### Offer

The <see cref="Offer"/> to which this OfferLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Offers](Crm.Presales.Offers.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Product

The offered product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( obj.ProductCode.Product == null), obj.Product, obj.ProductCode.Product)`

_Front-End Recalc Expressions:_  
`IIF( ( obj.ProductCode.Product == null), obj.Product, obj.ProductCode.Product)`
### ProductCode

Not null, when the product is selected using a coding system code. `Filter(multi eq)`

_Type_: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ProductPrice

Not null when the price has been selected from the list of valid standard prices. `Filter(multi eq)`

_Type_: **[ProductPrices](Crm.Pricing.ProductPrices.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`DetermineProductPrice( obj.Product, obj.Quantity, obj.QuantityUnit, obj.RequiredDeliveryDate, obj.Offer.Customer, obj.Offer.ShipToCustomer, obj.Offer.EnterpriseCompany, obj.Offer.EnterpriseCompanyLocation, null, obj.Offer.PriceList, obj.ProductPrice)`
### QuantityUnit

The measurement unit of Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit)`

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit)`

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

