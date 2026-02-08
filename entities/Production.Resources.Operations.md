---
uid: Production.Resources.Operations
---
# Production.Resources.Operations


The different steps performed to create products.

## General
Namespace: [Production.Resources](Production.Resources.md)  
Repository: Production.Resources.Operations  
Base Table: Prd_Operations  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Resources.OperationGroups](Production.Resources.OperationGroups.md)  
Aggregate Root:  
[Production.Resources.OperationGroups](Production.Resources.OperationGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Production.Resources.Operations.md#active) | boolean | Indicates whether the current operation is active.`Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26` 
| [Description](Production.Resources.Operations.md#description) | string (max) __nullable__ | The description of this Operation. 
| [MinimumConcurrent<br />StartTimeMinutes](Production.Resources.Operations.md#minimumconcurrentstarttimeminutes) | int32 __nullable__ | How many minutes after the start of this operation can the next operation start. NULL means that the next operation should wait this operation to finish before starting 
| [MoveTimeMinutes](Production.Resources.Operations.md#movetimeminutes) | int32 | The time required for the product to move to the next operation. During this time no resource is allocated.`Required` `Default(0)` 
| [Name](Production.Resources.Operations.md#name) | string (50) | The name of this Operation. `Required` `Filter(like)` 
| [RunTimeMinutes](Production.Resources.Operations.md#runtimeminutes) | int32 | The time required to process one product lot. The run time is calculated for each produced lot.`Required` `Default(0)` 
| [ScrapRate](Production.Resources.Operations.md#scraprate) | decimal (7, 6) __nullable__ | The percentage (0..1) of scrap usually occurring during the production operation. NULL means that the scrap rate cannot be generally calculated. 
| [SetupTimeMinutes](Production.Resources.Operations.md#setuptimeminutes) | int32 | The time required to setup the operation. The setup is incurred only once, regardless of the produced quntity.`Required` `Default(0)` 
| [StandardPricePerHour](Production.Resources.Operations.md#standardpriceperhour) | decimal (18, 6) | Standard price for 1 hour work for this operation.`Required` `Default(0)` 
| [Tooling](Production.Resources.Operations.md#tooling) | string (254) __nullable__ | Short description of the needed instruments for the operation. 
| [UseQuantityBase](Production.Resources.Operations.md#usequantitybase) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity of the resource that need to be allocated for the operation, in base measurement units for the resource`Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)` 
| [WaitTimeMinutes](Production.Resources.Operations.md#waittimeminutes) | int32 | The time required to wait after completing the operation. During this time, the resource is still allocated to the operation.`Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [OperationGroup](Production.Resources.Operations.md#operationgroup) | [OperationGroups](Production.Resources.OperationGroups.md) | The <see cref="OperationGroup"/> to which this Operation belongs. `Required` `Filter(multi eq)` `Owner` |
| [OperationInstructions](Production.Resources.Operations.md#operationinstructions) | [OperationInstructions](Production.Resources.OperationInstructions.md) (nullable) | Full instructions for the operation. |
| [WorkgroupResource](Production.Resources.Operations.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) (nullable) | When not NULL, specifies the Workgroup Resource, which is required by the operation. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Resources.Operations.md#id) | guid |  
| [ObjectVersion](Production.Resources.Operations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Resources.Operations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Active

Indicates whether the current operation is active.`Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Description

The description of this Operation.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### MinimumConcurrentStartTimeMinutes

How many minutes after the start of this operation can the next operation start. NULL means that the next operation should wait this operation to finish before starting

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MoveTimeMinutes

The time required for the product to move to the next operation. During this time no resource is allocated.`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Name

The name of this Operation. `Required` `Filter(like)`

Type: **string (50)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### RunTimeMinutes

The time required to process one product lot. The run time is calculated for each produced lot.`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### ScrapRate

The percentage (0..1) of scrap usually occurring during the production operation. NULL means that the scrap rate cannot be generally calculated.

Type: **decimal (7, 6) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SetupTimeMinutes

The time required to setup the operation. The setup is incurred only once, regardless of the produced quntity.`Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### StandardPricePerHour

Standard price for 1 hour work for this operation.`Required` `Default(0)`

Type: **decimal (18, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **CannotBeShown**  

### Tooling

Short description of the needed instruments for the operation.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### UseQuantityBase

Quantity of the resource that need to be allocated for the operation, in base measurement units for the resource`Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)`

Type: **[Quantity (9, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### WaitTimeMinutes

The time required to wait after completing the operation. During this time, the resource is still allocated to the operation.`Required` `Default(0)`

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

### OperationGroup

The <see cref="OperationGroup"/> to which this Operation belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[OperationGroups](Production.Resources.OperationGroups.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### OperationInstructions

Full instructions for the operation.

Type: **[OperationInstructions](Production.Resources.OperationInstructions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### WorkgroupResource

When not NULL, specifies the Workgroup Resource, which is required by the operation.

Type: **[WorkgroupResources](Production.Resources.WorkgroupResources.md) (nullable)**  
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

[!list limit=1000 erp.entity=Production.Resources.Operations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Resources.Operations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Resources_Operations

Domain API Entity Type: 
Production_Resources_Operation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Resources_Operations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Resources_Operations?$top=10>

