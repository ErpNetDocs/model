---
uid: Regulatory.Excise.ExciseAdministrativeDocumentLines
---
# Regulatory.Excise.ExciseAdministrativeDocumentLines


The details of the movement of each excise product for each excise document.

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.ExciseAdministrativeDocumentLines  
Base Table: Exc_Excise_Administrative_Document_Lines  
Introduced In Version: 21.1.3.54  
API access:  ReadWrite  

## Renames

Old name: Finance.Excise.ExciseAdministrativeDocumentLines  
New name: Regulatory.Excise.ExciseAdministrativeDocumentLines  
Version: 26.2.1.17  
Case: 39297  



## Visualization
Display Format: {LineNo}. {ExciseAdministrativeDocument.DocumentNo} {ExciseAdministrativeDocument.DocumentType.TypeName:T}  
Search Members: ExciseAdministrativeDocument.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Excise.ExciseAdministrativeDocuments](Regulatory.Excise.ExciseAdministrativeDocuments.md)  
Aggregate Root:  
[Regulatory.Excise.ExciseAdministrativeDocuments](Regulatory.Excise.ExciseAdministrativeDocuments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [ExciseAlcoholicStrength](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#excisealcoholicstrength) | decimal (5, 2) __nullable__ | The alcoholic strength, which will be used for Excise reporting purposes. NULL  if the product is not subject to alcoholic Excise reporting. 
| [ExciseAmount](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#exciseamount) | [Amount (14, 2)](../data-types.md#amount) | The excise amount  
| [ExciseAmountBase](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#exciseamountbase) | decimal (14, 4) | The excise amount in base currency 
| [ExciseDutyRateValue](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#excisedutyratevalue) | decimal (10, 6) __nullable__ | The rate which should be applied for the specified product and purpose. NULL means not assigned yet. 
| [ExciseQuantity](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#excisequantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity, converted, for reporting purposes, in the measurement unit of the excise product type. 
| [LineNo](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#lineno) | int32 | Consecutive line number within the document. 
| [Notes](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#notes) | string (max) __nullable__ | Notes for this ExciseAdministrative<br />DocumentLine. 
| [ParentLineNo](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. Null when the current line does not execute line. 
| [Quantity](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity being sold, in the measurement unit, specified in Quantity Unit. 
| [QuantityBase](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity in base measurement category for the product. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#document) | [ExciseAdministrativeDocuments](Regulatory.Excise.ExciseAdministrativeDocuments.md) | The owner document. The <see cref="ExciseAdministrative<br />Document"/> to which this ExciseAdministrative<br />DocumentLine belongs. `Required` `Filter(multi eq)` |
| [ExciseAdministrative<br />Document](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#exciseadministrativedocument) | [ExciseAdministrativeDocuments](Regulatory.Excise.ExciseAdministrativeDocuments.md) | The <see cref="ExciseAdministrative<br />Document"/> to which this ExciseAdministrative<br />DocumentLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ExciseDutyRate](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#excisedutyrate) | [ExciseDutyRates](Regulatory.Excise.ExciseDutyRates.md) (nullable) | The Duty rate specified by the taxation and customs authorities. |
| [ExciseProduct](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#exciseproduct) | [ExciseProducts](Regulatory.Excise.ExciseProducts.md) (nullable) | The Excise product code defined by the taxation and customs authorities. |
| [ExcisePurposeCode](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#excisepurposecode) | [ExcisePurposeCodes](Regulatory.Excise.ExcisePurposeCodes.md) (nullable) | The Purpose codes specify the different purposes recognized by the authorities for determining the excise rate. |
| [ExciseQuantityUnit](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#excisequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Excise Quantity. Copied from the excise product type. |
| [Lot](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Warehouse lot |
| [MeasuringTransaction](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#measuringtransaction) | [MeasuringTransactions](Regulatory.Excise.MeasuringTransactions.md) (nullable) | Transaction of product input or output, measured with specialized measuring device for excise purposes. |
| [ParentDocument](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. Null when the current line does not execute another line. |
| [Product](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#product) | [Products](General.Products.Products.md) | The product being sold. |
| [QuantityUnit](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Excise.ExciseAdministrativeDocumentLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExciseAlcoholicStrength

The alcoholic strength, which will be used for Excise reporting purposes. NULL  if the product is not subject to alcoholic Excise reporting.

Type: **decimal (5, 2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.GetNewAlcoholicStrength( obj.MeasuringTransaction, obj.Product)`
### ExciseAmount

The excise amount

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`new Amount( ( obj.ExciseAmountBase * ( obj.ExciseDutyRateValue ?? 0)), obj.ExciseAdministrativeDocument.BaseCurrency)`
### ExciseAmountBase

The excise amount in base currency

Type: **decimal (14, 4)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.CalculateExciseAmountBase( obj.ExciseProduct, obj.ExciseQuantity, obj.ExciseAlcoholicStrength).IfNullThen( obj.ExciseAmountBase)`
### ExciseDutyRateValue

The rate which should be applied for the specified product and purpose. NULL means not assigned yet.

Type: **decimal (10, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.ExciseDutyRate.ExciseDutyRateField`
### ExciseQuantity

The quantity, converted, for reporting purposes, in the measurement unit of the excise product type.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.QuantityBase.ConvertTo( obj.ExciseQuantityUnit, obj.Product)`
### LineNo

Consecutive line number within the document.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ExciseAdministrativeDocument.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.ExciseAdministrativeDocument.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this ExciseAdministrativeDocumentLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. Null when the current line does not execute line.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Quantity

The quantity being sold, in the measurement unit, specified in Quantity Unit.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The quantity in base measurement category for the product.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
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

The owner document. The <see cref="ExciseAdministrativeDocument"/> to which this ExciseAdministrativeDocumentLine belongs. `Required` `Filter(multi eq)`

Type: **[ExciseAdministrativeDocuments](Regulatory.Excise.ExciseAdministrativeDocuments.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExciseAdministrativeDocument

The <see cref="ExciseAdministrativeDocument"/> to which this ExciseAdministrativeDocumentLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ExciseAdministrativeDocuments](Regulatory.Excise.ExciseAdministrativeDocuments.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ExciseDutyRate

The Duty rate specified by the taxation and customs authorities.

Type: **[ExciseDutyRates](Regulatory.Excise.ExciseDutyRates.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.DetermineExciseDutyRate( obj.ExciseProduct, obj.ExcisePurposeCode, obj.ExciseAdministrativeDocument.DocumentDate)`
### ExciseProduct

The Excise product code defined by the taxation and customs authorities.

Type: **[ExciseProducts](Regulatory.Excise.ExciseProducts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product.ExciseProductType.ExciseProduct`
### ExcisePurposeCode

The Purpose codes specify the different purposes recognized by the authorities for determining the excise rate.

Type: **[ExcisePurposeCodes](Regulatory.Excise.ExcisePurposeCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.LineNo == obj.LineNo), obj.DefaultExcisePurposeCode( ), null)`
### ExciseQuantityUnit

The measurement unit of Excise Quantity. Copied from the excise product type.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product.ExciseProductType.MeasurementUnit`
### Lot

Warehouse lot

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MeasuringTransaction

Transaction of product input or output, measured with specialized measuring device for excise purposes.

Type: **[MeasuringTransactions](Regulatory.Excise.MeasuringTransactions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ParentDocument

The document, which the current line executes. Null when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The product being sold.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`

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

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseAdministrativeDocumentLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseAdministrativeDocumentLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_ExciseAdministrativeDocumentLines

Domain API Entity Type: 
Regulatory_Excise_ExciseAdministrativeDocumentLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_ExciseAdministrativeDocumentLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_ExciseAdministrativeDocumentLines?$top=10>

