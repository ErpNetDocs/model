---
uid: Finance.Excise.ExciseStampOperationLines
---
# Finance.Excise.ExciseStampOperationLines Entity

**Namespace:** [Finance.Excise](Finance.Excise.md)  

Excise Stamp Operation Lines. Entity: Exc_Excise_Stamp_Operation_Lines (Introduced in version 22.1.6.17)

## Default Visualization
Default Display Text Format:  
_{LineNo}. {ExciseStampOperation.DocumentNo} {ExciseStampOperation.DocumentType.TypeName:T}_  
Default Search Members:  
_ExciseStampOperation.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Excise.ExciseStampOperations](Finance.Excise.ExciseStampOperations.md)  
Aggregate Root:  
[Finance.Excise.ExciseStampOperations](Finance.Excise.ExciseStampOperations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Finance.Excise.ExciseStampOperationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EndNumber](Finance.Excise.ExciseStampOperationLines.md#endnumber) | string (30) __nullable__ | The end number of the sequence of excise stamps that are processed with the current operation. 
| [Id](Finance.Excise.ExciseStampOperationLines.md#id) | guid |  
| [LineNo](Finance.Excise.ExciseStampOperationLines.md#lineno) | int32 | Consecutive number of the line within the excise stamp operation. Determines the order of execution of the excise stamp operation lines. `Required` 
| [Notes](Finance.Excise.ExciseStampOperationLines.md#notes) | string (max) __nullable__ | Notes for this ExciseStampOperationLine. 
| [ObjectVersion](Finance.Excise.ExciseStampOperationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentLineNo](Finance.Excise.ExciseStampOperationLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute line. `Introduced in version 22.1.6.32` 
| [Quantity](Finance.Excise.ExciseStampOperationLines.md#quantity) | int32 __nullable__ | The number of excise stamps that are processed with the current operation. `Default(0)` 
| [StartNumber](Finance.Excise.ExciseStampOperationLines.md#startnumber) | string (30) __nullable__ | The start number of the sequence of excise stamps that are processed with the current operation. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Finance.Excise.ExciseStampOperationLines.md#document) | [ExciseStampOperations](Finance.Excise.ExciseStampOperations.md) | The owner document. The <see cref="ExciseStamp<br />Operation"/> to which this ExciseStampOperationLine belongs. `Required` `Filter(multi eq)` |
| [ExciseProductType](Finance.Excise.ExciseStampOperationLines.md#exciseproducttype) | [ExciseProductTypes](Finance.Excise.ExciseProductTypes.md) (nullable) | Specifies the excise product type which is used in the current operation. Determine which excise stamp lots can be chosen. `Filter(multi eq)` `Introduced in version 22.1.6.46` |
| [ExciseStampLot](Finance.Excise.ExciseStampOperationLines.md#excisestamplot) | [ExciseStampLots](Finance.Excise.ExciseStampLots.md) (nullable) | The lot of the excise stamps. `Filter(multi eq)` |
| [ExciseStampOperation](Finance.Excise.ExciseStampOperationLines.md#excisestampoperation) | [ExciseStampOperations](Finance.Excise.ExciseStampOperations.md) | The <see cref="ExciseStamp<br />Operation"/> to which this ExciseStampOperationLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ParentDocument](Finance.Excise.ExciseStampOperationLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 22.1.6.32` |
| [Product](Finance.Excise.ExciseStampOperationLines.md#product) | [Products](General.Products.Products.md) (nullable) | The product for which the operation is applied. When is null then there is no product yet. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EndNumber

The end number of the sequence of excise stamps that are processed with the current operation.

_Type_: **string (30) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`Format( "{0}", Convert( ( ( Convert( Parse( obj.StartNumber), Nullable`1) + Convert( obj.Quantity, Nullable`1)) - Convert( Convert( 1, Int64), Nullable`1)), Object)).PadLeft( obj.StartNumber.Trim( ).Length, 0)`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Consecutive number of the line within the excise stamp operation. Determines the order of execution of the excise stamp operation lines. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.ExciseStampOperation.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.ExciseStampOperation.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this ExciseStampOperationLine.

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

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute line. `Introduced in version 22.1.6.32`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Quantity

The number of excise stamps that are processed with the current operation. `Default(0)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ExciseStampLot.Quantity`
### StartNumber

The start number of the sequence of excise stamps that are processed with the current operation.

_Type_: **string (30) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ExciseStampLot.StartNumber`

## Reference Details

### Document

The owner document. The <see cref="ExciseStampOperation"/> to which this ExciseStampOperationLine belongs. `Required` `Filter(multi eq)`

_Type_: **[ExciseStampOperations](Finance.Excise.ExciseStampOperations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExciseProductType

Specifies the excise product type which is used in the current operation. Determine which excise stamp lots can be chosen. `Filter(multi eq)` `Introduced in version 22.1.6.46`

_Type_: **[ExciseProductTypes](Finance.Excise.ExciseProductTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.Product != null), obj.Product.ExciseProductType, null)`
### ExciseStampLot

The lot of the excise stamps. `Filter(multi eq)`

_Type_: **[ExciseStampLots](Finance.Excise.ExciseStampLots.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExciseStampOperation

The <see cref="ExciseStampOperation"/> to which this ExciseStampOperationLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ExciseStampOperations](Finance.Excise.ExciseStampOperations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 22.1.6.32`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product for which the operation is applied. When is null then there is no product yet. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
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

[!list limit=1000 erp.entity=Finance.Excise.ExciseStampOperationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Excise.ExciseStampOperationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Excise_ExciseStampOperationLines

Domain API Entity Type: 
Finance_Excise_ExciseStampOperationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Excise_ExciseStampOperationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Excise_ExciseStampOperationLines?$top=10>

