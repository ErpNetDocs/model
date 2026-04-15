---
uid: Logistics.Planning.RequisitionPlan
---
# Logistics.Planning.RequisitionPlan


The current requisition (MRP) plan. The data is deleted and re-created upon each planning.

## General
Namespace: [Logistics.Planning](Logistics.Planning.md)  
Repository: Logistics.Planning.RequisitionPlan  
Base Table: Inv_Requisition_Plan  
API access:  ReadWrite  

## Renames

Old name: Logistics.Inventory.RequisitionPlan  
New name: Logistics.Planning.RequisitionPlan  
Version: 26.2.2.12  
Case: 39709  



## Visualization
Display Format: {FirmPlannedOrderReceiptsValue}: {FirmPlannedOrderReleasesValue}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Planning.RequisitionPlan](Logistics.Planning.RequisitionPlan.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CalendarDate](Logistics.Planning.RequisitionPlan.md#calendardate) | datetime | The date for which we are planning. A record is created for each calendar date, on which there are events (orders, executions, planned events, etc.) for the product. Past events are stored on the current date of the planning.`Required` `Filter(ge;le)` |
| [CompletionDate](Logistics.Planning.RequisitionPlan.md#completiondate) | datetime __nullable__ | The suggested by the program value equals Calendar_Date + Planning_Lead_Time_Days of the default product supply for this store; the completion date of the purchase orders to be generated`Filter(ge;le)` |
| [ConfirmAction](Logistics.Planning.RequisitionPlan.md#confirmaction) | boolean | 1 - generate firm planned orders for the current row; 0- do not generate;`Required` `Default(false)` `Filter(eq)` |
| [ExplanationMessage](Logistics.Planning.RequisitionPlan.md#explanationmessage) | string (max) __nullable__ | A message that explains why the program has generated the planned orders for this row |
| [FirmPlannedOrderReceipts](Logistics.Planning.RequisitionPlan.md#firmplannedorderreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The quantity, which is expected to be received on the calendar date. The quantity is the same as the quantity, planned in Firm Planned Order Releases, but at a different calendar date - the expected receivement date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [FirmPlannedOrderReleases](Logistics.Planning.RequisitionPlan.md#firmplannedorderreleases) | [Quantity (18, 3)](../data-types.md#quantity) | The order releases which were manually confirmed for release on the specified calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [GenerationDate](Logistics.Planning.RequisitionPlan.md#generationdate) | datetime | Indicates the date on which the plan is generated`Required` `Default(Now)` `Filter(ge;le)` |
| [GrossRequirements](Logistics.Planning.RequisitionPlan.md#grossrequirements) | [Quantity (18, 3)](../data-types.md#quantity) | The gross requirements of the product on the specified calendar date. This is calculated as the unexecuted quantity of issue store orders, whose expected execution date is equal to the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [NetRequirements](Logistics.Planning.RequisitionPlan.md#netrequirements) | [Quantity (18, 3)](../data-types.md#quantity) | The net requirements for the date, which are in shortage for the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [PlannedOrderReceipts](Logistics.Planning.RequisitionPlan.md#plannedorderreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The planned by the calculation process order receipts on the calendar date. This is calculated by the MRP process as the quantity, which is expected to be received on the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [PlannedOrderReleases](Logistics.Planning.RequisitionPlan.md#plannedorderreleases) | [Quantity (18, 3)](../data-types.md#quantity) | The planned by the calculation process order releases on the specified calendar date. This is calculated by the MRP process as the quantity, which should be released for purchasing, transfer or production on the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [ProjectedAvailableBalance](Logistics.Planning.RequisitionPlan.md#projectedavailablebalance) | [Quantity (18, 3)](../data-types.md#quantity) | Expected balance of the product for the calendar date. This is a calculation, based on the current physical inventory and expected future transactions.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [Quantity](Logistics.Planning.RequisitionPlan.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | The Quantity of the purchase orders the program shall generate; the suggested value equals Planned_Order_Releases but can be changed by the user;`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [ReleaseDate](Logistics.Planning.RequisitionPlan.md#releasedate) | datetime __nullable__ | The suggested by the program value equals Calendar_Date; the release date of the purchase orders to be generated`Filter(ge;le)` |
| [ScheduledReceipts](Logistics.Planning.RequisitionPlan.md#scheduledreceipts) | [Quantity (18, 3)](../data-types.md#quantity) | The scheduled receipts of the product on the specified calendar date. This is calculated as the unexecuted quantity of released receipt store orders, whose expected execution date is equal to the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)` |
| [State](Logistics.Planning.RequisitionPlan.md#state) | [State](Logistics.Planning.RequisitionPlan.md#state) __nullable__ | Indicates the current stage of the requisition planning process, from initial calculation through user confirmation to execution.`Default(&quot;DRF&quot;)` `Filter(multi eq)` `Introduced in version 26.2.1.99` |
| [SuggestedQuantity](Logistics.Planning.RequisitionPlan.md#suggestedquantity) | [Quantity (18, 3)](../data-types.md#quantity) __nullable__ | The quantity suggested by the system based on planning calculations (MRP/DRP). It represents the recommended amount to cover the demand.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)` `Introduced in version 26.2.1.99` |
| [SupplyType](Logistics.Planning.RequisitionPlan.md#supplytype) | [SupplyType](Logistics.Planning.RequisitionPlan.md#supplytype) __nullable__ | Indicates how the required quantity will be supplied – by purchase, manufacturing, or stock transfer.`Filter(eq)` `Introduced in version 26.2.1.99` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Logistics.Planning.RequisitionPlan.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this RequisitionPlan applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [FromStore](Logistics.Planning.RequisitionPlan.md#fromstore) | [Stores](Logistics.Inventory.Stores.md) (nullable) | When the order is for transfer, this is the store from which we shall transfer the product. |
| [Product](Logistics.Planning.RequisitionPlan.md#product) | [Products](General.Products.Products.md) | The product, for which we are planning. |
| [Store](Logistics.Planning.RequisitionPlan.md#store) | [Stores](Logistics.Inventory.Stores.md) | The store, which is planned. |
| [Supplier](Logistics.Planning.RequisitionPlan.md#supplier) | [Suppliers](Logistics.Procurement.Suppliers.md) (nullable) | The default supplier in the default product supply for current store, if any |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Planning.RequisitionPlan.md#id) | guid |  |
| [ObjectVersion](Logistics.Planning.RequisitionPlan.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [ExternalId](Logistics.Planning.RequisitionPlan.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] |
| [ExternalSystem](Logistics.Planning.RequisitionPlan.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] |
| [AggregateLastUpdateTimeUtc](Logistics.Planning.RequisitionPlan.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] |
| [DisplayText](Logistics.Planning.RequisitionPlan.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### CalendarDate

The date for which we are planning. A record is created for each calendar date, on which there are events (orders, executions, planned events, etc.) for the product. Past events are stored on the current date of the planning.`Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CompletionDate

The suggested by the program value equals Calendar_Date + Planning_Lead_Time_Days of the default product supply for this store; the completion date of the purchase orders to be generated`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConfirmAction

1 - generate firm planned orders for the current row; 0- do not generate;`Required` `Default(false)` `Filter(eq)`

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

The quantity, which is expected to be received on the calendar date. The quantity is the same as the quantity, planned in Firm Planned Order Releases, but at a different calendar date - the expected receivement date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### FirmPlannedOrderReleases

The order releases which were manually confirmed for release on the specified calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### GenerationDate

Indicates the date on which the plan is generated`Required` `Default(Now)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **CannotBeShown**  

### GrossRequirements

The gross requirements of the product on the specified calendar date. This is calculated as the unexecuted quantity of issue store orders, whose expected execution date is equal to the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### NetRequirements

The net requirements for the date, which are in shortage for the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### PlannedOrderReceipts

The planned by the calculation process order receipts on the calendar date. This is calculated by the MRP process as the quantity, which is expected to be received on the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### PlannedOrderReleases

The planned by the calculation process order releases on the specified calendar date. This is calculated by the MRP process as the quantity, which should be released for purchasing, transfer or production on the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ProjectedAvailableBalance

Expected balance of the product for the calendar date. This is a calculation, based on the current physical inventory and expected future transactions.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### Quantity

The Quantity of the purchase orders the program shall generate; the suggested value equals Planned_Order_Releases but can be changed by the user;`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ReleaseDate

The suggested by the program value equals Calendar_Date; the release date of the purchase orders to be generated`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ScheduledReceipts

The scheduled receipts of the product on the specified calendar date. This is calculated as the unexecuted quantity of released receipt store orders, whose expected execution date is equal to the calendar date.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Required` `Default(0)`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### State

Indicates the current stage of the requisition planning process, from initial calculation through user confirmation to execution.`Default(&quot;DRF&quot;)` `Filter(multi eq)` `Introduced in version 26.2.1.99`

Type: **[State](Logistics.Planning.RequisitionPlan.md#state) __nullable__**  
Category: **System**  
Allowed values for the `State`(Logistics.Planning.RequisitionPlan.md#state) data attribute  
Allowed Values (Logistics.Planning.RequisitionPlanRepository.State Enum Members)  

| Value | Description |
| ---- | --- |
| Draft | The plan is automatically generated or updated by the system. Quantities are based on calculations and can be freely adjusted by the user.. Stored as 'DRF'. <br /> Database Value: 'DRF' <br /> Model Value: 0 <br /> Domain API Value: 'Draft' |
| Firmed | The plan has been reviewed and confirmed by the user. Quantities are fixed and will not be changed by subsequent planning runs.. Stored as 'FRM'. <br /> Database Value: 'FRM' <br /> Model Value: 1 <br /> Domain API Value: 'Firmed' |
| Released | The plan has been executed. Corresponding supply orders (purchase, transfer, or production) have been generated.. Stored as 'REL'. <br /> Database Value: 'REL' <br /> Model Value: 2 <br /> Domain API Value: 'Released' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Draft**  
Show in UI: **ShownByDefault**  

### SuggestedQuantity

The quantity suggested by the system based on planning calculations (MRP/DRP). It represents the recommended amount to cover the demand.`Unit: Product.BaseMeasurementCategory.BaseUnit` `Filter(eq;ge;le)` `Introduced in version 26.2.1.99`

Type: **[Quantity (18, 3)](../data-types.md#quantity) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SupplyType

Indicates how the required quantity will be supplied – by purchase, manufacturing, or stock transfer.`Filter(eq)` `Introduced in version 26.2.1.99`

Type: **[SupplyType](Logistics.Planning.RequisitionPlan.md#supplytype) __nullable__**  
Category: **System**  
Allowed values for the `SupplyType`(Logistics.Planning.RequisitionPlan.md#supplytype) data attribute  
Allowed Values (Logistics.Planning.RequisitionPlanRepository.SupplyType Enum Members)  

| Value | Description |
| ---- | --- |
| Purchase | The required quantity will be supplied by purchasing from an external supplier.. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 0 <br /> Domain API Value: 'Purchase' |
| Manufacture | The required quantity will be produced internally through a manufacturing (work) order.. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 1 <br /> Domain API Value: 'Manufacture' |
| Transfer | The required quantity will be supplied by transferring stock from another warehouse or location.. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 2 <br /> Domain API Value: 'Transfer' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Show in UI: **HiddenByDefault**  

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

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Logistics.Planning.RequisitionPlan erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Planning.RequisitionPlan erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Planning_RequisitionPlan

Domain API Entity Type: 
Logistics_Planning_RequisitionPlan

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Planning_RequisitionPlan?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Planning_RequisitionPlan?$top=10>

