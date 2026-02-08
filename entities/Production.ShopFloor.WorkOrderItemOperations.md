---
uid: Production.ShopFloor.WorkOrderItemOperations
---
# Production.ShopFloor.WorkOrderItemOperations


The operations that are performed to produce the product

## General
Namespace: [Production.ShopFloor](Production.ShopFloor.md)  
Repository: Production.ShopFloor.WorkOrderItemOperations  
Base Table: Prd_Work_Order_Item_Operations  
API access:  ReadWrite  

## Visualization
Display Format: {WorkOrderItem.WorkOrder.EntityName}  
Search Members: WorkOrderItem.WorkOrder.EntityName  
Name Member: WorkOrderItem.WorkOrder.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)  
Aggregate Root:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActualEndDateTime](Production.ShopFloor.WorkOrderItemOperations.md#actualenddatetime) | datetime __nullable__ | The date/time when the operation has completed. NULL means that the operation is not completed.`Filter(ge;le)` 
| [ActualStartDateTime](Production.ShopFloor.WorkOrderItemOperations.md#actualstartdatetime) | datetime __nullable__ | The date/time when the operation has started. NULL means that the has not started yet`Filter(ge;le)` 
| [LineOrd](Production.ShopFloor.WorkOrderItemOperations.md#lineord) | int32 | Order of the line within the work order routing`Required` `Filter(eq;like)` 
| [MinimumConcurrent<br />StartTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#minimumconcurrentstarttimeminutes) | int32 __nullable__ | How many minutes after the start of this operation can the next operation start. NULL means that the next operation should wait this operation to finish before starting 
| [MoveTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#movetimeminutes) | int32 | Time to move the lot to the next operation in minutes`Required` `Default(0)` 
| [Notes](Production.ShopFloor.WorkOrderItemOperations.md#notes) | string (254) __nullable__ | Notes for this WorkOrderItemOperation. 
| [OperationDescription](Production.ShopFloor.WorkOrderItemOperations.md#operationdescription) | string (max) __nullable__ | The short description of the operation. 
| [RunTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#runtimeminutes) | int32 | Time for production of one lot of the produced item in minutes`Required` `Default(0)` 
| [ScheduledEndDateTime](Production.ShopFloor.WorkOrderItemOperations.md#scheduledenddatetime) | datetime __nullable__ | The date/time when the operation is scheduled to complete. NULL means that there is still no plan when the operation will finish (for new orders only)`Filter(ge;le)` 
| [ScheduledStartDateTime](Production.ShopFloor.WorkOrderItemOperations.md#scheduledstartdatetime) | datetime __nullable__ | The date/time when the operation is planned to start. NULL means that there is still no plan when to start the operaion (only for new work orders)`Filter(ge;le)` 
| [ScrapRate](Production.ShopFloor.WorkOrderItemOperations.md#scraprate) | decimal (7, 6) | Projected scrap rate of the operation`Required` `Default(0)` 
| [SetupTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#setuptimeminutes) | int32 | Time needed to setup the equipment in minutes`Required` `Default(0)` 
| [Tooling](Production.ShopFloor.WorkOrderItemOperations.md#tooling) | string (max) __nullable__ | Description of the instruments that are used fot this operation. 
| [UseQuantity](Production.ShopFloor.WorkOrderItemOperations.md#usequantity) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity of the resource, that should be allocated for the operation`Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)` 
| [WaitTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#waittimeminutes) | int32 | Wait time (drying, cooling, etc.) after the operation in minutes`Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Operation](Production.ShopFloor.WorkOrderItemOperations.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | The performed operation. |
| [WorkgroupResource](Production.ShopFloor.WorkOrderItemOperations.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) | The resource that will be used for the operation. NULL means that no resource will be locked for the operation |
| [WorkOrderItem](Production.ShopFloor.WorkOrderItemOperations.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) | The work order item, containing the line. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.ShopFloor.WorkOrderItemOperations.md#id) | guid |  
| [ObjectVersion](Production.ShopFloor.WorkOrderItemOperations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.ShopFloor.WorkOrderItemOperations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Load | [Load](Production.Resources.Load.md) | List of `Load`(Production.Resources.Load.md) child objects, based on the `Production.Resources.Load.WorkOrderItemOperation`(Production.Resources.Load.md#workorderitemoperation) back reference 


## Attribute Details

### ActualEndDateTime

The date/time when the operation has completed. NULL means that the operation is not completed.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ActualStartDateTime

The date/time when the operation has started. NULL means that the has not started yet`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineOrd

Order of the line within the work order routing`Required` `Filter(eq;like)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.WorkOrderItem.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.WorkOrderItem.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### MinimumConcurrentStartTimeMinutes

How many minutes after the start of this operation can the next operation start. NULL means that the next operation should wait this operation to finish before starting

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MoveTimeMinutes

Time to move the lot to the next operation in minutes`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this WorkOrderItemOperation.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### OperationDescription

The short description of the operation.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Operation.Name`
### RunTimeMinutes

Time for production of one lot of the produced item in minutes`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ScheduledEndDateTime

The date/time when the operation is scheduled to complete. NULL means that there is still no plan when the operation will finish (for new orders only)`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ScheduledStartDateTime

The date/time when the operation is planned to start. NULL means that there is still no plan when to start the operaion (only for new work orders)`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ScrapRate

Projected scrap rate of the operation`Required` `Default(0)`

Type: **decimal (7, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **CannotBeShown**  

### SetupTimeMinutes

Time needed to setup the equipment in minutes`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Tooling

Description of the instruments that are used fot this operation.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### UseQuantity

Quantity of the resource, that should be allocated for the operation`Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)`

Type: **[Quantity (9, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### WaitTimeMinutes

Wait time (drying, cooling, etc.) after the operation in minutes`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

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

### Operation

The performed operation.

Type: **[Operations](Production.Resources.Operations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WorkgroupResource

The resource that will be used for the operation. NULL means that no resource will be locked for the operation

Type: **[WorkgroupResources](Production.Resources.WorkgroupResources.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WorkOrderItem

The work order item, containing the line.

Type: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)**  
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

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderItemOperations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.ShopFloor.WorkOrderItemOperations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_ShopFloor_WorkOrderItemOperations

Domain API Entity Type: 
Production_ShopFloor_WorkOrderItemOperation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_ShopFloor_WorkOrderItemOperations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_ShopFloor_WorkOrderItemOperations?$top=10>

