---
uid: Logistics.Inventory.RequisitionPlan
---
# Logistics.Inventory.RequisitionPlan Entity

**Namespace:** [Logistics.Inventory](Logistics.Inventory.md)  

The current requisition (MRP) plan. The data is deleted and re-created upon each planning. Entity: Inv_Requisition_Plan

## Default Visualization
Default Display Text Format:  
_{Id}: {FirmPlannedOrderReceiptsValue}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.RequisitionPlan](Logistics.Inventory.RequisitionPlan.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Logistics.Inventory.RequisitionPlan.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [CalendarDate](Logistics.Inventory.RequisitionPlan.md#calendardate) | datetime | The date for which we are planning. A record is created for each calendar date, on which there are events (orders, executions, planned events, etc.) for the product. Past events are stored on the current date of the planning. `Required` `Filter(ge;le)` 
| [CompletionDate](Logistics.Inventory.RequisitionPlan.md#completiondate) | datetime __nullable__ | The suggested by the program value equals Calendar_Date + Planning_Lead_Time_Days of the default product supply for this store; the completion date of the purchase orders to be generated. `Filter(ge;le)` 
| [ConfirmAction](Logistics.Inventory.RequisitionPlan.md#confirmaction) | boolean | True - generate firm planned orders for the current row; false- do not generate;. `Required` `Default(false)` `Filter(eq)` 
| [DisplayText](Logistics.Inventory.RequisitionPlan.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExplanationMessage](Logistics.Inventory.RequisitionPlan.md#explanationmessage) | string (max) __nullable__ | A message that explains why the program has generated the planned orders for this row. 
| [ExternalId](Logistics.Inventory.RequisitionPlan.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Inventory.RequisitionPlan.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [FirmPlannedOrderReceipts](Logistics.Inventory.RequisitionPlan.md#firmplannedorderreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity, which is expected to be received on the calendar date. The quantity is the same as the quantity, planned in Firm Planned Order Releases, but at a different calendar date - the expected receivement date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [FirmPlannedOrderReleases](Logistics.Inventory.RequisitionPlan.md#firmplannedorderreleases) | [Quantity (18, 3)](../data-types.md#quantity) | The order releases which were manually confirmed for release on the specified calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [GenerationDate](Logistics.Inventory.RequisitionPlan.md#generationdate) | datetime | Indicates the date on which the plan is generated. `Required` `Default(Now)` `Filter(ge;le)` 
| [GrossRequirements](Logistics.Inventory.RequisitionPlan.md#grossrequirements) | [Quantity (18, 3)](../data-types.md#quantity) | The gross requirements of the product on the specified calendar date. This is calculated as the unexecuted quantity of issue store orders, whose expected execution date is equal to the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [Id](Logistics.Inventory.RequisitionPlan.md#id) | guid |  
| [NetRequirements](Logistics.Inventory.RequisitionPlan.md#netrequirements) | [Quantity (18, 3)](../data-types.md#quantity) | The net requirements for the date, which are in shortage for the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [ObjectVersion](Logistics.Inventory.RequisitionPlan.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PlannedOrderReceipts](Logistics.Inventory.RequisitionPlan.md#plannedorderreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The planned by the calculation process order receipts on the calendar date. This is calculated by the MRP process as the quantity, which is expected to be received on the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [PlannedOrderReleases](Logistics.Inventory.RequisitionPlan.md#plannedorderreleases) | [Quantity (18, 3)](../data-types.md#quantity) | The planned by the calculation process order releases on the specified calendar date. This is calculated by the MRP process as the quantity, which should be released for purchasing, transfer or production on the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [ProjectedAvailableBalance](Logistics.Inventory.RequisitionPlan.md#projectedavailablebalance) | [Quantity (18, 3)](../data-types.md#quantity) | Expected balance of the product for the calendar date. This is a calculation, based on the current physical inventory and expected future transactions. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [Quantity](Logistics.Inventory.RequisitionPlan.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The Quantity of the purchase orders the program shall generate; the suggested value equals Planned_Order_Releases but can be changed by the user;. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 
| [ReleaseDate](Logistics.Inventory.RequisitionPlan.md#releasedate) | datetime __nullable__ | The suggested by the program value equals Calendar_Date; the release date of the purchase orders to be generated. `Filter(ge;le)` 
| [ScheduledReceipts](Logistics.Inventory.RequisitionPlan.md#scheduledreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The scheduled receipts of the product on the specified calendar date. This is calculated as the unexecuted quantity of released receipt store orders, whose expected execution date is equal to the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.RequisitionPlan.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this RequisitionPlan applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [FromStore](Logistics.Inventory.RequisitionPlan.md#fromstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | When the order is for transfer, this is the store from which we shall transfer the product. `Filter(multi eq)` |
| [Product](Logistics.Inventory.RequisitionPlan.md#product) | [Products](General.Products.Products.md) | The product, for which we are planning. `Required` `Filter(multi eq)` |
| [Store](Logistics.Inventory.RequisitionPlan.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store, which is planned. `Required` `Filter(multi eq)` |
| [Supplier](Logistics.Inventory.RequisitionPlan.md#supplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | The default supplier in the default product supply for current store, if any. `Filter(multi eq)` |


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### CalendarDate

The date for which we are planning. A record is created for each calendar date, on which there are events (orders, executions, planned events, etc.) for the product. Past events are stored on the current date of the planning. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### CompletionDate

The suggested by the program value equals Calendar_Date + Planning_Lead_Time_Days of the default product supply for this store; the completion date of the purchase orders to be generated. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ConfirmAction

True - generate firm planned orders for the current row; false- do not generate;. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExplanationMessage

A message that explains why the program has generated the planned orders for this row.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FirmPlannedOrderReceipts

The quantity, which is expected to be received on the calendar date. The quantity is the same as the quantity, planned in Firm Planned Order Releases, but at a different calendar date - the expected receivement date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### FirmPlannedOrderReleases

The order releases which were manually confirmed for release on the specified calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### GenerationDate

Indicates the date on which the plan is generated. `Required` `Default(Now)` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **CannotBeShown**  

### GrossRequirements

The gross requirements of the product on the specified calendar date. This is calculated as the unexecuted quantity of issue store orders, whose expected execution date is equal to the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

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
_Show in UI_: **CannotBeShown**  

### NetRequirements

The net requirements for the date, which are in shortage for the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PlannedOrderReceipts

The planned by the calculation process order receipts on the calendar date. This is calculated by the MRP process as the quantity, which is expected to be received on the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### PlannedOrderReleases

The planned by the calculation process order releases on the specified calendar date. This is calculated by the MRP process as the quantity, which should be released for purchasing, transfer or production on the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ProjectedAvailableBalance

Expected balance of the product for the calendar date. This is a calculation, based on the current physical inventory and expected future transactions. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### Quantity

The Quantity of the purchase orders the program shall generate; the suggested value equals Planned_Order_Releases but can be changed by the user;. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### ReleaseDate

The suggested by the program value equals Calendar_Date; the release date of the purchase orders to be generated. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ScheduledReceipts

The scheduled receipts of the product on the specified calendar date. This is calculated as the unexecuted quantity of released receipt store orders, whose expected execution date is equal to the calendar date. `Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

_Type_: **[Quantity (18, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The Enterprise Company to which this RequisitionPlan applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### FromStore

When the order is for transfer, this is the store from which we shall transfer the product. `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

The product, for which we are planning. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Store

The store, which is planned. `Required` `Filter(multi eq)`

_Type_: **[Stores](Logistics.Inventory.Stores.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Supplier

The default supplier in the default product supply for current store, if any. `Filter(multi eq)`

_Type_: **[Suppliers](Logistics.Procurement.Suppliers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.RequisitionPlan erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.RequisitionPlan erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_RequisitionPlan

Domain API Entity Type: 
Logistics_Inventory_RequisitionPlan

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_RequisitionPlan?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_RequisitionPlan?$top=10>

