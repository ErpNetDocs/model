---
uid: Logistics.Inventory.ReconciliationLines
---
# Logistics.Inventory.ReconciliationLines Entity

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

Store reconciliations (physical counting) detail lines. Each line contains the reconciliation for one combination of product, lot, bin and serial number. Entity: Inv_Reconciliation_Lines

## Default Visualization
Default Display Text Format:  
_{LineOrd}. {Reconciliation.DocumentNo} {Reconciliation.DocumentType.TypeName:T}_  
Default Search Members:  
_Reconciliation.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.Reconciliations](Logistics.Inventory.Reconciliations.md)  
Aggregate Root:  
[Logistics.Inventory.Reconciliations](Logistics.Inventory.Reconciliations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AvailableQuantityBase](Logistics.Inventory.ReconciliationLines.md#availablequantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity found at the reconciliation, in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [CurrentBalanceBase](Logistics.Inventory.ReconciliationLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Logistics.Inventory.ReconciliationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Inventory.ReconciliationLines.md#id) | guid |  
| [LineOrd](Logistics.Inventory.ReconciliationLines.md#lineord) | int32 | The ordinal position of the line within the document. Duplicates are allowed, but not suggested. `Required` 
| [Notes](Logistics.Inventory.ReconciliationLines.md#notes) | string (254) __nullable__ | Notes for this ReconciliationLine. 
| [ObjectVersion](Logistics.Inventory.ReconciliationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Logistics.Inventory.ReconciliationLines.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity found at the reconciliation, . `Unit: QuantityUnit` `Required` `Filter(ge;le)` 
| [QuantityBase](Logistics.Inventory.ReconciliationLines.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity found at the reconciliation, expressed in base measurement units. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(ge;le)` 
| [StandardQuantityBase](Logistics.Inventory.ReconciliationLines.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [TransactionTimestamp](Logistics.Inventory.ReconciliationLines.md#transactiontimestamp) | datetime __nullable__ | Exact time when the transaction occurred. `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Logistics.Inventory.ReconciliationLines.md#document) | [Reconciliations](Logistics.Inventory.Reconciliations.md) | The owner document. Parent reconciliation Id. `Required` `Filter(multi eq)` |
| [Lot](Logistics.Inventory.ReconciliationLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot, which was reconciled. `Filter(multi eq)` |
| [Product](Logistics.Inventory.ReconciliationLines.md#product) | [Products](General.Products.Products.md) | The id of the reconciled product. `Required` `Filter(multi eq)` |
| [ProductCode](Logistics.Inventory.ReconciliationLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product thru some of the product codes. `Filter(multi eq)` |
| [ProductVariant](Logistics.Inventory.ReconciliationLines.md#productvariant) | [ProductVariants](General.Products.ProductVariants.md) (nullable) | The product variant, which was reconciled. `Filter(multi eq)` `Introduced in version 22.1.6.15` |
| [QuantityUnit](Logistics.Inventory.ReconciliationLines.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. `Required` `Filter(multi eq)` |
| [Reconciliation](Logistics.Inventory.ReconciliationLines.md#reconciliation) | [Reconciliations](Logistics.Inventory.Reconciliations.md) | Parent reconciliation Id. `Required` `Filter(multi eq)` `Owner` |
| [SerialNumber](Logistics.Inventory.ReconciliationLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Item serial number for serialized items. null for non-serializable items. `Filter(multi eq)` |
| [Store](Logistics.Inventory.ReconciliationLines.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store, containing the reconciled product. `Required` `Filter(multi eq)` |
| [StoreBin](Logistics.Inventory.ReconciliationLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin, that was counted. `Filter(multi eq)` |
| [WarehouseTransaction](Logistics.Inventory.ReconciliationLines.md#warehousetransaction) | [WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md) (nullable) | The warehouse operation, whose result is reflected in the current line. Null when the reconciliation line is not a result of the counting warehouse operations in the Warehouse Management module. `Filter(multi eq)` `Introduced in version 22.1.6.13` |


## Attribute Details

### AvailableQuantityBase

Quantity found at the reconciliation, in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineOrd

The ordinal position of the line within the document. Duplicates are allowed, but not suggested. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Reconciliation.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.Reconciliation.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this ReconciliationLine.

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

### Quantity

Quantity found at the reconciliation, . `Unit: QuantityUnit` `Required` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

Quantity found at the reconciliation, expressed in base measurement units. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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

Exact time when the transaction occurred. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The owner document. Parent reconciliation Id. `Required` `Filter(multi eq)`

_Type_: **[Reconciliations](Logistics.Inventory.Reconciliations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

The lot, which was reconciled. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Product

The id of the reconciled product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ProductCode.Product.IfNullThen( obj.Product)`
### ProductCode

Selects the product thru some of the product codes. `Filter(multi eq)`

_Type_: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Product != null) AndAlso ( obj.ProductCode != null)) AndAlso ( obj.Product != obj.ProductCode.Product)), null, obj.ProductCode)`
### ProductVariant

The product variant, which was reconciled. `Filter(multi eq)` `Introduced in version 22.1.6.15`

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
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.MeasurementUnit.IfNullThen( obj.QuantityUnit))`
### Reconciliation

Parent reconciliation Id. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Reconciliations](Logistics.Inventory.Reconciliations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

Item serial number for serialized items. null for non-serializable items. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( Not( obj.Product.IsSerialized) OrElse ( ( obj.SerialNumber != null) AndAlso ( obj.Product != obj.SerialNumber.Product))), null, obj.SerialNumber)`
### Store

The store, containing the reconciled product. `Required` `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.Reconciliation.DefaultStore.IfNullThen( obj.Store)`
### StoreBin

The store bin, that was counted. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.Reconciliation.DefaultStoreBin.IfNullThen( obj.StoreBin)`
### WarehouseTransaction

The warehouse operation, whose result is reflected in the current line. Null when the reconciliation line is not a result of the counting warehouse operations in the Warehouse Management module. `Filter(multi eq)` `Introduced in version 22.1.6.13`

_Type_: **[WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.ReconciliationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.ReconciliationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_ReconciliationLines

Domain API Entity Type: 
Logistics_Inventory_ReconciliationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_ReconciliationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_ReconciliationLines?$top=10>

