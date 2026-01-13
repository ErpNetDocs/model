---
uid: Finance.Excise.ExciseAdministrativeDocumentLines
---
# Finance.Excise.ExciseAdministrativeDocumentLines Entity

**Namespace:** [Finance.Excise](Finance.Excise.md)  

The details of the movement of each excise product for each excise document. Entity: Exc_Excise_Administrative_Document_Lines (Introduced in version 21.1.3.54)

## Default Visualization
Default Display Text Format:  
_{LineNo}. {ExciseAdministrativeDocument.DocumentNo} {ExciseAdministrativeDocument.DocumentType.TypeName:T}_  
Default Search Members:  
_ExciseAdministrativeDocument.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Excise.ExciseAdministrativeDocuments](Finance.Excise.ExciseAdministrativeDocuments.md)  
Aggregate Root:  
[Finance.Excise.ExciseAdministrativeDocuments](Finance.Excise.ExciseAdministrativeDocuments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Finance.Excise.ExciseAdministrativeDocumentLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Finance.Excise.ExciseAdministrativeDocumentLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExciseAlcoholicStrength](Finance.Excise.ExciseAdministrativeDocumentLines.md#excisealcoholicstrength) | decimal (5, 2) __nullable__ | The alcoholic strength, which will be used for Excise reporting purposes. null  if the product is not subject to alcoholic Excise reporting. `Introduced in version 21.1.3.97` 
| [ExciseAmount](Finance.Excise.ExciseAdministrativeDocumentLines.md#exciseamount) | [Amount (14, 2)](../data-types.md#amount) | The excise amount . `Currency: ExciseAdministrative<br />Document.BaseCurrency` `Required` `Default(0)` `Filter(eq;ge;le)` `Introduced in version 21.1.3.94` 
| [ExciseAmountBase](Finance.Excise.ExciseAdministrativeDocumentLines.md#exciseamountbase) | decimal (14, 4) | The excise amount in base currency. `Unit: ExciseAdministrative<br />Document.BaseCurrency` `Required` `Default(0)` `Filter(eq;ge;le)` `Introduced in version 21.1.3.94` 
| [ExciseDutyRateValue](Finance.Excise.ExciseAdministrativeDocumentLines.md#excisedutyratevalue) | decimal (10, 6) __nullable__ | The rate which should be applied for the specified product and purpose. null means not assigned yet. `Introduced in version 21.1.3.97` 
| [ExciseQuantity](Finance.Excise.ExciseAdministrativeDocumentLines.md#excisequantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity, converted, for reporting purposes, in the measurement unit of the excise product type. `Unit: ExciseQuantityUnit` `Required` `Introduced in version 22.1.6.58` 
| [Id](Finance.Excise.ExciseAdministrativeDocumentLines.md#id) | guid |  
| [LineNo](Finance.Excise.ExciseAdministrativeDocumentLines.md#lineno) | int32 | Consecutive line number within the document. `Required` `Filter(multi eq)` 
| [Notes](Finance.Excise.ExciseAdministrativeDocumentLines.md#notes) | string (max) __nullable__ | Notes for this ExciseAdministrative<br />DocumentLine. 
| [ObjectVersion](Finance.Excise.ExciseAdministrativeDocumentLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentLineNo](Finance.Excise.ExciseAdministrativeDocumentLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. Null when the current line does not execute line. `Filter(multi eq)` `Introduced in version 22.1.4.9` 
| [Quantity](Finance.Excise.ExciseAdministrativeDocumentLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity being sold, in the measurement unit, specified in Quantity Unit. `Unit: QuantityUnit` `Required` `Default(1)` 
| [QuantityBase](Finance.Excise.ExciseAdministrativeDocumentLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity in base measurement category for the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Finance.Excise.ExciseAdministrativeDocumentLines.md#document) | [ExciseAdministrativeDocuments](Finance.Excise.ExciseAdministrativeDocuments.md) | The owner document. The <see cref="ExciseAdministrative<br />Document"/> to which this ExciseAdministrative<br />DocumentLine belongs. `Required` `Filter(multi eq)` |
| [ExciseAdministrative<br />Document](Finance.Excise.ExciseAdministrativeDocumentLines.md#exciseadministrativedocument) | [ExciseAdministrativeDocuments](Finance.Excise.ExciseAdministrativeDocuments.md) | The <see cref="ExciseAdministrative<br />Document"/> to which this ExciseAdministrative<br />DocumentLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ExciseDutyRate](Finance.Excise.ExciseAdministrativeDocumentLines.md#excisedutyrate) | [ExciseDutyRates](Finance.Excise.ExciseDutyRates.md) (nullable) | The Duty rate specified by the taxation and customs authorities. `Filter(multi eq)` `Introduced in version 21.1.3.97` |
| [ExciseProduct](Finance.Excise.ExciseAdministrativeDocumentLines.md#exciseproduct) | [ExciseProducts](Finance.Excise.ExciseProducts.md) (nullable) | The Excise product code defined by the taxation and customs authorities. `Filter(multi eq)` `Introduced in version 21.1.3.97` |
| [ExcisePurposeCode](Finance.Excise.ExciseAdministrativeDocumentLines.md#excisepurposecode) | [ExcisePurposeCodes](Finance.Excise.ExcisePurposeCodes.md) (nullable) | The Purpose codes specify the different purposes recognized by the authorities for determining the excise rate. `Filter(multi eq)` `Introduced in version 21.1.3.97` |
| [ExciseQuantityUnit](Finance.Excise.ExciseAdministrativeDocumentLines.md#excisequantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Excise Quantity. Copied from the excise product type. `Required` `Filter(multi eq)` `Introduced in version 22.1.6.58` |
| [Lot](Finance.Excise.ExciseAdministrativeDocumentLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Warehouse lot. `Filter(multi eq)` `Introduced in version 23.1.2.68` |
| [MeasuringTransaction](Finance.Excise.ExciseAdministrativeDocumentLines.md#measuringtransaction) | [MeasuringTransactions](Finance.Excise.MeasuringTransactions.md) (nullable) | Transaction of product input or output, measured with specialized measuring device for excise purposes. `Filter(multi eq)` `Introduced in version 21.1.3.87` |
| [ParentDocument](Finance.Excise.ExciseAdministrativeDocumentLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. Null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 22.1.4.9` |
| [Product](Finance.Excise.ExciseAdministrativeDocumentLines.md#product) | [Products](General.Products.Products.md) | The product being sold. `Required` `Filter(multi eq)` |
| [QuantityUnit](Finance.Excise.ExciseAdministrativeDocumentLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

_Type_: **[Quantity](../data-types.md#quantity)**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExciseAlcoholicStrength

The alcoholic strength, which will be used for Excise reporting purposes. null  if the product is not subject to alcoholic Excise reporting. `Introduced in version 21.1.3.97`

_Type_: **decimal (5, 2) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.GetNewAlcoholicStrength( obj.MeasuringTransaction, obj.Product)`
### ExciseAmount

The excise amount . `Currency: ExciseAdministrativeDocument.BaseCurrency` `Required` `Default(0)` `Filter(eq;ge;le)` `Introduced in version 21.1.3.94`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`new Amount( ( obj.ExciseAmountBase * ( obj.ExciseDutyRateValue ?? 0)), obj.ExciseAdministrativeDocument.BaseCurrency)`
### ExciseAmountBase

The excise amount in base currency. `Unit: ExciseAdministrativeDocument.BaseCurrency` `Required` `Default(0)` `Filter(eq;ge;le)` `Introduced in version 21.1.3.94`

_Type_: **decimal (14, 4)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.CalculateExciseAmountBase( obj.ExciseProduct, obj.ExciseQuantity, obj.ExciseAlcoholicStrength).IfNullThen( obj.ExciseAmountBase)`
### ExciseDutyRateValue

The rate which should be applied for the specified product and purpose. null means not assigned yet. `Introduced in version 21.1.3.97`

_Type_: **decimal (10, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.ExciseDutyRate.ExciseDutyRateField`
### ExciseQuantity

The quantity, converted, for reporting purposes, in the measurement unit of the excise product type. `Unit: ExciseQuantityUnit` `Required` `Introduced in version 22.1.6.58`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.QuantityBase.ConvertTo( obj.ExciseQuantityUnit, obj.Product)`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Consecutive line number within the document. `Required` `Filter(multi eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.ExciseAdministrativeDocument.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.ExciseAdministrativeDocument.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this ExciseAdministrativeDocumentLine.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. Null when the current line does not execute line. `Filter(multi eq)` `Introduced in version 22.1.4.9`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Quantity

The quantity being sold, in the measurement unit, specified in Quantity Unit. `Unit: QuantityUnit` `Required` `Default(1)`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The quantity in base measurement category for the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

## Reference Details

### Document

The owner document. The <see cref="ExciseAdministrativeDocument"/> to which this ExciseAdministrativeDocumentLine belongs. `Required` `Filter(multi eq)`

_Type_: **[ExciseAdministrativeDocuments](Finance.Excise.ExciseAdministrativeDocuments.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ExciseAdministrativeDocument

The <see cref="ExciseAdministrativeDocument"/> to which this ExciseAdministrativeDocumentLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ExciseAdministrativeDocuments](Finance.Excise.ExciseAdministrativeDocuments.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ExciseDutyRate

The Duty rate specified by the taxation and customs authorities. `Filter(multi eq)` `Introduced in version 21.1.3.97`

_Type_: **[ExciseDutyRates](Finance.Excise.ExciseDutyRates.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.DetermineExciseDutyRate( obj.ExciseProduct, obj.ExcisePurposeCode, obj.ExciseAdministrativeDocument.DocumentDate)`
### ExciseProduct

The Excise product code defined by the taxation and customs authorities. `Filter(multi eq)` `Introduced in version 21.1.3.97`

_Type_: **[ExciseProducts](Finance.Excise.ExciseProducts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.ExciseProductType.ExciseProduct`
### ExcisePurposeCode

The Purpose codes specify the different purposes recognized by the authorities for determining the excise rate. `Filter(multi eq)` `Introduced in version 21.1.3.97`

_Type_: **[ExcisePurposeCodes](Finance.Excise.ExcisePurposeCodes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.LineNo == obj.LineNo), obj.DefaultExcisePurposeCode( ), null)`
### ExciseQuantityUnit

The measurement unit of Excise Quantity. Copied from the excise product type. `Required` `Filter(multi eq)` `Introduced in version 22.1.6.58`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.ExciseProductType.MeasurementUnit`
### Lot

Warehouse lot. `Filter(multi eq)` `Introduced in version 23.1.2.68`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MeasuringTransaction

Transaction of product input or output, measured with specialized measuring device for excise purposes. `Filter(multi eq)` `Introduced in version 21.1.3.87`

_Type_: **[MeasuringTransactions](Finance.Excise.MeasuringTransactions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ParentDocument

The document, which the current line executes. Null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 22.1.4.9`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Product

The product being sold. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit`

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

[!list limit=1000 erp.entity=Finance.Excise.ExciseAdministrativeDocumentLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Excise.ExciseAdministrativeDocumentLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Excise_ExciseAdministrativeDocumentLines

Domain API Entity Type: 
Finance_Excise_ExciseAdministrativeDocumentLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Excise_ExciseAdministrativeDocumentLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Excise_ExciseAdministrativeDocumentLines?$top=10>

