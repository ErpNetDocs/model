# Table Sys_Jobs


## Entity

Entity: [Systems.Config.Jobs](~/entities/Systems.Config.Jobs.md)

The jobs, which are configured in the system. Entity: Sys_Jobs (Introduced in version 20.1)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Is_Active](#is_active)|`bit` |Specifies whether the job is active and ready for running.|
|[Job_Configurations](#job_configurations)|`nvarchar(max)` |The field specifies additional parameters for the execution of the Job in JSON format. NULL means that there are no specific parameters.|
|[Job_Id](#job_id)|`uniqueidentifier` `PK`||
|[Job_Name](#job_name)|`nvarchar(254)` |The name of the job.|
|[Job_Type](#job_type)|`char(3)` Allowed: `DOC`, `POS`, `DNT`, `DPI`, `DDV`, `DIM`, `DAC`, `DAL`, `CTE`, `CRC`, `ICP`, `DRT`|The system type of the job. DOC=Document Change State, POS=Run Postponed Events, DNT=Delete Old Notifications, DPI=Delete Old Print Images, DDV=Delete Old Document Versions, DIM=Delete Old Information Messages.|
|[Notes](#notes)|`nvarchar(max)` ||
|[Row_Version](#row_version)|`timestamp` ||
|[Run_On_Idle](#run_on_idle)|`bit` |Specifies whether to automatically run the job when the server is idle.|
|[Schedule](#schedule)|`char(3)` Allowed: `NON`, `NGH`|Defines the execution schedule of the Job.|

## Columns

### Is_Active


Specifies whether the job is active and ready for running.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|True|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|3|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|bit|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Is_Active - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Job_Configurations


The field specifies additional parameters for the execution of the Job in JSON format. NULL means that there are no specific parameters.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
|Order|7|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|yes|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Job_Configurations - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

### Job_Id

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|NewGuid|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|0|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|yes (order: 1)|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Job_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Job_Name


The name of the job.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
|Order|2|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(254)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Job_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|Like|None|no|no|

### Job_Type


The system type of the job. DOC=Document Change State, POS=Run Postponed Events, DNT=Delete Old Notifications, DPI=Delete Old Print Images, DDV=Delete Old Document Versions, DIM=Delete Old Information Messages.

| Property | Value |
| - | - |
|Allowed Values|`DOC`, `POS`, `DNT`, `DPI`, `DDV`, `DIM`, `DAC`, `DAL`, `CTE`, `CRC`, `ICP`, `DRT`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|3|
|Order|1|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|char(3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Job_Type - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Notes

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
|Order|4|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Row_Version

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|6|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|timestamp|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Run_On_Idle


Specifies whether to automatically run the job when the server is idle.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|True|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|5|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|bit|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Run_On_Idle - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Schedule


Defines the execution schedule of the Job.

| Property | Value |
| - | - |
|Allowed Values|`NON`, `NGH`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|NON|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|3|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|char(3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Schedule - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|


