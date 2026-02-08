---
uid: Logistics.Inventory.ReconciliationCounts
---
# Logistics.Inventory.ReconciliationCounts


Used for planned reconciliations to count product quantities from multiple devices.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.ReconciliationCounts  
Base Table: Inv_Reconciliation_Counts  
Introduced In Version: 24.1.3.48  
API access:  ReadWrite  

## Visualization
Display Format: {Reconciliation.EntityName}  
Search Members: Reconciliation.EntityName  
Name Member: Reconciliation.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.Reconciliations](Logistics.Inventory.Reconciliations.md)  
Aggregate Root:  
[Logistics.Inventory.Reconciliations](Logistics.Inventory.Reconciliations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Logistics.Inventory.ReconciliationCounts.md#creationtimeutc) | datetime | The exact time (UTC) the product was counted`Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly` 
| [Notes](Logistics.Inventory.ReconciliationCounts.md#notes) | string (max) __nullable__ | Additional information for the Count.`Introduced in version 24.1.5.37` 
| [Quantity](Logistics.Inventory.ReconciliationCounts.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The counted quantity in the default measurement unit of the product`Unit: QuantityUnit` `Required` `Filter(ge;le)` 
| [QuantityBase](Logistics.Inventory.ReconciliationCounts.md#quantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity in the base measurement unit of the product.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` `Introduced in version 25.1.1.42` 
| [StandardQuantityBase](Logistics.Inventory.ReconciliationCounts.md#standardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` `Introduced in version 25.1.1.42` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Logistics.Inventory.ReconciliationCounts.md#creationuser) | [Users](Systems.Security.Users.md) | The user who performed the count |
| [Product](Logistics.Inventory.ReconciliationCounts.md#product) | [Products](General.Products.Products.md) | The product which is currently counted |
| [QuantityUnit](Logistics.Inventory.ReconciliationCounts.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit from the definition of the product |
| [Reconciliation](Logistics.Inventory.ReconciliationCounts.md#reconciliation) | [Reconciliations](Logistics.Inventory.Reconciliations.md) | The planned reconciliation for which to execute the current counting |
| [WarehouseTransaction](Logistics.Inventory.ReconciliationCounts.md#warehousetransaction) | [WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md) (nullable) | The warehouse transaction with which the count has been recorded. Filled if the count information is loaded from the WMS module. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.ReconciliationCounts.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.ReconciliationCounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Inventory.ReconciliationCounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CreationTimeUtc

The exact time (UTC) the product was counted`Required` `Default(NowUtc)` `Filter(ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTimeUtc**  
Show in UI: **ShownByDefault**  

### Notes

Additional information for the Count.`Introduced in version 24.1.5.37`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Quantity

The counted quantity in the default measurement unit of the product`Unit: QuantityUnit` `Required` `Filter(ge;le)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### QuantityBase

Quantity in the base measurement unit of the product.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` `Introduced in version 25.1.1.42`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.QuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` `Introduced in version 25.1.1.42`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, IIF( obj.Product.AllowVariableMeasurementRatios, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.QuantityBase))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Quantity == null) OrElse ( obj.QuantityUnit == null)) OrElse ( obj.Product == null)), obj.StandardQuantityBase, obj.Quantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

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

### CreationUser

The user who performed the count

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product which is currently counted

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit from the definition of the product

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Reconciliation

The planned reconciliation for which to execute the current counting

Type: **[Reconciliations](Logistics.Inventory.Reconciliations.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### WarehouseTransaction

The warehouse transaction with which the count has been recorded. Filled if the count information is loaded from the WMS module.

Type: **[WarehouseTransactions](Logistics.Wms.WarehouseTransactions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

