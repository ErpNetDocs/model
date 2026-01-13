# Table Sys_Resolved_Conflicts


## Entity

Entity: [Systems.Monitoring.ResolvedConflicts](~/entities/Systems.Monitoring.ResolvedConflicts.md)

Contains records of conflicts, which were automatically resolved by update procedures. Entity: Sys_Resolved_Conflicts

## Summary

| Name | Type | Description |
| - | - | --- |
|[Conflict_Description](#conflict_description)|`nvarchar(400)` `ML`, Readonly|Description of the conflict.|
|[Resolve_Confirmed_By_User](#resolve_confirmed_by_user)|`bit` |True, when the conflict resolution was manually confirmed by user.|
|[Resolve_Confirmed_Time](#resolve_confirmed_time)|`datetime` Readonly|Time when the conflict resolution was confirmed by the user.|
|[Resolve_Description](#resolve_description)|`nvarchar(400)` `ML`, Readonly|Description of the resolution of the conflict.|
|[Resolved_Conflict_Id](#resolved_conflict_id)|`uniqueidentifier` `PK`|Unique identification of the resolved conflict.|
|[Resolved_Time](#resolved_time)|`datetime` Readonly|Time when the resolution of the conflict was made.|
|[Revised_By_User](#revised_by_user)|`bit` Readonly|True, when the conflict resolution was revised (reviewed) manually by user.|
|[Row_Version](#row_version)|`timestamp` ||
|[Table_Name](#table_name)|`nvarchar(64)` `ML`, Readonly|Name of the table in which the conflict has occurred.|
|[URL](#url)|`nvarchar(254)` Readonly|URL of the item (the row) for which the conflict occurred.|

## Columns

### Conflict_Description


Description of the conflict.

| Property | Value |
| - | - |
|Attributes|IsLongString|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|400|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(400) (MultiLanguage)|
|UI Memo Editor|no|
|UI Width|Long|
|User Login|no|
|Visible|yes|

### Resolve_Confirmed_By_User


True, when the conflict resolution was manually confirmed by user.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|False|
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
|Type|bit|
|UI Memo Editor|no|
|UI Width|Short|
|User Login|yes|
|Visible|yes|

#### Resolve_Confirmed_By_User - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Resolve_Confirmed_Time


Time when the conflict resolution was confirmed by the user.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|datetime (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Resolve_Confirmed_Time - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|GreaterThanOrLessThan|None|no|no|

### Resolve_Description


Description of the resolution of the conflict.

| Property | Value |
| - | - |
|Attributes|IsLongString|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|400|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(400) (MultiLanguage)|
|UI Memo Editor|no|
|UI Width|Long|
|User Login|no|
|Visible|yes|

### Resolved_Conflict_Id


Unique identification of the resolved conflict.

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

#### Resolved_Conflict_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### Resolved_Time


Time when the resolution of the conflict was made.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|CurrentDateTime|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|datetime|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Resolved_Time - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|GreaterThanOrLessThan|None|no|no|

### Revised_By_User


True, when the conflict resolution was revised (reviewed) manually by user.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|False|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|bit|
|UI Memo Editor|no|
|UI Width|Short|
|User Login|yes|
|Visible|yes|

#### Revised_By_User - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

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

### Table_Name


Name of the table in which the conflict has occurred.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|64|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(64) (MultiLanguage)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Table_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

### URL


URL of the item (the row) for which the conflict occurred.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|no|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(254)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|


