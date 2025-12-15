---
uid: Finance.Saft.ProfilePayments
---
# Finance.Saft.ProfilePayments Entity

**Namespace:** [Finance.Saft](Finance.Saft.md)  

Profile/settings used to generate the SAF-T Payments section. Defines how payments are classified and mapped to NRA accounts, direction, counterparty type, and debit/credit indicator. Entity: Saft_Profile_Payments (Introduced in version 26.2.0.80)

## Default Visualization
Default Display Text Format:  
_{Profile.Name}_  
Default Search Members:  
_Profile.Name_  
Name Data Member:  
_Profile.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Saft.Profiles](Finance.Saft.Profiles.md)  
Aggregate Root:  
[Finance.Saft.Profiles](Finance.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DebitCreditIndicator](Finance.Saft.ProfilePayments.md#debitcreditindicator) | [DebitCreditIndicator](Finance.Saft.ProfilePayments.md#debitcreditindicator) | Debit/credit indicator for SAF-T payment lines. `Required` `Filter(eq)` 
| [Direction](Finance.Saft.ProfilePayments.md#direction) | [Direction](Finance.Saft.ProfilePayments.md#direction) | Payment direction. `Required` `Filter(eq)` 
| [DisplayText](Finance.Saft.ProfilePayments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Saft.ProfilePayments.md#id) | guid |  
| [ObjectVersion](Finance.Saft.ProfilePayments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PartyType](Finance.Saft.ProfilePayments.md#partytype) | [PartyType](Finance.Saft.ProfilePayments.md#partytype) | Counterparty type to be populated in SAF-T: Supplier, Customer, None. `Required` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Finance.Saft.ProfilePayments.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | ERP.net document type that is the source of the payment. `Filter(multi eq)` |
| [PaymentAccount](Finance.Saft.ProfilePayments.md#paymentaccount) | [Accounts](Finance.Accounting.Accounts.md) | Description: Payment account)– cash desk/bank account used for the payment. `Required` `Filter(multi eq)` |
| [PaymentReason](Finance.Saft.ProfilePayments.md#paymentreason) | [PaymentReasons](Finance.Payments.PaymentReasons.md) (nullable) | Payment reason/classification. `Filter(multi eq)` |
| [Profile](Finance.Saft.ProfilePayments.md#profile) | [Profiles](Finance.Saft.Profiles.md) | Identifier of the SAFT profile associated with this settings. `Required` `Filter(multi eq)` `Owner` |
| [SaftAccountCodeEntry](Finance.Saft.ProfilePayments.md#saftaccountcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | Selected SAF-T mapping entry to the NRA nomenclature (value for AccountID in PaymentLine). `Required` `Filter(multi eq)` |


## Attribute Details

### DebitCreditIndicator

Debit/credit indicator for SAF-T payment lines. `Required` `Filter(eq)`

_Type_: **[DebitCreditIndicator](Finance.Saft.ProfilePayments.md#debitcreditindicator)**  
_Category_: **System**  
Allowed values for the `DebitCreditIndicator`(Finance.Saft.ProfilePayments.md#debitcreditindicator) data attribute  
_Allowed Values (Finance.Saft.ProfilePaymentsRepository.DebitCreditIndicator Enum Members)_  

| Value | Description |
| ---- | --- |
| Debit | Debit. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Debit' |
| Credit | Credit . Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Credit' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Direction

Payment direction. `Required` `Filter(eq)`

_Type_: **[Direction](Finance.Saft.ProfilePayments.md#direction)**  
_Category_: **System**  
Allowed values for the `Direction`(Finance.Saft.ProfilePayments.md#direction) data attribute  
_Allowed Values (Finance.Saft.ProfilePaymentsRepository.Direction Enum Members)_  

| Value | Description |
| ---- | --- |
| Outgoing | Outgoing. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Outgoing' |
| Incoming | Incoming. Stored as 'I'. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Incoming' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PartyType

Counterparty type to be populated in SAF-T: Supplier, Customer, None. `Required` `Filter(eq)`

_Type_: **[PartyType](Finance.Saft.ProfilePayments.md#partytype)**  
_Category_: **System**  
Allowed values for the `PartyType`(Finance.Saft.ProfilePayments.md#partytype) data attribute  
_Allowed Values (Finance.Saft.ProfilePaymentsRepository.PartyType Enum Members)_  

| Value | Description |
| ---- | --- |
| Supplier | Supplier. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Supplier' |
| Customer | Customer. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Customer' |
| None | None. Stored as 'N'. <br /> _Database Value:_ 'N' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'None' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DocumentType

ERP.net document type that is the source of the payment. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PaymentAccount

Description: Payment account)– cash desk/bank account used for the payment. `Required` `Filter(multi eq)`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PaymentReason

Payment reason/classification. `Filter(multi eq)`

_Type_: **[PaymentReasons](Finance.Payments.PaymentReasons.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Profile

Identifier of the SAFT profile associated with this settings. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Profiles](Finance.Saft.Profiles.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### SaftAccountCodeEntry

Selected SAF-T mapping entry to the NRA nomenclature (value for AccountID in PaymentLine). `Required` `Filter(multi eq)`

_Type_: **[CodeEntries](Regulatory.Common.CodeEntries.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Finance.Saft.ProfilePayments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Saft.ProfilePayments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Saft_ProfilePayments

Domain API Entity Type: 
Finance_Saft_ProfilePayment

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Saft_ProfilePayments?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Saft_ProfilePayments?$top=10>

