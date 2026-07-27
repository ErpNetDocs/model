---
uid: Regulatory.Saft.DeclarationExportVoucherLines
---
# Regulatory.Saft.DeclarationExportVoucherLines


Contains Voucher lines of `SAFT_Declaration_Export_Vouchers`.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.DeclarationExportVoucherLines  
Base Table: Saft_Declaration_Export_Voucher_Lines  
Introduced In Version: 27.1.0.86  
API access:  ReadOnly  

## Visualization
Display Format: {CurrencyCode}  
Search Members: CurrencyCode  
Code Member: CurrencyCode  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Saft.DeclarationExportVoucherLines](Regulatory.Saft.DeclarationExportVoucherLines.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountId](Regulatory.Saft.DeclarationExportVoucherLines.md#accountid) | string (10) | Account Id`Required` |
| [Amount](Regulatory.Saft.DeclarationExportVoucherLines.md#amount) | decimal (18, 2) | Amount`Required` |
| [Credit](Regulatory.Saft.DeclarationExportVoucherLines.md#credit) | decimal (18, 2) | Credit`Required` |
| [CreditBase](Regulatory.Saft.DeclarationExportVoucherLines.md#creditbase) | decimal (18, 2) | Credit Base`Required` |
| [CurrencyAmount](Regulatory.Saft.DeclarationExportVoucherLines.md#currencyamount) | decimal (18, 2) | Currency Amount`Required` |
| [CurrencyCode](Regulatory.Saft.DeclarationExportVoucherLines.md#currencycode) | string (3) | Currency Code`Required` |
| [CustomerId](Regulatory.Saft.DeclarationExportVoucherLines.md#customerid) | string (35) | Customer Id`Required` |
| [Debit](Regulatory.Saft.DeclarationExportVoucherLines.md#debit) | decimal (18, 2) | Debit`Required` |
| [DebitBase](Regulatory.Saft.DeclarationExportVoucherLines.md#debitbase) | decimal (18, 2) | Debit Base`Required` |
| [Description](Regulatory.Saft.DeclarationExportVoucherLines.md#description) | string (255) __nullable__ | Description |
| [ExportSequence](Regulatory.Saft.DeclarationExportVoucherLines.md#exportsequence) | int32 | Monotonc sequence within Declaration Export`Required` `Filter(ge;le)` `ORD` `Introduced in version 27.1.0.89` |
| [PartyCode](Regulatory.Saft.DeclarationExportVoucherLines.md#partycode) | string (2) | Party Code`Required` |
| [RecordId](Regulatory.Saft.DeclarationExportVoucherLines.md#recordid) | int32 | Recort Id`Required` |
| [SupplierId](Regulatory.Saft.DeclarationExportVoucherLines.md#supplierid) | string (35) | Supplier Id`Required` |
| [TaxCode](Regulatory.Saft.DeclarationExportVoucherLines.md#taxcode) | string (10) | Tax Code`Required` |
| [TaxpayerAccountId](Regulatory.Saft.DeclarationExportVoucherLines.md#taxpayeraccountid) | string (10) | Taxpayer Account`Required` |
| [TaxType](Regulatory.Saft.DeclarationExportVoucherLines.md#taxtype) | string (10) | Tax Type`Required` |
| [TransactionId](Regulatory.Saft.DeclarationExportVoucherLines.md#transactionid) | guid | Trnsaction Id. `Required` `Filter(multi eq)` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [SaftDeclaration<br />ExportVoucher](Regulatory.Saft.DeclarationExportVoucherLines.md#saftdeclarationexportvoucher) | [DeclarationExportVouchers](Regulatory.Saft.DeclarationExportVouchers.md) | Saft Declaration Export Voucher |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.DeclarationExportVoucherLines.md#id) | guid |  |
| [ObjectVersion](Regulatory.Saft.DeclarationExportVoucherLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [ExternalId](Regulatory.Saft.DeclarationExportVoucherLines.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] |
| [ExternalSystem](Regulatory.Saft.DeclarationExportVoucherLines.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] |
| [AggregateLastUpdateTimeUtc](Regulatory.Saft.DeclarationExportVoucherLines.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] |
| [AdditionalDataJson](Regulatory.Saft.DeclarationExportVoucherLines.md#additionaldatajson) | string | Extensible JSON object for storing this entity&apos;s custom or optional attributes. [Introduced in version 26.3.100.4] |
| [DisplayText](Regulatory.Saft.DeclarationExportVoucherLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### AccountId

Account Id`Required`

Type: **string (10)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### Amount

Amount`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Credit

Credit`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreditBase

Credit Base`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CurrencyAmount

Currency Amount`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CurrencyCode

Currency Code`Required`

Type: **string (3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **3**  
Show in UI: **ShownByDefault**  

### CustomerId

Customer Id`Required`

Type: **string (35)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **35**  
Show in UI: **ShownByDefault**  

### Debit

Debit`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DebitBase

Debit Base`Required`

Type: **decimal (18, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Description

Description

Type: **string (255) __nullable__**  
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

### PartyCode

Party Code`Required`

Type: **string (2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2**  
Show in UI: **ShownByDefault**  

### RecordId

Recort Id`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SupplierId

Supplier Id`Required`

Type: **string (35)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **35**  
Show in UI: **ShownByDefault**  

### TaxCode

Tax Code`Required`

Type: **string (10)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### TaxpayerAccountId

Taxpayer Account`Required`

Type: **string (10)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### TaxType

Tax Type`Required`

Type: **string (10)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### TransactionId

Trnsaction Id. `Required` `Filter(multi eq)`

Type: **guid**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

### SaftDeclarationExportVoucher

Saft Declaration Export Voucher

Type: **[DeclarationExportVouchers](Regulatory.Saft.DeclarationExportVouchers.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Saft.DeclarationExportVoucherLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.DeclarationExportVoucherLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_DeclarationExportVoucherLines

Domain API Entity Type: 
Regulatory_Saft_DeclarationExportVoucherLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_DeclarationExportVoucherLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_DeclarationExportVoucherLines?$top=10>

