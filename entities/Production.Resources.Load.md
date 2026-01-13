---
uid: Production.Resources.Load
---
# Production.Resources.Load Entity

**Namespace:** [Production.Resources](Production.Resources.md)  

Contains scheduled operations usage of the resources. Entity: Prd_Load

## Default Visualization
Default Display Text Format:  
_{WorkOrderItemOperation.WorkOrderItem.WorkOrder.EntityName}_  
Default Search Members:  
_WorkOrderItemOperation.WorkOrderItem.WorkOrder.EntityName_  
Name Data Member:  
_WorkOrderItemOperation.WorkOrderItem.WorkOrder.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.ShopFloor.WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md)  
Aggregate Root:  
[Production.ShopFloor.WorkOrders](Production.ShopFloor.WorkOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CalendarDate](Production.Resources.Load.md#calendardate) | datetime | Date of the scheduled load. This is date only. Start_Time and End_Time specify time of day. `Required` `Filter(ge;le)` 
| [DisplayText](Production.Resources.Load.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.Resources.Load.md#id) | guid |  
| [ObjectVersion](Production.Resources.Load.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Priority](Production.Resources.Load.md#priority) | [Priority](Production.Resources.Load.md#priority) | Priority of the allocation. 1=Lowest ... 5=Highest. `Required` `Default(3)` 
| [TimeType](Production.Resources.Load.md#timetype) | [TimeType](Production.Resources.Load.md#timetype) | S=Setup; R=Run; W=Wait; M=Move. `Required` `Default("R")` 
| [UsageEndTime](Production.Resources.Load.md#usageendtime) | datetime | The ending time of the planned usage. `Required` `Filter(ge;le)` 
| [UsageQuantity](Production.Resources.Load.md#usagequantity) | [Quantity (9, 0)](../data-types.md#quantity) | Quantity of the resource, which will be used for production. `Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)` `Filter(ge;le)` 
| [UsageStartTime](Production.Resources.Load.md#usagestarttime) | datetime | The starting time of the planned usage. `Required` `Filter(ge;le)` 
| [UsageTimeMinutes](Production.Resources.Load.md#usagetimeminutes) | int32 | Time allocated for the operation in minutes. `Required` `Default(0)` `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [WorkgroupResource](Production.Resources.Load.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) | The exact resource being utilised. `Required` `Filter(multi eq)` |
| [WorkOrderItemOperation](Production.Resources.Load.md#workorderitemoperation) | [WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md) | The <see cref="Production.ShopFloor.WorkOrderItemOperation"/> to which this Load belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### CalendarDate

Date of the scheduled load. This is date only. Start_Time and End_Time specify time of day. `Required` `Filter(ge;le)`

_Type_: **datetime**  
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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Priority

Priority of the allocation. 1=Lowest ... 5=Highest. `Required` `Default(3)`

_Type_: **[Priority](Production.Resources.Load.md#priority)**  
_Category_: **System**  
Allowed values for the `Priority`(Production.Resources.Load.md#priority) data attribute  
_Allowed Values (Production.Resources.LoadRepository.Priority Enum Members)_  

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
_Show in UI_: **ShownByDefault**  

### TimeType

S=Setup; R=Run; W=Wait; M=Move. `Required` `Default("R")`

_Type_: **[TimeType](Production.Resources.Load.md#timetype)**  
_Category_: **System**  
Allowed values for the `TimeType`(Production.Resources.Load.md#timetype) data attribute  
_Allowed Values (Production.Resources.LoadRepository.TimeType Enum Members)_  

| Value | Description |
| ---- | --- |
| Move | Move value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Move' |
| Run | Run value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Run' |
| Setup | Setup value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Setup' |
| Wait | Wait value. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Wait' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Run**  
_Show in UI_: **ShownByDefault**  

### UsageEndTime

The ending time of the planned usage. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UsageQuantity

Quantity of the resource, which will be used for production. `Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)` `Filter(ge;le)`

_Type_: **[Quantity (9, 0)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### UsageStartTime

The starting time of the planned usage. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UsageTimeMinutes

Time allocated for the operation in minutes. `Required` `Default(0)` `Filter(ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### WorkgroupResource

The exact resource being utilised. `Required` `Filter(multi eq)`

_Type_: **[WorkgroupResources](Production.Resources.WorkgroupResources.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WorkOrderItemOperation

The <see cref="Production.ShopFloor.WorkOrderItemOperation"/> to which this Load belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WorkOrderItemOperations](Production.ShopFloor.WorkOrderItemOperations.md)**  
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

