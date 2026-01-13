---
uid: Logistics.Procurement.Suppliers
---
# Logistics.Procurement.Suppliers Entity

**Namespace:** [Logistics.Procurement](Logistics.Procurement.md)  

Contains supplier conditions (contracts). Entity: Scm_Suppliers

## Default Visualization
Default Display Text Format:  
_{Party.PartyName:T}_  
Default Search Members:  
_Number; Party.PartyName_  
Code Data Member:  
_Number_  
Name Data Member:  
_Party.PartyName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  
Layout category attribute:  _SupplierTypeId_  

## Track Changes  
Min level:  _1 - Track last changes only_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Procurement.Suppliers](Logistics.Procurement.Suppliers.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTime](Logistics.Procurement.Suppliers.md#creationtime) | datetime __nullable__ | Date and time when the Supplier was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](Logistics.Procurement.Suppliers.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Supplier. `Filter(like)` `ReadOnly` 
| [DefaultDeliveryTermDays](Logistics.Procurement.Suppliers.md#defaultdeliverytermdays) | int32 | Default term in days for goods delivery, starting at the day of sending the purchase order. `Required` `Default(0)` 
| [DefaultPaymentStartDays](Logistics.Procurement.Suppliers.md#defaultpaymentstartdays) | int32 | Default number of days until the payment becomes executable. 0 means that the payment is executable at all times. `Required` `Default(0)` 
| [DefaultPaymentTermDays](Logistics.Procurement.Suppliers.md#defaultpaymenttermdays) | int32 | Default payment term in days, starting from the date of receiving the invoice. `Required` `Default(0)` 
| [DisplayText](Logistics.Procurement.Suppliers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Logistics.Procurement.Suppliers.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Procurement.Suppliers.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FromDate](Logistics.Procurement.Suppliers.md#fromdate) | datetime __nullable__ | The date on which this party became a supplier or the date, when the supplier contract was signed. `Filter(ge;le)` 
| [Id](Logistics.Procurement.Suppliers.md#id) | guid |  
| [IsActive](Logistics.Procurement.Suppliers.md#isactive) | boolean | Indicates whether the current supplier is active. `Required` `Default(true)` `Filter(eq)` 
| [Number](Logistics.Procurement.Suppliers.md#number) | string (16) __nullable__ | The unique supplier number. `Filter(eq;like)` `ORD` 
| [ObjectVersion](Logistics.Procurement.Suppliers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ThruDate](Logistics.Procurement.Suppliers.md#thrudate) | datetime __nullable__ | The date (inclusive) on which this party ceased to be a supplier. `Filter(ge;le)` 
| [UpdateTime](Logistics.Procurement.Suppliers.md#updatetime) | datetime __nullable__ | Date and time when the Supplier was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](Logistics.Procurement.Suppliers.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Supplier. `Filter(like)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultCurrency](Logistics.Procurement.Suppliers.md#defaultcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The default currency for purchases from this supplier. null means there is no default. `Filter(multi eq)` |
| [DefaultPaymentAccount](Logistics.Procurement.Suppliers.md#defaultpaymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable) | When not null, specifies the default payment account which should be used for new purchase document for this supplier. `Filter(multi eq)` |
| [DefaultPaymentType](Logistics.Procurement.Suppliers.md#defaultpaymenttype) | [PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable) | When not null, specifies the default payment type which should be used for new purchase document for this supplier. `Filter(multi eq)` |
| [DefaultPurchasePriceList](Logistics.Procurement.Suppliers.md#defaultpurchasepricelist) | [PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable) | The default purchase price list, which shall be used for new purchase documents for this supplier. `Filter(multi eq)` |
| [EnterpriseCompany](Logistics.Procurement.Suppliers.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Supplier applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [Party](Logistics.Procurement.Suppliers.md#party) | [Parties](General.Contacts.Parties.md) | The party who is the supplier for the enterprise company. `Required` `Filter(multi eq)` `FilterableReference` |
| [SupplierType](Logistics.Procurement.Suppliers.md#suppliertype) | [SupplierTypes](Logistics.Procurement.SupplierTypes.md) (nullable) | When not null, specifies the type of this supplier. The type is primarily used for security access differentiation of the supplier records. `Filter(multi eq)` |


## Attribute Details

### CreationTime

Date and time when the Supplier was created. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Supplier. `Filter(like)` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  

### DefaultDeliveryTermDays

Default term in days for goods delivery, starting at the day of sending the purchase order. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### DefaultPaymentStartDays

Default number of days until the payment becomes executable. 0 means that the payment is executable at all times. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### DefaultPaymentTermDays

Default payment term in days, starting from the date of receiving the invoice. `Required` `Default(0)`

_Type_: **int32**  
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

### FromDate

The date on which this party became a supplier or the date, when the supplier contract was signed. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the current supplier is active. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Number

The unique supplier number. `Filter(eq;like)` `ORD`

_Type_: **string (16) __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.IncMax( o => o.Number, null, "00000")`

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ThruDate

The date (inclusive) on which this party ceased to be a supplier. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UpdateTime

Date and time when the Supplier was last updated. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Supplier. `Filter(like)` `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### DefaultCurrency

The default currency for purchases from this supplier. null means there is no default. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DefaultPaymentAccount

When not null, specifies the default payment account which should be used for new purchase document for this supplier. `Filter(multi eq)`

_Type_: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DefaultPaymentType

When not null, specifies the default payment type which should be used for new purchase document for this supplier. `Filter(multi eq)`

_Type_: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DefaultPurchasePriceList

The default purchase price list, which shall be used for new purchase documents for this supplier. `Filter(multi eq)`

_Type_: **[PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this Supplier applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Party

The party who is the supplier for the enterprise company. `Required` `Filter(multi eq)` `FilterableReference`

_Type_: **[Parties](General.Contacts.Parties.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### SupplierType

When not null, specifies the type of this supplier. The type is primarily used for security access differentiation of the supplier records. `Filter(multi eq)`

_Type_: **[SupplierTypes](Logistics.Procurement.SupplierTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Procurement.Suppliers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.Suppliers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_Suppliers

Domain API Entity Type: 
Logistics_Procurement_Supplier

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_Suppliers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_Suppliers?$top=10>

