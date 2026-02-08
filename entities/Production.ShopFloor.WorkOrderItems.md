---
uid: Production.ShopFloor.WorkOrderItems
---
# Production.ShopFloor.WorkOrderItems


The different items that are produced with a work order

## General
Namespace: [Production.ShopFloor](Production.ShopFloor.md)  
Repository: Production.ShopFloor.WorkOrderItems  
Base Table: Prd_Work_Order_Items  
API access:  ReadWrite  

## Visualization
Display Format: {LineOrd}. {WorkOrder.DocumentNo} {WorkOrder.DocumentType.TypeName:T}  
Search Members: WorkOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  
Aggregate Root:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletionDate](Production.ShopFloor.WorkOrderItems.md#completiondate) | datetime __nullable__ | The date, when the item should be completed. NULL means that there is no constraint for completion date`Filter(ge;le)` 
| [CurrentBalanceBase](Production.ShopFloor.WorkOrderItems.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [LineOrd](Production.ShopFloor.WorkOrderItems.md#lineord) | int32 | The order of the line within the work order.`Required` `Filter(eq;like)` 
| [LotSize](Production.ShopFloor.WorkOrderItems.md#lotsize) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity produced in one production run`Unit: ProducedQuantityUnit` `Required` `Default(1)` 
| [Notes](Production.ShopFloor.WorkOrderItems.md#notes) | string (max) __nullable__ | Notes for this WorkOrderItem. 
| [ParentLineId](Production.ShopFloor.WorkOrderItems.md#parentlineid) | guid __nullable__ | If not null contains the Id of the line of the parent document, that created the current row. `Filter(multi eq)` 
| [ParentLineNo](Production.ShopFloor.WorkOrderItems.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. NULL when the current line does not execute another line.`Filter(eq)` 
| [Priority](Production.ShopFloor.WorkOrderItems.md#priority) | [Priority](Production.ShopFloor.WorkOrderItems.md#priority) | Priority of the production of the item. Initially inherits the priority of the work order. 1=Lowest ... 5=Highest`Required` `Default(3)` 
| [ProducedQuantity](Production.ShopFloor.WorkOrderItems.md#producedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity produced in the operation.`Unit: ProducedQuantityUnit` `Required` `Default(1)` 
| [ProducedQuantityBase](Production.ShopFloor.WorkOrderItems.md#producedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Produced Quantity in the base measurement category of the product.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [ProducedStandard<br />QuantityBase](Production.ShopFloor.WorkOrderItems.md#producedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions of the product. Used to measure the execution. NULL means to take the value from Produced Quantity Base.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [ReleaseDate](Production.ShopFloor.WorkOrderItems.md#releasedate) | datetime __nullable__ | The date, when the item is released to production. NULL means that still there is no plan when the item will be released to production`Filter(ge;le)` 
| [ScheduledEndDateTime](Production.ShopFloor.WorkOrderItems.md#scheduledenddatetime) | datetime __nullable__ | Date and time when the production of this item is scheduled to end`Filter(ge;le)` 
| [ScheduledStartDateTime](Production.ShopFloor.WorkOrderItems.md#scheduledstartdatetime) | datetime __nullable__ | Date and time when the production of this item is scheduled to begin`Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Production.ShopFloor.WorkOrderItems.md#document) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The owner document. The Id of the work order, containing the item. `Required` `Filter(multi eq)` |
| [Lot](Production.ShopFloor.WorkOrderItems.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the produced product. |
| [OutputStore](Production.ShopFloor.WorkOrderItems.md#outputstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | Output store for the production |
| [ParentDocument](Production.ShopFloor.WorkOrderItems.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. NULL when the current line does not execute another line. |
| [ProducedQuantityUnit](Production.ShopFloor.WorkOrderItems.md#producedquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the quantity produced in the operation. |
| [Product](Production.ShopFloor.WorkOrderItems.md#product) | [Products](General.Products.Products.md) | The Id of the produced product. |
| [ProductCode](Production.ShopFloor.WorkOrderItems.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product thru some of the product codes. |
| [Recipe](Production.ShopFloor.WorkOrderItems.md#recipe) | [Recipes](Production.Technologies.Recipes.md) (nullable) | The base recipe. NULL means that the item is produced without recipe. |
| [SerialNumber](Production.ShopFloor.WorkOrderItems.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the product. NULL means that the serial number is unknown or not applicable. |
| [StoreBin](Production.ShopFloor.WorkOrderItems.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin in which to store the products |
| [WorkOrder](Production.ShopFloor.WorkOrderItems.md#workorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The Id of the work order, containing the item |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.ShopFloor.WorkOrderItems.md#id) | guid |  
| [ObjectVersion](Production.ShopFloor.WorkOrderItems.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.ShopFloor.WorkOrderItems.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Operations | [WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) | List of `WorkOrderItemOperation`(Production.ShopFloor.WorkOrderItemOperations.md) child objects, based on the `Production.ShopFloor.WorkOrderItemOperation.WorkOrderItem`(Production.ShopFloor.WorkOrderItemOperations.md#workorderitem) back reference 


## Attribute Details

### CompletionDate

The date, when the item should be completed. NULL means that there is no constraint for completion date`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.WorkOrder.CompletionDate`

Front-End Recalc Expressions:  
`obj.WorkOrder.CompletionDate`
### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### LineOrd

The order of the line within the work order.`Required` `Filter(eq;like)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.WorkOrder.Items.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.WorkOrder.Items.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### LotSize

Quantity produced in one production run`Unit: ProducedQuantityUnit` `Required` `Default(1)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`new Quantity( obj.Recipe.ProduceQuantity.Value, obj.ProducedQuantity.Unit)`
### Notes

Notes for this WorkOrderItem.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### ParentLineId

If not null contains the Id of the line of the parent document, that created the current row. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. NULL when the current line does not execute another line.`Filter(eq)`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### Priority

Priority of the production of the item. Initially inherits the priority of the work order. 1=Lowest ... 5=Highest`Required` `Default(3)`

Type: **[Priority](Production.ShopFloor.WorkOrderItems.md#priority)**  
Category: **System**  
Allowed values for the `Priority`(Production.ShopFloor.WorkOrderItems.md#priority) data attribute  
Allowed Values (Production.ShopFloor.WorkOrderItemsRepository.Priority Enum Members)  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'Lowest' |
| Two | Two value. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'Two' |
| Three | Three value. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'Three' |
| Four | Four value. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'Four' |
| Highest | Highest value. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'Highest' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **3**  
Show in UI: **HiddenByDefault**  

### ProducedQuantity

The quantity produced in the operation.`Unit: ProducedQuantityUnit` `Required` `Default(1)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`new Quantity( obj.Recipe.ProduceQuantity.Value, obj.ProducedQuantity.Unit)`
### ProducedQuantityBase

The equivalence of Produced Quantity in the base measurement category of the product.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.ProducedQuantity != null) AndAlso ( obj.ProducedQuantityUnit != null)) AndAlso ( obj.Product != null)), obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.ProducedQuantityBase)`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ProducedQuantity != null) AndAlso ( obj.ProducedQuantityUnit != null)) AndAlso ( obj.Product != null)), obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.ProducedQuantityBase)`
### ProducedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions of the product. Used to measure the execution. NULL means to take the value from Produced Quantity Base.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.ProducedQuantity != null) AndAlso ( obj.ProducedQuantityUnit != null)) AndAlso ( obj.Product != null)), IIF( obj.Product.AllowVariableMeasurementRatios, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.ProducedQuantityBase), obj.ProducedStandardQuantityBase)`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ProducedQuantity != null) AndAlso ( obj.ProducedQuantityUnit != null)) AndAlso ( obj.Product != null)), obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.ProducedStandardQuantityBase)`
### ReleaseDate

The date, when the item is released to production. NULL means that still there is no plan when the item will be released to production`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.WorkOrder.ReleaseDate`

Front-End Recalc Expressions:  
`obj.WorkOrder.ReleaseDate`
### ScheduledEndDateTime

Date and time when the production of this item is scheduled to end`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### ScheduledStartDateTime

Date and time when the production of this item is scheduled to begin`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
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

The owner document. The Id of the work order, containing the item. `Required` `Filter(multi eq)`

Type: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

The lot of the produced product.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( obj.Lot.Product != obj.Product), null, obj.Lot)`

Front-End Recalc Expressions:  
`IIF( ( obj.Lot.Product != obj.Product), null, obj.Lot)`
### OutputStore

Output store for the production

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.WorkOrder.DefaultOutputStore`

Front-End Recalc Expressions:  
`obj.WorkOrder.DefaultOutputStore`
### ParentDocument

The document, which the current line executes. NULL when the current line does not execute another line.

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### ProducedQuantityUnit

The measurement unit of the quantity produced in the operation.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.MeasurementUnit.IfNullThen( obj.ProducedQuantityUnit))`

Front-End Recalc Expressions:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.MeasurementUnit.IfNullThen( obj.ProducedQuantityUnit))`
### Product

The Id of the produced product.

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ProductCode.Product.IfNullThen( obj.Product)`

Front-End Recalc Expressions:  
`obj.ProductCode.Product.IfNullThen( obj.Product)`
### ProductCode

Selects the product thru some of the product codes.

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( obj.ProductCode.Product != obj.Product), null, obj.ProductCode)`

Front-End Recalc Expressions:  
`IIF( ( obj.ProductCode.Product != obj.Product), null, obj.ProductCode)`
### Recipe

The base recipe. NULL means that the item is produced without recipe.

Type: **[Recipes](Production.Technologies.Recipes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Product.GetDefaultRecipe( ( obj.ReleaseDate ?? obj.WorkOrder.DocumentDate), obj.OutputStore.IfNullThen( obj.WorkOrder.DefaultOutputStore))`
### SerialNumber

Serial number of the product. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### StoreBin

The store bin in which to store the products

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### WorkOrder

The Id of the work order, containing the item

Type: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
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

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderItems erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderItems erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_WorkOrderItems

Domain API Entity Type: 
Production_ShopFloor_WorkOrderItem

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_WorkOrderItems?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_WorkOrderItems?$top=10>

