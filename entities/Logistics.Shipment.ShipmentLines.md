---
uid: Logistics.Shipment.ShipmentLines
---
# Logistics.Shipment.ShipmentLines


Represents detail lines of shipments. Each line contains the shipment of one product.

## General
Namespace: [Logistics.Shipment](Logistics.Shipment.md)  
Repository: Logistics.Shipment.ShipmentLines  
Base Table: Log_Shipment_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {Shipment.DocumentNo} {Shipment.DocumentType.TypeName:T}  
Search Members: Shipment.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Shipment.Shipments](Logistics.Shipment.Shipments.md)  
Aggregate Root:  
[Logistics.Shipment.Shipments](Logistics.Shipment.Shipments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BoxCount](Logistics.Shipment.ShipmentLines.md#boxcount) | int32 __nullable__ | The count of boxes in which the goods are packaged. NULL means unknown 
| [CurrentBalanceBase](Logistics.Shipment.ShipmentLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [Finished](Logistics.Shipment.ShipmentLines.md#finished) | boolean | 1 if this shipment should prohibit further shipments for the sales order line 
| [GrossWeightkg](Logistics.Shipment.ShipmentLines.md#grossweightkg) | decimal (12, 3) __nullable__ | The gross weight of the whole line in kilogramms. NULL means unknown 
| [GuaranteePeriodDays](Logistics.Shipment.ShipmentLines.md#guaranteeperioddays) | int32 __nullable__ | standard guarantee period in days. Can be set only if the product type is serviced. 
| [Heightm](Logistics.Shipment.ShipmentLines.md#heightm) | decimal (12, 3) __nullable__ | The height of the package in meters. NULL means unknown 
| [Lengthm](Logistics.Shipment.ShipmentLines.md#lengthm) | decimal (12, 3) __nullable__ | The length of the package in meters. NULL means unknown 
| [LineNo](Logistics.Shipment.ShipmentLines.md#lineno) | int32 | Line number, unique for the shipment 
| [LineRequiredDeliveryDate](Logistics.Shipment.ShipmentLines.md#linerequireddeliverydate) | datetime __nullable__ | Required delivery date for this lines. Depending on the shipment route travel time, the shipment should be released accordingly 
| [NetWeightkg](Logistics.Shipment.ShipmentLines.md#netweightkg) | decimal (12, 3) __nullable__ | The net weight of the entire batch of goods in kilograms. NULL means unknown 
| [Notes](Logistics.Shipment.ShipmentLines.md#notes) | string (max) __nullable__ | Specific notes for this line. 
| [PalletNo](Logistics.Shipment.ShipmentLines.md#palletno) | int32 __nullable__ | The number of the pallet in which the goods are packaged. NULL means unknown 
| [ParentLineNo](Logistics.Shipment.ShipmentLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute parent line. 
| [Product](Logistics.Shipment.ShipmentLines.md#product) | [Product](../data-types.md#general.products.product) |              Gets or sets the product.              
| [Quantity](Logistics.Shipment.ShipmentLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity to be shipped 
| [QuantityBase](Logistics.Shipment.ShipmentLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalence of Quantity in the base measurement category of the product. 
| [StandardQuantityBase](Logistics.Shipment.ShipmentLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. 
| [Volumel](Logistics.Shipment.ShipmentLines.md#volumel) | decimal (12, 3) __nullable__ | The volume in litres of the whole batch. NULL means unknown 
| [Widthm](Logistics.Shipment.ShipmentLines.md#widthm) | decimal (12, 3) __nullable__ | The width of the package in meters. NULL means unknown 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Shipment.ShipmentLines.md#document) | [Shipments](Logistics.Shipment.Shipments.md) | The owner document. The <see cref="Shipment"/> to which this ShipmentLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Shipment.ShipmentLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The store lot from which to take the goods |
| [ParentDocument](Logistics.Shipment.ShipmentLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [ParentSalesOrderLine](Logistics.Shipment.ShipmentLines.md#parentsalesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) | Sales order line which is shipped |
| [QuantityUnit](Logistics.Shipment.ShipmentLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity |
| [SerialNumber](Logistics.Shipment.ShipmentLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [Shipment](Logistics.Shipment.ShipmentLines.md#shipment) | [Shipments](Logistics.Shipment.Shipments.md) | The <see cref="Shipment"/> to which this ShipmentLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ShipmentOrderLine](Logistics.Shipment.ShipmentLines.md#shipmentorderline) | [ShipmentOrderLines](Logistics.Shipment.ShipmentOrderLines.md) (nullable) | Shipment order line for which this quantity is shipped. |
| [StoreBin](Logistics.Shipment.ShipmentLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin from which to take the goods |
| [TransactionLine](Logistics.Shipment.ShipmentLines.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable) | The Transaction Line, based on which this shipment line was created. The transaction line contains the store issue operation of the shipped product. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Shipment.ShipmentLines.md#id) | guid |  
| [ObjectVersion](Logistics.Shipment.ShipmentLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Shipment.ShipmentLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BoxCount

The count of boxes in which the goods are packaged. NULL means unknown

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### Finished

1 if this shipment should prohibit further shipments for the sales order line

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **CannotBeShown**  

### GrossWeightkg

The gross weight of the whole line in kilogramms. NULL means unknown

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### GuaranteePeriodDays

standard guarantee period in days. Can be set only if the product type is serviced.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( obj.ParentSalesOrderLine.Product.ProductType.IsServiced, obj.ParentSalesOrderLine.Product.GuaranteePeriodDays, null)`
### Heightm

The height of the package in meters. NULL means unknown

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Lengthm

The length of the package in meters. NULL means unknown

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### LineNo

Line number, unique for the shipment

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Shipment.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.Shipment.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineRequiredDeliveryDate

Required delivery date for this lines. Depending on the shipment route travel time, the shipment should be released accordingly

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.Shipment.RequiredDeliveryDate`

Front-End Recalc Expressions:  
`obj.Shipment.RequiredDeliveryDate`
### NetWeightkg

The net weight of the entire batch of goods in kilograms. NULL means unknown

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Notes

Specific notes for this line.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### PalletNo

The number of the pallet in which the goods are packaged. NULL means unknown

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute parent line.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Product

Gets or sets the product.

Type: **[Product](../data-types.md#general.products.product)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### Quantity

The quantity to be shipped

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ParentSalesOrderLine.Quantity`
### QuantityBase

The equivalence of Quantity in the base measurement category of the product.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### Volumel

The volume in litres of the whole batch. NULL means unknown

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Widthm

The width of the package in meters. NULL means unknown

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

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

The owner document. The <see cref="Shipment"/> to which this ShipmentLine belongs. `Required` `Filter(multi eq)`

Type: **[Shipments](Logistics.Shipment.Shipments.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

The store lot from which to take the goods

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.ParentSalesOrderLine.Lot`
### ParentDocument

The document, which the current line executes. NULL when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ParentSalesOrderLine

Sales order line which is shipped

Type: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md)**  
Indexed: **True**  
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
`obj.ParentSalesOrderLine.QuantityUnit`
### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Shipment

The <see cref="Shipment"/> to which this ShipmentLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Shipments](Logistics.Shipment.Shipments.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ShipmentOrderLine

Shipment order line for which this quantity is shipped.

Type: **[ShipmentOrderLines](Logistics.Shipment.ShipmentOrderLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### StoreBin

The store bin from which to take the goods

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### TransactionLine

The Transaction Line, based on which this shipment line was created. The transaction line contains the store issue operation of the shipped product.

Type: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Logistics.Shipment.ShipmentLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Shipment.ShipmentLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Shipment_ShipmentLines

Domain API Entity Type: 
Logistics_Shipment_ShipmentLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Shipment_ShipmentLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Shipment_ShipmentLines?$top=10>

