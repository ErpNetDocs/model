# View Dmv_Apps_Performance


## Entity

Entity: [Systems.Monitoring.AppsPerformance](~/entities/Systems.Monitoring.AppsPerformance.md)

Applications performance statistics dynamic management view. Entity: Dmv_Apps_Performance (Introduced in version 25.1.3.47)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Application](#application)|`nvarchar(64)` |The name of the application that executes the operation|
|[Busy_Time_Hours_Per_Day](#busy_time_hours_per_day)|`float` |Busy time in percentage per day|
|[Busy_Time_Percentage](#busy_time_percentage)|`float` |Busy time in percentage|
|[Requests](#requests)|`float` |The number of requests per minute the application has made to the server|
|[Statistics_Since](#statistics_since)|`datetime` |The date and time since when the statistics are collected|

## Columns

### Application


The name of the application that executes the operation

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|64|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(64)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Application - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|no|

### Busy_Time_Hours_Per_Day


Busy time in percentage per day

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Format|N2|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|float|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Busy_Time_Hours_Per_Day - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|GreaterThanOrLessThan|None|no|no|

### Busy_Time_Percentage


Busy time in percentage

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Format|N2|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|float|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Busy_Time_Percentage - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|GreaterThanOrLessThan|None|no|no|

### Requests


The number of requests per minute the application has made to the server

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Format|N2|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|float|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Requests - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|
|Like|None|no|no|

### Statistics_Since


The date and time since when the statistics are collected

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|datetime|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Statistics_Since - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|GreaterThanOrLessThan|None|no|no|


