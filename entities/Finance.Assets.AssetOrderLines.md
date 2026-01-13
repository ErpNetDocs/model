---
uid: Finance.Assets.AssetOrderLines
---
# Finance.Assets.AssetOrderLines Entity

**Namespace:** [Finance.Assets](Finance.Assets.md)  

Asset purchase or sales order line for one asset. Entity: Ast_Asset_Order_Lines

## Default Visualization
Default Display Text Format:  
_{Id}. {AssetOrder.DocumentNo} {AssetOrder.DocumentType.TypeName:T}_  
Default Search Members:  
_AssetOrder.DocumentNo_  
Name Data Member:  
_AssetOrder.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Finance.Assets.AssetOrderLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Assets.AssetOrderLines.md#id) | guid |  
| [ObjectVersion](Finance.Assets.AssetOrderLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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


## Attribute Details

### AssetValue

Value of the acquired or retired asset. `Currency: AssetValueCurrency` `Required` `Default(0)`

_Type_: **[Amount (14, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Constant**  
_Show in UI_: **ShownByDefault**  

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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ParentLineNo

The number of the line within the parent document, which the current line executes. null when the current line does not execute line. `Introduced in version 18.2`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Quantity

Indicates the nature of the current operation: 1 - the operation is applied, 0 - no change, -1 - the operation is cancelled. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Asset

The asset that is acquired or retired. `Required` `Filter(multi eq)`

_Type_: **[Assets](Finance.Assets.Assets.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### AssetOrder

The <see cref="AssetOrder"/> to which this AssetOrderLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[AssetOrders](Finance.Assets.AssetOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### AssetValueCurrency

Currency of Asset Value. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Document

The owner document. The <see cref="AssetOrder"/> to which this AssetOrderLine belongs. `Required` `Filter(multi eq)`

_Type_: **[AssetOrders](Finance.Assets.AssetOrders.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ParentDocument

The document, which the current line executes. null when the current line does not execute another line. `Filter(multi eq)` `Introduced in version 18.2`

_Type_: **[Documents](General.Documents.Documents.md) (nullable)**  
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

