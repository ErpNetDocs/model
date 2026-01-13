# Table Cm_Contact_Mechanisms


## Entity

Entity: [General.Contacts.ContactMechanisms](~/entities/General.Contacts.ContactMechanisms.md)

Contains contacting mechanisms - telephone numbers, addresses, web sites, etc. Contact mechanisms can be attached to parties. Currently each contact mechanism is attached to strictly one party. Entity: Cm_Contact_Mechanisms

## Summary

| Name | Type | Description |
| - | - | --- |
|[Administrative_Region_Id](#administrative_region_id)|`uniqueidentifier` |The administrative region, where the contact mechanism is situated. Null if this is unknown or N/A.|
|[Contact_Mechanism_Name](#contact_mechanism_name)|`nvarchar(254)` |Contact mechanism description|
|[Contact_Mechanism_Type](#contact_mechanism_type)|`char(1)` Allowed: `A`, `E`, `F`, `M`, `O`, `T`, `W`, `P`, `X`|A=Address; E=e-mail; T=Telephone|
|[Geo_Point_Id](#geo_point_id)|`uniqueidentifier` |The geographical point, where the contact mechanism is situated. Null if this is unknown or N/A.|
|[Id](#id)|`uniqueidentifier` `PK`|Unique contact mechanism Id|
|[Row_Version](#row_version)|`timestamp` ||

## Columns

### Administrative_Region_Id


The administrative region, where the contact mechanism is situated. Null if this is unknown or N/A.

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
|Referenced Table|[Gen_Administrative_Regions](Gen_Administrative_Regions.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Administrative_Region_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Contact_Mechanism_Name


Contact mechanism description

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
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
|Type|nvarchar(254)|
|UI Memo Editor|no|
|UI Width|Long|
|User Login|no|
|Visible|yes|

#### Contact_Mechanism_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|
|Like|None|no|no|

### Contact_Mechanism_Type


A=Address; E=e-mail; T=Telephone

| Property | Value |
| - | - |
|Allowed Values|`A`, `E`, `F`, `M`, `O`, `T`, `W`, `P`, `X`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|A|
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

#### Contact_Mechanism_Type - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Geo_Point_Id


The geographical point, where the contact mechanism is situated. Null if this is unknown or N/A.

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
|Referenced Table|[Gen_Geo_Points](Gen_Geo_Points.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Geo_Point_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Id


Unique contact mechanism Id

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

#### Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|
|GreaterThanOrLessThan|None|no|yes|

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


