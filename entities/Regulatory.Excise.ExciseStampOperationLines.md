---
uid: Regulatory.Excise.ExciseStampOperationLines
---
# Regulatory.Excise.ExciseStampOperationLines


Excise Stamp Operation Lines

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.ExciseStampOperationLines  
Base Table: Exc_Excise_Stamp_Operation_Lines  
Introduced In Version: 22.1.6.17  
API access:  ReadWrite  

## Renames

Old name: Finance.Excise.ExciseStampOperationLines  
New name: Regulatory.Excise.ExciseStampOperationLines  
Version: 26.2.1.17  
Case: 39297  



## Visualization
Display Format: {LineNo}. {ExciseStampOperation.DocumentNo} {ExciseStampOperation.DocumentType.TypeName:T}  
Search Members: ExciseStampOperation.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Excise.ExciseStampOperations](Regulatory.Excise.ExciseStampOperations.md)  
Aggregate Root:  
[Regulatory.Excise.ExciseStampOperations](Regulatory.Excise.ExciseStampOperations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EndNumber](Regulatory.Excise.ExciseStampOperationLines.md#endnumber) | string (30) __nullable__ | The end number of the sequence of excise stamps that are processed with the current operation. 
| [LineNo](Regulatory.Excise.ExciseStampOperationLines.md#lineno) | int32 | Consecutive line number within the document. Determines the order of execution of the excise stamp operation lines.[Required] 
| [Notes](Regulatory.Excise.ExciseStampOperationLines.md#notes) | string (max) __nullable__ | Notes for this ExciseStampOperationLine. 
| [ParentLineNo](Regulatory.Excise.ExciseStampOperationLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line.[Introduced in version 22.1.6.32] 
| [Quantity](Regulatory.Excise.ExciseStampOperationLines.md#quantity) | int32 __nullable__ | The number of excise stamps that are processed with the current operation.[Default(0)] 
| [StartNumber](Regulatory.Excise.ExciseStampOperationLines.md#startnumber) | string (30) __nullable__ | The start number of the sequence of excise stamps that are processed with the current operation. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Regulatory.Excise.ExciseStampOperationLines.md#document) | [ExciseStampOperations](Regulatory.Excise.ExciseStampOperations.md) | The owner document. The <see cref="ExciseStamp<br />Operation"/> to which this ExciseStampOperationLine belongs. `Required` `Filter(multi eq)` |
| [ExciseProductType](Regulatory.Excise.ExciseStampOperationLines.md#exciseproducttype) | [ExciseProductTypes](Regulatory.Excise.ExciseProductTypes.md) (nullable) | Specifies the excise product type which is used in the current operation. Determine which excise stamp lots can be chosen. |
| [ExciseStampLot](Regulatory.Excise.ExciseStampOperationLines.md#excisestamplot) | [ExciseStampLots](Regulatory.Excise.ExciseStampLots.md) (nullable) | The lot of the excise stamps. |
| [ExciseStampOperation](Regulatory.Excise.ExciseStampOperationLines.md#excisestampoperation) | [ExciseStampOperations](Regulatory.Excise.ExciseStampOperations.md) | The <see cref="ExciseStamp<br />Operation"/> to which this ExciseStampOperationLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ParentDocument](Regulatory.Excise.ExciseStampOperationLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [Product](Regulatory.Excise.ExciseStampOperationLines.md#product) | [Products](General.Products.Products.md) (nullable) | The product for which the operation is applied. When is NULL then there is no product yet. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.ExciseStampOperationLines.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.ExciseStampOperationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Excise.ExciseStampOperationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### EndNumber

The end number of the sequence of excise stamps that are processed with the current operation.

Type: **string (30) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`Format( "{0}", Convert( ( ( Convert( Parse( obj.StartNumber), Nullable`1) + Convert( obj.Quantity, Nullable`1)) - Convert( Convert( 1, Int64), Nullable`1)), Object)).PadLeft( obj.StartNumber.Trim( ).Length, 0)`
### LineNo

Consecutive line number within the document. Determines the order of execution of the excise stamp operation lines.[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ExciseStampOperation.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.ExciseStampOperation.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this ExciseStampOperationLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line.[Introduced in version 22.1.6.32]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Quantity

The number of excise stamps that are processed with the current operation.[Default(0)]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ExciseStampLot.Quantity`
### StartNumber

The start number of the sequence of excise stamps that are processed with the current operation.

Type: **string (30) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ExciseStampLot.StartNumber`
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

The owner document. The <see cref="ExciseStampOperation"/> to which this ExciseStampOperationLine belongs. `Required` `Filter(multi eq)`

Type: **[ExciseStampOperations](Regulatory.Excise.ExciseStampOperations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExciseProductType

Specifies the excise product type which is used in the current operation. Determine which excise stamp lots can be chosen.

Type: **[ExciseProductTypes](Regulatory.Excise.ExciseProductTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.Product != null), obj.Product.ExciseProductType, null)`
### ExciseStampLot

The lot of the excise stamps.

Type: **[ExciseStampLots](Regulatory.Excise.ExciseStampLots.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExciseStampOperation

The <see cref="ExciseStampOperation"/> to which this ExciseStampOperationLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ExciseStampOperations](Regulatory.Excise.ExciseStampOperations.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. NULL when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product for which the operation is applied. When is NULL then there is no product yet.

Type: **[Products](General.Products.Products.md) (nullable)**  
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

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseStampOperationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseStampOperationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_ExciseStampOperationLines

Domain API Entity Type: 
Regulatory_Excise_ExciseStampOperationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_ExciseStampOperationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_ExciseStampOperationLines?$top=10>

