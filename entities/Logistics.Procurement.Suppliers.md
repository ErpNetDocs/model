---
uid: Logistics.Procurement.Suppliers
---
# Logistics.Procurement.Suppliers


Contains supplier conditions (contracts).

## General
Namespace: [Logistics.Procurement](Logistics.Procurement.md)  
Repository: Logistics.Procurement.Suppliers  
Base Table: Scm_Suppliers  
API access:  ReadWrite  

## Visualization
Display Format: {Party.PartyName:T}  
Search Members: Number; Party.PartyName  
Code Member: Number  
Name Member: Party.PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  SupplierTypeId  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

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
| [FromDate](Logistics.Procurement.Suppliers.md#fromdate) | datetime __nullable__ | The date on which this party became a supplier or the date, when the supplier contract was signed. `Filter(ge;le)` 
| [IsActive](Logistics.Procurement.Suppliers.md#isactive) | boolean | Indicates whether the current supplier is active. `Required` `Default(true)` `Filter(eq)` 
| [Number](Logistics.Procurement.Suppliers.md#number) | string (16) __nullable__ | The unique supplier number. `Filter(eq;like)` `ORD` 
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


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Procurement.Suppliers.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.Suppliers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Procurement.Suppliers.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Procurement.Suppliers.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Procurement.Suppliers.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Procurement.Suppliers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreationTime

Date and time when the Supplier was created. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Supplier. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### DefaultDeliveryTermDays

Default term in days for goods delivery, starting at the day of sending the purchase order. `Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### DefaultPaymentStartDays

Default number of days until the payment becomes executable. 0 means that the payment is executable at all times. `Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### DefaultPaymentTermDays

Default payment term in days, starting from the date of receiving the invoice. `Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### FromDate

The date on which this party became a supplier or the date, when the supplier contract was signed. `Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current supplier is active. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Number

The unique supplier number. `Filter(eq;like)` `ORD`

Type: **string (16) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Number, null, "00000")`

### ThruDate

The date (inclusive) on which this party ceased to be a supplier. `Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UpdateTime

Date and time when the Supplier was last updated. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Supplier. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
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

### DefaultCurrency

The default currency for purchases from this supplier. null means there is no default. `Filter(multi eq)`

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultPaymentAccount

When not null, specifies the default payment account which should be used for new purchase document for this supplier. `Filter(multi eq)`

Type: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultPaymentType

When not null, specifies the default payment type which should be used for new purchase document for this supplier. `Filter(multi eq)`

Type: **[PaymentTypes](Finance.Payments.PaymentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultPurchasePriceList

The default purchase price list, which shall be used for new purchase documents for this supplier. `Filter(multi eq)`

Type: **[PurchasePriceLists](Logistics.Procurement.PurchasePriceLists.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this Supplier applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Party

The party who is the supplier for the enterprise company. `Required` `Filter(multi eq)` `FilterableReference`

Type: **[Parties](General.Contacts.Parties.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### SupplierType

When not null, specifies the type of this supplier. The type is primarily used for security access differentiation of the supplier records. `Filter(multi eq)`

Type: **[SupplierTypes](Logistics.Procurement.SupplierTypes.md) (nullable)**  
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

