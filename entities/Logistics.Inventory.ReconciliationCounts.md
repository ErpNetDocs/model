---
uid: Logistics.Inventory.ReconciliationCounts
---
# Logistics.Inventory.ReconciliationCounts Entity

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

Used for planned reconciliations to count product quantities from multiple devices. Entity: Inv_Reconciliation_Counts (Introduced in version 24.1.3.48)

## Default Visualization
Default Display Text Format:  
_{Reconciliation.EntityName}_  
Default Search Members:  
_Reconciliation.EntityName_  
Name Data Member:  
_Reconciliation.EntityName_  
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
| [CreationTimeUtc](Logistics.Inventory.ReconciliationCounts.md#creationtimeutc) | datetime | The exact time (UTC) the product was counted. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` 
| [DisplayText](Logistics.Inventory.ReconciliationCounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Logistics.Inventory.ReconciliationCounts.md#id) | guid |  
| [Notes](Logistics.Inventory.ReconciliationCounts.md#notes) | string (max) __nullable__ | Additional information for the Count. `Introduced in version 24.1.5.37` 
| [ObjectVersion](Logistics.Inventory.ReconciliationCounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Logistics.Inventory.ReconciliationCounts.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The counted quantity in the default measurement unit of the product. `Unit: QuantityUnit` `Required` `Filter(ge;le)` 
| [QuantityBase](Logistics.Inventory.ReconciliationCounts.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` `Introduced in version 25.1.1.42` 
| [StandardQuantityBase](Logistics.Inventory.ReconciliationCounts.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` `Introduced in version 25.1.1.42` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Logistics.Inventory.ReconciliationCounts.md#creationuser) | [Users](Systems.Security.Users.md) | The user who performed the count. `Required` `Filter(multi eq)` `ReadOnly` |
| [Product](Logistics.Inventory.ReconciliationCounts.md#product) | [Products](General.Products.Products.md) | The product which is currently counted. `Required` `Filter(multi eq)` |
| [QuantityUnit](Logistics.Inventory.ReconciliationCounts.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit from the definition of the product. `Required` `Filter(multi eq)` |
| [Reconciliation](Logistics.Inventory.ReconciliationCounts.md#reconciliation) | [Reconciliations](Logistics.Inventory.Reconciliations.md) | The planned reconciliation for which to execute the current counting. `Required` `Filter(multi eq)` `Introduced in version 24.1.4.51` `Owner` |
| [WarehouseTransaction](Logistics.Inventory.ReconciliationCounts.md#warehousetransaction) | [WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md) (nullable) | The warehouse transaction with which the count has been recorded. Filled if the count information is loaded from the WMS module. `Filter(multi eq)` `ReadOnly` `Introduced in version 24.1.5.37` |


## Attribute Details

### CreationTimeUtc

The exact time (UTC) the product was counted. `Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTimeUtc**  
_Show in UI_: **ShownByDefault**  

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
_Show in UI_: **ShownByDefault**  

### Notes

Additional information for the Count. `Introduced in version 24.1.5.37`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The counted quantity in the default measurement unit of the product. `Unit: QuantityUnit` `Required` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

Quantity in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` `Introduced in version 25.1.1.42`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` `Introduced in version 25.1.1.42`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

## Reference Details

### CreationUser

The user who performed the count. `Required` `Filter(multi eq)` `ReadOnly`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product which is currently counted. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### QuantityUnit

The measurement unit from the definition of the product. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Reconciliation

The planned reconciliation for which to execute the current counting. `Required` `Filter(multi eq)` `Introduced in version 24.1.4.51` `Owner`

_Type_: **[Reconciliations](Logistics.Inventory.Reconciliations.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### WarehouseTransaction

The warehouse transaction with which the count has been recorded. Filled if the count information is loaded from the WMS module. `Filter(multi eq)` `ReadOnly` `Introduced in version 24.1.5.37`

_Type_: **[WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.ReconciliationCounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.ReconciliationCounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_ReconciliationCounts

Domain API Entity Type: 
Logistics_Inventory_ReconciliationCount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_ReconciliationCounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_ReconciliationCounts?$top=10>

