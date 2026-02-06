---
uid: Finance.Accounting.AccountRequiredProperties
---
# Finance.Accounting.AccountRequiredProperties


Defines the required properties for new vouchers, for each account.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.AccountRequiredProperties  
Base Table: Acc_Account_Required_Properties  
API access:  ReadWrite  

## Visualization
Display Format: {Account.Name:T}  
Search Members: Account.Name  
Name Member: Account.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Accounting.Accounts](Finance.Accounting.Accounts.md)  
Aggregate Root:  
[Finance.Accounting.Accounts](Finance.Accounting.Accounts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [KeyOrder](Finance.Accounting.AccountRequiredProperties.md#keyorder) | int32 | The key order determines in which order the values and descriptions of the properties will form the item (grouping) key and description.[Required] 
| [KeyProperty](Finance.Accounting.AccountRequiredProperties.md#keyproperty) | boolean | Key properties particiate in forming the grouping key, which is the smallest unit of calculation for account balance. Non-key properties simply serve for comment and clarification purposes[Required] [Default(true)] [Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Finance.Accounting.AccountRequiredProperties.md#account) | [Accounts](Finance.Accounting.Accounts.md) | The <see cref="Account"/> to which this AccountRequiredProperty belongs. `Required` `Filter(multi eq)` `Owner` |
| [Property](Finance.Accounting.AccountRequiredProperties.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | A property of type (Entity_Name = Account Voucher Line) for which the user can specify value when entering accounting vouchers |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Accounting.AccountRequiredProperties.md#id) | guid |  
| [ObjectVersion](Finance.Accounting.AccountRequiredProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Accounting.AccountRequiredProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### KeyOrder

The key order determines in which order the values and descriptions of the properties will form the item (grouping) key and description.[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Account.RequiredProperties.Select( c => c.KeyOrder).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.Account.RequiredProperties.Select( c => c.KeyOrder).DefaultIfEmpty( 0).Max( ) + 1)`
### KeyProperty

Key properties particiate in forming the grouping key, which is the smallest unit of calculation for account balance. Non-key properties simply serve for comment and clarification purposes[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
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

### Account

The <see cref="Account"/> to which this AccountRequiredProperty belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **HiddenByDefault**  

### Property

A property of type (Entity_Name = Account Voucher Line) for which the user can specify value when entering accounting vouchers

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
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

[!list limit=1000 erp.entity=Finance.Accounting.AccountRequiredProperties erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Accounting.AccountRequiredProperties erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Accounting_AccountRequiredProperties

Domain API Entity Type: 
Finance_Accounting_AccountRequiredProperty

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_AccountRequiredProperties?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_AccountRequiredProperties?$top=10>

