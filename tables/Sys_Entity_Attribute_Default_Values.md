# Table Sys_Entity_Attribute_Default_Values


## Entity

Entity: [Systems.Core.EntityAttributeDefaultValues](~/entities/Systems.Core.EntityAttributeDefaultValues.md)

Contains user-specified default values for fields in data entry forms. Entity: Sys_Entity_Attribute_Default_Values (Introduced in version 27.1.1.68)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Attribute_Name](#attribute_name)|`nvarchar(128)` |The name of the attribute in the specified repository for which the default value is defined.|
|[Condition_Enterprise_Company_Id](#condition_enterprise_company_id)|`uniqueidentifier` |When not NULL, the default value is applied only for the specified enterprise company. NULL means that no enterprise company condition is specified.|
|[Condition_Enterprise_Company_Location_Id](#condition_enterprise_company_location_id)|`uniqueidentifier` |When not NULL, the default value is applied only for the specified enterprise company location. NULL means that no enterprise company location condition is specified.|
|[Condition_Entity_Category](#condition_entity_category)|`nvarchar(254)` |When not NULL, the default value is applied only when the entity category attribute of the specified repository has this internal value. Stores the category attribute value in invariant text format; reference values are stored as GUIDs. NULL means that no entity category condition is specified.|
|[Condition_Language](#condition_language)|`nvarchar(15)` |When not NULL, the default value is applied only for the specified current language. Stores the language code, for example en or bg. NULL means that no language condition is specified.|
|[Condition_Role_Id](#condition_role_id)|`uniqueidentifier` |If not NULL, the default value is applied only when the current user has the specified role.|
|[Condition_User_Id](#condition_user_id)|`uniqueidentifier` |When not null, the default value is applied only for the specified user.|
|[Default_Internal_Value](#default_internal_value)|`nvarchar(254)` |The internal value to be assigned to the specified attribute by default. For a reference attribute, stores the ID of the selected record. NULL specifies a NULL default value.|
|[Default_Text_Value](#default_text_value)|`nvarchar(254)` |The text displayed for the default value of the specified attribute. For a reference attribute, contains the display text of the selected record.|
|[Entity_Attribute_Default_Value_Id](#entity_attribute_default_value_id)|`uniqueidentifier` `PK`|Unique identifier of the entity attribute default value.|
|[Repository_Name](#repository_name)|`nvarchar(128)` |The repository containing the attribute for which the default value is specified.|
|[Row_Version](#row_version)|`timestamp` |Automatically generated row version used for optimistic concurrency control.|

## Columns

### Attribute_Name


The name of the attribute in the specified repository for which the default value is defined.

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
|Type|nvarchar(128)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Attribute_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|Like|None|no|no|

### Condition_Enterprise_Company_Id


When not NULL, the default value is applied only for the specified enterprise company. NULL means that no enterprise company condition is specified.

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
|Referenced Table|[Gen_Enterprise_Companies](Gen_Enterprise_Companies.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Condition_Enterprise_Company_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Enterprise_Company_Location_Id


When not NULL, the default value is applied only for the specified enterprise company location. NULL means that no enterprise company location condition is specified.

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
|Referenced Table|[Cm_Company_Locations](Cm_Company_Locations.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Condition_Enterprise_Company_Location_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Entity_Category


When not NULL, the default value is applied only when the entity category attribute of the specified repository has this internal value. Stores the category attribute value in invariant text format; reference values are stored as GUIDs. NULL means that no entity category condition is specified.

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
|Type|nvarchar(254) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Condition_Entity_Category - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Language


When not NULL, the default value is applied only for the specified current language. Stores the language code, for example en or bg. NULL means that no language condition is specified.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|15|
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
|Type|nvarchar(15) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Condition_Language - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_Role_Id


If not NULL, the default value is applied only when the current user has the specified role.

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
|Referenced Table|[Wf_Roles](Wf_Roles.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Condition_Role_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Condition_User_Id


When not null, the default value is applied only for the specified user.

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

#### Condition_User_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Default_Internal_Value


The internal value to be assigned to the specified attribute by default. For a reference attribute, stores the ID of the selected record. NULL specifies a NULL default value.

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
|Type|nvarchar(254) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Default_Text_Value


The text displayed for the default value of the specified attribute. For a reference attribute, contains the display text of the selected record.

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
|Type|nvarchar(254) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Entity_Attribute_Default_Value_Id


Unique identifier of the entity attribute default value.

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

#### Entity_Attribute_Default_Value_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### Repository_Name


The repository containing the attribute for which the default value is specified.

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
|Type|nvarchar(128)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Repository_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|Like|None|no|no|

### Row_Version


Automatically generated row version used for optimistic concurrency control.

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


