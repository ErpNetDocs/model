---
uid: Logistics.Shipment.ShipmentLines
---
# Logistics.Shipment.ShipmentLines Entity

**Namespace:** [Logistics.Shipment](Logistics.Shipment.md)  

Represents detail lines of shipments. Each line contains the shipment of one product. Entity: Log_Shipment_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo}. {Shipment.DocumentNo} {Shipment.DocumentType.TypeName:T}_  
Default Search Members:  
_Shipment.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Shipment.Shipments](Logistics.Shipment.Shipments.md)  
Aggregate Root:  
[Logistics.Shipment.Shipments](Logistics.Shipment.Shipments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BoxCount](Logistics.Shipment.ShipmentLines.md#boxcount) | int32 __nullable__ | The count of boxes in which the goods are packaged. null means unknown. 
| [CurrentBalanceBase](Logistics.Shipment.ShipmentLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Logistics.Shipment.ShipmentLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Finished](Logistics.Shipment.ShipmentLines.md#finished) | boolean | True if this shipment should prohibit further shipments for the sales order line. `Required` `Default(false)` `Filter(eq)` `ReadOnly` 
| [GrossWeightkg](Logistics.Shipment.ShipmentLines.md#grossweightkg) | decimal (12, 3) __nullable__ | The gross weight of the whole line in kilogramms. null means unknown. 
| [GuaranteePeriodDays](Logistics.Shipment.ShipmentLines.md#guaranteeperioddays) | int32 __nullable__ | Guarantee period in days for the offered product. null for non-serviced products. 
| [Heightm](Logistics.Shipment.ShipmentLines.md#heightm) | decimal (12, 3) __nullable__ | The height of the package in meters. null means unknown. 
| [Id](Logistics.Shipment.ShipmentLines.md#id) | guid |  
| [Lengthm](Logistics.Shipment.ShipmentLines.md#lengthm) | decimal (12, 3) __nullable__ | The length of the package in meters. null means unknown. 
| [LineNo](Logistics.Shipment.ShipmentLines.md#lineno) | int32 | Line number, unique for the shipment. `Required` 
| [LineRequiredDeliveryDate](Logistics.Shipment.ShipmentLines.md#linerequireddeliverydate) | datetime __nullable__ | Required delivery date for this lines. Depending on the shipment route travel time, the shipment should be released accordingly. `Filter(ge;le)` 
| [NetWeightkg](Logistics.Shipment.ShipmentLines.md#netweightkg) | decimal (12, 3) __nullable__ | The net weight of the entire batch of goods in kilograms. null means unknown. 
| [Notes](Logistics.Shipment.ShipmentLines.md#notes) | string (max) __nullable__ | Specific notes for this line. 
| [ObjectVersion](Logistics.Shipment.ShipmentLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PalletNo](Logistics.Shipment.ShipmentLines.md#palletno) | int32 __nullable__ | The number of the pallet in which the goods are packaged. null means unknown. 
| [ParentLineNo](Logistics.Shipment.ShipmentLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute parent line. `Filter(multi eq)` 
| [Product](Logistics.Shipment.ShipmentLines.md#product) | [Product](../data-types.md#general.products.product) |              Gets or sets the product.              
| [Quantity](Logistics.Shipment.ShipmentLines.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity to be shipped. `Unit: QuantityUnit` `Required` 
| [QuantityBase](Logistics.Shipment.ShipmentLines.md#quantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The equivalence of Quantity in the base measurement category of the product. `Unit: ParentSalesOrderLine.Product.BaseMeasurementCategory.BaseUnit` `Required` 
| [StandardQuantityBase](Logistics.Shipment.ShipmentLines.md#standardquantitybase) | [Quantity (12, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: ParentSalesOrderLine.Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [Volumel](Logistics.Shipment.ShipmentLines.md#volumel) | decimal (12, 3) __nullable__ | The volume in litres of the whole batch. null means unknown. 
| [Widthm](Logistics.Shipment.ShipmentLines.md#widthm) | decimal (12, 3) __nullable__ | The width of the package in meters. null means unknown. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Shipment.ShipmentLines.md#document) | [Shipments](Logistics.Shipment.Shipments.md) | The owner document. The <see cref="Shipment"/> to which this ShipmentLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Shipment.ShipmentLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The store lot from which to take the goods. `Filter(multi eq)` |
| [ParentDocument](Logistics.Shipment.ShipmentLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` |
| [ParentSalesOrderLine](Logistics.Shipment.ShipmentLines.md#parentsalesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) | Sales order line which is shipped. `Required` `Filter(multi eq)` |
| [QuantityUnit](Logistics.Shipment.ShipmentLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |
| [SerialNumber](Logistics.Shipment.ShipmentLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | The serial number of the shipped product. null means that serial number is unknown or not applicable. `Filter(multi eq)` |
| [Shipment](Logistics.Shipment.ShipmentLines.md#shipment) | [Shipments](Logistics.Shipment.Shipments.md) | The <see cref="Shipment"/> to which this ShipmentLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ShipmentOrderLine](Logistics.Shipment.ShipmentLines.md#shipmentorderline) | [ShipmentOrderLines](Logistics.Shipment.ShipmentOrderLines.md) (nullable) | Shipment order line for which this quantity is shipped. `Filter(multi eq)` |
| [StoreBin](Logistics.Shipment.ShipmentLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin from which to take the goods. `Filter(multi eq)` |
| [TransactionLine](Logistics.Shipment.ShipmentLines.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable) | The Transaction Line, based on which this shipment line was created. The transaction line contains the store issue operation of the shipped product. `Filter(multi eq)` |


## Attribute Details

### BoxCount

The count of boxes in which the goods are packaged. null means unknown.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

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

### Finished

True if this shipment should prohibit further shipments for the sales order line. `Required` `Default(false)` `Filter(eq)` `ReadOnly`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **CannotBeShown**  

### GrossWeightkg

The gross weight of the whole line in kilogramms. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### GuaranteePeriodDays

Guarantee period in days for the offered product. null for non-serviced products.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.ParentSalesOrderLine.Product.ProductType.IsServiced, obj.ParentSalesOrderLine.Product.GuaranteePeriodDays, null)`
### Heightm

The height of the package in meters. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Lengthm

The length of the package in meters. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### LineNo

Line number, unique for the shipment. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Shipment.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.Shipment.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineRequiredDeliveryDate

Required delivery date for this lines. Depending on the shipment route travel time, the shipment should be released accordingly. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.Shipment.RequiredDeliveryDate`

_Front-End Recalc Expressions:_  
`obj.Shipment.RequiredDeliveryDate`
### NetWeightkg

The net weight of the entire batch of goods in kilograms. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Notes

Specific notes for this line.

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

### PalletNo

The number of the pallet in which the goods are packaged. null means unknown.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute parent line. `Filter(multi eq)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Product

Gets or sets the product.

_Type_: **[Product](../data-types.md#general.products.product)**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The quantity to be shipped. `Unit: QuantityUnit` `Required`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ParentSalesOrderLine.Quantity`
### QuantityBase

The equivalence of Quantity in the base measurement category of the product. `Unit: ParentSalesOrderLine.Product.BaseMeasurementCategory.BaseUnit` `Required`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: ParentSalesOrderLine.Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (12, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### Volumel

The volume in litres of the whole batch. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Widthm

The width of the package in meters. null means unknown.

_Type_: **decimal (12, 3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The owner document. The <see cref="Shipment"/> to which this ShipmentLine belongs. `Required` `Filter(multi eq)`

_Type_: **[Shipments](Logistics.Shipment.Shipments.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

The store lot from which to take the goods. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.ParentSalesOrderLine.Lot`
### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ParentSalesOrderLine

Sales order line which is shipped. `Required` `Filter(multi eq)`

_Type_: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### QuantityUnit

The measurement unit of Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ParentSalesOrderLine.QuantityUnit`
### SerialNumber

The serial number of the shipped product. null means that serial number is unknown or not applicable. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Shipment

The <see cref="Shipment"/> to which this ShipmentLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Shipments](Logistics.Shipment.Shipments.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ShipmentOrderLine

Shipment order line for which this quantity is shipped. `Filter(multi eq)`

_Type_: **[ShipmentOrderLines](Logistics.Shipment.ShipmentOrderLines.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### StoreBin

The store bin from which to take the goods. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### TransactionLine

The Transaction Line, based on which this shipment line was created. The transaction line contains the store issue operation of the shipped product. `Filter(multi eq)`

_Type_: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  


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

