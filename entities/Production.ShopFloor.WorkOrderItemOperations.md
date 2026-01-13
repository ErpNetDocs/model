---
uid: Production.ShopFloor.WorkOrderItemOperations
---
# Production.ShopFloor.WorkOrderItemOperations Entity

**Namespace:** [Production.ShopFloor](Production.ShopFloor.md)  

The operations that are performed to produce the product. Entity: Prd_Work_Order_Item_Operations

## Default Visualization
Default Display Text Format:  
_{WorkOrderItem.WorkOrder.EntityName}_  
Default Search Members:  
_WorkOrderItem.WorkOrder.EntityName_  
Name Data Member:  
_WorkOrderItem.WorkOrder.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)  
Aggregate Root:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActualEndDateTime](Production.ShopFloor.WorkOrderItemOperations.md#actualenddatetime) | datetime __nullable__ | The date/time when the operation has completed. null means that the operation is not completed. `Filter(ge;le)` 
| [ActualStartDateTime](Production.ShopFloor.WorkOrderItemOperations.md#actualstartdatetime) | datetime __nullable__ | The date/time when the operation has started. null means that the has not started yet. `Filter(ge;le)` 
| [DisplayText](Production.ShopFloor.WorkOrderItemOperations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.ShopFloor.WorkOrderItemOperations.md#id) | guid |  
| [LineOrd](Production.ShopFloor.WorkOrderItemOperations.md#lineord) | int32 | Order of the line within the work order routing. `Required` `Filter(eq;like)` 
| [MinimumConcurrent<br />StartTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#minimumconcurrentstarttimeminutes) | int32 __nullable__ | How many minutes after the start of this operation can the next operation start. null means that the next operation should wait this operation to finish before starting. 
| [MoveTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#movetimeminutes) | int32 | Time to move the lot to the next operation in minutes. `Required` `Default(0)` 
| [Notes](Production.ShopFloor.WorkOrderItemOperations.md#notes) | string (254) __nullable__ | Notes for this WorkOrderItemOperation. 
| [ObjectVersion](Production.ShopFloor.WorkOrderItemOperations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OperationDescription](Production.ShopFloor.WorkOrderItemOperations.md#operationdescription) | string (max) __nullable__ | The short description of the operation. 
| [RunTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#runtimeminutes) | int32 | Time for production of one lot of the produced item in minutes. `Required` `Default(0)` 
| [ScheduledEndDateTime](Production.ShopFloor.WorkOrderItemOperations.md#scheduledenddatetime) | datetime __nullable__ | The date/time when the operation is scheduled to complete. null means that there is still no plan when the operation will finish (for new orders only). `Filter(ge;le)` 
| [ScheduledStartDateTime](Production.ShopFloor.WorkOrderItemOperations.md#scheduledstartdatetime) | datetime __nullable__ | The date/time when the operation is planned to start. null means that there is still no plan when to start the operaion (only for new work orders). `Filter(ge;le)` 
| [ScrapRate](Production.ShopFloor.WorkOrderItemOperations.md#scraprate) | decimal (7, 6) | Projected scrap rate of the operation. `Required` `Default(0)` 
| [SetupTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#setuptimeminutes) | int32 | Time needed to setup the equipment in minutes. `Required` `Default(0)` 
| [Tooling](Production.ShopFloor.WorkOrderItemOperations.md#tooling) | string (max) __nullable__ | The tools needed for the routing step. 
| [UseQuantity](Production.ShopFloor.WorkOrderItemOperations.md#usequantity) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity of the resource, that should be allocated for the operation. `Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)` 
| [WaitTimeMinutes](Production.ShopFloor.WorkOrderItemOperations.md#waittimeminutes) | int32 | Wait time (drying, cooling, etc.) after the operation in minutes. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Operation](Production.ShopFloor.WorkOrderItemOperations.md#operation) | [Operations](Production.Resources.Operations.md) (nullable) | The performed operation. `Filter(multi eq)` |
| [WorkgroupResource](Production.ShopFloor.WorkOrderItemOperations.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) | The resource that will be used for the operation. null means that no resource will be locked for the operation. `Required` `Filter(multi eq)` |
| [WorkOrderItem](Production.ShopFloor.WorkOrderItemOperations.md#workorderitem) | [WorkOrderItems](Production.ShopFloor.WorkOrderItems.md) | The work order item, containing the line. `Required` `Filter(multi eq)` `Owner` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Load | [Load](Production.Resources.Load.md) | List of `Load`(Production.Resources.Load.md) child objects, based on the `Production.Resources.Load.WorkOrderItemOperation`(Production.Resources.Load.md#workorderitemoperation) back reference 


## Attribute Details

### ActualEndDateTime

The date/time when the operation has completed. null means that the operation is not completed. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ActualStartDateTime

The date/time when the operation has started. null means that the has not started yet. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
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
_Show in UI_: **CannotBeShown**  

### LineOrd

Order of the line within the work order routing. `Required` `Filter(eq;like)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.WorkOrderItem.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.WorkOrderItem.Operations.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 10)`
### MinimumConcurrentStartTimeMinutes

How many minutes after the start of this operation can the next operation start. null means that the next operation should wait this operation to finish before starting.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MoveTimeMinutes

Time to move the lot to the next operation in minutes. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this WorkOrderItemOperation.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OperationDescription

The short description of the operation.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Operation.Name`
### RunTimeMinutes

Time for production of one lot of the produced item in minutes. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### ScheduledEndDateTime

The date/time when the operation is scheduled to complete. null means that there is still no plan when the operation will finish (for new orders only). `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ScheduledStartDateTime

The date/time when the operation is planned to start. null means that there is still no plan when to start the operaion (only for new work orders). `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ScrapRate

Projected scrap rate of the operation. `Required` `Default(0)`

_Type_: **decimal (7, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **CannotBeShown**  

### SetupTimeMinutes

Time needed to setup the equipment in minutes. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### Tooling

The tools needed for the routing step.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### UseQuantity

Quantity of the resource, that should be allocated for the operation. `Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)`

_Type_: **[Quantity (9, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### WaitTimeMinutes

Wait time (drying, cooling, etc.) after the operation in minutes. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Operation

The performed operation. `Filter(multi eq)`

_Type_: **[Operations](Production.Resources.Operations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WorkgroupResource

The resource that will be used for the operation. null means that no resource will be locked for the operation. `Required` `Filter(multi eq)`

_Type_: **[WorkgroupResources](Production.Resources.WorkgroupResources.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WorkOrderItem

The work order item, containing the line. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WorkOrderItems](Production.ShopFloor.WorkOrderItems.md)**  
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

