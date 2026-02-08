---
uid: Logistics.Inventory.CostCorrectionLines
---
# Logistics.Inventory.CostCorrectionLines


Cost correction detail lines. One line is created for each corrected transaction line.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.CostCorrectionLines  
Base Table: Inv_Cost_Correction_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {Id}. {CostCorrection.DocumentNo} {CostCorrection.DocumentType.TypeName:T}  
Search Members: CostCorrection.DocumentNo  
Name Member: CostCorrection.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Inventory.CostCorrections](Logistics.Inventory.CostCorrections.md)  
Aggregate Root:  
[Logistics.Inventory.CostCorrections](Logistics.Inventory.CostCorrections.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseCostAdjustment](Logistics.Inventory.CostCorrectionLines.md#basecostadjustment) | [Amount (14, 2)](../data-types.md#amount) | The amount of correction (plus or minus) for the Base Cost field of the transaction line.`Currency: TransactionLine.TransactionObj.EnterpriseCompany.BaseCurrency` `Required` `Default(0)` 
| [CostCorrectionAmount](Logistics.Inventory.CostCorrectionLines.md#costcorrectionamount) | [Amount (14, 2)](../data-types.md#amount) | The amount of correction (plus or minus) for the Amount field of the transaction line.`Currency: TransactionLine.TransactionObj.DocumentCurrency` `Required` `Default(0)` 
| [ProductCostAdjustment](Logistics.Inventory.CostCorrectionLines.md#productcostadjustment) | [Amount (14, 2)](../data-types.md#amount) | The amount of correction (plus or minus) for the Product Cost field of the transaction line.`Currency: TransactionLine.Product.CostingCurrency` `Required` `Default(0)` 
| [StoreCostAdjustment](Logistics.Inventory.CostCorrectionLines.md#storecostadjustment) | [Amount (14, 2)](../data-types.md#amount) | The amount of correction (plus or minus) for the Store Cost field of the transaction line.`Currency: TransactionLine.TransactionObj.Store.Currency` `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CostCorrection](Logistics.Inventory.CostCorrectionLines.md#costcorrection) | [CostCorrections](Logistics.Inventory.CostCorrections.md) | The <see cref="CostCorrection"/> to which this CostCorrectionLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [Document](Logistics.Inventory.CostCorrectionLines.md#document) | [CostCorrections](Logistics.Inventory.CostCorrections.md) | The owner document. The <see cref="CostCorrection"/> to which this CostCorrectionLine belongs. `Required` `Filter(multi eq)` |
| [TransactionLine](Logistics.Inventory.CostCorrectionLines.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) | Store transaction line that is corrected with the correction amount. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.CostCorrectionLines.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.CostCorrectionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Inventory.CostCorrectionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BaseCostAdjustment

The amount of correction (plus or minus) for the Base Cost field of the transaction line.`Currency: TransactionLine.TransactionObj.EnterpriseCompany.BaseCurrency` `Required` `Default(0)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### CostCorrectionAmount

The amount of correction (plus or minus) for the Amount field of the transaction line.`Currency: TransactionLine.TransactionObj.DocumentCurrency` `Required` `Default(0)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ProductCostAdjustment

The amount of correction (plus or minus) for the Product Cost field of the transaction line.`Currency: TransactionLine.Product.CostingCurrency` `Required` `Default(0)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### StoreCostAdjustment

The amount of correction (plus or minus) for the Store Cost field of the transaction line.`Currency: TransactionLine.TransactionObj.Store.Currency` `Required` `Default(0)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

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

### CostCorrection

The <see cref="CostCorrection"/> to which this CostCorrectionLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[CostCorrections](Logistics.Inventory.CostCorrections.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Document

The owner document. The <see cref="CostCorrection"/> to which this CostCorrectionLine belongs. `Required` `Filter(multi eq)`

Type: **[CostCorrections](Logistics.Inventory.CostCorrections.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TransactionLine

Store transaction line that is corrected with the correction amount.

Type: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.CostCorrectionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.CostCorrectionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_CostCorrectionLines

Domain API Entity Type: 
Logistics_Inventory_CostCorrectionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_CostCorrectionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_CostCorrectionLines?$top=10>

