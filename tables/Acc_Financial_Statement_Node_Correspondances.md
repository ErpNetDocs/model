# Table Acc_Financial_Statement_Node_Correspondances


## Entity

Entity: [Finance.Accounting.FinancialStatementNodeCorrespondances](~/entities/Finance.Accounting.FinancialStatementNodeCorrespondances.md)

Contains the actual correspondance filters, which specify how each financial statement node is calculated. Entity: Acc_Financial_Statement_Node_Correspondances

## Owner Tables Hierarchy

* [Acc_Financial_Statement_Nodes](Acc_Financial_Statement_Nodes.md)
* [Acc_Financial_Statements](Acc_Financial_Statements.md)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Account_Group_Id](#account_group_id)|`uniqueidentifier` |Main account group determining the correspondances for which the balances are summed|
|[Correspondant_Account_Group_Id](#correspondant_account_group_id)|`uniqueidentifier` |Correspondant account group determining the correspondances for which the balances are summed. If NULL means that the balances of all correspondances for the main account group are summed.|
|[Financial_Statement_Node_Correspondance_Id](#financial_statement_node_correspondance_id)|`uniqueidentifier` `PK`||
|[Financial_Statement_Node_Id](#financial_statement_node_id)|`uniqueidentifier` ||
|[Multiplier](#multiplier)|`decimal(18, 0)` |Factor by which the correspondence balance will be multiplied.|
|[Row_Version](#row_version)|`timestamp` ||

## Columns

### Account_Group_Id


Main account group determining the correspondances for which the balances are summed

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
|Referenced Table|[Acc_Account_Groups](Acc_Account_Groups.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Account_Group_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Correspondant_Account_Group_Id


Correspondant account group determining the correspondances for which the balances are summed. If NULL means that the balances of all correspondances for the main account group are summed.

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
|Referenced Table|[Acc_Account_Groups](Acc_Account_Groups.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Correspondant_Account_Group_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### Financial_Statement_Node_Correspondance_Id

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

#### Financial_Statement_Node_Correspondance_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|
|GreaterThanOrLessThan|None|no|yes|

### Financial_Statement_Node_Id

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
|Ownership Reference|yes|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Acc_Financial_Statement_Nodes](Acc_Financial_Statement_Nodes.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Financial_Statement_Node_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|

### Multiplier


Factor by which the correspondence balance will be multiplied.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|1|
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
|Type|decimal(18, 0)|
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


