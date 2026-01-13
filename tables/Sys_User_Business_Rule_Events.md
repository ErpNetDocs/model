# Table Sys_User_Business_Rule_Events


## Entity

Entity: [Systems.Bpm.UserBusinessRuleEvents](~/entities/Systems.Bpm.UserBusinessRuleEvents.md)

Represents event registration of a business rule. Entity: Sys_User_Business_Rule_Events

## Owner Tables Hierarchy

* [Sys_User_Business_Rules](Sys_User_Business_Rules.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Event_Parameter](#event_parameter)|`nvarchar(128)` |Registration parameter. The meaning is determined by the event. Usually - attribute name, document state, etc.|
|[Event_Type](#event_type)|`nvarchar(64)` Allowed: `AGGREGATECLIENTCOMMIT`, `ATTRIBUTECHANGED`, `ATTRIBUTECHANGING`, `CLIENTCOMMIT`, `COMMIT`, `STATECHANGED`, `STATECHANGING`, `VOIDING`, `CREATENEW`, `COMMITTED`, `CLIENTCOMMITTED`, `AGGREGATECLIENTCOMMITTED`, `BEFORERECALCULATE `|The event for which to register the business rule.|
|[Execution_Priority](#execution_priority)|`int` Allowed: `30`, `50`, `70`|Execution priority. Lower values indicate earlier priorities. Possible values - 30-Early, 50-Normal, 70-Late.|
|[Layer](#layer)|`char(3)` Allowed: `FTE`, `BKE`|Specifies the layer on which to register the event. Allowed values = FTE-FrontEnd, BKE-BackEnd.|
|[Row_Version](#row_version)|`timestamp` ||
|[User_Business_Rule_Event_Id](#user_business_rule_event_id)|`uniqueidentifier` `PK`||
|[User_Business_Rule_Id](#user_business_rule_id)|`uniqueidentifier` |The rule, which will be registered for the event.|

## Columns

### Event_Parameter


Registration parameter. The meaning is determined by the event. Usually - attribute name, document state, etc.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|128|
|Order|2|
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

### Event_Type


The event for which to register the business rule.

| Property | Value |
| - | - |
|Allowed Values|`AGGREGATECLIENTCOMMIT`, `ATTRIBUTECHANGED`, `ATTRIBUTECHANGING`, `CLIENTCOMMIT`, `COMMIT`, `STATECHANGED`, `STATECHANGING`, `VOIDING`, `CREATENEW`, `COMMITTED`, `CLIENTCOMMITTED`, `AGGREGATECLIENTCOMMITTED`, `BEFORERECALCULATE `|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|64|
|Order|1|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(64)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Execution_Priority


Execution priority. Lower values indicate earlier priorities. Possible values - 30-Early, 50-Normal, 70-Late.

| Property | Value |
| - | - |
|Allowed Values|`30`, `50`, `70`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|50|
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
|Type|int|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Layer


Specifies the layer on which to register the event. Allowed values = FTE-FrontEnd, BKE-BackEnd.

| Property | Value |
| - | - |
|Allowed Values|`FTE`, `BKE`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|BKE|
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
|Supports EQUALS_IN|no|
|Type|char(3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

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

### User_Business_Rule_Event_Id

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

#### User_Business_Rule_Event_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### User_Business_Rule_Id


The rule, which will be registered for the event.

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
|Ownership Reference|yes|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Sys_User_Business_Rules](Sys_User_Business_Rules.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### User_Business_Rule_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|


