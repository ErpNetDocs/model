---
uid: Systems.Monitoring.InstanceStatistics
---
# Systems.Monitoring.InstanceStatistics


Logs time‑windowed performance metrics for the instance across specified intervals.

## General
Namespace: [Systems.Monitoring](Systems.Monitoring.md)  
Repository: Systems.Monitoring.InstanceStatistics  
Base Table: Sys_Instance_Statistics  
Introduced In Version: 25.1.3.11  
API access:  ReadWrite  

## Visualization
Display Format: {ApplicationName}  
Search Members: ApplicationName  
Name Member: ApplicationName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.InstanceStatistics](Systems.Monitoring.InstanceStatistics.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationName](Systems.Monitoring.InstanceStatistics.md#applicationname) | string (128) __nullable__ | The application (if applicable) for which we are recording stats. 
| [Avg](Systems.Monitoring.InstanceStatistics.md#avg) | int32 __nullable__ | The avg value of the stat for the time period. 
| [Count](Systems.Monitoring.InstanceStatistics.md#count) | int32 | Number of occurrences. 
| [ExcludeFromSummary](Systems.Monitoring.InstanceStatistics.md#excludefromsummary) | boolean | Denotes that the stat should be excluded from summarization queries (for example long polling requests). 
| [InstanceName](Systems.Monitoring.InstanceStatistics.md#instancename) | string (128) | The name of the instance to which this statistic applies. 
| [Max](Systems.Monitoring.InstanceStatistics.md#max) | int32 __nullable__ | The max value of the stat within the time period. 
| [ObjectName](Systems.Monitoring.InstanceStatistics.md#objectname) | string (256) __nullable__ | Name of the object or operation (depending on the statistic type). 
| [StatisticDate](Systems.Monitoring.InstanceStatistics.md#statisticdate) | date | The date (in UTC time) for which we are storing the statistics. 
| [StatisticFromTimeUtc](Systems.Monitoring.InstanceStatistics.md#statisticfromtimeutc) | time | The starting of the time period within the date. 
| [StatisticToTimeUtc](Systems.Monitoring.InstanceStatistics.md#statistictotimeutc) | time | The ending of the time period within the date. 
| [StatisticType](Systems.Monitoring.InstanceStatistics.md#statistictype) | [StatisticType](Systems.Monitoring.InstanceStatistics.md#statistictype) | The type of the statistic: 'EXE' = Exec, 'WAI' = Wait, 'TAB' = Table, 'PER' = Performance, 'SIT' = Site 
| [SubType](Systems.Monitoring.InstanceStatistics.md#subtype) | string (64) | Kind of stat (depending on the type). 
| [Total](Systems.Monitoring.InstanceStatistics.md#total) | int32 | The total of the stat for the time period. 
| [UnitOfMeasure](Systems.Monitoring.InstanceStatistics.md#unitofmeasure) | string (10) | Unit of measure for Total and Max. 
| [Value](Systems.Monitoring.InstanceStatistics.md#value) | string (64) __nullable__ | Holds the metric in text when numeric fields can't represent it. 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Monitoring.InstanceStatistics.md#id) | guid |  
| [ObjectVersion](Systems.Monitoring.InstanceStatistics.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Systems.Monitoring.InstanceStatistics.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Monitoring.InstanceStatistics.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Systems.Monitoring.InstanceStatistics.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Systems.Monitoring.InstanceStatistics.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ApplicationName

The application (if applicable) for which we are recording stats.

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Avg

The avg value of the stat for the time period.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Count

Number of occurrences.

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExcludeFromSummary

Denotes that the stat should be excluded from summarization queries (for example long polling requests).

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### InstanceName

The name of the instance to which this statistic applies.

Type: **string (128)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### Max

The max value of the stat within the time period.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ObjectName

Name of the object or operation (depending on the statistic type).

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### StatisticDate

The date (in UTC time) for which we are storing the statistics.

Type: **date**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### StatisticFromTimeUtc

The starting of the time period within the date.

Type: **time**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StatisticToTimeUtc

The ending of the time period within the date.

Type: **time**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StatisticType

The type of the statistic: 'EXE' = Exec, 'WAI' = Wait, 'TAB' = Table, 'PER' = Performance, 'SIT' = Site

Type: **[StatisticType](Systems.Monitoring.InstanceStatistics.md#statistictype)**  
Indexed: **True**  
Category: **System**  
Allowed values for the `StatisticType`(Systems.Monitoring.InstanceStatistics.md#statistictype) data attribute  
Allowed Values (Systems.Monitoring.InstanceStatisticsRepository.StatisticType Enum Members)  

| Value | Description |
| ---- | --- |
| Exec | Exec value. Stored as 'EXE'. <br /> Database Value: 'EXE' <br /> Model Value: 0 <br /> Domain API Value: 'Exec' |
| Wait | Wait value. Stored as 'WAI'. <br /> Database Value: 'WAI' <br /> Model Value: 1 <br /> Domain API Value: 'Wait' |
| Table | Table value. Stored as 'TAB'. <br /> Database Value: 'TAB' <br /> Model Value: 2 <br /> Domain API Value: 'Table' |
| Perf | Perf value. Stored as 'PER'. <br /> Database Value: 'PER' <br /> Model Value: 3 <br /> Domain API Value: 'Perf' |
| Site | Site value. Stored as 'SIT'. <br /> Database Value: 'SIT' <br /> Model Value: 4 <br /> Domain API Value: 'Site' |
| Parameter | Parameter value. Stored as 'PAR'. <br /> Database Value: 'PAR' <br /> Model Value: 5 <br /> Domain API Value: 'Parameter' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### SubType

Kind of stat (depending on the type).

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Total

The total of the stat for the time period.

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UnitOfMeasure

Unit of measure for Total and Max.

Type: **string (10)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **10**  
Show in UI: **ShownByDefault**  

### Value

Holds the metric in text when numeric fields can't represent it.

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Show in UI: **ShownByDefault**  

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

[!list limit=1000 erp.entity=Systems.Monitoring.InstanceStatistics erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Monitoring.InstanceStatistics erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Monitoring_InstanceStatistics

Domain API Entity Type: 
Systems_Monitoring_InstanceStatistic

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Monitoring_InstanceStatistics?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_InstanceStatistics?$top=10>

