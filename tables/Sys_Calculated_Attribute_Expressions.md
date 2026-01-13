# Table Sys_Calculated_Attribute_Expressions


## Entity

Entity: [Systems.Bpm.CalculatedAttributeExpressions](~/entities/Systems.Bpm.CalculatedAttributeExpressions.md)

Represent an expression within the calculation of a calculated attribute. Entity: Sys_Calculated_Attribute_Expressions

## Owner Tables Hierarchy

* [Sys_Calculated_Attributes](Sys_Calculated_Attributes.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Calculated_Attribute_Expression_Id](#calculated_attribute_expression_id)|`uniqueidentifier` `PK`||
|[Calculated_Attribute_Id](#calculated_attribute_id)|`uniqueidentifier` ||
|[Expression_No](#expression_no)|`int` |Unique number of the expression within the attribute. Expression No 0 is the default expression, which provides the result value of the attribute.|
|[Notes](#notes)|`nvarchar(max)` ||
|[Operator](#operator)|`nvarchar(16)` Allowed: `ADD`, `ADDDAYS`, `AND`, `CAST`, `CEILING`, `CONCAT`, `CONVERT`, `COUNT`, `DIVIDE`, `IN`, `IIF`, `INCNUM`, `EQUAL`, `FILTER`, `FIRST`, `FLOOR`, `FORMATSTRING`, `GETVALUE`, `GETOBJVALUE`, `GT`, `GTE`, `LIKE`, `LIST`, `LEFT`, `LEN`, `LT`, `LTE`, `MULTIPLY`, `NOT`, `OR`, `ORDERBY`, `POS`, `REGEX`, `REPLACE`, `RIGHT`, `ROUND`, `SELECT`, `SORT`, `SUBSTRING`, `SUM`, `TODAY`, `TOLOWER`, `TOP`, `TOUPPER`, `WHERE`, `INTERPOLATE`, `DATEDIFF`, `DATESPAN`, `IFERROR`|The exprssion operator. Available operators are limited to a pre-selected list of operators.|
|[Parameter1_Type](#parameter1_type)|`nvarchar(16)` Allowed: `CONST`, `ATTRIB`, `REF`, `CHILD`, `EXP`, `INPUT`, `REPO`, `SYS`|The type of the parameter specifies how to obtain the parameter value.|
|[Parameter1_Value](#parameter1_value)|`nvarchar(256)` |The actual value of parameter 1.|
|[Parameter2_Type](#parameter2_type)|`nvarchar(16)` Allowed: `CONST`, `ATTRIB`, `REF`, `CHILD`, `EXP`, `INPUT`, `REPO`, `SYS`|The type of the parameter specifies how to obtain the parameter value.|
|[Parameter2_Value](#parameter2_value)|`nvarchar(256)` |The actual value of the parameter.|
|[Parameter3_Type](#parameter3_type)|`nvarchar(16)` Allowed: `CONST`, `ATTRIB`, `REF`, `CHILD`, `EXP`, `INPUT`, `REPO`, `SYS`|The type of the parameter specifies how to obtain the parameter value.|
|[Parameter3_Value](#parameter3_value)|`nvarchar(256)` |The actual value of the parameter.|
|[Row_Version](#row_version)|`timestamp` ||

## Columns

### Calculated_Attribute_Expression_Id

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

#### Calculated_Attribute_Expression_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### Calculated_Attribute_Id

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
|Referenced Table|[Sys_Calculated_Attributes](Sys_Calculated_Attributes.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Calculated_Attribute_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Expression_No


Unique number of the expression within the attribute. Expression No 0 is the default expression, which provides the result value of the attribute.

| Property | Value |
| - | - |
|Auto Complete|no|
|Autoincrement|10|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
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
|Type|int|
|UI Memo Editor|no|
|UI Width|Short|
|User Login|no|
|Visible|yes|

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
|Order|14|
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
|UI Width|Long|
|User Login|no|
|Visible|yes|

### Operator


The exprssion operator. Available operators are limited to a pre-selected list of operators.

| Property | Value |
| - | - |
|Allowed Values|`ADD`, `ADDDAYS`, `AND`, `CAST`, `CEILING`, `CONCAT`, `CONVERT`, `COUNT`, `DIVIDE`, `IN`, `IIF`, `INCNUM`, `EQUAL`, `FILTER`, `FIRST`, `FLOOR`, `FORMATSTRING`, `GETVALUE`, `GETOBJVALUE`, `GT`, `GTE`, `LIKE`, `LIST`, `LEFT`, `LEN`, `LT`, `LTE`, `MULTIPLY`, `NOT`, `OR`, `ORDERBY`, `POS`, `REGEX`, `REPLACE`, `RIGHT`, `ROUND`, `SELECT`, `SORT`, `SUBSTRING`, `SUM`, `TODAY`, `TOLOWER`, `TOP`, `TOUPPER`, `WHERE`, `INTERPOLATE`, `DATEDIFF`, `DATESPAN`, `IFERROR`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|16|
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
|Type|nvarchar(16)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Parameter1_Type


The type of the parameter specifies how to obtain the parameter value.

| Property | Value |
| - | - |
|Allowed Values|`CONST`, `ATTRIB`, `REF`, `CHILD`, `EXP`, `INPUT`, `REPO`, `SYS`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|16|
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
|Type|nvarchar(16) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Parameter1_Value


The actual value of parameter 1.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|256|
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
|Type|nvarchar(256) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Parameter2_Type


The type of the parameter specifies how to obtain the parameter value.

| Property | Value |
| - | - |
|Allowed Values|`CONST`, `ATTRIB`, `REF`, `CHILD`, `EXP`, `INPUT`, `REPO`, `SYS`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|16|
|Order|8|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(16) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Parameter2_Value


The actual value of the parameter.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|256|
|Order|10|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(256) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Parameter3_Type


The type of the parameter specifies how to obtain the parameter value.

| Property | Value |
| - | - |
|Allowed Values|`CONST`, `ATTRIB`, `REF`, `CHILD`, `EXP`, `INPUT`, `REPO`, `SYS`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|16|
|Order|11|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(16) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Parameter3_Value


The actual value of the parameter.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|256|
|Order|13|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(256) (Allows NULL)|
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


