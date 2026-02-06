---
uid: Production.ShopFloor.OutputOrderLines
---
# Production.ShopFloor.OutputOrderLines


Detail records of output orders.

## General
Namespace: [Production.ShopFloor](Production.ShopFloor.md)  
Repository: Production.ShopFloor.OutputOrderLines  
Base Table: Prd_Output_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineOrd}. {OutputOrder.DocumentNo} {OutputOrder.DocumentType.TypeName:T}  
Search Members: OutputOrder.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  
Aggregate Root:  
[Production.ShopFloor.OutputOrders](Production.ShopFloor.OutputOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>BeginDateTime</s>](Production.ShopFloor.OutputOrderLines.md#begindatetime) | datetime __nullable__ | **OBSOLETE! Do not use!** Not used. 
| [CurrentBalanceBase](Production.ShopFloor.OutputOrderLines.md#currentbalancebase) | [Quantity](../data-types.md#quantity) | The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly. 
| [EndTime](Production.ShopFloor.OutputOrderLines.md#endtime) | datetime | Date and time when the operation has ended 
| [Finished](Production.ShopFloor.OutputOrderLines.md#finished) | boolean | 1 if this output entry completes the operation. 0 if there might be more entries 
| [LineOrd](Production.ShopFloor.OutputOrderLines.md#lineord) | int32 | Line number within the order 
| [Notes](Production.ShopFloor.OutputOrderLines.md#notes) | string (max) __nullable__ | Notes for this OutputOrderLine. 
| [ProducedQuantity](Production.ShopFloor.OutputOrderLines.md#producedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | The processed quantity of the end product. 
| [ProducedQuantityBase](Production.ShopFloor.OutputOrderLines.md#producedquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The equivalence of Produced Quantity in the base measurement unit of the product. 
| [ProducedStandard<br />QuantityBase](Production.ShopFloor.OutputOrderLines.md#producedstandardquantitybase) | [Quantity (18, 3)](../data-types.md#quantity) | The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. NULL means to convert the value from Quantity using the measurement ratios. 
| [StartTime](Production.ShopFloor.OutputOrderLines.md#starttime) | datetime | Date and time when the operation has began 
| [TransactionTimestamp](Production.ShopFloor.OutputOrderLines.md#transactiontimestamp) | datetime __nullable__ | Sets the timestamp of the receipt store operations for this output order line. Used in completing output orders. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Production.ShopFloor.OutputOrderLines.md#document) | [OutputOrders](Production.ShopFloor.OutputOrders.md) | The owner document. The <see cref="OutputOrder"/> to which this OutputOrderLine belongs. `Required` `Filter(multi eq)` |
| [LineWorkOrder](Production.ShopFloor.OutputOrderLines.md#lineworkorder) | [WorkOrders](Production.ShopFloor.WorkOrders.md) | The work order for which work is being accounted |
| [Lot](Production.ShopFloor.OutputOrderLines.md#lot) | [Lots](Logistics.Inventory.Lots.md) (nullable) | The lot of the produced product. |
| [OutputOrder](Production.ShopFloor.OutputOrderLines.md#outputorder) | [OutputOrders](Production.ShopFloor.OutputOrders.md) | The <see cref="OutputOrder"/> to which this OutputOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ProducedQuantityUnit](Production.ShopFloor.OutputOrderLines.md#producedquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Produced Quantity. |
| [Product](Production.ShopFloor.OutputOrderLines.md#product) | [Products](General.Products.Products.md) | The actually produced product |
| [ProductCode](Production.ShopFloor.OutputOrderLines.md#productcode) | [ProductCodes](General.Products.ProductCodes.md) (nullable) | Selects the product thru some of the product codes. |
| [SerialNumber](Production.ShopFloor.OutputOrderLines.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | If not NULL, specifies that the product was (has to be) stored with specific serial number |
| [Store](Production.ShopFloor.OutputOrderLines.md#store) | [Stores](Logistics.Inventory.Stores.md) (nullable) | Where to output the produced quantity. Can be NULL only if Produced_Quantity = 0 |
| [StoreBin](Production.ShopFloor.OutputOrderLines.md#storebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | If not NULL, specifies that the product was (has to be) stored to specific store bin |
| [WorkDoneByParty](Production.ShopFloor.OutputOrderLines.md#workdonebyparty) | [Parties](General.Contacts.Parties.md) (nullable) | Indicates who has done the work. Usualy this is an employee, but also can be an outside person or company |
| [WorkgroupResource](Production.ShopFloor.OutputOrderLines.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) (nullable) | The actual resource used in the production |
| [WorkOrderItem](Production.ShopFloor.OutputOrderLines.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) | The work order item for which this output is recorded. |
| [WorkOrderItemOperation](Production.ShopFloor.OutputOrderLines.md#workorderitemoperation) | [WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) (nullable) | The operation for which this output is recorded. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.ShopFloor.OutputOrderLines.md#id) | guid |  
| [ObjectVersion](Production.ShopFloor.OutputOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.ShopFloor.OutputOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| OutputOrderDistributed<br />MaterialConsumptions | [OutputOrderDistributedMaterialConsumptions](Production.ShopFloor.OutputOrderDistributedMaterialConsumptions.md) | List of `OutputOrderDistributed<br />MaterialConsumption`(Production.ShopFloor.OutputOrderDistributed<br />MaterialConsumptions.md) child objects, based on the `Production.ShopFloor.OutputOrderDistributed<br />MaterialConsumption.OutputOrderLine`(Production.ShopFloor.OutputOrderDistributed<br />MaterialConsumptions.md#outputorderline) back reference 


## Attribute Details

### BeginDateTime

**OBSOLETE! Do not use!** Not used.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### CurrentBalanceBase

The current balance of the product in the selected store and enterprise company. If lot, serial number or product variant are specified the quantity is calculated accordingly.

Type: **[Quantity](../data-types.md#quantity)**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### EndTime

Date and time when the operation has ended

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **HiddenByDefault**  

### Finished

1 if this output entry completes the operation. 0 if there might be more entries

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **HiddenByDefault**  

### LineOrd

Line number within the order

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.OutputOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.OutputOrder.Lines.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this OutputOrderLine.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **HiddenByDefault**  

### ProducedQuantity

The processed quantity of the end product.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ProducedQuantityBase

The equivalence of Produced Quantity in the base measurement unit of the product.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.ProducedQuantity == null) OrElse ( obj.ProducedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ProducedQuantityBase, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ProducedQuantity == null) OrElse ( obj.ProducedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ProducedQuantityBase, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### ProducedStandardQuantityBase

The theoretical quantity in base measurement unit according to the current measurement dimensions for the product. Used to measure the execution. NULL means to convert the value from Quantity using the measurement ratios.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`IIF( ( ( ( obj.ProducedQuantity == null) OrElse ( obj.ProducedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ProducedStandardQuantityBase, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`

Front-End Recalc Expressions:  
`IIF( ( ( ( obj.ProducedQuantity == null) OrElse ( obj.ProducedQuantityUnit == null)) OrElse ( obj.Product == null)), obj.ProducedStandardQuantityBase, obj.ProducedQuantity.ConvertTo( obj.Product.BaseUnit, obj.Product))`
### StartTime

Date and time when the operation has began

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **HiddenByDefault**  

### TransactionTimestamp

Sets the timestamp of the receipt store operations for this output order line. Used in completing output orders.

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

The owner document. The <see cref="OutputOrder"/> to which this OutputOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[OutputOrders](Production.ShopFloor.OutputOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LineWorkOrder

The work order for which work is being accounted

Type: **[WorkOrders](Production.ShopFloor.WorkOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Back-End Default Expression:  
`obj.OutputOrder.WorkOrder`

Front-End Recalc Expressions:  
`obj.OutputOrder.WorkOrder`
### Lot

The lot of the produced product.

Type: **[Lots](Logistics.Inventory.Lots.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### OutputOrder

The <see cref="OutputOrder"/> to which this OutputOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[OutputOrders](Production.ShopFloor.OutputOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ProducedQuantityUnit

The measurement unit of Produced Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.ProductCode != null) AndAlso ( obj.ProductCode.CodingSystem.DefaultMeasurementUnit != null)), obj.ProductCode.CodingSystem.DefaultMeasurementUnit, obj.Product.MeasurementUnit)`
### Product

The actually produced product

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.ProductCode.Product`
### ProductCode

Selects the product thru some of the product codes.

Type: **[ProductCodes](General.Products.ProductCodes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ProductCode.Product != obj.Product), null, obj.ProductCode)`
### SerialNumber

If not NULL, specifies that the product was (has to be) stored with specific serial number

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### Store

Where to output the produced quantity. Can be NULL only if Produced_Quantity = 0

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### StoreBin

If not NULL, specifies that the product was (has to be) stored to specific store bin

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### WorkDoneByParty

Indicates who has done the work. Usualy this is an employee, but also can be an outside person or company

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### WorkgroupResource

The actual resource used in the production

Type: **[WorkgroupResources](Production.Resources.WorkgroupResources.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

Front-End Recalc Expressions:  
`obj.WorkOrderItemOperation.WorkgroupResource`
### WorkOrderItem

The work order item for which this output is recorded.

Type: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### WorkOrderItemOperation

The operation for which this output is recorded.

Type: **[WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  


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

