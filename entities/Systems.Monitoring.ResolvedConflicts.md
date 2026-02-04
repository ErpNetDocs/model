---
uid: Systems.Monitoring.ResolvedConflicts
---
# Systems.Monitoring.ResolvedConflicts


Contains records of conflicts, which were automatically resolved by update procedures.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.ResolvedConflicts  
Base Table: Sys_Resolved_Conflicts  
API access:  ReadWrite  

## Renames

Old name: Systems.Core.ResolvedConflicts  
New name: Systems.Monitoring.ResolvedConflicts  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {TableName:T}  
Search Members: TableName  
Name Member: TableName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.ResolvedConflicts](Systems.Monitoring.ResolvedConflicts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ConflictDescription](Systems.Monitoring.ResolvedConflicts.md#conflictdescription) | [MultilanguageString (400)](../data-types.md#multilanguagestring) | Description of the conflict. 
| [ResolveConfirmedByUser](Systems.Monitoring.ResolvedConflicts.md#resolveconfirmedbyuser) | boolean | True, when the conflict resolution was manually confirmed by user. 
| [ResolveConfirmedTime](Systems.Monitoring.ResolvedConflicts.md#resolveconfirmedtime) | datetime __nullable__ | Time when the conflict resolution was confirmed by the user. 
| [ResolveDescription](Systems.Monitoring.ResolvedConflicts.md#resolvedescription) | [MultilanguageString (400)](../data-types.md#multilanguagestring) | Description of the resolution of the conflict. 
| [ResolvedTime](Systems.Monitoring.ResolvedConflicts.md#resolvedtime) | datetime | Time when the resolution of the conflict was made. 
| [RevisedByUser](Systems.Monitoring.ResolvedConflicts.md#revisedbyuser) | boolean | True, when the conflict resolution was revised (reviewed) manually by user. 
| [TableName](Systems.Monitoring.ResolvedConflicts.md#tablename) | [MultilanguageString (64)](../data-types.md#multilanguagestring) | Name of the table in which the conflict has occurred. 
| [URL](Systems.Monitoring.ResolvedConflicts.md#url) | string (254) | URL of the item (the row) for which the conflict occurred. 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Monitoring.ResolvedConflicts.md#id) | guid |  
| [ObjectVersion](Systems.Monitoring.ResolvedConflicts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Monitoring.ResolvedConflicts.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Monitoring.ResolvedConflicts.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Monitoring.ResolvedConflicts.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Monitoring.ResolvedConflicts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ConflictDescription

Description of the conflict.

Type: **[MultilanguageString (400)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ResolveConfirmedByUser

True, when the conflict resolution was manually confirmed by user.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ResolveConfirmedTime

Time when the conflict resolution was confirmed by the user.

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`DateTime.Now`

### ResolveDescription

Description of the resolution of the conflict.

Type: **[MultilanguageString (400)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ResolvedTime

Time when the resolution of the conflict was made.

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### RevisedByUser

True, when the conflict resolution was revised (reviewed) manually by user.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### TableName

Name of the table in which the conflict has occurred.

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### URL

URL of the item (the row) for which the conflict occurred.

Type: **string (254)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
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

[!list limit=1000 erp.entity=Systems.Monitoring.ResolvedConflicts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Monitoring.ResolvedConflicts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Monitoring_ResolvedConflicts

Domain API Entity Type: 
Systems_Monitoring_ResolvedConflict

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_ResolvedConflicts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_ResolvedConflicts?$top=10>

