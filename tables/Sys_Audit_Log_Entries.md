# Table Sys_Audit_Log_Entries


## Entity

Entity: [Systems.Monitoring.AuditLogEntries](~/entities/Systems.Monitoring.AuditLogEntries.md)

Each record represents the occurrence of one logged event. Entity: Sys_Audit_Log_Entries (Introduced in version 18.2)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Application_Name](#application_name)|`nvarchar(64)` |The client application that triggered the event. Null when unknown or N/A.|
|[Audit_Log_Entry_Id](#audit_log_entry_id)|`uniqueidentifier` `PK`||
|[Details](#details)|`nvarchar(max)` |Detailed contents of the event. Contents depend on the Event Type and Event Name.|
|[Entity_Item_Id](#entity_item_id)|`uniqueidentifier` |The Id of the record, which is referenced by the event. Null when unknown or N/A.|
|[Entity_Name](#entity_name)|`nvarchar(64)` |The entity, which is being referenced by the event. Null when unknown or N/A.|
|[Event_Class](#event_class)|`char(1)` Allowed: `E`, `A`, `S`, `P`|The event primary classification, which shows the source of the event. E=Entity methods; A=Auth events; S=Server events.|
|[Event_Name](#event_name)|`nvarchar(128)` |Specific event or method name. Contents depend on the Event Type. Null when N/A.|
|[Event_Time_Utc](#event_time_utc)|`datetime` |The exact date and time (in Utc) when the event occurred.|
|[Event_Type](#event_type)|`char(3)` Allowed: `EID`, `ELD`, `ECR`, `EUP`, `EDE`, `EMT`, `ETH`, `AIN`, `AOU`, `AUP`, `AFL`, `APW`, `ATH`, `STH`, `APC`|Detailed action type. EID=Read one record by Id; ELD=Load many records; EUP=Update data; EDE=Delete record; EMT=Call method; ETH=Other entity event; AIN=Login; AOU=Log out; AUP=Sign Up; AFL=Login failed; APW=Change password; ATH=Other auth event; STH=Other server event.|
|[Personal_Data_Process_Id](#personal_data_process_id)|`uniqueidentifier` |The personal data process, which was used to process the data, referenced by the event. Null when unknown or N/A.|
|[Row_Version](#row_version)|`timestamp` ||
|[User_Id](#user_id)|`uniqueidentifier` |The user account under which the event has occurred. Null only for events which are not user-specific.|

## Columns

### Application_Name


The client application that triggered the event. Null when unknown or N/A.

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
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(64) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Application_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|
|Like|None|no|no|

### Audit_Log_Entry_Id

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|NewGuid|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
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

#### Audit_Log_Entry_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Details


Detailed contents of the event. Contents depend on the Event Type and Event Name.

| Property | Value |
| - | - |
|Attributes|IsLongString|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
|Order|2147483647|
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

### Entity_Item_Id


The Id of the record, which is referenced by the event. Null when unknown or N/A.

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
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Entity_Item_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Entity_Name


The entity, which is being referenced by the event. Null when unknown or N/A.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|yes|
|Max Length|64|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(64) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Entity_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|
|Like|None|no|no|

### Event_Class


The event primary classification, which shows the source of the event. E=Entity methods; A=Auth events; S=Server events.

| Property | Value |
| - | - |
|Allowed Values|`E`, `A`, `S`, `P`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
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
|Type|char(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Event_Class - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Event_Name


Specific event or method name. Contents depend on the Event Type. Null when N/A.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|128|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(128) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Event_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|
|Like|None|no|no|

### Event_Time_Utc


The exact date and time (in Utc) when the event occurred.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|CurrentDateTime|
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

#### Event_Time_Utc - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|GreaterThanOrLessThan|None|no|no|

### Event_Type


Detailed action type. EID=Read one record by Id; ELD=Load many records; EUP=Update data; EDE=Delete record; EMT=Call method; ETH=Other entity event; AIN=Login; AOU=Log out; AUP=Sign Up; AFL=Login failed; APW=Change password; ATH=Other auth event; STH=Other server event.

| Property | Value |
| - | - |
|Allowed Values|`EID`, `ELD`, `ECR`, `EUP`, `EDE`, `EMT`, `ETH`, `AIN`, `AOU`, `AUP`, `AFL`, `APW`, `ATH`, `STH`, `APC`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
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

#### Event_Type - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Personal_Data_Process_Id


The personal data process, which was used to process the data, referenced by the event. Null when unknown or N/A.

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
|Referenced Table|[Pdm_Personal_Data_Processes](Pdm_Personal_Data_Processes.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Personal_Data_Process_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

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
|Order|2147483647|
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

### User_Id


The user account under which the event has occurred. Null only for events which are not user-specific.

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
|Referenced Table|[Sec_Users](Sec_Users.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### User_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|


