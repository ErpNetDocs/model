---
uid: Finance.Assets.AssetOrderLines
---
# Finance.Assets.AssetOrderLines


Asset purchase or sales order line for one asset.

## General
Namespace: [Finance.Assets](Finance.Assets.md)  
Repository: Finance.Assets.AssetOrderLines  
Base Table: Ast_Asset_Order_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {Id}. {AssetOrder.DocumentNo} {AssetOrder.DocumentType.TypeName:T}  
Search Members: AssetOrder.DocumentNo  
Name Member: AssetOrder.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Assets.AssetOrders](Finance.Assets.AssetOrders.md)  
Aggregate Root:  
[Finance.Assets.AssetOrders](Finance.Assets.AssetOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AssetValue](Finance.Assets.AssetOrderLines.md#assetvalue) | [Amount (14, 2)](../data-types.md#amount) | Value of the acquired or retired asset. `Currency: AssetValueCurrency` `Required` `Default(0)` 
| [ParentLineNo](Finance.Assets.AssetOrderLines.md#parentlineno) | int32 __nullable__ | The number of the line within the parent document, which the current line executes. null when the current line does not execute line. `Introduced in version 18.2` 
| [Quantity](Finance.Assets.AssetOrderLines.md#quantity) | int32 | Indicates the nature of the current operation: 1 - the operation is applied, 0 - no change, -1 - the operation is cancelled. `Required` `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Asset](Finance.Assets.AssetOrderLines.md#asset) | [Assets](Finance.Assets.Assets.md) | The asset that is acquired or retired. `Required` `Filter(multi eq)` |
| [AssetOrder](Finance.Assets.AssetOrderLines.md#assetorder) | [AssetOrders](Finance.Assets.AssetOrders.md) | The <see cref="AssetOrder"/> to which this AssetOrderLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [AssetValueCurrency](Finance.Assets.AssetOrderLines.md#assetvaluecurrency) | [Currencies](General.Currencies.Currencies.md) | Currency of Asset Value. `Required` `Filter(multi eq)` |
| [Document](Finance.Assets.AssetOrderLines.md#document) | [AssetOrders](Finance.Assets.AssetOrders.md) | The owner document. The <see cref="AssetOrder"/> to which this AssetOrderLine belongs. `Required` `Filter(multi eq)` |
| [ParentDocument](Finance.Assets.AssetOrderLines.md#parentdocument) | [Documents](General.Documents.Documents.md) (nullable) | The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 18.2` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Assets.AssetOrderLines.md#id) | guid |  
| [ObjectVersion](Finance.Assets.AssetOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Assets.AssetOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AssetValue

Value of the acquired or retired asset. `Currency: AssetValueCurrency` `Required` `Default(0)`

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute line. `Introduced in version 18.2`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Quantity

Indicates the nature of the current operation: 1 - the operation is applied, 0 - no change, -1 - the operation is cancelled. `Required` `Default(0)`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **0**  
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

### Asset

The asset that is acquired or retired. `Required` `Filter(multi eq)`

Type: **[Assets](Finance.Assets.Assets.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### AssetOrder

The <see cref="AssetOrder"/> to which this AssetOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[AssetOrders](Finance.Assets.AssetOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### AssetValueCurrency

Currency of Asset Value. `Required` `Filter(multi eq)`

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Document

The owner document. The <see cref="AssetOrder"/> to which this AssetOrderLine belongs. `Required` `Filter(multi eq)`

Type: **[AssetOrders](Finance.Assets.AssetOrders.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 18.2`

Type: **[Documents](General.Documents.Documents.md) (nullable)**  
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

[!list limit=1000 erp.entity=Finance.Assets.AssetOrderLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Assets.AssetOrderLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Assets_AssetOrderLines

Domain API Entity Type: 
Finance_Assets_AssetOrderLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Assets_AssetOrderLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Assets_AssetOrderLines?$top=10>

