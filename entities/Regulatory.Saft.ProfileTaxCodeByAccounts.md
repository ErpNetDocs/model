---
uid: Regulatory.Saft.ProfileTaxCodeByAccounts
---
# Regulatory.Saft.ProfileTaxCodeByAccounts


Maps SAF-T TaxCode for GL entry lines by account, analytic and document type.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.ProfileTaxCodeByAccounts  
Base Table: Saft_Profile_Tax_Code_By_Accounts  
Introduced In Version: 26.2.0.85  
API access:  ReadWrite  

## Renames

Old name: Finance.Saft.ProfileTaxCodeByAccounts  
New name: Regulatory.Saft.ProfileTaxCodeByAccounts  
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
| [CustomPropertyValue](Regulatory.Saft.ProfileTaxCodeByAccounts.md#custompropertyvalue) | string (254) __nullable__ | The specific value of the selected analytic custom property for which this mapping applies. 
| [Notes](Regulatory.Saft.ProfileTaxCodeByAccounts.md#notes) | string (max) __nullable__ | Additional explanation or comments about this mapping rule (e.g., rationale, special cases, internal reference). 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Regulatory.Saft.ProfileTaxCodeByAccounts.md#account) | [Accounts](Finance.Accounting.Accounts.md) | The ERP.net general ledger account for which the SAF-T tax code is defined. |
| [CustomProperty](Regulatory.Saft.ProfileTaxCodeByAccounts.md#customproperty) | [CustomProperties](Systems.Bpm.CustomProperties.md) (nullable) | The account analytic custom property used to differentiate the applicable SAF-T tax code. |
| [DocumentType](Regulatory.Saft.ProfileTaxCodeByAccounts.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The ERP.net document type under which this mapping rule should be applied. |
| [Profile](Regulatory.Saft.ProfileTaxCodeByAccounts.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | The SAF-T profile this mapping belongs to. |
| [TaxCodeEntry](Regulatory.Saft.ProfileTaxCodeByAccounts.md#taxcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | The SAF-T Tax Code to output when the criteria (account + analytic + document type) are met. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.ProfileTaxCodeByAccounts.md#id) | guid |  
| [ObjectVersion](Regulatory.Saft.ProfileTaxCodeByAccounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Saft.ProfileTaxCodeByAccounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CustomPropertyValue

The specific value of the selected analytic custom property for which this mapping applies.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Notes

Additional explanation or comments about this mapping rule (e.g., rationale, special cases, internal reference).

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

### Account

The ERP.net general ledger account for which the SAF-T tax code is defined.

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CustomProperty

The account analytic custom property used to differentiate the applicable SAF-T tax code.

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentType

The ERP.net document type under which this mapping rule should be applied.

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
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

### TaxCodeEntry

The SAF-T Tax Code to output when the criteria (account + analytic + document type) are met.

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

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileTaxCodeByAccounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileTaxCodeByAccounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_ProfileTaxCodeByAccounts

Domain API Entity Type: 
Regulatory_Saft_ProfileTaxCodeByAccount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_ProfileTaxCodeByAccounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_ProfileTaxCodeByAccounts?$top=10>

