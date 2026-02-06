---
uid: Regulatory.Saft.ProfilePayments
---
# Regulatory.Saft.ProfilePayments


Profile/settings used to generate the SAF-T Payments section. Defines how payments are classified and mapped to NRA accounts, direction, counterparty type, and debit/credit indicator.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.ProfilePayments  
Base Table: Saft_Profile_Payments  
Introduced In Version: 26.2.0.80  
API access:  ReadWrite  

## Renames

Old name: Finance.Saft.ProfilePayments  
New name: Regulatory.Saft.ProfilePayments  
Version: 26.2.1.17  
Case: 39297  



## Visualization
Display Format: {Profile.Name}  
Search Members: Profile.Name  
Name Member: Profile.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  
Aggregate Root:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DebitCreditIndicator](Regulatory.Saft.ProfilePayments.md#debitcreditindicator) | [DebitCreditIndicator](Regulatory.Saft.ProfilePayments.md#debitcreditindicator) | Debit/credit indicator for SAF-T payment lines. 
| [Direction](Regulatory.Saft.ProfilePayments.md#direction) | [Direction](Regulatory.Saft.ProfilePayments.md#direction) | Payment direction. 
| [PartyType](Regulatory.Saft.ProfilePayments.md#partytype) | [PartyType](Regulatory.Saft.ProfilePayments.md#partytype) | Counterparty type to be populated in SAF-T: Supplier, Customer, None. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Regulatory.Saft.ProfilePayments.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | ERP.net document type that is the source of the payment. |
| [PaymentAccount](Regulatory.Saft.ProfilePayments.md#paymentaccount) | [PaymentAccounts](Finance.Payments.PaymentAccounts.md) | description: Payment account – cash desk/bank account used for the payment. |
| [PaymentReason](Regulatory.Saft.ProfilePayments.md#paymentreason) | [PaymentReasons](Finance.Payments.PaymentReasons.md) (nullable) | Payment reason/classification. |
| [Profile](Regulatory.Saft.ProfilePayments.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | Identifier of the SAFT profile associated with this settings. |
| [SaftAccountCodeEntry](Regulatory.Saft.ProfilePayments.md#saftaccountcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | Selected SAF-T mapping entry to the NRA nomenclature (value for AccountID in PaymentLine). |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.ProfilePayments.md#id) | guid |  
| [ObjectVersion](Regulatory.Saft.ProfilePayments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Saft.ProfilePayments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DebitCreditIndicator

Debit/credit indicator for SAF-T payment lines.

Type: **[DebitCreditIndicator](Regulatory.Saft.ProfilePayments.md#debitcreditindicator)**  
Category: **System**  
Allowed values for the `DebitCreditIndicator`(Regulatory.Saft.ProfilePayments.md#debitcreditindicator) data attribute  
Allowed Values (Regulatory.Saft.ProfilePaymentsRepository.DebitCreditIndicator Enum Members)  

| Value | Description |
| ---- | --- |
| Debit | Debit value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 0 <br /> Domain API Value: 'Debit' |
| Credit | Credit value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 1 <br /> Domain API Value: 'Credit' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Direction

Payment direction.

Type: **[Direction](Regulatory.Saft.ProfilePayments.md#direction)**  
Category: **System**  
Allowed values for the `Direction`(Regulatory.Saft.ProfilePayments.md#direction) data attribute  
Allowed Values (Regulatory.Saft.ProfilePaymentsRepository.Direction Enum Members)  

| Value | Description |
| ---- | --- |
| Outgoing | Outgoing value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 0 <br /> Domain API Value: 'Outgoing' |
| Incoming | Incoming value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 1 <br /> Domain API Value: 'Incoming' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PartyType

Counterparty type to be populated in SAF-T: Supplier, Customer, None.

Type: **[PartyType](Regulatory.Saft.ProfilePayments.md#partytype)**  
Category: **System**  
Allowed values for the `PartyType`(Regulatory.Saft.ProfilePayments.md#partytype) data attribute  
Allowed Values (Regulatory.Saft.ProfilePaymentsRepository.PartyType Enum Members)  

| Value | Description |
| ---- | --- |
| Supplier | Supplier value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'Supplier' |
| Customer | Customer value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 1 <br /> Domain API Value: 'Customer' |
| None | None value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 2 <br /> Domain API Value: 'None' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

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

### DocumentType

ERP.net document type that is the source of the payment.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentAccount

description: Payment account – cash desk/bank account used for the payment.

Type: **[PaymentAccounts](Finance.Payments.PaymentAccounts.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PaymentReason

Payment reason/classification.

Type: **[PaymentReasons](Finance.Payments.PaymentReasons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Profile

Identifier of the SAFT profile associated with this settings.

Type: **[Profiles](Regulatory.Saft.Profiles.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### SaftAccountCodeEntry

Selected SAF-T mapping entry to the NRA nomenclature (value for AccountID in PaymentLine).

Type: **[CodeEntries](Regulatory.Common.CodeEntries.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Regulatory.Saft.ProfilePayments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.ProfilePayments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_ProfilePayments

Domain API Entity Type: 
Regulatory_Saft_ProfilePayment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_ProfilePayments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_ProfilePayments?$top=10>

