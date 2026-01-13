---
uid: Regulatory.Vat.BoxTypeDealTypes
---
# Regulatory.Vat.BoxTypeDealTypes Entity

**Namespace:** [Regulatory.Vat](Regulatory.Vat.md)  

Determines the Amount Category which will be accumulated in the Box Type according to the specified the Deal Type. Entity: VAT_Box_Type_Deal_Types (Introduced in version 22.1.5.98)

## Default Visualization
Default Display Text Format:  
_{Id}: {BoxTypeId}_  
Default Search Members:  
__  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Vat.BoxTypeDealTypes](Regulatory.Vat.BoxTypeDealTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountCategory](Regulatory.Vat.BoxTypeDealTypes.md#amountcategory) | [AmountCategory](Regulatory.Vat.BoxTypeDealTypes.md#amountcategory) | Specifies the amount type from the Vat Entry which will be accumulated. `Required` `Filter(multi eq)` 
| [DisplayText](Regulatory.Vat.BoxTypeDealTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Regulatory.Vat.BoxTypeDealTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Vat.BoxTypeDealTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Regulatory.Vat.BoxTypeDealTypes.md#id) | guid |  
| [Notes](Regulatory.Vat.BoxTypeDealTypes.md#notes) | string (max) __nullable__ | Notes for this BoxTypeDealType. 
| [ObjectVersion](Regulatory.Vat.BoxTypeDealTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BoxType](Regulatory.Vat.BoxTypeDealTypes.md#boxtype) | [BoxTypes](Regulatory.Vat.BoxTypes.md) | The type of box in a VAT declaration. `Required` `Filter(multi eq)` |
| [DealType](Regulatory.Vat.BoxTypeDealTypes.md#dealtype) | [DealTypes](Regulatory.Vat.DealTypes.md) | Deal Type for the box. `Required` `Filter(multi eq)` |


## Attribute Details

### AmountCategory

Specifies the amount type from the Vat Entry which will be accumulated. `Required` `Filter(multi eq)`

_Type_: **[AmountCategory](Regulatory.Vat.BoxTypeDealTypes.md#amountcategory)**  
_Category_: **System**  
Allowed values for the `AmountCategory`(Regulatory.Vat.BoxTypeDealTypes.md#amountcategory) data attribute  
_Allowed Values (Regulatory.Vat.BoxTypeDealTypesRepository.AmountCategory Enum Members)_  

| Value | Description |
| ---- | --- |
| VAT | The amount of the tax for the operation in base currency.. Stored as 'V'. <br /> _Database Value:_ 'V' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'VAT' |
| BASE | Amount of the operation without the tax in base currency.. Stored as 'B'. <br /> _Database Value:_ 'B' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'BASE' |
| TOTAL | Amount of the operation with the tax in base currency.. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'TOTAL' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Notes for this BoxTypeDealType.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

### BoxType

The type of box in a VAT declaration. `Required` `Filter(multi eq)`

_Type_: **[BoxTypes](Regulatory.Vat.BoxTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DealType

Deal Type for the box. `Required` `Filter(multi eq)`

_Type_: **[DealTypes](Regulatory.Vat.DealTypes.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Vat.BoxTypeDealTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Vat.BoxTypeDealTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Vat_BoxTypeDealTypes

Domain API Entity Type: 
Regulatory_Vat_BoxTypeDealType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Vat_BoxTypeDealTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Vat_BoxTypeDealTypes?$top=10>

