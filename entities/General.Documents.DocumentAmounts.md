---
uid: General.Documents.DocumentAmounts
---
# General.Documents.DocumentAmounts


Contains a specific instance of an additional amount for a specific document.

## General
Namespace: [General.Documents](General.Documents.md)  
Repository: General.Documents.DocumentAmounts  
Base Table: Gen_Document_Amounts  
API access:  ReadWrite  

## Renames

Old name: General.DocumentAmounts  
New name: General.Documents.DocumentAmounts  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {DocumentAmountType.AmountTypeName:T}  
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
| [BaseAmount](General.Documents.DocumentAmounts.md#baseamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | The calculated base amount (in documents currency) from the last document amount recalculation. The base amount is the base, over which the additional amounts are calculated. Null if the amount is not distributed yet. `Currency: LogisticsDocument.DocumentCurrency` `ReadOnly` 
| [InputAmount](General.Documents.DocumentAmounts.md#inputamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | When not null, specifies directly the amount of the additional amount. `Currency: GetInputAmountCurrency()` `Filter(ge;le)` 
| [InputPercent](General.Documents.DocumentAmounts.md#inputpercent) | decimal (7, 6) __nullable__ | When not null, specifies that the amount for this document will be calculated as percent of the base amounts (which are defined in the amount type). `Filter(ge;le)` 
| [InputUnitAmount](General.Documents.DocumentAmounts.md#inputunitamount) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | Input unit amount for the calculation of the current amount. `Currency: GetInputAmountCurrency()` `Filter(eq;ge;le)` 
| [TotalDistributedAmount](General.Documents.DocumentAmounts.md#totaldistributedamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | The total amount (in documents currency) which was distributed to the documents lines. Null if the amount is not distributed yet. `Currency: LogisticsDocument.DocumentCurrency` `ReadOnly` 
| [UserCanChangeInput](General.Documents.DocumentAmounts.md#usercanchangeinput) | boolean | True if the user, entering the document is allowed to change the default input percent. `Required` `Default(true)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.Documents.DocumentAmounts.md#document) | [Documents](General.Documents.Documents.md) | The <see cref="Document"/> to which this DocumentAmount belongs. `Required` `Filter(multi eq)` `Owner` |
| [DocumentAmountType](General.Documents.DocumentAmounts.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) | The type of the amount. `Required` `Filter(multi eq)` |
| [InputAmountCurrency](General.Documents.DocumentAmounts.md#inputamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | When specifying the amount directly in Input Amount, this contains the currency of the amount. Used and required when Input Amount is not null. `Filter(multi eq)` |
| [InputUnit](General.Documents.DocumentAmounts.md#inputunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | Measurement unit of the input unit amount. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Documents.DocumentAmounts.md#id) | guid |  
| [ObjectVersion](General.Documents.DocumentAmounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Documents.DocumentAmounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ReferencedDocuments | [DocumentAmountReferencedDocuments](General.Documents.DocumentAmountReferencedDocuments.md) | List of `DocumentAmount<br />ReferencedDocument`(General.Documents.DocumentAmount<br />ReferencedDocuments.md) child objects, based on the `General.Documents.DocumentAmount<br />ReferencedDocument.DocumentAmount`(General.Documents.DocumentAmount<br />ReferencedDocuments.md#documentamount) back reference 


## Attribute Details

### BaseAmount

The calculated base amount (in documents currency) from the last document amount recalculation. The base amount is the base, over which the additional amounts are calculated. Null if the amount is not distributed yet. `Currency: LogisticsDocument.DocumentCurrency` `ReadOnly`

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InputAmount

When not null, specifies directly the amount of the additional amount. `Currency: GetInputAmountCurrency()` `Filter(ge;le)`

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( obj.DocumentAmountType.AmountInputAllowed, obj.InputAmount, null)`
### InputPercent

When not null, specifies that the amount for this document will be calculated as percent of the base amounts (which are defined in the amount type). `Filter(ge;le)`

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.DocumentAmountType.DefaultPercent`

Front-End Recalc Expressions:  
`obj.DocumentAmountType.DefaultPercent`
### InputUnitAmount

Input unit amount for the calculation of the current amount. `Currency: GetInputAmountCurrency()` `Filter(eq;ge;le)`

Type: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( obj.DocumentAmountType.UnitAmountInputAllowed, obj.InputUnitAmount, null)`
### TotalDistributedAmount

The total amount (in documents currency) which was distributed to the documents lines. Null if the amount is not distributed yet. `Currency: LogisticsDocument.DocumentCurrency` `ReadOnly`

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UserCanChangeInput

True if the user, entering the document is allowed to change the default input percent. `Required` `Default(true)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
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

The <see cref="Document"/> to which this DocumentAmount belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Documents](General.Documents.Documents.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **CannotBeShown**  

### DocumentAmountType

The type of the amount. `Required` `Filter(multi eq)`

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### InputAmountCurrency

When specifying the amount directly in Input Amount, this contains the currency of the amount. Used and required when Input Amount is not null. `Filter(multi eq)`

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( obj.DocumentAmountType.AmountInputAllowed, obj.InputAmountCurrency, null)`
### InputUnit

Measurement unit of the input unit amount. `Filter(multi eq)`

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( obj.DocumentAmountType.UnitAmountInputAllowed, obj.InputUnit, null)`

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

[!list limit=1000 erp.entity=General.Documents.DocumentAmounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Documents.DocumentAmounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Documents_DocumentAmounts

Domain API Entity Type: 
General_Documents_DocumentAmount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Documents_DocumentAmounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Documents_DocumentAmounts?$top=10>

