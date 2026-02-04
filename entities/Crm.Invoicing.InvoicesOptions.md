---
uid: Crm.Invoicing.InvoicesOptions
---
# Crm.Invoicing.InvoicesOptions


Default options for user document types for Invoices

## General
Namespace: [Crm.Invoicing](Crm.Invoicing.md)  
Repository: Crm.Invoicing.InvoicesOptions  
Base Table: Crm_Invoices_Options  
API access:  ReadWrite  

## Visualization
Display Format: {DocumentType.EntityName}  
Search Members: DocumentType.EntityName  
Name Member: DocumentType.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreatesVATEntries](Crm.Invoicing.InvoicesOptions.md#createsvatentries) | boolean | Specifies whether the invoices of the current type create entries in the VAT ledges. If is used, for instance, to determine if null VAT entry should be automatically created when the invoice is voided. `Required` `Default(true)` 
| [SignRestriction](Crm.Invoicing.InvoicesOptions.md#signrestriction) | [SignRestriction](Crm.Invoicing.InvoicesOptions.md#signrestriction) | Restricts the sign of the line amounts of the invoices. -1 =allow only negative, 0=allow all, 1=allow only positive amounts. `Required` `Default(0)` 
| [TotalAmountSignRestriction](Crm.Invoicing.InvoicesOptions.md#totalamountsignrestriction) | [SignRestriction](Crm.Invoicing.InvoicesOptions.md#totalamountsignrestriction) | Restricts the sign of the total amount (amount to pay) of the invoices. -1 =allow only negative, 0=allow all, 1=allow only positive amounts. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DefaultDealType](Crm.Invoicing.InvoicesOptions.md#defaultdealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) (nullable) | When not null, specifies default VAT deal type. `Filter(multi eq)` |
| [DocumentType](Crm.Invoicing.InvoicesOptions.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type for which the invoice option applies. `Required` `Filter(multi eq)` `Owner` |
| [VATDeviationDocument<br />AmountType](Crm.Invoicing.InvoicesOptions.md#vatdeviationdocumentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | Document amount that contains the difference between the total amount of the invoice formed by unit prices with VAT and the amount formed by unit prices without VAT. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Invoicing.InvoicesOptions.md#id) | guid |  
| [ObjectVersion](Crm.Invoicing.InvoicesOptions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Crm.Invoicing.InvoicesOptions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreatesVATEntries

Specifies whether the invoices of the current type create entries in the VAT ledges. If is used, for instance, to determine if null VAT entry should be automatically created when the invoice is voided. `Required` `Default(true)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### SignRestriction

Restricts the sign of the line amounts of the invoices. -1 =allow only negative, 0=allow all, 1=allow only positive amounts. `Required` `Default(0)`

Type: **[SignRestriction](Crm.Invoicing.InvoicesOptions.md#signrestriction)**  
Category: **System**  
Generic enum type for SignRestriction properties  
Allowed Values (General.SignRestriction Enum Members)  

| Value | Description |
| ---- | --- |
| AllowAll | AllowAll value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'AllowAll' |
| AllowOnlyPositive | AllowOnlyPositive value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'AllowOnlyPositive' |
| AllowOnlyNegative | AllowOnlyNegative value. Stored as -1. <br /> Database Value: -1 <br /> Model Value: -1 <br /> Domain API Value: 'AllowOnlyNegative' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### TotalAmountSignRestriction

Restricts the sign of the total amount (amount to pay) of the invoices. -1 =allow only negative, 0=allow all, 1=allow only positive amounts. `Required` `Default(0)`

Type: **[SignRestriction](Crm.Invoicing.InvoicesOptions.md#totalamountsignrestriction)**  
Category: **System**  
Generic enum type for SignRestriction properties  
Allowed Values (General.SignRestriction Enum Members)  

| Value | Description |
| ---- | --- |
| AllowAll | AllowAll value. Stored as 0. <br /> Database Value: 0 <br /> Model Value: 0 <br /> Domain API Value: 'AllowAll' |
| AllowOnlyPositive | AllowOnlyPositive value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'AllowOnlyPositive' |
| AllowOnlyNegative | AllowOnlyNegative value. Stored as -1. <br /> Database Value: -1 <br /> Model Value: -1 <br /> Domain API Value: 'AllowOnlyNegative' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
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

### DefaultDealType

When not null, specifies default VAT deal type. `Filter(multi eq)`

Type: **[DealTypes](Regulatory.Vat.DealTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentType

The document type for which the invoice option applies. `Required` `Filter(multi eq)` `Owner`

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### VATDeviationDocumentAmountType

Document amount that contains the difference between the total amount of the invoice formed by unit prices with VAT and the amount formed by unit prices without VAT. `Filter(multi eq)`

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Invoicing.InvoicesOptions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Invoicing.InvoicesOptions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Invoicing_InvoicesOptions

Domain API Entity Type: 
Crm_Invoicing_InvoicesOption

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Invoicing_InvoicesOptions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Invoicing_InvoicesOptions?$top=10>

