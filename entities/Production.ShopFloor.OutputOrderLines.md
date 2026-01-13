---
uid: Production.ShopFloor.OutputOrderLines
---
# Production.ShopFloor.OutputOrderLines Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

Detail records of output orders. Entity: Prd_Output_Order_Lines

## Default Visualization
Default Display Text Format:  
_{LineOrd}. {OutputOrder.DocumentNo} {OutputOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_OutputOrder.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  
Aggregate Root:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>BeginDateTime</s>](Production.ShopFloor.OutputOrderLines.md#begindatetime) | datetime __nullable__ | **OBSOLETE! Do not use!** Not used. `Obsolete` `Filter(ge;le)` `Obsoleted in version 22.1.6.61` 
| [CurrentBalanceBase](Production.ShopFloor.OutputOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [DisplayText](Production.ShopFloor.OutputOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EndTime](Production.ShopFloor.OutputOrderLines.md#endtime) | datetime | Date and time when the operation has ended. `Required` `Default(Now)` `Filter(ge;le)` 
| [Finished](Production.ShopFloor.OutputOrderLines.md#finished) | boolean | True if this output entry completes the operation. false if there might be more entries. `Required` `Default(false)` `Filter(eq)` 
| [Id](Production.ShopFloor.OutputOrderLines.md#id) | guid |  
| [LineOrd](Production.ShopFloor.OutputOrderLines.md#lineord) | int32 | Line number within the order. `Required` 
| [Notes](Production.ShopFloor.OutputOrderLines.md#notes) | string (max) __nullable__ | Notes for this OutputOrderLine. 
| [ObjectVersion](Production.ShopFloor.OutputOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProducedQuantity](Production.ShopFloor.OutputOrderLines.md#producedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The processed quantity of the end product. `Unit: ProducedQuantityUnit` `Required` `Default(0)` `Filter(ge;le)` 
| [ProducedQuantityBase](Production.ShopFloor.OutputOrderLines.md#producedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Produced Quantity in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly` 
| [ProducedStandard<br />QuantityBase](Production.ShopFloor.OutputOrderLines.md#producedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. null means to convert the value from Quantity using the measurement ratios. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2` 
| [StartTime](Production.ShopFloor.OutputOrderLines.md#starttime) | datetime | Date and time when the operation has began. `Required` `Default(Now)` `Filter(ge;le)` 
| [TransactionTimestamp](Production.ShopFloor.OutputOrderLines.md#transactiontimestamp) | datetime __nullable__ | Sets the timestamp of the receipt store operations for this output order line. Used in completing output orders. `Filter(ge;le)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Production.ShopFloor.OutputOrderLines.md#document) | [OutputOrders](Production.ShopFloor.OutputOrders.md) | The owner document. The <see cref="OutputOrder"/> to which this OutputOrderLine belongs. `Required` `Filter(multi eq)` |
| [LineWorkOrder](Production.ShopFloor.OutputOrderLines.md#lineworkorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The work order for which work is being accounted. `Required` `Filter(multi eq)` |
| [Lot](Production.ShopFloor.OutputOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the produced product. `Filter(multi eq)` |
| [OutputOrder](Production.ShopFloor.OutputOrderLines.md#outputorder) | [OutputOrders](Production.ShopFloor.OutputOrders.md) | The <see cref="OutputOrder"/> to which this OutputOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ProducedQuantityUnit](Production.ShopFloor.OutputOrderLines.md#producedquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Produced Quantity. `Required` `Filter(multi eq)` |
| [Product](Production.ShopFloor.OutputOrderLines.md#product) | [Products](General.Products.Products.md) | The actually produced product. `Required` `Filter(multi eq)` |
| [ProductCode](Production.ShopFloor.OutputOrderLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product thru some of the product codes. `Filter(multi eq)` |
| [SerialNumber](Production.ShopFloor.OutputOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | If not null, specifies that the product was (has to be) stored with specific serial number. `Filter(multi eq)` |
| [Store](Production.ShopFloor.OutputOrderLines.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | Where to output the produced quantity. Can be null only if Produced_Quantity = 0. `Filter(multi eq)` |
| [StoreBin](Production.ShopFloor.OutputOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | If not null, specifies that the product was (has to be) stored to specific store bin. `Filter(multi eq)` |
| [WorkDoneByParty](Production.ShopFloor.OutputOrderLines.md#workdonebyparty) | [Parties](General.Contacts.Parties.md) (nullable) | The party (usually employee worker) who has accomplished the work. null if unknown or N/A. `Filter(multi eq)` |
| [WorkgroupResource](Production.ShopFloor.OutputOrderLines.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) (nullable) | The resource, which was used to perform the operation. `Filter(multi eq)` |
| [WorkOrderItem](Production.ShopFloor.OutputOrderLines.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) | The work order item for which this output is recorded. `Required` `Filter(multi eq)` |
| [WorkOrderItemOperation](Production.ShopFloor.OutputOrderLines.md#workorderitemoperation) | [WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) (nullable) | The operation for which this output is recorded. `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| OutputOrderDistributed<br />MaterialConsumptions | [OutputOrderDistributedMaterialConsumptions](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md) | List of `OutputOrderDistributed<br />MaterialConsumption`(Production.ShopFloor.OutputOrderDistributed<br />MaterialConsumptions.md) child objects, based on the `Production.ShopFloor.OutputOrderDistributed<br />MaterialConsumption.OutputOrderLine`(Production.ShopFloor.OutputOrderDistributed<br />MaterialConsumptions.md#outputorderline) back reference 


## Attribute Details

### BeginDateTime

**OBSOLETE! Do not use!** Not used. `Obsolete` `Filter(ge;le)` `Obsoleted in version 22.1.6.61`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **CannotBeShown**  

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

### EndTime

Date and time when the operation has ended. `Required` `Default(Now)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **HiddenByDefault**  

### Finished

True if this output entry completes the operation. false if there might be more entries. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineOrd

Line number within the order. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.OutputOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.OutputOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this OutputOrderLine.

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

### ProducedQuantity

The processed quantity of the end product. `Unit: ProducedQuantityUnit` `Required` `Default(0)` `Filter(ge;le)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ProducedQuantityBase

The equivalence of Produced Quantity in the base measurement unit of the product. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` `ReadOnly`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ProducedQuantity == null) OrElse ( obj.ProducedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ProducedQuantityBase, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ProducedQuantity == null) OrElse ( obj.ProducedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ProducedQuantityBase, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ProducedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. null means to convert the value from Quantity using the measurement ratios. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `ReadOnly` `Introduced in version 18.2`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`IIF( ( ( ( obj.ProducedQuantity == null) OrElse ( obj.ProducedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ProducedStandardQuantityBase, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

_Front-End Recalc Expressions:_  
`IIF( ( ( ( obj.ProducedQuantity == null) OrElse ( obj.ProducedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ProducedStandardQuantityBase, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StartTime

Date and time when the operation has began. `Required` `Default(Now)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **HiddenByDefault**  

### TransactionTimestamp

Sets the timestamp of the receipt store operations for this output order line. Used in completing output orders. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Document

The owner document. The <see cref="OutputOrder"/> to which this OutputOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[OutputOrders](Production.ShopFloor.OutputOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LineWorkOrder

The work order for which work is being accounted. `Required` `Filter(multi eq)`

_Type_: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Back-End Default Expression:_  
`obj.OutputOrder.WorkOrder`

_Front-End Recalc Expressions:_  
`obj.OutputOrder.WorkOrder`
### Lot

The lot of the produced product. `Filter(multi eq)`

_Type_: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### OutputOrder

The <see cref="OutputOrder"/> to which this OutputOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[OutputOrders](Production.ShopFloor.OutputOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ProducedQuantityUnit

The measurement unit of Produced Quantity. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.ProductCode != null) AndAlso ( obj.ProductCode.CodingSystem.DefaultMeasurementUnit != null)), obj.ProductCode.CodingSystem.DefaultMeasurementUnit, obj.Product.MeasurementUnit)`
### Product

The actually produced product. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.ProductCode.Product`
### ProductCode

Selects the product thru some of the product codes. `Filter(multi eq)`

_Type_: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( obj.ProductCode.Product != obj.Product), null, obj.ProductCode)`
### SerialNumber

If not null, specifies that the product was (has to be) stored with specific serial number. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### Store

Where to output the produced quantity. Can be null only if Produced_Quantity = 0. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### StoreBin

If not null, specifies that the product was (has to be) stored to specific store bin. `Filter(multi eq)`

_Type_: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### WorkDoneByParty

The party (usually employee worker) who has accomplished the work. null if unknown or N/A. `Filter(multi eq)`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### WorkgroupResource

The resource, which was used to perform the operation. `Filter(multi eq)`

_Type_: **[WorkgroupResources](Production.Resources.WorkgroupResources.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

_Front-End Recalc Expressions:_  
`obj.WorkOrderItemOperation.WorkgroupResource`
### WorkOrderItem

The work order item for which this output is recorded. `Required` `Filter(multi eq)`

_Type_: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### WorkOrderItemOperation

The operation for which this output is recorded. `Filter(multi eq)`

_Type_: **[WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) (nullable)**  
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

[!list limit=1000 erp.entity=Production.ShopFloor.OutputOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.OutputOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_OutputOrderLines

Domain API Entity Type: 
Production_ShopFloor_OutputOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_OutputOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_OutputOrderLines?$top=10>

