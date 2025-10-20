---
uid: Finance.Vat.DealTypes
---
# Finance.Vat.DealTypes Entity

**Namespace:** [Finance.Vat](Finance.Vat.md)  

Contains deal types supported by the system as well as user-defined types. Entity: VAT_Deal_Types

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Vat.DealTypes](Finance.Vat.DealTypes.md)  
  * [Finance.Vat.DealTypeDocumentAmounts](Finance.Vat.DealTypeDocumentAmounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Finance.Vat.DealTypes.md#code) | string (32) | Code of the deal type. `Required` `Filter(multi eq;like)` `ORD` `Introduced in version 23.1.0.32` 
| [DisplayText](Finance.Vat.DealTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EntryType](Finance.Vat.DealTypes.md#entrytype) | [EntryType](Finance.Vat.DealTypes.md#entrytype) | Type of the VAT entries, which are made for this deal type. S=Sales, P=Purchases. `Required` `Filter(eq)` 
| [ExternalId](Finance.Vat.DealTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Vat.DealTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Finance.Vat.DealTypes.md#id) | guid |  
| [IsSystem](Finance.Vat.DealTypes.md#issystem) | boolean | Is_System is True for those deal types that are managed by the system via update procedures and cannot be edited by the user. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [Name](Finance.Vat.DealTypes.md#name) | string (254) | Description of the deal type. `Required` `Filter(eq;like)` 
| [ObjectVersion](Finance.Vat.DealTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [TaxCode](Finance.Vat.DealTypes.md#taxcode) | [TaxCode](Finance.Vat.DealTypes.md#taxcode) | VAT rate type for this deal type. Can be among "STD"(Standard rate), "RED"(Reduced rate), "SPR"(Super-reduced rates), "INT"(Intermediary (Parking) rates), "EXM"(Tax Exempt), "NS"(Non-subject to tax). `Required` `Filter(multi eq)` `Introduced in version 23.1.0.33` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Country](Finance.Vat.DealTypes.md#country) | [Countries](General.Geography.Countries.md) | The country for which this deal type applies. The country is matched against the country of the enterprise company. `Required` `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| DocumentAmounts | [DealTypeDocumentAmounts](Finance.Vat.DealTypeDocumentAmounts.md) | List of `DealTypeDocumentAmount`(Finance.Vat.DealTypeDocumentAmounts.md) child objects, based on the `Finance.Vat.DealTypeDocumentAmount.DealType`(Finance.Vat.DealTypeDocumentAmounts.md#dealtype) back reference 


## Attribute Details

### Code

Code of the deal type. `Required` `Filter(multi eq;like)` `ORD` `Introduced in version 23.1.0.32`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EntryType

Type of the VAT entries, which are made for this deal type. S=Sales, P=Purchases. `Required` `Filter(eq)`

_Type_: **[EntryType](Finance.Vat.DealTypes.md#entrytype)**  
_Category_: **System**  
Allowed values for the `EntryType`(Finance.Vat.DealTypes.md#entrytype) data attribute  
_Allowed Values (Finance.Vat.DealTypesRepository.EntryType Enum Members)_  

| Value | Description |
| ---- | --- |
| Purchases | Purchases value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Purchases' |
| Sales | Sales value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Sales' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsSystem

Is_System is True for those deal types that are managed by the system via update procedures and cannot be edited by the user. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

Description of the deal type. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### TaxCode

VAT rate type for this deal type. Can be among "STD"(Standard rate), "RED"(Reduced rate), "SPR"(Super-reduced rates), "INT"(Intermediary (Parking) rates), "EXM"(Tax Exempt), "NS"(Non-subject to tax). `Required` `Filter(multi eq)` `Introduced in version 23.1.0.33`

_Type_: **[TaxCode](Finance.Vat.DealTypes.md#taxcode)**  
_Category_: **System**  
Allowed values for the `TaxCode`(Finance.Vat.DealTypes.md#taxcode) data attribute  
_Allowed Values (Finance.Vat.DealTypesRepository.TaxCode Enum Members)_  

| Value | Description |
| ---- | --- |
| StandardRate | StandardRate value. Stored as 'STD'. <br /> _Database Value:_ 'STD' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'StandardRate' |
| ReducedRate | ReducedRate value. Stored as 'RED'. <br /> _Database Value:_ 'RED' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ReducedRate' |
| SuperReducedRates | SuperReducedRates value. Stored as 'SPR'. <br /> _Database Value:_ 'SPR' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'SuperReducedRates' |
| IntermediaryParkingRates | IntermediaryParkingRates value. Stored as 'INT'. <br /> _Database Value:_ 'INT' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'IntermediaryParkingRates' |
| TaxExempt | TaxExempt value. Stored as 'EXM'. <br /> _Database Value:_ 'EXM' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'TaxExempt' |
| NonSubjectToTax | NonSubjectToTax value. Stored as 'NS '. <br /> _Database Value:_ 'NS ' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'NonSubjectToTax' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Country

The country for which this deal type applies. The country is matched against the country of the enterprise company. `Required` `Filter(multi eq)`

_Type_: **[Countries](General.Geography.Countries.md)**  
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

[!list limit=1000 erp.entity=Finance.Vat.DealTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Vat.DealTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set:
Finance_Vat_DealTypes

Domain API Entity Type:
Finance_Vat_DealType

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Vat_DealTypes?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Vat_DealTypes?$top=10>

