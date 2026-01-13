---
uid: Production.ShopFloor.WorkOrderItemIngredients
---
# Production.ShopFloor.WorkOrderItemIngredients Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

The materials consumed in the production order operations. Entity: Prd_Work_Order_Item_Ingredients

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
| [DisplayText](Production.ShopFloor.WorkOrderItemIngredients.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [DistributeBy](Production.ShopFloor.WorkOrderItemIngredients.md#distributeby) | [DistributeBy](Production.ShopFloor.WorkOrderItemIngredients.md#distributeby) __nullable__ | Distribution method in case the materials from the line are distributed amongst all work order items. Should be NOT null iif Work_Order_Item_Id is null. MC=Measurement, SP=Standard_Price. 
| [FixedScrapQuantity](Production.ShopFloor.WorkOrderItemIngredients.md#fixedscrapquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity of the material, which will be used for setup. `Unit: UsedQuantityUnit` `Required` `Default(0)` 
| [Id](Production.ShopFloor.WorkOrderItemIngredients.md#id) | guid |  
| [LineOrd](Production.ShopFloor.WorkOrderItemIngredients.md#lineord) | int32 | The order of the line within the item. `Required` `Filter(eq;like)` 
| [Notes](Production.ShopFloor.WorkOrderItemIngredients.md#notes) | string (254) __nullable__ | Notes for this WorkOrderItemIngredient. 
| [ObjectVersion](Production.ShopFloor.WorkOrderItemIngredients.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [UsedQuantity](Production.ShopFloor.WorkOrderItemIngredients.md#usedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity of the material consumed in the operation. `Unit: UsedQuantityUnit` `Required` `Default(1)` 
| [UsedQuantityBase](Production.ShopFloor.WorkOrderItemIngredients.md#usedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Used Quantity in the base measurement category of the material. `Unit: Material.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` 
| [UsedStandardQuantityBase](Production.ShopFloor.WorkOrderItemIngredients.md#usedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions of the product. Used to measure the execution. null means to take the value from Used Quantity Base. `Unit: Material.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DistributeByMeasurement<br />Category](Production.ShopFloor.WorkOrderItemIngredients.md#distributebymeasurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) (nullable) | Measurement category by which the materials from the line are distributed amongst all work order items in case Distribute_By = MC. Should be NOT null iif Distribute_By = MC. `Filter(multi eq)` |
| [Document](Production.ShopFloor.WorkOrderItemIngredients.md#document) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The owner document. The <see cref="WorkOrder"/> to which this WorkOrderItemIngredient belongs. `Required` `Filter(multi eq)` |
| [Lot](Production.ShopFloor.WorkOrderItemIngredients.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | Lot from which to get the material. When null, any lot can be used. `Filter(multi eq)` |
| [Material](Production.ShopFloor.WorkOrderItemIngredients.md#material) | [Products](General.Products.Products.md) | The Id of the consumed material (Gen_Products_Table). `Required` `Filter(multi eq)` |
| [Operation](Production.ShopFloor.WorkOrderItemIngredients.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | Specifies for which operation this ingredient is used. `Filter(multi eq)` |
| [PrincipalRecipeIngredient](Production.ShopFloor.WorkOrderItemIngredients.md#principalrecipeingredient) | [PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) (nullable) | The principal recipe ingredient on which this record is based. `Filter(multi eq)` |
| [ProductCode](Production.ShopFloor.WorkOrderItemIngredients.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product thru some of the product codes. `Filter(multi eq)` |
| [SerialNumber](Production.ShopFloor.WorkOrderItemIngredients.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | If not null, specifies the serial number of the ingredient. `Filter(multi eq)` |
| [Store](Production.ShopFloor.WorkOrderItemIngredients.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | The store from which to retrieve the material. `Filter(multi eq)` |
| [StoreBin](Production.ShopFloor.WorkOrderItemIngredients.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | The store bin from which to take the ingredients. `Filter(multi eq)` |
| [UsedQuantityUnit](Production.ShopFloor.WorkOrderItemIngredients.md#usedquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of the quantity of the material consumed in the operation. `Required` `Filter(multi eq)` |
| [WorkOrder](Production.ShopFloor.WorkOrderItemIngredients.md#workorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The <see cref="WorkOrder"/> to which this WorkOrderItemIngredient belongs. `Required` `Filter(multi eq)` `Owner` |
| [WorkOrderItem](Production.ShopFloor.WorkOrderItemIngredients.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) (nullable) | The work order item for which the materials in this line are used. If null means that the materials are distributed amongst all work order items in the document. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### DistributeBy

Distribution method in case the materials from the line are distributed amongst all work order items. Should be NOT null iif Work_Order_Item_Id is null. MC=Measurement, SP=Standard_Price.

_Type_: **[DistributeBy](Production.ShopFloor.WorkOrderItemIngredients.md#distributeby) __nullable__**  
_Category_: **System**  
Allowed values for the `DistributeBy`(Production.ShopFloor.WorkOrderItemIngredients.md#distributeby) data attribute  
_Allowed Values (Production.ShopFloor.WorkOrderItemIngredientsRepository.DistributeBy Enum Members)_  

| Value | Description |
| ---- | --- |
| StandardPrice | StandardPrice value. Stored as 'SP'. <br /> _Database Value:_ 'SP' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'StandardPrice' |
| Measurement | Measurement value. Stored as 'MC'. <br /> _Database Value:_ 'MC' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Measurement' |
| StandardCost | StandardCost value. Stored as 'SC'. <br /> _Database Value:_ 'SC' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'StandardCost' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.WorkOrderItem != null), null, obj.DistributeBy)`
### FixedScrapQuantity

The quantity of the material, which will be used for setup. `Unit: UsedQuantityUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineOrd

The order of the line within the item. `Required` `Filter(eq;like)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.WorkOrder.ItemIngredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.WorkOrder.ItemIngredients.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this WorkOrderItemIngredient.

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

### UsedQuantity

The quantity of the material consumed in the operation. `Unit: UsedQuantityUnit` `Required` `Default(1)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### UsedQuantityBase

The equivalence of Used Quantity in the base measurement category of the material. `Unit: Material.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.Material != null) AndAlso ( obj.UsedQuantity != null)) AndAlso ( obj.UsedQuantityUnit != null)), obj.UsedQuantity.ConvertTo( obj.Material.BaseUnit, obj.Material), obj.UsedQuantityBase)`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.Material != null) AndAlso ( obj.UsedQuantity != null)) AndAlso ( obj.UsedQuantityUnit != null)), obj.UsedQuantity.ConvertTo( obj.Material.BaseUnit, obj.Material), obj.UsedQuantityBase)`
### UsedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions of the product. Used to measure the execution. null means to take the value from Used Quantity Base. `Unit: Material.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.UsedQuantity != null) AndAlso ( obj.UsedQuantityUnit != null)) AndAlso ( obj.Material != null)), IIF( obj.Material.AllowVariableMeasurementRatios, obj.UsedQuantity.ConvertTo( obj.Material.BaseUnit, obj.Material), obj.UsedQuantityBase), obj.UsedStandardQuantityBase)`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.UsedQuantity != null) AndAlso ( obj.UsedQuantityUnit != null)) AndAlso ( obj.Material != null)), obj.UsedQuantity.ConvertTo( obj.Material.BaseUnit, obj.Material), obj.UsedStandardQuantityBase)`

## Reference Details

### DistributeByMeasurementCategory

Measurement category by which the materials from the line are distributed amongst all work order items in case Distribute_By = MC. Should be NOT null iif Distribute_By = MC. `Filter(multi eq)`

_Type_: **[MeasurementCategories](General.Products.MeasurementCategories.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.DistributeBy == null) OrElse ( Convert( obj.DistributeBy.Value, Int32) != 1)), null, obj.DistributeByMeasurementCategory)`
### Document

The owner document. The <see cref="WorkOrder"/> to which this WorkOrderItemIngredient belongs. `Required` `Filter(multi eq)`

_Type_: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Lot

Lot from which to get the material. When null, any lot can be used. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Material

The Id of the consumed material (Gen_Products_Table). `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ProductCode.Product.IfNullThen( obj.Material)`

_Front-End Recalc Expressions:_  
`obj.ProductCode.Product.IfNullThen( obj.Material)`
### Operation

Specifies for which operation this ingredient is used. `Filter(multi eq)`

_Type_: **[Operations](Production.Resources.Operations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PrincipalRecipeIngredient

The principal recipe ingredient on which this record is based. `Filter(multi eq)`

_Type_: **[PrincipalRecipeIngredients](Production.Technologies.PrincipalRecipeIngredients.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductCode

Selects the product thru some of the product codes. `Filter(multi eq)`

_Type_: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.ProductCode.Product != obj.Material), null, obj.ProductCode)`
### SerialNumber

If not null, specifies the serial number of the ingredient. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Store

The store from which to retrieve the material. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.WorkOrder.DefaultMaterialsStore`

_Front-End Recalc Expressions:_  
`obj.WorkOrder.DefaultMaterialsStore`
### StoreBin

The store bin from which to take the ingredients. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### UsedQuantityUnit

The measurement unit of the quantity of the material consumed in the operation. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Material.MeasurementUnit.IfNullThen( obj.UsedQuantityUnit))`

_Front-End Recalc Expressions:_  
`obj.ProductCode.CodingSystem.DefaultMeasurementUnit.IfNullThen( obj.Material.MeasurementUnit.IfNullThen( obj.UsedQuantityUnit))`
### WorkOrder

The <see cref="WorkOrder"/> to which this WorkOrderItemIngredient belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### WorkOrderItem

The work order item for which the materials in this line are used. If null means that the materials are distributed amongst all work order items in the document. `Filter(multi eq)`

_Type_: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.DistributeBy != null), null, obj.WorkOrderItem)`

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

