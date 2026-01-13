---
uid: Finance.Assets.AssetTransactionLines
---
# Finance.Assets.AssetTransactionLines Entity

**Namespace:** [Finance.Assets](Finance.Assets.md)  

Asset value transaction lines. Each line changes the values of one asset in one valuation model. Entity: Ast_Asset_Transaction_Lines

## Default Visualization
Default Display Text Format:  
_{AssetTransaction.EntityName}_  
Default Search Members:  
_AssetTransaction.EntityName_  
Name Data Member:  
_AssetTransaction.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Assets.AssetTransactions](Finance.Assets.AssetTransactions.md)  
Aggregate Root:  
[Finance.Assets.AssetTransactions](Finance.Assets.AssetTransactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DepreciationValue](Finance.Assets.AssetTransactionLines.md#depreciationvalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the depreciation value of the asset (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)` 
| [DepreciationValueBase](Finance.Assets.AssetTransactionLines.md#depreciationvaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the depreciation value of the asset (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [DisplayText](Finance.Assets.AssetTransactionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Assets.AssetTransactionLines.md#id) | guid |  
| [NegativeReserveValue](Finance.Assets.AssetTransactionLines.md#negativereservevalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the value of the negative reserve after asset valuations (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)` 
| [NegativeReserveValueBase](Finance.Assets.AssetTransactionLines.md#negativereservevaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the value of the negative reserve after asset valuations (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [ObjectVersion](Finance.Assets.AssetTransactionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OperationType](Finance.Assets.AssetTransactionLines.md#operationtype) | [OperationType](Finance.Assets.AssetTransactionLines.md#operationtype) | Type of the current asset operation: PUR = Purchase, SLS = Sale, DEP = Depreciation, ADJ = Adjustment, REV = Reevaluation. `Required` `Default("ADJ")` `Filter(multi eq)` 
| [PositiveReserveValue](Finance.Assets.AssetTransactionLines.md#positivereservevalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the value of the positive reserve after asset valuations (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)` 
| [PositiveReserveValueBase](Finance.Assets.AssetTransactionLines.md#positivereservevaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the value of the positive reserve after asset valuations (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [PurchaseValue](Finance.Assets.AssetTransactionLines.md#purchasevalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the purchase value of the asset (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)` 
| [PurchaseValueBase](Finance.Assets.AssetTransactionLines.md#purchasevaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the purchase value of the asset (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [SalvageValue](Finance.Assets.AssetTransactionLines.md#salvagevalue) | [Amount (14, 2)](../data-types.md#amount) | Change in the salvage value of the asset (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)` 
| [SalvageValueBase](Finance.Assets.AssetTransactionLines.md#salvagevaluebase) | [Amount (14, 2)](../data-types.md#amount) | Change in the salvage value of the asset (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Asset](Finance.Assets.AssetTransactionLines.md#asset) | [Assets](Finance.Assets.Assets.md) | Asset for which changes in values have occurred. `Required` `Filter(multi eq)` |
| [AssetTransaction](Finance.Assets.AssetTransactionLines.md#assettransaction) | [AssetTransactions](Finance.Assets.AssetTransactions.md) | The <see cref="AssetTransaction"/> to which this AssetTransactionLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [ValuationModel](Finance.Assets.AssetTransactionLines.md#valuationmodel) | [ValuationModels](Finance.Assets.ValuationModels.md) | Valuation model in which the changes of the asset values have occurred (Taxation model or Accounting model or other). `Required` `Filter(multi eq)` |


## Attribute Details

### DepreciationValue

Change in the depreciation value of the asset (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.DepreciationValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### DepreciationValueBase

Change in the depreciation value of the asset (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.DepreciationValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### NegativeReserveValue

Change in the value of the negative reserve after asset valuations (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.NegativeReserveValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### NegativeReserveValueBase

Change in the value of the negative reserve after asset valuations (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.NegativeReserveValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OperationType

Type of the current asset operation: PUR = Purchase, SLS = Sale, DEP = Depreciation, ADJ = Adjustment, REV = Reevaluation. `Required` `Default("ADJ")` `Filter(multi eq)`

_Type_: **[OperationType](Finance.Assets.AssetTransactionLines.md#operationtype)**  
_Category_: **System**  
Allowed values for the `OperationType`(Finance.Assets.AssetTransactionLines.md#operationtype) data attribute  
_Allowed Values (Finance.Assets.AssetTransactionLinesRepository.OperationType Enum Members)_  

| Value | Description |
| ---- | --- |
| Adjustment | Adjustment value. Stored as 'ADJ'. <br /> _Database Value:_ 'ADJ' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Adjustment' |
| Depreciation | Depreciation value. Stored as 'DEP'. <br /> _Database Value:_ 'DEP' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Depreciation' |
| Purchase | Purchase value. Stored as 'PUR'. <br /> _Database Value:_ 'PUR' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Purchase' |
| Sale | Sale value. Stored as 'SLS'. <br /> _Database Value:_ 'SLS' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Sale' |
| Reevaluation | Reevaluation value. Stored as 'REV'. <br /> _Database Value:_ 'REV' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Reevaluation' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Adjustment**  
_Show in UI_: **ShownByDefault**  

### PositiveReserveValue

Change in the value of the positive reserve after asset valuations (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PositiveReserveValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### PositiveReserveValueBase

Change in the value of the positive reserve after asset valuations (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PositiveReserveValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### PurchaseValue

Change in the purchase value of the asset (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PurchaseValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### PurchaseValueBase

Change in the purchase value of the asset (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.PurchaseValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`
### SalvageValue

Change in the salvage value of the asset (in the currency of the asset). `Currency: Asset.ValuationCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.SalvageValueBase.ConvertTo( obj.Asset.ValuationCurrency, obj.AssetTransaction.CurrencyDirectory)`
### SalvageValueBase

Change in the salvage value of the asset (in the currency of the enterprise company). `Currency: Asset.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.SalvageValue.ConvertTo( obj.Asset.EnterpriseCompany.BaseCurrency, obj.AssetTransaction.CurrencyDirectory)`

## Reference Details

### Asset

Asset for which changes in values have occurred. `Required` `Filter(multi eq)`

_Type_: **[Assets](Finance.Assets.Assets.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### AssetTransaction

The <see cref="AssetTransaction"/> to which this AssetTransactionLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[AssetTransactions](Finance.Assets.AssetTransactions.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ValuationModel

Valuation model in which the changes of the asset values have occurred (Taxation model or Accounting model or other). `Required` `Filter(multi eq)`

_Type_: **[ValuationModels](Finance.Assets.ValuationModels.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    _Type_: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    _Type_: string  
     _Optional_: True  
    _Default Value_: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    _Type_: boolean  
     _Optional_: True  
    _Default Value_: False  

  * **top**  
    The top clause - default is 10  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 10  

  * **skip**  
    The skip clause - default is 0  
    _Type_: int32  
     _Optional_: True  
    _Default Value_: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
_Return Type_: **void**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  

**Parameters**  
  * **user**  
    The user.  
    _Type_: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    _Type_: string  

  * **subject**  
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


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

