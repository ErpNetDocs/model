---
uid: General.Documents.DocumentDistributedAmounts
---
# General.Documents.DocumentDistributedAmounts Entity

**Namespace:** [General.Documents](General.Documents.md)  

Contains the amounts which are distributed by the system over the document lines as a result of additional amount calculations. Entity: Gen_Document_Distributed_Amounts

## Renames

Old name: **General.DocumentDistributedAmounts**  
New name: **General.Documents.DocumentDistributedAmounts**  
Version: **25.1.0.64**  
Case: **37169**  



## Default Visualization
Default Display Text Format:  
_{DocumentAmountType} {DocumentLineId} {Amount}_  
Default Search Members:  
_Document.DocumentNo_  
Name Data Member:  
_Document.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Documents.Documents](General.Documents.Documents.md)  
Aggregate Root:  
[General.Documents.Documents](General.Documents.Documents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](General.Documents.DocumentDistributedAmounts.md#amount) | [Amount (14, 2)](../data-types.md#amount) | The amount which has beed distributed over the current line. The amount is in the currency of the document. `Currency: GetDocumentCurrency()` `Required` `Filter(ge;le)` 
| [BaseAmount](General.Documents.DocumentDistributedAmounts.md#baseamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | The calculated base amount for the line in document currency. The base amount is the base, over which the additional amounts are calculated. Null if the base amount is not stored (for amounts distributed in older versions of the system). . `Currency: GetDocumentCurrency()` `Introduced in version 22.1.4.44` 
| [DisplayText](General.Documents.DocumentDistributedAmounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DocumentLineId](General.Documents.DocumentDistributedAmounts.md#documentlineid) | guid __nullable__ | The Id of the line over which the amount is distributed. `Filter(multi eq)` 
| [Id](General.Documents.DocumentDistributedAmounts.md#id) | guid |  
| [ObjectVersion](General.Documents.DocumentDistributedAmounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.Documents.DocumentDistributedAmounts.md#document) | [Documents](General.Documents.Documents.md) | The <see cref="Document"/> to which this DocumentDistributedAmount belongs. `Required` `Filter(multi eq)` `Owner` |
| [DocumentAmountType](General.Documents.DocumentDistributedAmounts.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) | The type of amount which is distributed. `Required` `Filter(multi eq)` |
| [ReferencedDocument](General.Documents.DocumentDistributedAmounts.md#referenceddocument) | [Documents](General.Documents.Documents.md) (nullable) | In not null the Document_Line_Id is a line of the document with Referenced_Document_Id. `Filter(multi eq)` |


## Attribute Details

### Amount

The amount which has beed distributed over the current line. The amount is in the currency of the document. `Currency: GetDocumentCurrency()` `Required` `Filter(ge;le)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BaseAmount

The calculated base amount for the line in document currency. The base amount is the base, over which the additional amounts are calculated. Null if the base amount is not stored (for amounts distributed in older versions of the system). . `Currency: GetDocumentCurrency()` `Introduced in version 22.1.4.44`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DocumentLineId

The Id of the line over which the amount is distributed. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The <see cref="Document"/> to which this DocumentDistributedAmount belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Documents](General.Documents.Documents.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **CannotBeShown**  

### DocumentAmountType

The type of amount which is distributed. `Required` `Filter(multi eq)`

_Type_: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ReferencedDocument

In not null the Document_Line_Id is a line of the document with Referenced_Document_Id. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Documents.DocumentDistributedAmounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Documents.DocumentDistributedAmounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Documents_DocumentDistributedAmounts

Domain API Entity Type: 
General_Documents_DocumentDistributedAmount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Documents_DocumentDistributedAmounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Documents_DocumentDistributedAmounts?$top=10>

