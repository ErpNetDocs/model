# View Cmm_Social_Reactions_Summary


## Entity

Entity: [Communities.Social.ReactionsSummary](~/entities/Communities.Social.ReactionsSummary.md)

Summary with the social reactions per comment and dataobject. Entity: Cmm_Social_Reactions_Summary (Introduced in version 22.1.6.73)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Cnt](#cnt)|`bigint` |Count of social reactions.|
|[Data_Object_Id](#data_object_id)|`uniqueidentifier` |The extensible data object.|
|[Reaction_Type](#reaction_type)|`char(3)` Allowed: `LIK`, `LOV`, `HAH`, `WOW`, `SAD`, `ANG`|The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry.|
|[Social_Comment_Id](#social_comment_id)|`uniqueidentifier` |The social comment.|

## Columns

### Cnt


Count of social reactions.

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
|Type|bigint|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Data_Object_Id


The extensible data object.

| Property | Value |
| - | - |
|Auto Complete|no|
|Base Table.Column|[Sys_Objects](Sys_Objects.md).[Object_Id](Sys_Objects.md#object_id)|
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
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Data_Object_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Reaction_Type


The type of the reaction. LIK = Like; LOV = Love; HAH = Haha; WOW = Wow; SAD = Sad; ANG = Angry.

| Property | Value |
| - | - |
|Allowed Values|`LIK`, `LOV`, `HAH`, `WOW`, `SAD`, `ANG`|
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
|Supports EQUALS_IN|no|
|Type|char(3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Social_Comment_Id


The social comment.

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
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Social_Comment_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|


