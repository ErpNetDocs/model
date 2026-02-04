---
uid: Logistics.Inventory.RequisitionPlan
---
# Logistics.Inventory.RequisitionPlan


The current requisition (MRP) plan. The data is deleted and re-created upon each planning.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.RequisitionPlan  
Base Table: Inv_Requisition_Plan  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {FirmPlannedOrderReceiptsValue}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.RequisitionPlan](Logistics.Inventory.RequisitionPlan.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CalendarDate](Logistics.Inventory.RequisitionPlan.md#calendardate) | datetime | The date for which we are planning. A record is created for each calendar date, on which there are events (orders, executions, planned events, etc.) for the product. Past events are stored on the current date of the planning. 
| [CompletionDate](Logistics.Inventory.RequisitionPlan.md#completiondate) | datetime __nullable__ | The suggested by the program value equals Calendar_Date + Planning_Lead_Time_Days of the default product supply for this store; the completion date of the purchase orders to be generated 
| [ConfirmAction](Logistics.Inventory.RequisitionPlan.md#confirmaction) | boolean | 1 - generate firm planned orders for the current row; 0- do not generate; 
| [ExplanationMessage](Logistics.Inventory.RequisitionPlan.md#explanationmessage) | string (max) __nullable__ | A message that explains why the program has generated the planned orders for this row 
| [FirmPlannedOrderReceipts](Logistics.Inventory.RequisitionPlan.md#firmplannedorderreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity, which is expected to be received on the calendar date. The quantity is the same as the quantity, planned in Firm Planned Order Releases, but at a different calendar date - the expected receivement date. 
| [FirmPlannedOrderReleases](Logistics.Inventory.RequisitionPlan.md#firmplannedorderreleases) | [Quantity (18, 3)](../data-types.md#quantity) | The order releases which were manually confirmed for release on the specified calendar date. 
| [GenerationDate](Logistics.Inventory.RequisitionPlan.md#generationdate) | datetime | Indicates the date on which the plan is generated 
| [GrossRequirements](Logistics.Inventory.RequisitionPlan.md#grossrequirements) | [Quantity (18, 3)](../data-types.md#quantity) | The gross requirements of the product on the specified calendar date. This is calculated as the unexecuted quantity of issue store orders, whose expected execution date is equal to the calendar date. 
| [NetRequirements](Logistics.Inventory.RequisitionPlan.md#netrequirements) | [Quantity (18, 3)](../data-types.md#quantity) | The net requirements for the date, which are in shortage for the calendar date. 
| [PlannedOrderReceipts](Logistics.Inventory.RequisitionPlan.md#plannedorderreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The planned by the calculation process order receipts on the calendar date. This is calculated by the MRP process as the quantity, which is expected to be received on the calendar date. 
| [PlannedOrderReleases](Logistics.Inventory.RequisitionPlan.md#plannedorderreleases) | [Quantity (18, 3)](../data-types.md#quantity) | The planned by the calculation process order releases on the specified calendar date. This is calculated by the MRP process as the quantity, which should be released for purchasing, transfer or production on the calendar date. 
| [ProjectedAvailableBalance](Logistics.Inventory.RequisitionPlan.md#projectedavailablebalance) | [Quantity (18, 3)](../data-types.md#quantity) | Expected balance of the product for the calendar date. This is a calculation, based on the current physical inventory and expected future transactions. 
| [Quantity](Logistics.Inventory.RequisitionPlan.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The Quantity of the purchase orders the program shall generate; the suggested value equals Planned_Order_Releases but can be changed by the user; 
| [ReleaseDate](Logistics.Inventory.RequisitionPlan.md#releasedate) | datetime __nullable__ | The suggested by the program value equals Calendar_Date; the release date of the purchase orders to be generated 
| [ScheduledReceipts](Logistics.Inventory.RequisitionPlan.md#scheduledreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The scheduled receipts of the product on the specified calendar date. This is calculated as the unexecuted quantity of released receipt store orders, whose expected execution date is equal to the calendar date. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Inventory.RequisitionPlan.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this RequisitionPlan applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [FromStore](Logistics.Inventory.RequisitionPlan.md#fromstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | When the order is for transfer, this is the store from which we shall transfer the product. |
| [Product](Logistics.Inventory.RequisitionPlan.md#product) | [Products](General.Products.Products.md) | The product, for which we are planning. |
| [Store](Logistics.Inventory.RequisitionPlan.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store, which is planned. |
| [Supplier](Logistics.Inventory.RequisitionPlan.md#supplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | The default supplier in the default product supply for current store, if any |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.RequisitionPlan.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.RequisitionPlan.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Inventory.RequisitionPlan.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Inventory.RequisitionPlan.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Inventory.RequisitionPlan.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Inventory.RequisitionPlan.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CalendarDate

The date for which we are planning. A record is created for each calendar date, on which there are events (orders, executions, planned events, etc.) for the product. Past events are stored on the current date of the planning.

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CompletionDate

The suggested by the program value equals Calendar_Date + Planning_Lead_Time_Days of the default product supply for this store; the completion date of the purchase orders to be generated

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConfirmAction

1 - generate firm planned orders for the current row; 0- do not generate;

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ExplanationMessage

A message that explains why the program has generated the planned orders for this row

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### FirmPlannedOrderReceipts

The quantity, which is expected to be received on the calendar date. The quantity is the same as the quantity, planned in Firm Planned Order Releases, but at a different calendar date - the expected receivement date.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### FirmPlannedOrderReleases

The order releases which were manually confirmed for release on the specified calendar date.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### GenerationDate

Indicates the date on which the plan is generated

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **CannotBeShown**  

### GrossRequirements

The gross requirements of the product on the specified calendar date. This is calculated as the unexecuted quantity of issue store orders, whose expected execution date is equal to the calendar date.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### NetRequirements

The net requirements for the date, which are in shortage for the calendar date.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### PlannedOrderReceipts

The planned by the calculation process order receipts on the calendar date. This is calculated by the MRP process as the quantity, which is expected to be received on the calendar date.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### PlannedOrderReleases

The planned by the calculation process order releases on the specified calendar date. This is calculated by the MRP process as the quantity, which should be released for purchasing, transfer or production on the calendar date.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ProjectedAvailableBalance

Expected balance of the product for the calendar date. This is a calculation, based on the current physical inventory and expected future transactions.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### Quantity

The Quantity of the purchase orders the program shall generate; the suggested value equals Planned_Order_Releases but can be changed by the user;

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ReleaseDate

The suggested by the program value equals Calendar_Date; the release date of the purchase orders to be generated

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ScheduledReceipts

The scheduled receipts of the product on the specified calendar date. This is calculated as the unexecuted quantity of released receipt store orders, whose expected execution date is equal to the calendar date.

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### EnterpriseCompany

The Enterprise Company to which this RequisitionPlan applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### FromStore

When the order is for transfer, this is the store from which we shall transfer the product.

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

The product, for which we are planning.

Type: **[Products](General.Products.Products.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Store

The store, which is planned.

Type: **[Stores](Logistics.Inventory.Stores.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Supplier

The default supplier in the default product supply for current store, if any

Type: **[Suppliers](Logistics.Procurement.Suppliers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

