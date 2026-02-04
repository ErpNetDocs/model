---
uid: Regulatory.Saft.ProfileTaxCodeByDealTypes
---
# Regulatory.Saft.ProfileTaxCodeByDealTypes


Maps SAF-T TaxCode for document lines by Deal type.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.ProfileTaxCodeByDealTypes  
Base Table: Saft_Profile_Tax_Code_By_Deal_Types  
Introduced In Version: 26.2.0.84  
API access:  ReadWrite  

## Visualization
Display Format: {Profile.Name}  
Search Members: Profile.Name  
Name Member: Profile.Name  
Category:  Settings  
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
| [Notes](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#notes) | string (max) __nullable__ | Additional explanation or comments about this mapping rule (e.g., rationale, special cases, internal reference). 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DealType](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#dealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) | The ERP.net deal type the mapping applies to and for which the SAF-T TaxCode is determined. |
| [DocumentType](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The ERP.net document type under which this mapping rule should be applied. |
| [Profile](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | The SAF-T profile this mapping belongs to. |
| [TaxCodeEntry](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#taxcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | The SAF-T TaxCode that the system outputs/uses during SAF-T generation when the mapping criteria are met. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#id) | guid |  
| [ObjectVersion](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

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

### DealType

The ERP.net deal type the mapping applies to and for which the SAF-T TaxCode is determined.

Type: **[DealTypes](Regulatory.Vat.DealTypes.md)**  
Indexed: **True**  
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

The SAF-T TaxCode that the system outputs/uses during SAF-T generation when the mapping criteria are met.

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

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileTaxCodeByDealTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileTaxCodeByDealTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_ProfileTaxCodeByDealTypes

Domain API Entity Type: 
Regulatory_Saft_ProfileTaxCodeByDealType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_ProfileTaxCodeByDealTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_ProfileTaxCodeByDealTypes?$top=10>

