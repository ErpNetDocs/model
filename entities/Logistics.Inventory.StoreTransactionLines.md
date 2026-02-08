---
uid: Logistics.Inventory.StoreTransactionLines
---
# Logistics.Inventory.StoreTransactionLines


Details records of Transactions. Each detail contains the movement for one product.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.StoreTransactionLines  
Base Table: Inv_Transaction_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {TransactionObj.DocumentNo} {TransactionObj.DocumentType.TypeName:T}  
Search Members: TransactionObj.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md)  
Aggregate Root:  
[Logistics.Inventory.StoreTransactions](Logistics.Inventory.StoreTransactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowOverExecution](Logistics.Inventory.StoreTransactionLines.md#allowoverexecution) | boolean | If checked specifies that the quantity in this line may exceed the quantity in the corresponding store order line`Required` `Default(false)` 
| [CurrentBalanceBase](Logistics.Inventory.StoreTransactionLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [Finished](Logistics.Inventory.StoreTransactionLines.md#finished) | boolean __nullable__ | 1 if this transaction entry completes the operation. 0 if there might be more entries`Default(false)` `Filter(eq)` 
| [GuaranteePeriodDays](Logistics.Inventory.StoreTransactionLines.md#guaranteeperioddays) | int32 __nullable__ | standard guarantee period in days. Can be set only if the product type is serviced. 
| [LineBaseCost](Logistics.Inventory.StoreTransactionLines.md#linebasecost) | [Amount (14, 2)](../data-types.md#amount) | The cost of the transaction in the currency of the enterprise company`Currency: TransactionObj.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [LineCost](Logistics.Inventory.StoreTransactionLines.md#linecost) | [Amount (14, 2)](../data-types.md#amount) | Suggested total cost for the line, specified by the user or when the document was generated. Used only when Cost Source = Document, in which case it is used to specify the actual total cost for the line.`Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)` 
| [LineDocumentCost](Logistics.Inventory.StoreTransactionLines.md#linedocumentcost) | [Amount (14, 2)](../data-types.md#amount) | The cost of the transaction in the currency of the document`Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)` `ReadOnly` 
| [LineNo](Logistics.Inventory.StoreTransactionLines.md#lineno) | int32 | Line number, unique within the store transaction.`Required` 
| [LineProductCost](Logistics.Inventory.StoreTransactionLines.md#lineproductcost) | [Amount (14, 2)](../data-types.md#amount) | The cost of the transaction in the currency of the product`Currency: Product.CostingCurrency` `Required` `Default(0)` `ReadOnly` 
| [LineStoreCost](Logistics.Inventory.StoreTransactionLines.md#linestorecost) | [Amount (14, 2)](../data-types.md#amount) | The cost of the transaction in the currency of the warehouse`Currency: TransactionObj.Store.Currency` `Required` `Default(0)` `ReadOnly` 
| [Notes](Logistics.Inventory.StoreTransactionLines.md#notes) | string (254) __nullable__ | Notes for this StoreTransactionLine. 
| [ParentLineId](Logistics.Inventory.StoreTransactionLines.md#parentlineid) | guid __nullable__ | Used, when transaction lines are generated directly from other entities (different from Store Order). Denotes the Id of the parent document line, which generated the transaction line. `Filter(multi eq)` 
| [ParentLineNo](Logistics.Inventory.StoreTransactionLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line. 
| [Quantity](Logistics.Inventory.StoreTransactionLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity received/issued in the measurement unit, specified in Quantity_Unit_Id. NULL means that the quantity is specified only in base measurement unit`Unit: QuantityUnit` `Required` `Default(0)` 
| [QuantityBase](Logistics.Inventory.StoreTransactionLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity of the stock received/issued in base measurement unit`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)` 
| [StandardQuantityBase](Logistics.Inventory.StoreTransactionLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [TempOrderNo](Logistics.Inventory.StoreTransactionLines.md#temporderno) | string (50) __nullable__ | Obsolete. Not used.`Filter(eq)` 
| [TransactionTimestamp](Logistics.Inventory.StoreTransactionLines.md#transactiontimestamp) | datetime __nullable__ | Exact time when the transaction changes the cost of the product.`Filter(ge;le)` `ORD` 
| [UnitCost](Logistics.Inventory.StoreTransactionLines.md#unitcost) | [Amount (14, 5)](../data-types.md#amount) | Cost for 1 of the specified quantity`Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Inventory.StoreTransactionLines.md#document) | [StoreTransactions](Logistics.Inventory.StoreTransactions.md) | The owner document. The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Inventory.StoreTransactionLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement |
| [OriginalProduct](Logistics.Inventory.StoreTransactionLines.md#originalproduct) | [Products](General.Products.Products.md) (nullable) | When specified, contains the original product, which was ordered to be received or issued. The actual product is recorded in the Product field. Deprecated. Use Parent Store Order Line.Product instead. |
| [ParentDocument](Logistics.Inventory.StoreTransactionLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [ParentStoreOrderLine](Logistics.Inventory.StoreTransactionLines.md#parentstoreorderline) | [StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable) | The line, containing the ordered quantity, which this execution line executes. |
| [Product](Logistics.Inventory.StoreTransactionLines.md#product) | [Products](General.Products.Products.md) | The item that was received/issued |
| [ProductCode](Logistics.Inventory.StoreTransactionLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product through some of the product codes. |
| [ProductVariant](Logistics.Inventory.StoreTransactionLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. |
| [QuantityUnit](Logistics.Inventory.StoreTransactionLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. NULL means that the quantity is specified only in base measurement unit |
| [SerialNumber](Logistics.Inventory.StoreTransactionLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [StoreBin](Logistics.Inventory.StoreTransactionLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | Store bin, from/to which the transaction was performed. |
| [TransactionObj](Logistics.Inventory.StoreTransactionLines.md#transactionobj) | [StoreTransactions](Logistics.Inventory.StoreTransactions.md) | The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.StoreTransactionLines.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.StoreTransactionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Inventory.StoreTransactionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AllowOverExecution

If checked specifies that the quantity in this line may exceed the quantity in the corresponding store order line`Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### Finished

1 if this transaction entry completes the operation. 0 if there might be more entries`Default(false)` `Filter(eq)`

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### GuaranteePeriodDays

standard guarantee period in days. Can be set only if the product type is serviced.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product.GuaranteePeriodDays`
### LineBaseCost

The cost of the transaction in the currency of the enterprise company`Currency: TransactionObj.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### LineCost

Suggested total cost for the line, specified by the user or when the document was generated. Used only when Cost Source = Document, in which case it is used to specify the actual total cost for the line.`Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### LineDocumentCost

The cost of the transaction in the currency of the document`Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)` `ReadOnly`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### LineNo

Line number, unique within the store transaction.`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.TransactionObj.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.TransactionObj.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineProductCost

The cost of the transaction in the currency of the product`Currency: Product.CostingCurrency` `Required` `Default(0)` `ReadOnly`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### LineStoreCost

The cost of the transaction in the currency of the warehouse`Currency: TransactionObj.Store.Currency` `Required` `Default(0)` `ReadOnly`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

### Notes

Notes for this StoreTransactionLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### ParentLineId

Used, when transaction lines are generated directly from other entities (different from Store Order). Denotes the Id of the parent document line, which generated the transaction line. `Filter(multi eq)`

Type: **guid __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute line.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Quantity

The quantity received/issued in the measurement unit, specified in Quantity_Unit_Id. NULL means that the quantity is specified only in base measurement unit`Unit: QuantityUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

The quantity of the stock received/issued in base measurement unit`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `Filter(ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### TempOrderNo

Obsolete. Not used.`Filter(eq)`

Type: **string (50) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **HiddenByDefault**  

### TransactionTimestamp

Exact time when the transaction changes the cost of the product.`Filter(ge;le)` `ORD`

Type: **datetime __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **HiddenByDefault**  

### UnitCost

Cost for 1 of the specified quantity`Currency: TransactionObj.DocumentCurrency` `Required` `Default(0)`

Type: **[Amount (14, 5)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

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

The owner document. The transaction to which the transaction line belongs. `Required` `Filter(multi eq)`

Type: **[StoreTransactions](Logistics.Inventory.StoreTransactions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

If non-null, contains the specific lot to use for the movement

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### OriginalProduct

When specified, contains the original product, which was ordered to be received or issued. The actual product is recorded in the Product field. Deprecated. Use Parent Store Order Line.Product instead.

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.Product`
### ParentDocument

The document, which the current line executes. NULL when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ParentStoreOrderLine

The line, containing the ordered quantity, which this execution line executes.

Type: **[StoreOrderLines](Logistics.Inventory.StoreOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The item that was received/issued

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.OriginalProduct`
### ProductCode

Selects the product through some of the product codes.

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### QuantityUnit

The measurement unit of Quantity. NULL means that the quantity is specified only in base measurement unit

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### StoreBin

Store bin, from/to which the transaction was performed.

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### TransactionObj

The transaction to which the transaction line belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[StoreTransactions](Logistics.Inventory.StoreTransactions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.StoreTransactionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.StoreTransactionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_StoreTransactionLines

Domain API Entity Type: 
Logistics_Inventory_StoreTransactionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_StoreTransactionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_StoreTransactionLines?$top=10>

