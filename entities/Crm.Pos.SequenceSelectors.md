---
uid: Crm.Pos.SequenceSelectors
---
# Crm.Pos.SequenceSelectors


Maps point-of-sale context data to the appropriate sequence definition used for number generation.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.SequenceSelectors  
Base Table: Pos_Sequence_Selectors  
Introduced In Version: 26.2.1.31  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {EnterpriseCompanyId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.SequenceSelectors](Crm.Pos.SequenceSelectors.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Notes](Crm.Pos.SequenceSelectors.md#notes) | string (max) __nullable__ | Stores optional descriptive notes; null means no additional information is provided. 
| [SaleKind](Crm.Pos.SequenceSelectors.md#salekind) | [SaleKind](Crm.Pos.SequenceSelectors.md#salekind) | Specifies the type of sale that determines which sequence is selected. `Required` `Default("SAL")` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Crm.Pos.SequenceSelectors.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Identifies the company for which the sequence selection applies; null means the rule applies to all companies. `Filter(multi eq)` |
| [PosDevice](Crm.Pos.SequenceSelectors.md#posdevice) | [Devices](Crm.Pos.Devices.md) (nullable) | Identifies the POS device used to determine the sequence; null means all devices are applicable. `Filter(multi eq)` |
| [PosLocation](Crm.Pos.SequenceSelectors.md#poslocation) | [Locations](Crm.Pos.Locations.md) (nullable) | Identifies the POS location used in sequence selection; null means all locations are applicable. `Filter(multi eq)` |
| [Sequence](Crm.Pos.SequenceSelectors.md#sequence) | [Sequences](Systems.Core.Sequences.md) | References the sequence definition selected for the given POS context. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.SequenceSelectors.md#id) | guid |  
| [ObjectVersion](Crm.Pos.SequenceSelectors.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pos.SequenceSelectors.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pos.SequenceSelectors.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pos.SequenceSelectors.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pos.SequenceSelectors.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Notes

Stores optional descriptive notes; null means no additional information is provided.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### SaleKind

Specifies the type of sale that determines which sequence is selected. `Required` `Default("SAL")` `Filter(multi eq)`

Type: **[SaleKind](Crm.Pos.SequenceSelectors.md#salekind)**  
Category: **System**  
Allowed values for the `SaleKind`(Crm.Pos.Sales.md#salekind) data attribute  
Allowed Values (Crm.Pos.SalesRepository.SaleKind Enum Members)  

| Value | Description |
| ---- | --- |
| NormalSale | Normal sale. Stored as 'SAL'. <br /> Database Value: 'SAL' <br /> Model Value: 0 <br /> Domain API Value: 'NormalSale' |
| ReturnOrrefund | Return/refund. Stored as 'RET'. <br /> Database Value: 'RET' <br /> Model Value: 1 <br /> Domain API Value: 'ReturnOrrefund' |
| Invoice | Invoice value. Stored as 'INV'. <br /> Database Value: 'INV' <br /> Model Value: 2 <br /> Domain API Value: 'Invoice' |
| CreditNote | CreditNote value. Stored as 'CRN'. <br /> Database Value: 'CRN' <br /> Model Value: 3 <br /> Domain API Value: 'CreditNote' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **NormalSale**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

### EnterpriseCompany

Identifies the company for which the sequence selection applies; null means the rule applies to all companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PosDevice

Identifies the POS device used to determine the sequence; null means all devices are applicable. `Filter(multi eq)`

Type: **[Devices](Crm.Pos.Devices.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PosLocation

Identifies the POS location used in sequence selection; null means all locations are applicable. `Filter(multi eq)`

Type: **[Locations](Crm.Pos.Locations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Sequence

References the sequence definition selected for the given POS context. `Required` `Filter(multi eq)`

Type: **[Sequences](Systems.Core.Sequences.md)**  
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

[!list limit=1000 erp.entity=Crm.Pos.SequenceSelectors erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.SequenceSelectors erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_SequenceSelectors

Domain API Entity Type: 
Crm_Pos_SequenceSelector

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_SequenceSelectors?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_SequenceSelectors?$top=10>

