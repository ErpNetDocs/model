---
uid: Production.ShopFloor.WorkOrderItems
---
# Production.ShopFloor.WorkOrderItems Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

The different items that are produced with a work order. Entity: Prd_Work_Order_Items

## Default Visualization
Default Display Text Format:  
_{LineOrd}. {WorkOrder.DocumentNo} {WorkOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_WorkOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  
Aggregate Root:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompletionDate](Production.ShopFloor.WorkOrderItems.md#completiondate) | datetime __nullable__ | The date, when the item should be completed. null means that there is no constraint for completion date. `Filter(ge;le)` 
| [CurrentBalanceBase](Production.ShopFloor.WorkOrderItems.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Production.ShopFloor.WorkOrderItems.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.ShopFloor.WorkOrderItems.md#id) | guid |  
| [LineOrd](Production.ShopFloor.WorkOrderItems.md#lineord) | int32 | The order of the line within the work order. `Required` `Filter(eq;like)` 
| [LotSize](Production.ShopFloor.WorkOrderItems.md#lotsize) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity produced in one production run. `Unit: ProducedQuantityUnit` `Required` `Default(1)` 
| [Notes](Production.ShopFloor.WorkOrderItems.md#notes) | string (max) __nullable__ | Notes for this WorkOrderItem. 
| [ObjectVersion](Production.ShopFloor.WorkOrderItems.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ParentLineId](Production.ShopFloor.WorkOrderItems.md#parentlineid) | guid __nullable__ | If not null contains the Id of the line of the parent document, that created the current row. `Filter(multi eq)` 
| [ParentLineNo](Production.ShopFloor.WorkOrderItems.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Filter(eq)` 
| [Priority](Production.ShopFloor.WorkOrderItems.md#priority) | [Priority](Production.ShopFloor.WorkOrderItems.md#priority) | Priority of the production of the item. Initially inherits the priority of the work order. 1=Lowest ... 5=Highest. `Required` `Default(3)` 
| [ProducedQuantity](Production.ShopFloor.WorkOrderItems.md#producedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity produced in the operation. `Unit: ProducedQuantityUnit` `Required` `Default(1)` 
| [ProducedQuantityBase](Production.ShopFloor.WorkOrderItems.md#producedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Produced Quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [ProducedStandard<br />QuantityBase](Production.ShopFloor.WorkOrderItems.md#producedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions of the product. Used to measure the execution. null means to take the value from Produced Quantity Base. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [ReleaseDate](Production.ShopFloor.WorkOrderItems.md#releasedate) | datetime __nullable__ | The date, when the item is released to production. null means that still there is no plan when the item will be released to production. `Filter(ge;le)` 
| [ScheduledEndDateTime](Production.ShopFloor.WorkOrderItems.md#scheduledenddatetime) | datetime __nullable__ | Date and time when the production of this item is scheduled to end. `Filter(ge;le)` 
| [ScheduledStartDateTime](Production.ShopFloor.WorkOrderItems.md#scheduledstartdatetime) | datetime __nullable__ | Date and time when the production of this item is scheduled to begin. `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Production.ShopFloor.WorkOrderItems.md#document) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The owner document. The Id of the work order, containing the item. `Required` `Filter(multi eq)` |
| [Lot](Production.ShopFloor.WorkOrderItems.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the produced product. `Filter(multi eq)` |
| [OutputStore](Production.ShopFloor.WorkOrderItems.md#outputstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | Output store for the production. `Filter(multi eq)` |
| [ParentDocument](Production.ShopFloor.WorkOrderItems.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` |
| [ProducedQuantityUnit](Production.ShopFloor.WorkOrderItems.md#producedquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the quantity produced in the operation. `Required` `Filter(multi eq)` |
| [Product](Production.ShopFloor.WorkOrderItems.md#product) | [Products](General.Products.Products.md) | The Id of the produced product. `Required` `Filter(multi eq)` |
| [ProductCode](Production.ShopFloor.WorkOrderItems.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product thru some of the product codes. `Filter(multi eq)` |
| [Recipe](Production.ShopFloor.WorkOrderItems.md#recipe) | [Recipes](Production.Technologies.Recipes.md) (nullable) | The base recipe. null means that the item is produced without recipe. `Filter(multi eq)` |
| [SerialNumber](Production.ShopFloor.WorkOrderItems.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | If not null, specifies that the product was (has to be) produced with specific serial number. `Filter(multi eq)` |
| [StoreBin](Production.ShopFloor.WorkOrderItems.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin in which to store the products. `Filter(multi eq)` |
| [WorkOrder](Production.ShopFloor.WorkOrderItems.md#workorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The Id of the work order, containing the item. `Required` `Filter(multi eq)` `Owner` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Operations | [WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) | List of `WorkOrderItemOperation`(Production.ShopFloor.WorkOrderItemOperations.md) child objects, based on the `Production.ShopFloor.WorkOrderItemOperation.WorkOrderItem`(Production.ShopFloor.WorkOrderItemOperations.md#workorderitem) back reference 


## Attribute Details

### CompletionDate

The date, when the item should be completed. null means that there is no constraint for completion date. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.WorkOrder.CompletionDate`

_Front-End Recalc Expressions:_  
`obj.WorkOrder.CompletionDate`
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

The order of the line within the work order. `Required` `Filter(eq;like)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.WorkOrder.Items.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.WorkOrder.Items.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### LotSize

Quantity produced in one production run. `Unit: ProducedQuantityUnit` `Required` `Default(1)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`new Quantity( obj.Recipe.ProduceQuantity.Value, obj.ProducedQuantity.Unit)`
### Notes

Notes for this WorkOrderItem.

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

### ParentLineId

If not null contains the Id of the line of the parent document, that created the current row. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute another line. `Filter(eq)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### Priority

Priority of the production of the item. Initially inherits the priority of the work order. 1=Lowest ... 5=Highest. `Required` `Default(3)`

_Type_: **[Priority](Production.ShopFloor.WorkOrderItems.md#priority)**  
_Category_: **System**  
Allowed values for the `Priority`(Production.ShopFloor.WorkOrderItems.md#priority) data attribute  
_Allowed Values (Production.ShopFloor.WorkOrderItemsRepository.Priority Enum Members)_  

| Value | Description |
| ---- | --- |
| Lowest | Lowest value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Lowest' |
| Two | Two value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Two' |
| Three | Three value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Three' |
| Four | Four value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Four' |
| Highest | Highest value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Highest' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **3**  
_Show in UI_: **HiddenByDefault**  

### ProducedQuantity

The quantity produced in the operation. `Unit: ProducedQuantityUnit` `Required` `Default(1)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`new Quantity( obj.Recipe.ProduceQuantity.Value, obj.ProducedQuantity.Unit)`
### ProducedQuantityBase

The equivalence of Produced Quantity in the base measurement category of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ProducedQuantity != null) AndAlso ( obj.ProducedQuantityUnit != null)) AndAlso ( obj.Product != null)), obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.ProducedQuantityBase)`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ProducedQuantity != null) AndAlso ( obj.ProducedQuantityUnit != null)) AndAlso ( obj.Product != null)), obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.ProducedQuantityBase)`
### ProducedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions of the product. Used to measure the execution. null means to take the value from Produced Quantity Base. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ProducedQuantity != null) AndAlso ( obj.ProducedQuantityUnit != null)) AndAlso ( obj.Product != null)), IIF( obj.Product.AllowVariableMeasurementRatios, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.ProducedQuantityBase), obj.ProducedStandardQuantityBase)`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ProducedQuantity != null) AndAlso ( obj.ProducedQuantityUnit != null)) AndAlso ( obj.Product != null)), obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product), obj.ProducedStandardQuantityBase)`
### ReleaseDate

The date, when the item is released to production. null means that still there is no plan when the item will be released to production. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.WorkOrder.ReleaseDate`

_Front-End Recalc Expressions:_  
`obj.WorkOrder.ReleaseDate`
### ScheduledEndDateTime

Date and time when the production of this item is scheduled to end. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### ScheduledStartDateTime

Date and time when the production of this item is scheduled to begin. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The owner document. The Id of the work order, containing the item. `Required` `Filter(multi eq)`

_Type_: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

The lot of the produced product. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( obj.Lot.Product != obj.Product), null, obj.Lot)`

_Front-End Recalc Expressions:_  
`IIF( ( obj.Lot.Product != obj.Product), null, obj.Lot)`
### OutputStore

Output store for the production. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.WorkOrder.DefaultOutputStore`

_Front-End Recalc Expressions:_  
`obj.WorkOrder.DefaultOutputStore`
### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ProducedQuantityUnit

The measurement unit of the quantity produced in the operation. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.MeasurementUnit.IfNullThen( obj.ProducedQuantityUnit))`

_Front-End Recalc Expressions:_  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Product.MeasurementUnit.IfNullThen( obj.ProducedQuantityUnit))`
### Product

The Id of the produced product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ProductCode.Product.IfNullThen( obj.Product)`

_Front-End Recalc Expressions:_  
`obj.ProductCode.Product.IfNullThen( obj.Product)`
### ProductCode

Selects the product thru some of the product codes. `Filter(multi eq)`

_Type_: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( obj.ProductCode.Product != obj.Product), null, obj.ProductCode)`

_Front-End Recalc Expressions:_  
`IIF( ( obj.ProductCode.Product != obj.Product), null, obj.ProductCode)`
### Recipe

The base recipe. null means that the item is produced without recipe. `Filter(multi eq)`

_Type_: **[Recipes](Production.Technologies.Recipes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.GetDefaultRecipe( ( obj.ReleaseDate ?? obj.WorkOrder.DocumentDate), obj.OutputStore.IfNullThen( obj.WorkOrder.DefaultOutputStore))`
### SerialNumber

If not null, specifies that the product was (has to be) produced with specific serial number. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### StoreBin

The store bin in which to store the products. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### WorkOrder

The Id of the work order, containing the item. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
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

