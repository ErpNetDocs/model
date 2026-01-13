---
uid: Production.ShopFloor.ConsumptionOrderLines
---
# Production.ShopFloor.ConsumptionOrderLines Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

Detail lines of orders for material consumption. Entity: Prd_Consumption_Order_Lines

## Default Visualization
Default Display Text Format:  
_{LineOrd}. {ConsumptionOrder.DocumentNo} {ConsumptionOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_ConsumptionOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)  
Aggregate Root:  
[Production.ShopFloor.ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedQuantity](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Requested quantity of the material. `Unit: ConsumedQuantityUnit` `Required` `Filter(ge;le)` 
| [ConsumedQuantityBase](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The requested quantity equivalence in the base measurement category of the requested material. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [ConsumedStandard<br />QuantityBase](Production.ShopFloor.ConsumptionOrderLines.md#consumedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. null means to convert the value from Quantity using the measurement ratios. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) | [ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) | Determines whether the material cost is distributed among all produced products, or only one (specified in the Work Order Item Ingredient). `Required` `Filter(eq)` `ReadOnly` 
| [CurrentBalanceBase](Production.ShopFloor.ConsumptionOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Production.ShopFloor.ConsumptionOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.ShopFloor.ConsumptionOrderLines.md#id) | guid |  
| [LineOrd](Production.ShopFloor.ConsumptionOrderLines.md#lineord) | int32 | Non-unique line number within the order. `Required` 
| [Notes](Production.ShopFloor.ConsumptionOrderLines.md#notes) | string (max) __nullable__ | Notes for this ConsumptionOrderLine. 
| [ObjectVersion](Production.ShopFloor.ConsumptionOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ScheduledDateTime](Production.ShopFloor.ConsumptionOrderLines.md#scheduleddatetime) | datetime __nullable__ | The scheduled date, when the material is needed. `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ConsumedQuantityUnit](Production.ShopFloor.ConsumptionOrderLines.md#consumedquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | Measurement unit of the requested quantity. `Required` `Filter(multi eq)` |
| [ConsumptionOrder](Production.ShopFloor.ConsumptionOrderLines.md#consumptionorder) | [ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md) | The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [Document](Production.ShopFloor.ConsumptionOrderLines.md#document) | [ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md) | The owner document. The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` |
| [Lot](Production.ShopFloor.ConsumptionOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | If not null, specifies that the material has to be consumed from specific lot. `Filter(multi eq)` |
| [Product](Production.ShopFloor.ConsumptionOrderLines.md#product) | [Products](General.Products.Products.md) | The requested material. `Required` `Filter(multi eq)` |
| [SerialNumber](Production.ShopFloor.ConsumptionOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | If not null, specifies that the material has to be consumed with specific serial number. `Filter(multi eq)` |
| [Store](Production.ShopFloor.ConsumptionOrderLines.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store, from which the material is requested. `Filter(multi eq)` |
| [StoreBin](Production.ShopFloor.ConsumptionOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | If not null, specifies that the material has to be consumed from specific store bin. `Filter(multi eq)` |
| [WorkOrderItemIngredient](Production.ShopFloor.ConsumptionOrderLines.md#workorderitemingredient) | [WorkOrderItemIngredients](Production.ShopFloor.WorkOrderItemIngredients.md) | The Work Order Item Ingredient for which we are ordering materials. `Required` `Filter(multi eq)` |


## Attribute Details

### ConsumedQuantity

Requested quantity of the material. `Unit: ConsumedQuantityUnit` `Required` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.ConsumedQuantityUnit == null), null, IIF( ( obj.WorkOrderItemIngredient != null), obj.WorkOrderItemIngredient.GetSumConsumedQuantity( obj.ConsumedQuantityUnit), obj.ConsumedQuantity))`
### ConsumedQuantityBase

The requested quantity equivalence in the base measurement category of the requested material. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ConsumedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. null means to convert the value from Quantity using the measurement ratios. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedStandardQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ConsumedQuantity == null) OrElse ( obj.ConsumedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ConsumedStandardQuantityBase, obj.ConsumedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ConsumptionType

Determines whether the material cost is distributed among all produced products, or only one (specified in the Work Order Item Ingredient). `Required` `Filter(eq)` `ReadOnly`

_Type_: **[ConsumptionType](Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype)**  
_Category_: **System**  
Allowed values for the `ConsumptionType`(Production.ShopFloor.ConsumptionOrderLines.md#consumptiontype) data attribute  
_Allowed Values (Production.ShopFloor.ConsumptionOrderLinesRepository.ConsumptionType Enum Members)_  

| Value | Description |
| ---- | --- |
| ForSpecifiedItem | ForSpecifiedItem value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ForSpecifiedItem' |
| ForAllItems | ForAllItems value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ForAllItems' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.WorkOrderItemIngredient != null) AndAlso ( obj.WorkOrderItemIngredient.WorkOrderItem != null)), ForSpecifiedItem, ForAllItems)`
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

Non-unique line number within the order. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.ConsumptionOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.ConsumptionOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this ConsumptionOrderLine.

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

### ScheduledDateTime

The scheduled date, when the material is needed. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### ConsumedQuantityUnit

Measurement unit of the requested quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit`
### ConsumptionOrder

The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Document

The owner document. The <see cref="ConsumptionOrder"/> to which this ConsumptionOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[ConsumptionOrders](Production.ShopFloor.ConsumptionOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

If not null, specifies that the material has to be consumed from specific lot. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Product

The requested material. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.WorkOrderItemIngredient.Material`
### SerialNumber

If not null, specifies that the material has to be consumed with specific serial number. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Store

The store, from which the material is requested. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.ConsumptionOrder.Store`

_Front-End Recalc Expressions:_  
`obj.ConsumptionOrder.Store`
### StoreBin

If not null, specifies that the material has to be consumed from specific store bin. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### WorkOrderItemIngredient

The Work Order Item Ingredient for which we are ordering materials. `Required` `Filter(multi eq)`

_Type_: **[WorkOrderItemIngredients](Production.ShopFloor.WorkOrderItemIngredients.md)**  
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

[!list limit=1000 erp.entity=Production.ShopFloor.ConsumptionOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.ConsumptionOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_ConsumptionOrderLines

Domain API Entity Type: 
Production_ShopFloor_ConsumptionOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_ConsumptionOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_ConsumptionOrderLines?$top=10>

