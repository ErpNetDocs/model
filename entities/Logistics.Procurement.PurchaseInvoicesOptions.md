---
uid: Logistics.Procurement.PurchaseInvoicesOptions
---
# Logistics.Procurement.PurchaseInvoicesOptions Entity

**Namespace:** [Logistics.Procurement](Logistics.Procurement.md)  

Contains purchase invoice specific options for the different document types. Entity: Scm_Purchase_Invoices_Options

## Default Visualization
Default Display Text Format:  
_{DocumentType.EntityName}_  
Default Search Members:  
_DocumentType.EntityName_  
Name Data Member:  
_DocumentType.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Logistics.Procurement.PurchaseInvoicesOptions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Procurement.PurchaseInvoicesOptions.md#id) | guid |  
| [ObjectVersion](Logistics.Procurement.PurchaseInvoicesOptions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SignRestriction](Logistics.Procurement.PurchaseInvoicesOptions.md#signrestriction) | [SignRestriction](Logistics.Procurement.PurchaseInvoicesOptions.md#signrestriction) | This option can restrict the sign of the Line Amounts for each detail line in purchase invoices of the specified document type. `Required` `Default(0)` 
| [TotalAmountSignRestriction](Logistics.Procurement.PurchaseInvoicesOptions.md#totalamountsignrestriction) | [TotalAmountSignRestriction](Logistics.Procurement.PurchaseInvoicesOptions.md#totalamountsignrestriction) | This option can restrict the sign of the Total Amounts of the purchase invoices of the specified document type. The restriction is applied upon document Release. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Logistics.Procurement.PurchaseInvoicesOptions.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type, for which the options are specified. `Required` `Filter(multi eq)` `Owner` |


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
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### SignRestriction

This option can restrict the sign of the Line Amounts for each detail line in purchase invoices of the specified document type. `Required` `Default(0)`

_Type_: **[SignRestriction](Logistics.Procurement.PurchaseInvoicesOptions.md#signrestriction)**  
_Category_: **System**  
Allowed values for the `SignRestriction`(Logistics.Procurement.PurchaseInvoicesOptions.md#signrestriction) data attribute  
_Allowed Values (Logistics.Procurement.PurchaseInvoicesOptionsRepository.SignRestriction Enum Members)_  

| Value | Description |
| ---- | --- |
| AllowAll | AllowAll value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AllowAll' |
| AllowOnlyPositive | AllowOnlyPositive value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AllowOnlyPositive' |
| AllowOnlyNegative | AllowOnlyNegative value. Stored as -1. <br /> _Database Value:_ -1 <br /> _Model Value:_ -1 <br /> _Domain API Value:_ 'AllowOnlyNegative' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### TotalAmountSignRestriction

This option can restrict the sign of the Total Amounts of the purchase invoices of the specified document type. The restriction is applied upon document Release. `Required` `Default(0)`

_Type_: **[TotalAmountSignRestriction](Logistics.Procurement.PurchaseInvoicesOptions.md#totalamountsignrestriction)**  
_Category_: **System**  
Allowed values for the `TotalAmountSignRestriction`(Logistics.Procurement.PurchaseInvoicesOptions.md#totalamountsignrestriction) data attribute  
_Allowed Values (Logistics.Procurement.PurchaseInvoicesOptionsRepository.TotalAmountSignRestriction Enum Members)_  

| Value | Description |
| ---- | --- |
| AllowAll | AllowAll value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AllowAll' |
| AllowOnlyPositive | AllowOnlyPositive value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AllowOnlyPositive' |
| AllowOnlyNegative | AllowOnlyNegative value. Stored as -1. <br /> _Database Value:_ -1 <br /> _Model Value:_ -1 <br /> _Domain API Value:_ 'AllowOnlyNegative' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DocumentType

The document type, for which the options are specified. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseInvoicesOptions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Procurement.PurchaseInvoicesOptions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Procurement_PurchaseInvoicesOptions

Domain API Entity Type: 
Logistics_Procurement_PurchaseInvoicesOption

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Procurement_PurchaseInvoicesOptions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Procurement_PurchaseInvoicesOptions?$top=10>

