---
uid: Regulatory.Vat.DealTypes
---
# Regulatory.Vat.DealTypes


Contains deal types supported by the system as well as user-defined types.

## General
Namespace: [Regulatory.Vat](Regulatory.Vat.md)  
Repository: Regulatory.Vat.DealTypes  
Base Table: VAT_Deal_Types  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Vat.DealTypes](Regulatory.Vat.DealTypes.md)  
  * [Regulatory.Vat.DealTypeDocumentAmounts](Regulatory.Vat.DealTypeDocumentAmounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Regulatory.Vat.DealTypes.md#code) | string (32) | Code of the deal type. `Required` `Filter(multi eq;like)` `ORD` `Introduced in version 23.1.0.32` 
| [EntryType](Regulatory.Vat.DealTypes.md#entrytype) | [EntryType](Regulatory.Vat.DealTypes.md#entrytype) | Type of the VAT entries, which are made for this deal type. S=Sales, P=Purchases. `Required` `Filter(eq)` 
| [IsSystem](Regulatory.Vat.DealTypes.md#issystem) | boolean | Is_System is True for those deal types that are managed by the system via update procedures and cannot be edited by the user. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [Name](Regulatory.Vat.DealTypes.md#name) | string (254) | Description of the deal type. `Required` `Filter(eq;like)` 
| [TaxCode](Regulatory.Vat.DealTypes.md#taxcode) | [TaxCode](Regulatory.Vat.DealTypes.md#taxcode) | VAT rate type for this deal type. Can be among "STD"(Standard rate), "RED"(Reduced rate), "SPR"(Super-reduced rates), "INT"(Intermediary (Parking) rates), "EXM"(Tax Exempt), "NS"(Non-subject to tax). `Required` `Filter(multi eq)` `Introduced in version 23.1.0.33` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Country](Regulatory.Vat.DealTypes.md#country) | [Countries](General.Geography.Countries.md) | The country for which this deal type applies. The country is matched against the country of the enterprise company. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Vat.DealTypes.md#id) | guid |  
| [ObjectVersion](Regulatory.Vat.DealTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Vat.DealTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Vat.DealTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Vat.DealTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Vat.DealTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| DocumentAmounts | [DealTypeDocumentAmounts](Regulatory.Vat.DealTypeDocumentAmounts.md) | List of `DealTypeDocumentAmount`(Regulatory.Vat.DealTypeDocumentAmounts.md) child objects, based on the `Regulatory.Vat.DealTypeDocumentAmount.DealType`(Regulatory.Vat.DealTypeDocumentAmounts.md#dealtype) back reference 


## Attribute Details

### Code

Code of the deal type. `Required` `Filter(multi eq;like)` `ORD` `Introduced in version 23.1.0.32`

Type: **string (32)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### EntryType

Type of the VAT entries, which are made for this deal type. S=Sales, P=Purchases. `Required` `Filter(eq)`

Type: **[EntryType](Regulatory.Vat.DealTypes.md#entrytype)**  
Category: **System**  
Allowed values for the `EntryType`(Regulatory.Vat.DealTypes.md#entrytype) data attribute  
Allowed Values (Regulatory.Vat.DealTypesRepository.EntryType Enum Members)  

| Value | Description |
| ---- | --- |
| Purchases | Purchases value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 0 <br /> Domain API Value: 'Purchases' |
| Sales | Sales value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 1 <br /> Domain API Value: 'Sales' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsSystem

Is_System is True for those deal types that are managed by the system via update procedures and cannot be edited by the user. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Name

Description of the deal type. `Required` `Filter(eq;like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### TaxCode

VAT rate type for this deal type. Can be among "STD"(Standard rate), "RED"(Reduced rate), "SPR"(Super-reduced rates), "INT"(Intermediary (Parking) rates), "EXM"(Tax Exempt), "NS"(Non-subject to tax). `Required` `Filter(multi eq)` `Introduced in version 23.1.0.33`

Type: **[TaxCode](Regulatory.Vat.DealTypes.md#taxcode)**  
Category: **System**  
Allowed values for the `TaxCode`(Regulatory.Vat.DealTypes.md#taxcode) data attribute  
Allowed Values (Regulatory.Vat.DealTypesRepository.TaxCode Enum Members)  

| Value | Description |
| ---- | --- |
| StandardRate | StandardRate value. Stored as 'STD'. <br /> Database Value: 'STD' <br /> Model Value: 0 <br /> Domain API Value: 'StandardRate' |
| ReducedRate | ReducedRate value. Stored as 'RED'. <br /> Database Value: 'RED' <br /> Model Value: 1 <br /> Domain API Value: 'ReducedRate' |
| SuperReducedRates | SuperReducedRates value. Stored as 'SPR'. <br /> Database Value: 'SPR' <br /> Model Value: 2 <br /> Domain API Value: 'SuperReducedRates' |
| IntermediaryParkingRates | IntermediaryParkingRates value. Stored as 'INT'. <br /> Database Value: 'INT' <br /> Model Value: 3 <br /> Domain API Value: 'IntermediaryParkingRates' |
| TaxExempt | TaxExempt value. Stored as 'EXM'. <br /> Database Value: 'EXM' <br /> Model Value: 4 <br /> Domain API Value: 'TaxExempt' |
| NonSubjectToTax | NonSubjectToTax value. Stored as 'NS '. <br /> Database Value: 'NS ' <br /> Model Value: 5 <br /> Domain API Value: 'NonSubjectToTax' |

Supported Filters: **Equals, EqualsIn**  
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

### Country

The country for which this deal type applies. The country is matched against the country of the enterprise company. `Required` `Filter(multi eq)`

Type: **[Countries](General.Geography.Countries.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Vat.DealTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Vat.DealTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Vat_DealTypes

Domain API Entity Type: 
Regulatory_Vat_DealType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Vat_DealTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Vat_DealTypes?$top=10>

