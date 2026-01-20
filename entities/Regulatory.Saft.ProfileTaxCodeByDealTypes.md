---
uid: Regulatory.Saft.ProfileTaxCodeByDealTypes
---
# Regulatory.Saft.ProfileTaxCodeByDealTypes Entity

**Namespace:** [Regulatory.Saft](Regulatory.Saft.md)  

Maps SAF-T TaxCode for document lines by Deal type. Entity: Saft_Profile_Tax_Code_By_Deal_Types (Introduced in version 26.2.0.84)

## Default Visualization
Default Display Text Format:  
_{Profile.Name}_  
Default Search Members:  
_Profile.Name_  
Name Data Member:  
_Profile.Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  
Aggregate Root:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#id) | guid |  
| [Notes](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#notes) | string (max) __nullable__ | Additional explanation or comments about this mapping rule (e.g., rationale, special cases, internal reference). `Filter(like)` 
| [ObjectVersion](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DealType](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#dealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) | The ERP.net deal type the mapping applies to and for which the SAF-T TaxCode is determined. `Required` `Filter(multi eq)` |
| [DocumentType](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable) | The ERP.net document type under which this mapping rule should be applied. `Filter(multi eq)` |
| [Profile](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | The SAF-T profile this mapping belongs to. `Required` `Filter(multi eq)` `Owner` |
| [TaxCodeEntry](Regulatory.Saft.ProfileTaxCodeByDealTypes.md#taxcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | The SAF-T TaxCode that the system outputs/uses during SAF-T generation when the mapping criteria are met. `Required` `Filter(multi eq)` |


## Attribute Details

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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Additional explanation or comments about this mapping rule (e.g., rationale, special cases, internal reference). `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### DealType

The ERP.net deal type the mapping applies to and for which the SAF-T TaxCode is determined. `Required` `Filter(multi eq)`

_Type_: **[DealTypes](Regulatory.Vat.DealTypes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DocumentType

The ERP.net document type under which this mapping rule should be applied. `Filter(multi eq)`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Profile

The SAF-T profile this mapping belongs to. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Profiles](Regulatory.Saft.Profiles.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### TaxCodeEntry

The SAF-T TaxCode that the system outputs/uses during SAF-T generation when the mapping criteria are met. `Required` `Filter(multi eq)`

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

