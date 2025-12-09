# Table Saft_Profile_Measurement_Units


## Entity

Entity: [Finance.Saft.ProfileMeasurementUnits](~/entities/Finance.Saft.ProfileMeasurementUnits.md)

A mapping table defining the relationship between a SAFT profile and the measurement units associated with it. Stores the selected measurement unit and its required SAFT code used when generating the SAFT file. Entity: Saft_Profile_Measurement_Units (Introduced in version 26.2.0.74)

## Owner Tables Hierarchy

* [Saft_Profiles](Saft_Profiles.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Measurement_Unit_Code_Entry_Id](#measurement_unit_code_entry_id)|`uniqueidentifier` |Measurement unit code used when generating the SAFT file.|
|[Measurement_Unit_Id](#measurement_unit_id)|`uniqueidentifier` |Measurement unit used for this SAFT profile.|
|[Notes](#notes)|`nvarchar(max)` |Additional information or comments for this entry.|
|[Profile_Id](#profile_id)|`uniqueidentifier` |Identifier of the SAFT profile associated with this measurement unit.|
|[Row_Version](#row_version)|`timestamp` ||
|[Saft_Profile_Measurement_Unit_Id](#saft_profile_measurement_unit_id)|`uniqueidentifier` `PK`|Auto-generated GUID for this record.|

## Columns

### Measurement_Unit_Code_Entry_Id


Measurement unit code used when generating the SAFT file.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
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
|Referenced Table|[Reg_Code_Entries](Reg_Code_Entries.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Measurement_Unit_Code_Entry_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Measurement_Unit_Id


Measurement unit used for this SAFT profile.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Gen_Measurement_Units](Gen_Measurement_Units.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Measurement_Unit_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Notes


Additional information or comments for this entry.

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

#### Notes - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

### Profile_Id


Identifier of the SAFT profile associated with this measurement unit.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|1|
|Ownership Reference|yes|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Saft_Profiles](Saft_Profiles.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Profile_Id - Supported Filters

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
|Type|timestamp|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

### Saft_Profile_Measurement_Unit_Id


Auto-generated GUID for this record.

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

#### Saft_Profile_Measurement_Unit_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|


