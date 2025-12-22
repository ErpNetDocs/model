# Table Hrm_Governance_Policy_Revisions


## Entity

Entity: [HumanResources.Governance.GovernancePolicyRevisions](~/entities/HumanResources.Governance.GovernancePolicyRevisions.md)

Policy revisions store the actual text of a policy as it applies for a specific period of time. Each revision represents a concrete version of the policy content, including its lifecycle state and the dates when it is valid. Policy revisions are used to determine which policy text is in force at a given moment and to preserve a stable history for reference and auditing. Entity: Hrm_Governance_Policy_Revisions (Introduced in version 26.2.0.88)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Governance_Policy_Revision_Id](#governance_policy_revision_id)|`uniqueidentifier` `PK`|Governance Policy Revision Identifier|
|[Policy_Content](#policy_content)|`nvarchar(max)` |Full policy text for this revision - single editable text (in MarkDown). This is the authoritative content used by humans and AI.|
|[Policy_Id](#policy_id)|`uniqueidentifier` |Reference to the policy this revision belongs to.|
|[Row_Version](#row_version)|`timestamp` ||
|[State](#state)|`char(3)` Allowed: `DRF`, `REV`, `ACP`, `PUB`, `RET`, `CNL`|Lifecycle state of the revision.|
|[Valid_From](#valid_from)|`date` |Date from which this revision is intended to apply. Required when State = Published or Retired.|
|[Valid_To](#valid_to)|`date` |Date until which this revision applies (NULL = open-ended). Typically set automatically when a newer revision becomes effective.|

## Columns

### Governance_Policy_Revision_Id


Governance Policy Revision Identifier

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

#### Governance_Policy_Revision_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Policy_Content


Full policy text for this revision - single editable text (in MarkDown). This is the authoritative content used by humans and AI.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
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
|Type|nvarchar(max)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Policy_Content - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Like|None|no|no|

### Policy_Id


Reference to the policy this revision belongs to.

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
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Hrm_Governance_Policies](Hrm_Governance_Policies.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Policy_Id - Supported Filters

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

### State


Lifecycle state of the revision.

| Property | Value |
| - | - |
|Allowed Values|`DRF`, `REV`, `ACP`, `PUB`, `RET`, `CNL`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|DRF|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|3|
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
|Type|char(3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Valid_From


Date from which this revision is intended to apply. Required when State = Published or Retired.

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
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|date (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Valid_From - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|
|GreaterThanOrLessThan|None|no|no|

### Valid_To


Date until which this revision applies (NULL = open-ended). Typically set automatically when a newer revision becomes effective.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
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
|Type|date (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Valid_To - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|
|GreaterThanOrLessThan|None|no|no|


