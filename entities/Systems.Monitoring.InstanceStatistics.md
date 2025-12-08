---
uid: Systems.Monitoring.InstanceStatistics
---
# Systems.Monitoring.InstanceStatistics Entity

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Logs time-windowed performance metrics for the monitored system instance across specified intervals. Entity: Sys_Instance_Statistics (Introduced in version 25.1.3.11)

## Default Visualization
Default Display Text Format:  
_{ApplicationName}_  
Default Search Members:  
_ApplicationName_  
Name Data Member:  
_ApplicationName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.InstanceStatistics](Systems.Monitoring.InstanceStatistics.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationName](Systems.Monitoring.InstanceStatistics.md#applicationname) | string (128) __nullable__ | The application (if applicable) for which we are recording stats. `Filter(eq;like)` 
| [Avg](Systems.Monitoring.InstanceStatistics.md#avg) | int32 __nullable__ | The avg value of the stat for the time period. `Filter(ge;le)` 
| [Count](Systems.Monitoring.InstanceStatistics.md#count) | int32 | Number of occurrences. `Required` `Filter(ge;le)` 
| [DisplayText](Systems.Monitoring.InstanceStatistics.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExcludeFromSummary](Systems.Monitoring.InstanceStatistics.md#excludefromsummary) | boolean | Denotes that the stat should be excluded from summarization queries (for example long polling requests). `Required` 
| [ExternalId](Systems.Monitoring.InstanceStatistics.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Monitoring.InstanceStatistics.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Monitoring.InstanceStatistics.md#id) | guid |  
| [InstanceName](Systems.Monitoring.InstanceStatistics.md#instancename) | string (128) | The name of the instance to which this statistic applies. `Required` `Filter(eq;like)` 
| [Max](Systems.Monitoring.InstanceStatistics.md#max) | int32 __nullable__ | The max value of the stat within the time period. `Filter(ge;le)` 
| [ObjectName](Systems.Monitoring.InstanceStatistics.md#objectname) | string (256) __nullable__ | Name of the object or operation (depending on the statistic type). 
| [ObjectVersion](Systems.Monitoring.InstanceStatistics.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StatisticDate](Systems.Monitoring.InstanceStatistics.md#statisticdate) | date | The date (in UTC time) for which we are storing the statistics. `Required` `Filter(eq;ge;le)` `ORD` 
| [StatisticFromTimeUtc](Systems.Monitoring.InstanceStatistics.md#statisticfromtimeutc) | time | The starting of the time period within the date. `Required` `Filter(ge;le)` 
| [StatisticToTimeUtc](Systems.Monitoring.InstanceStatistics.md#statistictotimeutc) | time | The ending of the time period within the date. `Required` `Filter(ge;le)` 
| [StatisticType](Systems.Monitoring.InstanceStatistics.md#statistictype) | [StatisticType](Systems.Monitoring.InstanceStatistics.md#statistictype) | The type of the statistic: 'EXE' = Exec, 'WAI' = Wait, 'TAB' = Table, 'PER' = Performance, 'SIT' = Site. `Required` `Filter(multi eq)` `ORD` 
| [SubType](Systems.Monitoring.InstanceStatistics.md#subtype) | string (64) | Kind of stat (depending on the type). `Required` `Filter(eq)` 
| [Total](Systems.Monitoring.InstanceStatistics.md#total) | int32 | The total of the stat for the time period. `Required` `Filter(ge;le)` 
| [UnitOfMeasure](Systems.Monitoring.InstanceStatistics.md#unitofmeasure) | string (10) | Unit of measure for Total and Max. `Required` `Filter(eq)` 
| [Value](Systems.Monitoring.InstanceStatistics.md#value) | string (64) __nullable__ | Holds the metric in text when numeric fields can't represent it. `Introduced in version 26.2.0.73` 


## Attribute Details

### ApplicationName

The application (if applicable) for which we are recording stats. `Filter(eq;like)`

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Avg

The avg value of the stat for the time period. `Filter(ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Count

Number of occurrences. `Required` `Filter(ge;le)`

_Type_: **int32**  
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

### ExcludeFromSummary

Denotes that the stat should be excluded from summarization queries (for example long polling requests). `Required`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### InstanceName

The name of the instance to which this statistic applies. `Required` `Filter(eq;like)`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### Max

The max value of the stat within the time period. `Filter(ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectName

Name of the object or operation (depending on the statistic type).

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### StatisticDate

The date (in UTC time) for which we are storing the statistics. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **date**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### StatisticFromTimeUtc

The starting of the time period within the date. `Required` `Filter(ge;le)`

_Type_: **time**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StatisticToTimeUtc

The ending of the time period within the date. `Required` `Filter(ge;le)`

_Type_: **time**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StatisticType

The type of the statistic: 'EXE' = Exec, 'WAI' = Wait, 'TAB' = Table, 'PER' = Performance, 'SIT' = Site. `Required` `Filter(multi eq)` `ORD`

_Type_: **[StatisticType](Systems.Monitoring.InstanceStatistics.md#statistictype)**  
_Indexed_: **True**  
_Category_: **System**  
Allowed values for the `StatisticType`(Systems.Monitoring.InstanceStatistics.md#statistictype) data attribute  
_Allowed Values (Systems.Monitoring.InstanceStatisticsRepository.StatisticType Enum Members)_  

| Value | Description |
| ---- | --- |
| Exec | Exec value. Stored as 'EXE'. <br /> _Database Value:_ 'EXE' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Exec' |
| Wait | Wait value. Stored as 'WAI'. <br /> _Database Value:_ 'WAI' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Wait' |
| Table | Table value. Stored as 'TAB'. <br /> _Database Value:_ 'TAB' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Table' |
| Perf | Perf value. Stored as 'PER'. <br /> _Database Value:_ 'PER' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Perf' |
| Site | Site value. Stored as 'SIT'. <br /> _Database Value:_ 'SIT' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Site' |
| Parameter | Parameter value. Stored as 'PAR'. <br /> _Database Value:_ 'PAR' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Parameter' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

### SubType

Kind of stat (depending on the type). `Required` `Filter(eq)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Total

The total of the stat for the time period. `Required` `Filter(ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### UnitOfMeasure

Unit of measure for Total and Max. `Required` `Filter(eq)`

_Type_: **string (10)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **10**  
_Show in UI_: **ShownByDefault**  

### Value

Holds the metric in text when numeric fields can't represent it. `Introduced in version 26.2.0.73`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
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

