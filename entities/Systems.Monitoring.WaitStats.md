---
uid: Systems.Monitoring.WaitStats
---
# Systems.Monitoring.WaitStats View

**Namespace:** [Systems.Monitoring](Systems.Monitoring.md)  

Wait statistics dynamic management view. Entity: Dmv_Wait_Stats (Introduced in version 25.1.0.38)

## Default Visualization
Default Display Text Format:  
_{Database}: {WaitCategory}_  
Default Search Members:  
__  
Category:  _DynamicViews_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Monitoring.WaitStats](Systems.Monitoring.WaitStats.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Database](Systems.Monitoring.WaitStats.md#database) | string (64) | The database in which the wait operation is located. `Required` `Filter(eq;like)` `ORD` 
| [MaxHoldLockTimeMs](Systems.Monitoring.WaitStats.md#maxholdlocktimems) | double | Maximum time a lock was held, measured in milliseconds. `Required` 
| [MaxWaitTimeMs](Systems.Monitoring.WaitStats.md#maxwaittimems) | double | Maximum wait time for acquiring a lock, measured in milliseconds.       . `Required` 
| [StatisticsSince](Systems.Monitoring.WaitStats.md#statisticssince) | datetime | The date and time since when the statistics are collected. `Required` `Filter(ge;le)` 
| [TotalFailedAttempts](Systems.Monitoring.WaitStats.md#totalfailedattempts) | double | Indicates the total number of unsuccessful attempts to acquire locks. `Required` 
| [TotalFailWaitTimeMs](Systems.Monitoring.WaitStats.md#totalfailwaittimems) | double | Общо време на изчакване за неуспешни заключвания, измерено в милисекунди. `Required` 
| [TotalHoldLockTimeMs](Systems.Monitoring.WaitStats.md#totalholdlocktimems) | double | Indicates the total duration locks are held, measured in milliseconds. `Required` 
| [TotalLocks](Systems.Monitoring.WaitStats.md#totallocks) | double | The total number of locks. `Required` 
| [TotalSuccessWaitTimeMs](Systems.Monitoring.WaitStats.md#totalsuccesswaittimems) | double | Indicates the cumulative time spent waiting for successful lock acquisitions, measured in milliseconds. `Required` 
| [TotalWaitLocks](Systems.Monitoring.WaitStats.md#totalwaitlocks) | double | Indicates the total number of locks that have been acquired after waiting. `Required` 
| [WaitCategory](Systems.Monitoring.WaitStats.md#waitcategory) | string (128) | The category of the wait operation. `Required` 


## Attribute Details

### Database

The database in which the wait operation is located. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### MaxHoldLockTimeMs

Maximum time a lock was held, measured in milliseconds. `Required`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### MaxWaitTimeMs

Maximum wait time for acquiring a lock, measured in milliseconds.       . `Required`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StatisticsSince

The date and time since when the statistics are collected. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalFailedAttempts

Indicates the total number of unsuccessful attempts to acquire locks. `Required`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalFailWaitTimeMs

Общо време на изчакване за неуспешни заключвания, измерено в милисекунди. `Required`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalHoldLockTimeMs

Indicates the total duration locks are held, measured in milliseconds. `Required`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalLocks

The total number of locks. `Required`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalSuccessWaitTimeMs

Indicates the cumulative time spent waiting for successful lock acquisitions, measured in milliseconds. `Required`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TotalWaitLocks

Indicates the total number of locks that have been acquired after waiting. `Required`

_Type_: **double**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### WaitCategory

The category of the wait operation. `Required`

_Type_: **string (128)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### ResetStats

Reset wait statistics  
_Return Type_: **void**  
_Declaring Type_: **[WaitStats](Systems.Monitoring.WaitStats.md)**  
_Domain API Request_: **POST**  

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Monitoring_WaitStats?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Monitoring_WaitStats?$top=10>

