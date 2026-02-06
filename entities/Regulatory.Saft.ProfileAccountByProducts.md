---
uid: Regulatory.Saft.ProfileAccountByProducts
---
# Regulatory.Saft.ProfileAccountByProducts


Maps the SAF-T account by product type for a selected SAF-T profile.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.ProfileAccountByProducts  
Base Table: Saft_Profile_Account_By_Products  
Introduced In Version: 26.2.0.73  
API access:  ReadWrite  

## Renames

Old name: Finance.Saft.ProfileAccountByProducts  
New name: Regulatory.Saft.ProfileAccountByProducts  
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
| [DebitCreditIndicator](Regulatory.Saft.ProfileAccountByProducts.md#debitcreditindicator) | [DebitCreditIndicator](Regulatory.Saft.ProfileAccountByProducts.md#debitcreditindicator) | Debit/credit indicator for SAF-T invoice lines. 
| [EntityKind](Regulatory.Saft.ProfileAccountByProducts.md#entitykind) | [EntityKind](Regulatory.Saft.ProfileAccountByProducts.md#entitykind) | Specifies whether the product type to SAF-T account mapping applies to sales invoices or purchase invoices. 
| [Notes](Regulatory.Saft.ProfileAccountByProducts.md#notes) | string (max) __nullable__ | Additional information or comments about the mapping. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountCodeEntry](Regulatory.Saft.ProfileAccountByProducts.md#accountcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | The SAF-T account used during SAF-T generation for the selected product type. |
| [DocumentType](Regulatory.Saft.ProfileAccountByProducts.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The ERP.net document type under which this mapping rule should be applied. |
| [ProductType](Regulatory.Saft.ProfileAccountByProducts.md#producttype) | [ProductTypes](General.Products.ProductTypes.md) | The ERP.net product type for which the SAF-T account is defined. |
| [Profile](Regulatory.Saft.ProfileAccountByProducts.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | The SAF-T profile this mapping belongs to. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.ProfileAccountByProducts.md#id) | guid |  
| [ObjectVersion](Regulatory.Saft.ProfileAccountByProducts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Saft.ProfileAccountByProducts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DebitCreditIndicator

Debit/credit indicator for SAF-T invoice lines.

Type: **[DebitCreditIndicator](Regulatory.Saft.ProfileAccountByProducts.md#debitcreditindicator)**  
Category: **System**  
Allowed values for the `DebitCreditIndicator`(Regulatory.Saft.ProfileAccountByProducts.md#debitcreditindicator) data attribute  
Allowed Values (Regulatory.Saft.ProfileAccountByProductsRepository.DebitCreditIndicator Enum Members)  

| Value | Description |
| ---- | --- |
| Debit | Debit value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 0 <br /> Domain API Value: 'Debit' |
| Credit | Credit value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 1 <br /> Domain API Value: 'Credit' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Debit**  
Show in UI: **ShownByDefault**  

### EntityKind

Specifies whether the product type to SAF-T account mapping applies to sales invoices or purchase invoices.

Type: **[EntityKind](Regulatory.Saft.ProfileAccountByProducts.md#entitykind)**  
Category: **System**  
Allowed values for the `EntityKind`(Regulatory.Saft.ProfileAccountByProducts.md#entitykind) data attribute  
Allowed Values (Regulatory.Saft.ProfileAccountByProductsRepository.EntityKind Enum Members)  

| Value | Description |
| ---- | --- |
| Sales | Sales value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 0 <br /> Domain API Value: 'Sales' |
| Purchases | Purchases value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'Purchases' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Sales**  
Show in UI: **ShownByDefault**  

### Notes

Additional information or comments about the mapping.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

### AccountCodeEntry

The SAF-T account used during SAF-T generation for the selected product type.

Type: **[CodeEntries](Regulatory.Common.CodeEntries.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentType

The ERP.net document type under which this mapping rule should be applied.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductType

The ERP.net product type for which the SAF-T account is defined.

Type: **[ProductTypes](General.Products.ProductTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Profile

The SAF-T profile this mapping belongs to.

Type: **[Profiles](Regulatory.Saft.Profiles.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileAccountByProducts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileAccountByProducts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_ProfileAccountByProducts

Domain API Entity Type: 
Regulatory_Saft_ProfileAccountByProduct

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_ProfileAccountByProducts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_ProfileAccountByProducts?$top=10>

