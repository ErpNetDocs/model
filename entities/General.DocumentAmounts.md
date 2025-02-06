---
uid: General.DocumentAmounts
---
# General.DocumentAmounts Entity

**Namespace:** [General](General.md)  

Contains a specific instance of an additional amount for a specific document. Entity: Gen_Document_Amounts
## Renamed
**New name:** [General.Documents.DocumentAmounts](General.Documents.DocumentAmounts.md)  



## Default Visualization
Default Display Text Format:  
_{DocumentAmountType.AmountTypeName:T}_  
Default Search Members:  
_Document.EntityName_  
Name Data Member:  
_Document.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Documents](General.Documents.md)  
Aggregate Root:  
[General.Documents](General.Documents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseAmount](General.DocumentAmounts.md#baseamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | The calculated base amount (in documents currency) from the last document amount recalculation. The base amount is the base, over which the additional amounts are calculated. Null if the amount is not distributed yet. `Currency: LogisticsDocument.DocumentCurrency` `ReadOnly` 
| [DisplayText](General.DocumentAmounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.DocumentAmounts.md#id) | guid |  
| [InputAmount](General.DocumentAmounts.md#inputamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | When not null, specifies directly the amount of the additional amount. `Currency: GetInputAmountCurrency()` `Filter(ge;le)` 
| [InputPercent](General.DocumentAmounts.md#inputpercent) | decimal (7, 6) __nullable__ | When not null, specifies that the amount for this document will be calculated as percent of the base amounts (which are defined in the amount type). `Filter(ge;le)` 
| [InputUnitAmount](General.DocumentAmounts.md#inputunitamount) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | Input unit amount for the calculation of the current amount. `Currency: GetInputAmountCurrency()` `Filter(eq;ge;le)` 
| [ObjectVersion](General.DocumentAmounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [TotalDistributedAmount](General.DocumentAmounts.md#totaldistributedamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | The total amount (in documents currency) which was distributed to the documents lines. Null if the amount is not distributed yet. `Currency: LogisticsDocument.DocumentCurrency` `ReadOnly` 
| [UserCanChangeInput](General.DocumentAmounts.md#usercanchangeinput) | boolean | True if the user, entering the document is allowed to change the default input percent. `Required` `Default(true)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](General.DocumentAmounts.md#document) | [Documents](General.Documents.md) | The <see cref="Document"/> to which this DocumentAmount belongs. `Required` `Filter(multi eq)` `Owner` |
| [DocumentAmountType](General.DocumentAmounts.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) | The type of the amount. `Required` `Filter(multi eq)` |
| [InputAmountCurrency](General.DocumentAmounts.md#inputamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | When specifying the amount directly in Input Amount, this contains the currency of the amount. Used and required when Input Amount is not null. `Filter(multi eq)` |
| [InputUnit](General.DocumentAmounts.md#inputunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | Measurement unit of the input unit amount. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ReferencedDocuments | [DocumentAmountReferencedDocuments](General.DocumentAmountReferencedDocuments.md) | List of `DocumentAmount<br />ReferencedDocument`(General.DocumentAmount<br />ReferencedDocuments.md) child objects, based on the `General.DocumentAmount<br />ReferencedDocument.DocumentAmount`(General.DocumentAmount<br />ReferencedDocuments.md#documentamount) back reference 


## Attribute Details

### BaseAmount

The calculated base amount (in documents currency) from the last document amount recalculation. The base amount is the base, over which the additional amounts are calculated. Null if the amount is not distributed yet. `Currency: LogisticsDocument.DocumentCurrency` `ReadOnly`

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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### InputAmount

When not null, specifies directly the amount of the additional amount. `Currency: GetInputAmountCurrency()` `Filter(ge;le)`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.DocumentAmountType.AmountInputAllowed, obj.InputAmount, null)`
### InputPercent

When not null, specifies that the amount for this document will be calculated as percent of the base amounts (which are defined in the amount type). `Filter(ge;le)`

_Type_: **decimal (7, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.DocumentAmountType.DefaultPercent`

_Front-End Recalc Expressions:_  
`obj.DocumentAmountType.DefaultPercent`
### InputUnitAmount

Input unit amount for the calculation of the current amount. `Currency: GetInputAmountCurrency()` `Filter(eq;ge;le)`

_Type_: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.DocumentAmountType.UnitAmountInputAllowed, obj.InputUnitAmount, null)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### TotalDistributedAmount

The total amount (in documents currency) which was distributed to the documents lines. Null if the amount is not distributed yet. `Currency: LogisticsDocument.DocumentCurrency` `ReadOnly`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UserCanChangeInput

True if the user, entering the document is allowed to change the default input percent. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **CannotBeShown**  


## Reference Details

### Document

The <see cref="Document"/> to which this DocumentAmount belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Documents](General.Documents.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **CannotBeShown**  

### DocumentAmountType

The type of the amount. `Required` `Filter(multi eq)`

_Type_: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### InputAmountCurrency

When specifying the amount directly in Input Amount, this contains the currency of the amount. Used and required when Input Amount is not null. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.DocumentAmountType.AmountInputAllowed, obj.InputAmountCurrency, null)`
### InputUnit

Measurement unit of the input unit amount. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.DocumentAmountType.UnitAmountInputAllowed, obj.InputUnit, null)`

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


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=General.DocumentAmounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.DocumentAmounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_DocumentAmounts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_DocumentAmounts?$top=10>

