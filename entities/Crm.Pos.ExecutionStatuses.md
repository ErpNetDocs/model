---
uid: Crm.Pos.ExecutionStatuses
---
# Crm.Pos.ExecutionStatuses


Defines user-configurable status values that describe sub-stages within a broader, system-defined execution stage (ExecutionStage). This allows businesses to model their unique operational workflows — such as food prep steps, service sessions, or treatment progress.

## General
Namespace: [Crm.Pos](Crm.Pos.md)  
Repository: Crm.Pos.ExecutionStatuses  
Base Table: Pos_Execution_Statuses  
Introduced In Version: 25.1.3.45  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.ExecutionStatuses](Crm.Pos.ExecutionStatuses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Crm.Pos.ExecutionStatuses.md#code) | string (16) | Unique short descriptive code of the user status. Used for display constrained devices, import/export matching, etc. 
| [ExecutionStage](Crm.Pos.ExecutionStatuses.md#executionstage) | [ExecutionStage](Crm.Pos.ExecutionStatuses.md#executionstage) | The system-defined stage under which is the current status. 
| [IsActive](Crm.Pos.ExecutionStatuses.md#isactive) | boolean | Indicates whether the POS execution status is currently active. 
| [Name](Crm.Pos.ExecutionStatuses.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the execution status. Should be action-oriented, e.g. reflect the NEXT action which should be taken (and not what is completed). For example, "Scheduled", "Ready-to-serve", etc. 
| [Ord](Crm.Pos.ExecutionStatuses.md#ord) | int32 | The sort order of the status within the stage. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Crm.Pos.ExecutionStatuses.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When specified, means that the status applies only to the specified enterprise company. NULL means the status is applicable to all enterprise companies. |
| [Location](Crm.Pos.ExecutionStatuses.md#location) | [Locations](Crm.Pos.Locations.md) (nullable) | When specified, means that the status applies only to the specified location. NULL means the status is applicable to all locations. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pos.ExecutionStatuses.md#id) | guid |  
| [ObjectVersion](Crm.Pos.ExecutionStatuses.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pos.ExecutionStatuses.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pos.ExecutionStatuses.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pos.ExecutionStatuses.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pos.ExecutionStatuses.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

Unique short descriptive code of the user status. Used for display constrained devices, import/export matching, etc.

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### ExecutionStage

The system-defined stage under which is the current status.

Type: **[ExecutionStage](Crm.Pos.ExecutionStatuses.md#executionstage)**  
Category: **System**  
Allowed values for the `ExecutionStage`(Crm.Pos.ExecutionStatuses.md#executionstage) data attribute  
Allowed Values (Crm.Pos.ExecutionStatusesRepository.ExecutionStage Enum Members)  

| Value | Description |
| ---- | --- |
| Pending | Pending. Stored as 'PND'. <br /> Database Value: 'PND' <br /> Model Value: 0 <br /> Domain API Value: 'Pending' |
| Prepare | Prepare. Stored as 'PRP'. <br /> Database Value: 'PRP' <br /> Model Value: 1 <br /> Domain API Value: 'Prepare' |
| Deliver | Deliver. Stored as 'DEL'. <br /> Database Value: 'DEL' <br /> Model Value: 2 <br /> Domain API Value: 'Deliver' |
| Finalize | Finalize. Stored as 'FIN'. <br /> Database Value: 'FIN' <br /> Model Value: 3 <br /> Domain API Value: 'Finalize' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Pending**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the POS execution status is currently active.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Name of the execution status. Should be action-oriented, e.g. reflect the NEXT action which should be taken (and not what is completed). For example, "Scheduled", "Ready-to-serve", etc.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Ord

The sort order of the status within the stage.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.SetExecutionStatusOrd( obj.ExecutionStage)`

Front-End Recalc Expressions:  
`obj.SetExecutionStatusOrd( obj.ExecutionStage)`
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

When specified, means that the status applies only to the specified enterprise company. NULL means the status is applicable to all enterprise companies.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Location

When specified, means that the status applies only to the specified location. NULL means the status is applicable to all locations.

Type: **[Locations](Crm.Pos.Locations.md) (nullable)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Crm.Pos.ExecutionStatuses erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.ExecutionStatuses erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_ExecutionStatuses

Domain API Entity Type: 
Crm_Pos_ExecutionStatus

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_ExecutionStatuses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_ExecutionStatuses?$top=10>

