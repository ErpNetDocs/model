---
uid: Logistics.Inventory.StoreOrderLines
---
# Logistics.Inventory.StoreOrderLines


Detail lines of store orders. Each line represents one planned stock transaction line, but can be executed in parts. E.g. many transaction lines can be bound to one order line.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.StoreOrderLines  
Base Table: Inv_Store_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {StoreOrder.DocumentNo} {StoreOrder.DocumentType.TypeName:T}  
Search Members: StoreOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.StoreOrders](Logistics.Inventory.StoreOrders.md)  
Aggregate Root:  
[Logistics.Inventory.StoreOrders](Logistics.Inventory.StoreOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CurrentBalanceBase](Logistics.Inventory.StoreOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [ForOrdering](Logistics.Inventory.StoreOrderLines.md#forordering) | boolean | Specifies that the quantity of the product can be less than free to use quantity, because the product will be supplied [Required] [Default(false)] 
| [GuaranteePeriodDays](Logistics.Inventory.StoreOrderLines.md#guaranteeperioddays) | int32 __nullable__ | standard guarantee period in days. Can be set only if the product type is serviced. 
| [LineCost](Logistics.Inventory.StoreOrderLines.md#linecost) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | Total cost for the line in the currency of the document. Equals Quantity * Unit_Cost[Currency: StoreOrder.DocumentCurrency] 
| [LineNo](Logistics.Inventory.StoreOrderLines.md#lineno) | int32 | Serial record order[Required] [Filter(eq)] 
| [LotNumber](Logistics.Inventory.StoreOrderLines.md#lotnumber) | string (16) __nullable__ | Obsolete. Not used. 
| [Notes](Logistics.Inventory.StoreOrderLines.md#notes) | string (254) __nullable__ | Notes for this StoreOrderLine. 
| [ParentLineId](Logistics.Inventory.StoreOrderLines.md#parentlineid) | guid __nullable__ | Id of the line of the parent document, which generated the store order. null for user-entered store orders or if not applicable. `Filter(multi eq)` 
| [ParentLineNo](Logistics.Inventory.StoreOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute parent line.[Filter(eq)] 
| [PersistLot](Logistics.Inventory.StoreOrderLines.md#persistlot) | boolean | If checked specifies that the lot in the line cannot be changed in the sub-documents created by the current document.[Required] [Default(false)] [Filter(eq)] 
| [Quantity](Logistics.Inventory.StoreOrderLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity ordered for receipt/issue[Unit: QuantityUnit] [Required] [Default(0)] 
| [QuantityBase](Logistics.Inventory.StoreOrderLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity in the base (default) measurement unit of the Item (calculated at the time of last update of the current store order line). Should be updated in parallel with each Quantity update[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Default(0)] [ReadOnly] 
| [StandardQuantityBase](Logistics.Inventory.StoreOrderLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2] 
| [TransactionTimestamp](Logistics.Inventory.StoreOrderLines.md#transactiontimestamp) | datetime __nullable__ | Exact time when the transaction changes the cost of the product. It is written in the transaction lines created for the current line.[Filter(ge;le)] [ReadOnly] 
| [UnitCost](Logistics.Inventory.StoreOrderLines.md#unitcost) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | Cost for 1 unit of measure in the currency of the document[Currency: StoreOrder.DocumentCurrency] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Inventory.StoreOrderLines.md#document) | [StoreOrders](Logistics.Inventory.StoreOrders.md) | The owner document. The <see cref="StoreOrder"/> to which this StoreOrderLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Inventory.StoreOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement |
| [ParentDocument](Logistics.Inventory.StoreOrderLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [Product](Logistics.Inventory.StoreOrderLines.md#product) | [Products](General.Products.Products.md) | The product which should be received/issued |
| [ProductVariant](Logistics.Inventory.StoreOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. |
| [QuantityUnit](Logistics.Inventory.StoreOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity |
| [SalesOrderLine](Logistics.Inventory.StoreOrderLines.md#salesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable) | Sales order line which is managed by this store order line. When specified sales order line is used to make the margin analysis. |
| [SerialNumber](Logistics.Inventory.StoreOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [StoreBin](Logistics.Inventory.StoreOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | From/to which store bin to issue/receive the products. NULL means that the store bin is unknown or not applicable |
| [StoreOrder](Logistics.Inventory.StoreOrderLines.md#storeorder) | [StoreOrders](Logistics.Inventory.StoreOrders.md) | The <see cref="StoreOrder"/> to which this StoreOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.StoreOrderLines.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.StoreOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Inventory.StoreOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ForOrdering

Specifies that the quantity of the product can be less than free to use quantity, because the product will be supplied [Required] [Default(false)]

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
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
`IIF( obj.Product.ProductType.IsServiced, obj.Product.GuaranteePeriodDays, null)`
### LineCost

Total cost for the line in the currency of the document. Equals Quantity * Unit_Cost[Currency: StoreOrder.DocumentCurrency]

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Serial record order[Required] [Filter(eq)]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.StoreOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.StoreOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LotNumber

Obsolete. Not used.

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **HiddenByDefault**  

### Notes

Notes for this StoreOrderLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### ParentLineId

Id of the line of the parent document, which generated the store order. null for user-entered store orders or if not applicable. `Filter(multi eq)`

Type: **guid __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute parent line.[Filter(eq)]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PersistLot

If checked specifies that the lot in the line cannot be changed in the sub-documents created by the current document.[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### Quantity

Quantity ordered for receipt/issue[Unit: QuantityUnit] [Required] [Default(0)]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### QuantityBase

Quantity in the base (default) measurement unit of the Item (calculated at the time of last update of the current store order line). Should be updated in parallel with each Quantity update[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [Default(0)] [ReadOnly]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.[Unit: Product.BaseMeasurementCategory.BaseUnit] [Required] [ReadOnly] [Introduced in version 18.2]

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### TransactionTimestamp

Exact time when the transaction changes the cost of the product. It is written in the transaction lines created for the current line.[Filter(ge;le)] [ReadOnly]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### UnitCost

Cost for 1 unit of measure in the currency of the document[Currency: StoreOrder.DocumentCurrency]

Type: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
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

The owner document. The <see cref="StoreOrder"/> to which this StoreOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[StoreOrders](Logistics.Inventory.StoreOrders.md)**  
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

### ParentDocument

The document, which the current line executes. NULL when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Product

The product which should be received/issued

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used.

Type: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### QuantityUnit

The measurement unit of Quantity

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.MeasurementUnit`
### SalesOrderLine

Sales order line which is managed by this store order line. When specified sales order line is used to make the margin analysis.

Type: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### StoreBin

From/to which store bin to issue/receive the products. NULL means that the store bin is unknown or not applicable

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### StoreOrder

The <see cref="StoreOrder"/> to which this StoreOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[StoreOrders](Logistics.Inventory.StoreOrders.md)**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.StoreOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.StoreOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_StoreOrderLines

Domain API Entity Type: 
Logistics_Inventory_StoreOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_StoreOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_StoreOrderLines?$top=10>

