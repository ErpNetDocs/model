---
uid: Production.Resources.WorkgroupShifts
---
# Production.Resources.WorkgroupShifts


Contains the working shifts of the wrokgroups.

## General
Namespace: [Production.Resources](Production.Resources.md)  
Repository: Production.Resources.WorkgroupShifts  
Base Table: Prd_Workgroup_Shifts  
API access:  ReadWrite  

## Visualization
Display Format: {ShiftName}  
Search Members: ShiftName  
Name Member: ShiftName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Production.Resources.Workgroups](Production.Resources.Workgroups.md)  
Aggregate Root:  
[Production.Resources.Workgroups](Production.Resources.Workgroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EfficiencyFactorPercent](Production.Resources.WorkgroupShifts.md#efficiencyfactorpercent) | decimal (3, 2) | Efficiency factor of the routing steps for this shift, expressed as percentage`Required` `Default(1)` 
| [EstablishmentDate](Production.Resources.WorkgroupShifts.md#establishmentdate) | datetime | When the workgroup shift was established. Used as minimum date when generating calendar`Required` `Default(Today)` `Filter(ge;le)` 
| [ShiftName](Production.Resources.WorkgroupShifts.md#shiftname) | string (254) | The name of the workgroup shift.`Required` `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Workgroup](Production.Resources.WorkgroupShifts.md#workgroup) | [Workgroups](Production.Resources.Workgroups.md) | The <see cref="Workgroup"/> to which this WorkgroupShift belongs. `Required` `Filter(multi eq)` `Owner` |
| [WorkSchedule](Production.Resources.WorkgroupShifts.md#workschedule) | [WorkSchedules](General.Resources.WorkSchedules.md) | The work schedule used to calculate the working time for the shift. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Production.Resources.WorkgroupShifts.md#id) | guid | Unique workgroup shift Id 
| [ObjectVersion](Production.Resources.WorkgroupShifts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Production.Resources.WorkgroupShifts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### EfficiencyFactorPercent

Efficiency factor of the routing steps for this shift, expressed as percentage`Required` `Default(1)`

Type: **decimal (3, 2)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### EstablishmentDate

When the workgroup shift was established. Used as minimum date when generating calendar`Required` `Default(Today)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### ShiftName

The name of the workgroup shift.`Required` `Filter(like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Id

Unique workgroup shift Id

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

### Workgroup

The <see cref="Workgroup"/> to which this WorkgroupShift belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Workgroups](Production.Resources.Workgroups.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### WorkSchedule

The work schedule used to calculate the working time for the shift.

Type: **[WorkSchedules](General.Resources.WorkSchedules.md)**  
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

[!list limit=1000 erp.entity=Production.Resources.WorkgroupShifts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Production.Resources.WorkgroupShifts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Production_Resources_WorkgroupShifts

Domain API Entity Type: 
Production_Resources_WorkgroupShift

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Production_Resources_WorkgroupShifts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Production_Resources_WorkgroupShifts?$top=10>

