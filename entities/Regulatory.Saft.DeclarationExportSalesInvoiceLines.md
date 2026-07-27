---
uid: Regulatory.Saft.DeclarationExportSalesInvoiceLines
---
# Regulatory.Saft.DeclarationExportSalesInvoiceLines


Contains Sale invoice lines for `SAFT_Declaration_Export_Sales_Invoices`.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.DeclarationExportSalesInvoiceLines  
Base Table: Saft_Declaration_Export_Sales_Invoice_Lines  
Introduced In Version: 27.1.0.86  
API access:  ReadOnly  

## Visualization
Display Format: {LineCurrencyCode}  
Search Members: LineCurrencyCode  
Code Member: LineCurrencyCode  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Saft.DeclarationExportSalesInvoiceLines](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountId](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#accountid) | string (10) | Account Id`Required` |
| [DebitCreditIndicator](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#debitcreditindicator) | string (1) | Debit Credit Indicator`Required` |
| [Description](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#description) | string (255) | Description`Required` |
| [ExportSequence](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#exportsequence) | int32 | Monotonc sequence within Declaration Export`Required` `Filter(ge;le)` `ORD` `Introduced in version 27.1.0.89` |
| [LineAmount](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#lineamount) | decimal (18, 2) | Line Amount`Required` |
| [LineCurrencyAmount](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#linecurrencyamount) | decimal (18, 2) | Line Currency Amount`Required` |
| [LineCurrencyCode](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#linecurrencycode) | string (3) | Line Currency Code`Required` |
| [ProductCode](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#productcode) | string (35) | Product code`Required` |
| [Quantity](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#quantity) | decimal (18, 3) | Quantity`Required` |
| [TaxAmount](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#taxamount) | decimal (18, 2) | ax Amount`Required` |
| [TaxCode](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#taxcode) | string (10) | Tax Code`Required` |
| [TaxCurrencyAmount](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#taxcurrencyamount) | decimal (18, 2) | Tax Currency Amount`Required` |
| [TaxCurrencyCode](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#taxcurrencycode) | string (3) | Tax Currency Code`Required` |
| [TaxPointDate](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#taxpointdate) | datetime __nullable__ | Tax Point Date`Filter(ge;le)` |
| [TaxType](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#taxtype) | string (10) |  Tax Type`Required` |
| [UnitPrice](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#unitprice) | decimal (14, 5) | Unit Price`Required` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [SaftDeclaration<br />ExportSalesInvoice](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#saftdeclarationexportsalesinvoice) | [DeclarationExportSalesInvoices](Regulatory.Saft.DeclarationExportSalesInvoices.md) | Saft Declaration Export Sales Invoice |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#id) | guid |  |
| [ObjectVersion](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [ExternalId](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] |
| [ExternalSystem](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] |
| [AggregateLastUpdateTimeUtc](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] |
| [AdditionalDataJson](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#additionaldatajson) | string | Extensible JSON object for storing this entity&apos;s custom or optional attributes. [Introduced in version 26.3.100.4] |
| [DisplayText](Regulatory.Saft.DeclarationExportSalesInvoiceLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### AccountId

Account Id`Required`

Type: **string (10)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### DebitCreditIndicator

Debit Credit Indicator`Required`

Type: **string (1)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **1**  
Show in UI: **ShownByDefault**  

### Description

Description`Required`

Type: **string (255)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **255**  
Show in UI: **ShownByDefault**  

### ExportSequence

Monotonc sequence within Declaration Export`Required` `Filter(ge;le)` `ORD` `Introduced in version 27.1.0.89`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### LineAmount

Line Amount`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineCurrencyAmount

Line Currency Amount`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineCurrencyCode

Line Currency Code`Required`

Type: **string (3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **3**  
Show in UI: **ShownByDefault**  

### ProductCode

Product code`Required`

Type: **string (35)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **35**  
Show in UI: **ShownByDefault**  

### Quantity

Quantity`Required`

Type: **decimal (18, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TaxAmount

ax Amount`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TaxCode

Tax Code`Required`

Type: **string (10)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### TaxCurrencyAmount

Tax Currency Amount`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TaxCurrencyCode

Tax Currency Code`Required`

Type: **string (3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **3**  
Show in UI: **ShownByDefault**  

### TaxPointDate

Tax Point Date`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TaxType

Tax Type`Required`

Type: **string (10)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### UnitPrice

Unit Price`Required`

Type: **decimal (14, 5)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

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

### AdditionalDataJson

Extensible JSON object for storing this entity&apos;s custom or optional attributes. [Introduced in version 26.3.100.4]

Type: **string**  
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

### SaftDeclarationExportSalesInvoice

Saft Declaration Export Sales Invoice

Type: **[DeclarationExportSalesInvoices](Regulatory.Saft.DeclarationExportSalesInvoices.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.DeclarationExportSalesInvoiceLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.DeclarationExportSalesInvoiceLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_DeclarationExportSalesInvoiceLines

Domain API Entity Type: 
Regulatory_Saft_DeclarationExportSalesInvoiceLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_DeclarationExportSalesInvoiceLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_DeclarationExportSalesInvoiceLines?$top=10>

