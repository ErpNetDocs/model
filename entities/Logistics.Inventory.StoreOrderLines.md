---
uid: Logistics.Inventory.StoreOrderLines
---
# Logistics.Inventory.StoreOrderLines Entity

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

Detail lines of store orders. Each line represents one planned stock transaction line, but can be executed in parts. E.g. many transaction lines can be bound to one order line. Entity: Inv_Store_Order_Lines

## Default Visualization
Default Display Text Format:  
_{LineNo}. {StoreOrder.DocumentNo} {StoreOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_StoreOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Logistics.Inventory.StoreOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ForOrdering](Logistics.Inventory.StoreOrderLines.md#forordering) | boolean | Specifies that the quantity of the product can be less than free to use quantity, because the product will be supplied . `Required` `Default(false)` 
| [GuaranteePeriodDays](Logistics.Inventory.StoreOrderLines.md#guaranteeperioddays) | int32 __nullable__ | Guarantee period in days for the offered product. null for non-serviced products. 
| [Id](Logistics.Inventory.StoreOrderLines.md#id) | guid |  
| [LineCost](Logistics.Inventory.StoreOrderLines.md#linecost) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | Total cost for the line in the currency of the document. Equals Quantity * Unit_Cost. `Currency: StoreOrder.DocumentCurrency` 
| [LineNo](Logistics.Inventory.StoreOrderLines.md#lineno) | int32 | Line number within the store order. `Required` `Filter(eq)` 
| [LotNumber](Logistics.Inventory.StoreOrderLines.md#lotnumber) | string (16) __nullable__ | Obsolete. Not used. 
| [Notes](Logistics.Inventory.StoreOrderLines.md#notes) | string (254) __nullable__ | Notes for this StoreOrderLine. 
| [ObjectVersion](Logistics.Inventory.StoreOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentLineId](Logistics.Inventory.StoreOrderLines.md#parentlineid) | guid __nullable__ | Id of the line of the parent document, which generated the store order. null for user-entered store orders or if not applicable. `Filter(multi eq)` 
| [ParentLineNo](Logistics.Inventory.StoreOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute parent line. `Filter(eq)` 
| [PersistLot](Logistics.Inventory.StoreOrderLines.md#persistlot) | boolean | If checked specifies that the lot in the line cannot be changed in the sub-documents created by the current document. `Required` `Default(false)` `Filter(eq)` 
| [Quantity](Logistics.Inventory.StoreOrderLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity ordered for receipt/issue. `Unit: QuantityUnit` `Required` `Default(0)` 
| [QuantityBase](Logistics.Inventory.StoreOrderLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity in the base (default) measurement unit of the Item (calculated at the time of last update of the current store order line). Should be updated in parallel with each Quantity update. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` 
| [StandardQuantityBase](Logistics.Inventory.StoreOrderLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [TransactionTimestamp](Logistics.Inventory.StoreOrderLines.md#transactiontimestamp) | datetime __nullable__ | Exact time when the transaction for this store order line changes the cost of the product. `Filter(ge;le)` `ReadOnly` 
| [UnitCost](Logistics.Inventory.StoreOrderLines.md#unitcost) | [Amount (14, 5)](../data-types.md#amount) __nullable__ | Cost for 1 unit of measure in the currency of the document. `Currency: StoreOrder.DocumentCurrency` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Inventory.StoreOrderLines.md#document) | [StoreOrders](Logistics.Inventory.StoreOrders.md) | The owner document. The <see cref="StoreOrder"/> to which this StoreOrderLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Inventory.StoreOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If non-null, contains the specific lot to use for the movement. `Filter(multi eq)` |
| [ParentDocument](Logistics.Inventory.StoreOrderLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` |
| [Product](Logistics.Inventory.StoreOrderLines.md#product) | [Products](General.Products.Products.md) | The product which should be received/issued. `Required` `Filter(multi eq)` |
| [ProductVariant](Logistics.Inventory.StoreOrderLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | If specified determines which product variant of the current product in this line is used. `Filter(multi eq)` |
| [QuantityUnit](Logistics.Inventory.StoreOrderLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |
| [SalesOrderLine](Logistics.Inventory.StoreOrderLines.md#salesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable) | Sales order line which is managed by this store order line. When specified sales order line is used to make the margin analysis. `Filter(multi eq)` |
| [SerialNumber](Logistics.Inventory.StoreOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Which serial number to receive/issue. null means that serial number is unknown or not applicable. `Filter(multi eq)` |
| [StoreBin](Logistics.Inventory.StoreOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | From/to which store bin to issue/receive the products. null means that the store bin is unknown or not applicable. `Filter(multi eq)` |
| [StoreOrder](Logistics.Inventory.StoreOrderLines.md#storeorder) | [StoreOrders](Logistics.Inventory.StoreOrders.md) | The <see cref="StoreOrder"/> to which this StoreOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |


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

### ForOrdering

Specifies that the quantity of the product can be less than free to use quantity, because the product will be supplied . `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **HiddenByDefault**  

### GuaranteePeriodDays

Guarantee period in days for the offered product. null for non-serviced products.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( obj.Product.ProductType.IsServiced, obj.Product.GuaranteePeriodDays, null)`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineCost

Total cost for the line in the currency of the document. Equals Quantity * Unit_Cost. `Currency: StoreOrder.DocumentCurrency`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LineNo

Line number within the store order. `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.StoreOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.StoreOrder.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LotNumber

Obsolete. Not used.

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **HiddenByDefault**  

### Notes

Notes for this StoreOrderLine.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ParentLineId

Id of the line of the parent document, which generated the store order. null for user-entered store orders or if not applicable. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute parent line. `Filter(eq)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### PersistLot

If checked specifies that the lot in the line cannot be changed in the sub-documents created by the current document. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **HiddenByDefault**  

### Quantity

Quantity ordered for receipt/issue. `Unit: QuantityUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

Quantity in the base (default) measurement unit of the Item (calculated at the time of last update of the current store order line). Should be updated in parallel with each Quantity update. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### TransactionTimestamp

Exact time when the transaction for this store order line changes the cost of the product. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### UnitCost

Cost for 1 unit of measure in the currency of the document. `Currency: StoreOrder.DocumentCurrency`

_Type_: **[Amount (14, 5)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Document

The owner document. The <see cref="StoreOrder"/> to which this StoreOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[StoreOrders](Logistics.Inventory.StoreOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

If non-null, contains the specific lot to use for the movement. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Product

The product which should be received/issued. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductVariant

If specified determines which product variant of the current product in this line is used. `Filter(multi eq)`

_Type_: **[ProductVariants](General.Products.ProductVariants.md) (nullable)**  
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
`obj.Product.MeasurementUnit`
### SalesOrderLine

Sales order line which is managed by this store order line. When specified sales order line is used to make the margin analysis. `Filter(multi eq)`

_Type_: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### SerialNumber

Which serial number to receive/issue. null means that serial number is unknown or not applicable. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### StoreBin

From/to which store bin to issue/receive the products. null means that the store bin is unknown or not applicable. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### StoreOrder

The <see cref="StoreOrder"/> to which this StoreOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[StoreOrders](Logistics.Inventory.StoreOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

