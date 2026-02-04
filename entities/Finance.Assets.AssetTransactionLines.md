---
uid: Finance.Assets.AssetTransactionLines
---
# Finance.Assets.AssetTransactionLines


Asset value transaction lines. Each line changes the values of one asset in one valuation model.

## General
Namespace: [Finance.Assets](Finance.Assets.md)  
Repository: Finance.Assets.AssetTransactionLines  
Base Table: Ast_Asset_Transaction_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {AssetTransaction.EntityName}  
Search Members: AssetTransaction.EntityName  
Name Member: AssetTransaction.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Assets.AssetTransactions](Finance.Assets.AssetTransactions.md)  
Aggregate Root:  
[Finance.Assets.AssetTransactions](Finance.Assets.AssetTransactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DepreciationValue](Finance.Assets.AssetTransactionLines.md#depreciationvalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the depreciation value of the asset (in the currency of the asset). 
| [DepreciationValueBase](Finance.Assets.AssetTransactionLines.md#depreciationvaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the depreciation value of the asset (in the currency of the asset's enterprise company). 
| [NegativeReserveValue](Finance.Assets.AssetTransactionLines.md#negativereservevalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the value of the negative reserve after asset valuations (in the currency of the asset). 
| [NegativeReserveValueBase](Finance.Assets.AssetTransactionLines.md#negativereservevaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the value of the negative reserve after asset valuations (in the currency of the asset's enterprise company). 
| [OperationType](Finance.Assets.AssetTransactionLines.md#operationtype) | [OperationType](Finance.Assets.AssetTransactionLines.md#operationtype) | Type of the current asset operation: PUR = Purchase, SLS = Sale, DEP = Depreciation, ADJ = Adjustment, REV = Reevaluation 
| [PositiveReserveValue](Finance.Assets.AssetTransactionLines.md#positivereservevalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the value of the positive reserve after asset valuations (in the currency of the asset). 
| [PositiveReserveValueBase](Finance.Assets.AssetTransactionLines.md#positivereservevaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the value of the positive reserve after asset valuations (in the currency of the asset's enterprise company). 
| [PurchaseValue](Finance.Assets.AssetTransactionLines.md#purchasevalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the purchase value of the asset (in the currency of the asset). 
| [PurchaseValueBase](Finance.Assets.AssetTransactionLines.md#purchasevaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the purchase value of the asset (in the currency of the asset's enterprise company). 
| [SalvageValue](Finance.Assets.AssetTransactionLines.md#salvagevalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the salvage value of the asset (in the currency of the asset). 
| [SalvageValueBase](Finance.Assets.AssetTransactionLines.md#salvagevaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the salvage value of the asset (in the currency of the asset's enterprise company). 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Asset](Finance.Assets.AssetTransactionLines.md#asset) | [Assets](Finance.Assets.Assets.md) | Asset for which changes in values have occurred. |
| [AssetTransaction](Finance.Assets.AssetTransactionLines.md#assettransaction) | [AssetTransactions](Finance.Assets.AssetTransactions.md) | The <see cref="AssetTransaction"/> to which this AssetTransactionLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ValuationModel](Finance.Assets.AssetTransactionLines.md#valuationmodel) | [ValuationModels](Finance.Assets.ValuationModels.md) | Valuation model in which the changes of the asset values have occurred (Taxation model or Accounting model or other). |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Assets.AssetTransactionLines.md#id) | guid |  
| [ObjectVersion](Finance.Assets.AssetTransactionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Assets.AssetTransactionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DepreciationValue

Change in the depreciation value of the asset (in the currency of the asset).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DepreciationValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### DepreciationValueBase

Change in the depreciation value of the asset (in the currency of the asset's enterprise company).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.DepreciationValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### NegativeReserveValue

Change in the value of the negative reserve after asset valuations (in the currency of the asset).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.NegativeReserveValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### NegativeReserveValueBase

Change in the value of the negative reserve after asset valuations (in the currency of the asset's enterprise company).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.NegativeReserveValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### OperationType

Type of the current asset operation: PUR = Purchase, SLS = Sale, DEP = Depreciation, ADJ = Adjustment, REV = Reevaluation

Type: **[OperationType](Finance.Assets.AssetTransactionLines.md#operationtype)**  
Category: **System**  
Allowed values for the `OperationType`(Finance.Assets.AssetTransactionLines.md#operationtype) data attribute  
Allowed Values (Finance.Assets.AssetTransactionLinesRepository.OperationType Enum Members)  

| Value | Description |
| ---- | --- |
| Adjustment | Adjustment value. Stored as 'ADJ'. <br /> Database Value: 'ADJ' <br /> Model Value: 0 <br /> Domain API Value: 'Adjustment' |
| Depreciation | Depreciation value. Stored as 'DEP'. <br /> Database Value: 'DEP' <br /> Model Value: 1 <br /> Domain API Value: 'Depreciation' |
| Purchase | Purchase value. Stored as 'PUR'. <br /> Database Value: 'PUR' <br /> Model Value: 2 <br /> Domain API Value: 'Purchase' |
| Sale | Sale value. Stored as 'SLS'. <br /> Database Value: 'SLS' <br /> Model Value: 3 <br /> Domain API Value: 'Sale' |
| Reevaluation | Reevaluation value. Stored as 'REV'. <br /> Database Value: 'REV' <br /> Model Value: 4 <br /> Domain API Value: 'Reevaluation' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Adjustment**  
Show in UI: **ShownByDefault**  

### PositiveReserveValue

Change in the value of the positive reserve after asset valuations (in the currency of the asset).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PositiveReserveValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### PositiveReserveValueBase

Change in the value of the positive reserve after asset valuations (in the currency of the asset's enterprise company).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PositiveReserveValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### PurchaseValue

Change in the purchase value of the asset (in the currency of the asset).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PurchaseValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### PurchaseValueBase

Change in the purchase value of the asset (in the currency of the asset's enterprise company).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.PurchaseValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### SalvageValue

Change in the salvage value of the asset (in the currency of the asset).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.SalvageValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### SalvageValueBase

Change in the salvage value of the asset (in the currency of the asset's enterprise company).

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.SalvageValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Asset

Asset for which changes in values have occurred.

Type: **[Assets](Finance.Assets.Assets.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### AssetTransaction

The <see cref="AssetTransaction"/> to which this AssetTransactionLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[AssetTransactions](Finance.Assets.AssetTransactions.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ValuationModel

Valuation model in which the changes of the asset values have occurred (Taxation model or Accounting model or other).

Type: **[ValuationModels](Finance.Assets.ValuationModels.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
Return Type: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    Type: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    Type: string  
     Optional: True  
    Default Value: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **top**  
    The top clause - default is 10  
    Type: int32  
     Optional: True  
    Default Value: 10  

  * **skip**  
    The skip clause - default is 0  
    Type: int32  
     Optional: True  
    Default Value: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
Return Type: **void**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

**Parameters**  
  * **user**  
    The user.  
    Type: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    Type: string  

  * **subject**  
    The notification subject.  
    Type: string  

  * **priority**  
    The notification priority.  
    Type: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
    | Low | Low value. Stored as 2. <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
    | Normal | Normal value. Stored as 3. <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
    | High | High value. Stored as 4. <br /> Model Value: 4 <br /> Domain API Value: 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

     Optional: True  
    Default Value: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Finance.Assets.AssetTransactionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Assets.AssetTransactionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Assets_AssetTransactionLines

Domain API Entity Type: 
Finance_Assets_AssetTransactionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Assets_AssetTransactionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Assets_AssetTransactionLines?$top=10>

