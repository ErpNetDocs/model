---
uid: Production.ShopFloor.WorkOrderItemIngredients
---
# Production.ShopFloor.WorkOrderItemIngredients


The materials consumed in the production order operations

## General
Namespace: [Production.ShopFloor](Production.ShopFloor.md)  
Repository: Production.ShopFloor.WorkOrderItemIngredients  
Base Table: Prd_Work_Order_Item_Ingredients  
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
| [DistributeBy](Production.ShopFloor.WorkOrderItemIngredients.md#distributeby) | [DistributeBy](Production.ShopFloor.WorkOrderItemIngredients.md#distributeby) __nullable__ | Distribution method in case the materials from the line are distributed amongst all work order items. Should be specified if and only if 'Work order item' isn't specified. 
| [FixedScrapQuantity](Production.ShopFloor.WorkOrderItemIngredients.md#fixedscrapquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity of the material, which will be used for setup.`Unit: UsedQuantityUnit` `Required` `Default(0)` 
| [LineOrd](Production.ShopFloor.WorkOrderItemIngredients.md#lineord) | int32 | The order of the line within the item.`Required` `Filter(eq;like)` 
| [Notes](Production.ShopFloor.WorkOrderItemIngredients.md#notes) | string (254) __nullable__ | Notes for this WorkOrderItemIngredient. 
| [UsedQuantity](Production.ShopFloor.WorkOrderItemIngredients.md#usedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity of the material consumed in the operation.`Unit: UsedQuantityUnit` `Required` `Default(1)` 
| [UsedQuantityBase](Production.ShopFloor.WorkOrderItemIngredients.md#usedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Used Quantity in the base measurement category of the material.`Unit: Material.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [UsedStandardQuantityBase](Production.ShopFloor.WorkOrderItemIngredients.md#usedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions of the product. Used to measure the execution. NULL means to take the value from Used Quantity Base.`Unit: Material.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DistributeByMeasurement<br />Category](Production.ShopFloor.WorkOrderItemIngredients.md#distributebymeasurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) (nullable) | Measurement category by which the materials from the line are distributed amongst all work order items in case 'Distribute by' determines that the distribution is made by measurement. |
| [Document](Production.ShopFloor.WorkOrderItemIngredients.md#document) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The owner document. The <see cref="WorkOrder"/> to which this WorkOrderItemIngredient belongs. `Required` `Filter(multi eq)` |
| [Lot](Production.ShopFloor.WorkOrderItemIngredients.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Lot from which to get the material. If not specified (default) - Any lot can be used. |
| [Material](Production.ShopFloor.WorkOrderItemIngredients.md#material) | [Products](General.Products.Products.md) | The Id of the consumed material (Gen_Products_Table) |
| [Operation](Production.ShopFloor.WorkOrderItemIngredients.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | Specifies for which operation this ingredient is used. |
| [PrincipalRecipeIngredient](Production.ShopFloor.WorkOrderItemIngredients.md#principalrecipeingredient) | [PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) (nullable) | The principal recipe ingredient on which this record is based. |
| [ProductCode](Production.ShopFloor.WorkOrderItemIngredients.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product thru some of the product codes. |
| [SerialNumber](Production.ShopFloor.WorkOrderItemIngredients.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number of the ingredient. NULL means that the serial number is unknown or not applicable. |
| [Store](Production.ShopFloor.WorkOrderItemIngredients.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store from which to retrieve the material. |
| [StoreBin](Production.ShopFloor.WorkOrderItemIngredients.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin from which to take the ingredients |
| [UsedQuantityUnit](Production.ShopFloor.WorkOrderItemIngredients.md#usedquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the quantity of the material consumed in the operation. |
| [WorkOrder](Production.ShopFloor.WorkOrderItemIngredients.md#workorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The <see cref="WorkOrder"/> to which this WorkOrderItemIngredient belongs. `Required` `Filter(multi eq)` `Owner` |
| [WorkOrderItem](Production.ShopFloor.WorkOrderItemIngredients.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) (nullable) | The work order item for which the materials in this line are used. If not specified means that the materials are distributed amongst all work order items in the document. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.ShopFloor.WorkOrderItemIngredients.md#id) | guid | The Id of the production order operation 
| [ObjectVersion](Production.ShopFloor.WorkOrderItemIngredients.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.ShopFloor.WorkOrderItemIngredients.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DistributeBy

Distribution method in case the materials from the line are distributed amongst all work order items. Should be specified if and only if 'Work order item' isn't specified.

Type: **[DistributeBy](Production.ShopFloor.WorkOrderItemIngredients.md#distributeby) __nullable__**  
Category: **System**  
Allowed values for the `DistributeBy`(Production.ShopFloor.WorkOrderItemIngredients.md#distributeby) data attribute  
Allowed Values (Production.ShopFloor.WorkOrderItemIngredientsRepository.DistributeBy Enum Members)  

| Value | Description |
| ---- | --- |
| StandardPrice | StandardPrice value. Stored as 'SP'. <br /> Database Value: 'SP' <br /> Model Value: 0 <br /> Domain API Value: 'StandardPrice' |
| Measurement | Measurement value. Stored as 'MC'. <br /> Database Value: 'MC' <br /> Model Value: 1 <br /> Domain API Value: 'Measurement' |
| StandardCost | StandardCost value. Stored as 'SC'. <br /> Database Value: 'SC' <br /> Model Value: 2 <br /> Domain API Value: 'StandardCost' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.WorkOrderItem != null), null, obj.DistributeBy)`
### FixedScrapQuantity

The quantity of the material, which will be used for setup.`Unit: UsedQuantityUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### LineOrd

The order of the line within the item.`Required` `Filter(eq;like)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.WorkOrder.ItemIngredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.WorkOrder.ItemIngredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this WorkOrderItemIngredient.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

### UsedQuantity

The quantity of the material consumed in the operation.`Unit: UsedQuantityUnit` `Required` `Default(1)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### UsedQuantityBase

The equivalence of Used Quantity in the base measurement category of the material.`Unit: Material.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.Material != null) AndAlso ( obj.UsedQuantity != null)) AndAlso ( obj.UsedQuantityUnit != null)), obj.UsedQuantity.ConvertTo( obj.Material.BaseUnit, obj.Material), obj.UsedQuantityBase)`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.Material != null) AndAlso ( obj.UsedQuantity != null)) AndAlso ( obj.UsedQuantityUnit != null)), obj.UsedQuantity.ConvertTo( obj.Material.BaseUnit, obj.Material), obj.UsedQuantityBase)`
### UsedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions of the product. Used to measure the execution. NULL means to take the value from Used Quantity Base.`Unit: Material.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.UsedQuantity != null) AndAlso ( obj.UsedQuantityUnit != null)) AndAlso ( obj.Material != null)), IIF( obj.Material.AllowVariableMeasurementRatios, obj.UsedQuantity.ConvertTo( obj.Material.BaseUnit, obj.Material), obj.UsedQuantityBase), obj.UsedStandardQuantityBase)`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.UsedQuantity != null) AndAlso ( obj.UsedQuantityUnit != null)) AndAlso ( obj.Material != null)), obj.UsedQuantity.ConvertTo( obj.Material.BaseUnit, obj.Material), obj.UsedStandardQuantityBase)`
### Id

The Id of the production order operation

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

### DistributeByMeasurementCategory

Measurement category by which the materials from the line are distributed amongst all work order items in case 'Distribute by' determines that the distribution is made by measurement.

Type: **[MeasurementCategories](General.Products.MeasurementCategories.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.DistributeBy == null) OrElse ( Convert( obj.DistributeBy.Value, Int32) != 1)), null, obj.DistributeByMeasurementCategory)`
### Document

The owner document. The <see cref="WorkOrder"/> to which this WorkOrderItemIngredient belongs. `Required` `Filter(multi eq)`

Type: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Lot

Lot from which to get the material. If not specified (default) - Any lot can be used.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Material

The Id of the consumed material (Gen_Products_Table)

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ProductCode.Product.IfNullThen( obj.Material)`

Front-End Recalc Expressions:  
`obj.ProductCode.Product.IfNullThen( obj.Material)`
### Operation

Specifies for which operation this ingredient is used.

Type: **[Operations](Production.Resources.Operations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PrincipalRecipeIngredient

The principal recipe ingredient on which this record is based.

Type: **[PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductCode

Selects the product thru some of the product codes.

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ProductCode.Product != obj.Material), null, obj.ProductCode)`
### SerialNumber

Serial number of the ingredient. NULL means that the serial number is unknown or not applicable.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Store

The store from which to retrieve the material.

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.WorkOrder.DefaultMaterialsStore`

Front-End Recalc Expressions:  
`obj.WorkOrder.DefaultMaterialsStore`
### StoreBin

The store bin from which to take the ingredients

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### UsedQuantityUnit

The measurement unit of the quantity of the material consumed in the operation.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Material.MeasurementUnit.IfNullThen( obj.UsedQuantityUnit))`

Front-End Recalc Expressions:  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Material.MeasurementUnit.IfNullThen( obj.UsedQuantityUnit))`
### WorkOrder

The <see cref="WorkOrder"/> to which this WorkOrderItemIngredient belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### WorkOrderItem

The work order item for which the materials in this line are used. If not specified means that the materials are distributed amongst all work order items in the document.

Type: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.DistributeBy != null), null, obj.WorkOrderItem)`

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

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderItemIngredients erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderItemIngredients erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_WorkOrderItemIngredients

Domain API Entity Type: 
Production_ShopFloor_WorkOrderItemIngredient

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_WorkOrderItemIngredients?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_WorkOrderItemIngredients?$top=10>

