---
uid: General.Documents.DocumentDistributedAmounts
---
# General.Documents.DocumentDistributedAmounts


Contains the amounts which are distributed by the system over the document lines as a result of additional amount calculations.

## General
Namespace: [General.Documents](General.Documents.md)  
Repository: General.Documents.DocumentDistributedAmounts  
Base Table: Gen_Document_Distributed_Amounts  
API access:  ReadWrite  

## Renames

Old name: General.DocumentDistributedAmounts  
New name: General.Documents.DocumentDistributedAmounts  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {DocumentAmountType} {DocumentLineId} {Amount}  
Search Members: Document.DocumentNo  
Name Member: Document.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Documents.Documents](General.Documents.Documents.md)  
Aggregate Root:  
[General.Documents.Documents](General.Documents.Documents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](General.Documents.DocumentDistributedAmounts.md#amount) | [Amount (14, 2)](../data-types.md#amount) | The amount which has beed distributed over the current line. The amount is in the currency of the document.`Currency: GetDocumentCurrency()` `Required` `Filter(ge;le)` 
| [BaseAmount](General.Documents.DocumentDistributedAmounts.md#baseamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | The calculated base amount for the line in document currency. The base amount is the base, over which the additional amounts are calculated. Null if the base amount is not stored (for amounts distributed in older versions of the system). `Currency: GetDocumentCurrency()` `Introduced in version 22.1.4.44` 
| [DocumentLineId](General.Documents.DocumentDistributedAmounts.md#documentlineid) | guid __nullable__ | The Id of the line over which the amount is distributed. `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.Documents.DocumentDistributedAmounts.md#document) | [Documents](General.Documents.Documents.md) | The <see cref="Document"/> to which this DocumentDistributedAmount belongs. `Required` `Filter(multi eq)` `Owner` |
| [DocumentAmountType](General.Documents.DocumentDistributedAmounts.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) | The type of amount which is distributed. |
| [ReferencedDocument](General.Documents.DocumentDistributedAmounts.md#referenceddocument) | [Documents](General.Documents.Documents.md) (nullable) | In not null the Document_Line_Id is a line of the document with Referenced_Document_Id |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Documents.DocumentDistributedAmounts.md#id) | guid |  
| [ObjectVersion](General.Documents.DocumentDistributedAmounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Documents.DocumentDistributedAmounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Amount

The amount which has beed distributed over the current line. The amount is in the currency of the document.`Currency: GetDocumentCurrency()` `Required` `Filter(ge;le)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BaseAmount

The calculated base amount for the line in document currency. The base amount is the base, over which the additional amounts are calculated. Null if the base amount is not stored (for amounts distributed in older versions of the system). `Currency: GetDocumentCurrency()` `Introduced in version 22.1.4.44`

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DocumentLineId

The Id of the line over which the amount is distributed. `Filter(multi eq)`

Type: **guid __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

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

### Document

The <see cref="Document"/> to which this DocumentDistributedAmount belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Documents](General.Documents.Documents.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **CannotBeShown**  

### DocumentAmountType

The type of amount which is distributed.

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ReferencedDocument

In not null the Document_Line_Id is a line of the document with Referenced_Document_Id

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
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

