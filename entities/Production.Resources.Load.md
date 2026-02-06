---
uid: Production.Resources.Load
---
# Production.Resources.Load


Contains scheduled operations usage of the resources.

## General
Namespace: [Production.Resources](Production.Resources.md)  
Repository: Production.Resources.Load  
Base Table: Prd_Load  
API access:  ReadWrite  

## Visualization
Display Format: {WorkOrderItemOperation.WorkOrderItem.WorkOrder.EntityName}  
Search Members: WorkOrderItemOperation.WorkOrderItem.WorkOrder.EntityName  
Name Member: WorkOrderItemOperation.WorkOrderItem.WorkOrder.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md)  
Aggregate Root:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CalendarDate](Production.Resources.Load.md#calendardate) | datetime | Date of the scheduled load. This is date only. Start_Time and End_Time specify time of day[Required] [Filter(ge;le)] 
| [Priority](Production.Resources.Load.md#priority) | [Priority](Production.Resources.Load.md#priority) | Priority of the allocation. 1=Lowest ... 5=Highest[Required] [Default(3)] 
| [TimeType](Production.Resources.Load.md#timetype) | [TimeType](Production.Resources.Load.md#timetype) | S=Setup; R=Run; W=Wait; M=Move[Required] [Default(&quot;R&quot;)] 
| [UsageEndTime](Production.Resources.Load.md#usageendtime) | datetime | The ending time of the planned usage.[Required] [Filter(ge;le)] 
| [UsageQuantity](Production.Resources.Load.md#usagequantity) | [Quantity (9, 0)](../data-types.md#quantity) | Quantity of the resource, which will be used for production[Unit: WorkgroupResource.Resource.PrimaryUnit] [Required] [Default(1)] [Filter(ge;le)] 
| [UsageStartTime](Production.Resources.Load.md#usagestarttime) | datetime | The starting time of the planned usage.[Required] [Filter(ge;le)] 
| [UsageTimeMinutes](Production.Resources.Load.md#usagetimeminutes) | int32 | Time allocated for the operation in minutes[Required] [Default(0)] [Filter(ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [WorkgroupResource](Production.Resources.Load.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) | The exact resource being utilised |
| [WorkOrderItemOperation](Production.Resources.Load.md#workorderitemoperation) | [WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) | The <see cref="Production.ShopFloor.WorkOrderItemOperation"/> to which this Load belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Resources.Load.md#id) | guid |  
| [ObjectVersion](Production.Resources.Load.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Resources.Load.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CalendarDate

Date of the scheduled load. This is date only. Start_Time and End_Time specify time of day[Required] [Filter(ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Priority

Priority of the allocation. 1=Lowest ... 5=Highest[Required] [Default(3)]

Type: **[Priority](Production.Resources.Load.md#priority)**  
Category: **System**  
Allowed values for the `Priority`(Production.Resources.Load.md#priority) data attribute  
Allowed Values (Production.Resources.LoadRepository.Priority Enum Members)  

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
Show in UI: **ShownByDefault**  

### TimeType

S=Setup; R=Run; W=Wait; M=Move[Required] [Default(&quot;R&quot;)]

Type: **[TimeType](Production.Resources.Load.md#timetype)**  
Category: **System**  
Allowed values for the `TimeType`(Production.Resources.Load.md#timetype) data attribute  
Allowed Values (Production.Resources.LoadRepository.TimeType Enum Members)  

| Value | Description |
| ---- | --- |
| Move | Move value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 0 <br /> Domain API Value: 'Move' |
| Run | Run value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Run' |
| Setup | Setup value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 2 <br /> Domain API Value: 'Setup' |
| Wait | Wait value. Stored as 'W'. <br /> Database Value: 'W' <br /> Model Value: 3 <br /> Domain API Value: 'Wait' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Run**  
Show in UI: **ShownByDefault**  

### UsageEndTime

The ending time of the planned usage.[Required] [Filter(ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UsageQuantity

Quantity of the resource, which will be used for production[Unit: WorkgroupResource.Resource.PrimaryUnit] [Required] [Default(1)] [Filter(ge;le)]

Type: **[Quantity (9, 0)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### UsageStartTime

The starting time of the planned usage.[Required] [Filter(ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UsageTimeMinutes

Time allocated for the operation in minutes[Required] [Default(0)] [Filter(ge;le)]

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
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

### WorkgroupResource

The exact resource being utilised

Type: **[WorkgroupResources](Production.Resources.WorkgroupResources.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WorkOrderItemOperation

The <see cref="Production.ShopFloor.WorkOrderItemOperation"/> to which this Load belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md)**  
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

[!list limit=1000 erp.entity=Production.Resources.Load erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Resources.Load erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Resources_Load

Domain API Entity Type: 
Production_Resources_Load

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Resources_Load?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Resources_Load?$top=10>

