---
uid: Production.Resources.Operations
---
# Production.Resources.Operations Entity

**Namespace:** [Production.Resources](Production.Resources.md)  

The different steps performed to create products. Entity: Prd_Operations

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Resources.OperationGroups](Production.Resources.OperationGroups.md)  
Aggregate Root:  
[Production.Resources.OperationGroups](Production.Resources.OperationGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Production.Resources.Operations.md#active) | boolean | Indicates whether the current operation is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26` 
| [Description](Production.Resources.Operations.md#description) | string (max) __nullable__ | The description of this Operation. 
| [DisplayText](Production.Resources.Operations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Production.Resources.Operations.md#id) | guid |  
| [MinimumConcurrent<br />StartTimeMinutes](Production.Resources.Operations.md#minimumconcurrentstarttimeminutes) | int32 __nullable__ | How many minutes after the start of this operation can the next operation start. null means that the next operation should wait this operation to finish before starting. 
| [MoveTimeMinutes](Production.Resources.Operations.md#movetimeminutes) | int32 | The time required for the product to move to the next operation. During this time no resource is allocated. `Required` `Default(0)` 
| [Name](Production.Resources.Operations.md#name) | string (50) | The name of this Operation. `Required` `Filter(like)` 
| [ObjectVersion](Production.Resources.Operations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RunTimeMinutes](Production.Resources.Operations.md#runtimeminutes) | int32 | The time required to process one product lot. The run time is calculated for each produced lot. `Required` `Default(0)` 
| [ScrapRate](Production.Resources.Operations.md#scraprate) | decimal (7, 6) __nullable__ | The percentage (0..1) of scrap usually occurring during the production operation. null means that the scrap rate cannot be generally calculated. 
| [SetupTimeMinutes](Production.Resources.Operations.md#setuptimeminutes) | int32 | The time required to setup the operation. The setup is incurred only once, regardless of the produced quntity. `Required` `Default(0)` 
| [StandardPricePerHour](Production.Resources.Operations.md#standardpriceperhour) | decimal (18, 6) | Standard price for 1 hour work for this operation. `Required` `Default(0)` 
| [Tooling](Production.Resources.Operations.md#tooling) | string (254) __nullable__ | Short description of the needed instruments for the operation. 
| [UseQuantityBase](Production.Resources.Operations.md#usequantitybase) | [Quantity (9, 3)](../data-types.md#quantity) | Quantity of the resource that need to be allocated for the operation, in base measurement units for the resource. `Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)` 
| [WaitTimeMinutes](Production.Resources.Operations.md#waittimeminutes) | int32 | The time required to wait after completing the operation. During this time, the resource is still allocated to the operation. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [OperationGroup](Production.Resources.Operations.md#operationgroup) | [OperationGroups](Production.Resources.OperationGroups.md) | The <see cref="OperationGroup"/> to which this Operation belongs. `Required` `Filter(multi eq)` `Owner` |
| [OperationInstructions](Production.Resources.Operations.md#operationinstructions) | [OperationInstructions](Production.Resources.OperationInstructions.md) (nullable) | Full instructions for the operation. `Filter(multi eq)` |
| [WorkgroupResource](Production.Resources.Operations.md#workgroupresource) | [WorkgroupResources](Production.Resources.WorkgroupResources.md) (nullable) | When not null, specifies the Workgroup Resource, which is required by the operation. `Filter(multi eq)` |


## Attribute Details

### Active

Indicates whether the current operation is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 22.1.5.26`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Description

The description of this Operation.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
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

### MinimumConcurrentStartTimeMinutes

How many minutes after the start of this operation can the next operation start. null means that the next operation should wait this operation to finish before starting.

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MoveTimeMinutes

The time required for the product to move to the next operation. During this time no resource is allocated. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### Name

The name of this Operation. `Required` `Filter(like)`

_Type_: **string (50)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### RunTimeMinutes

The time required to process one product lot. The run time is calculated for each produced lot. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### ScrapRate

The percentage (0..1) of scrap usually occurring during the production operation. null means that the scrap rate cannot be generally calculated.

_Type_: **decimal (7, 6) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SetupTimeMinutes

The time required to setup the operation. The setup is incurred only once, regardless of the produced quntity. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### StandardPricePerHour

Standard price for 1 hour work for this operation. `Required` `Default(0)`

_Type_: **decimal (18, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **CannotBeShown**  

### Tooling

Short description of the needed instruments for the operation.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### UseQuantityBase

Quantity of the resource that need to be allocated for the operation, in base measurement units for the resource. `Unit: WorkgroupResource.Resource.PrimaryUnit` `Required` `Default(1)`

_Type_: **[Quantity (9, 3)](../data-types.md#quantity)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

### WaitTimeMinutes

The time required to wait after completing the operation. During this time, the resource is still allocated to the operation. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### OperationGroup

The <see cref="OperationGroup"/> to which this Operation belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[OperationGroups](Production.Resources.OperationGroups.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### OperationInstructions

Full instructions for the operation. `Filter(multi eq)`

_Type_: **[OperationInstructions](Production.Resources.OperationInstructions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  

### WorkgroupResource

When not null, specifies the Workgroup Resource, which is required by the operation. `Filter(multi eq)`

_Type_: **[WorkgroupResources](Production.Resources.WorkgroupResources.md) (nullable)**  
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

