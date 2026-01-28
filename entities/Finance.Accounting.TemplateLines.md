---
uid: Finance.Accounting.TemplateLines
---
# Finance.Accounting.TemplateLines


Each template line contains the posting to a single set of debit and credit account. It also specifies the way to calculate the amount.

## General
Namespace: [Finance.Accounting](Finance.Accounting.md)  
Repository: Finance.Accounting.TemplateLines  
Base Table: Acc_Template_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {AmountColumnName}  
Search Members: AmountColumnName  
Name Member: AmountColumnName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Accounting.Templates](Finance.Accounting.Templates.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AmountColumnName](Finance.Accounting.TemplateLines.md#amountcolumnname) | string (64) | The name of the column within the amount rowset where the amount is located. `Required` 
| [AmountCondition](Finance.Accounting.TemplateLines.md#amountcondition) | [AmountCondition](Finance.Accounting.TemplateLines.md#amountcondition) __nullable__ | Condition for the amount. The line is accounted only when the condition is matched. The condition can be one of: null - no condition, the line should be accounted unconditionally; '+' - The amount should be positive; '-' - The amount should be negative. The amount is matched as returned from the source, before applying the Multiplier. 
| [AmountRowId](Finance.Accounting.TemplateLines.md#amountrowid) | guid __nullable__ | The id of the row from the amount rowset where the amount is located. null means to account one by one for all rows within the rowset. `Filter(multi eq)` 
| [AmountRowName](Finance.Accounting.TemplateLines.md#amountrowname) | string (254) __nullable__ | The name of definition, specified in Amount_Row_Id. null means that no Amount_Row_Id is specified or there is no name. 
| [AmountSourceFilter](Finance.Accounting.TemplateLines.md#amountsourcefilter) | dataaccessfilter __nullable__ | Filter that further specifies which rows from the amount rowset determine the amount. `Unit: obj.GetAmountSource<br />FilterEntityName()` 
| [AmountSourceName](Finance.Accounting.TemplateLines.md#amountsourcename) | string (64) | The source rowset for the amount. For example: DocLines, DocHeader, Additional Amounts, Stock Types, etc. `Required` 
| [FilterXML](Finance.Accounting.TemplateLines.md#filterxml) | dataaccessfilter __nullable__ | The line is accounted only when the filter is satisfied compared with the source document header. `Unit: obj.Template.Route.DocumentType.EntityName` 
| [LineNo](Finance.Accounting.TemplateLines.md#lineno) | int32 | Consecutive number of the line within the template. Determines the order of execution of the template lines. `Required` 
| [Multiplier](Finance.Accounting.TemplateLines.md#multiplier) | decimal (18, 6) | Factor by which the amount from the source will be multiplied. `Required` `Default(1)` 
| [Notes](Finance.Accounting.TemplateLines.md#notes) | string (254) __nullable__ | Notes for this TemplateLine. 
| [ValidFromDate](Finance.Accounting.TemplateLines.md#validfromdate) | datetime __nullable__ | Start date from which the accounting template line is valid. `Filter(multi eq;ge;le)` 
| [ValidToDate](Finance.Accounting.TemplateLines.md#validtodate) | datetime __nullable__ | End date to which the accounting template line is valid. `Filter(multi eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreditAccount](Finance.Accounting.TemplateLines.md#creditaccount) | [Accounts](Finance.Accounting.Accounts.md) | The account which should be credited. `Required` `Filter(multi eq)` |
| [DebitAccount](Finance.Accounting.TemplateLines.md#debitaccount) | [Accounts](Finance.Accounting.Accounts.md) | The account which should be debited. `Required` `Filter(multi eq)` |
| [Template](Finance.Accounting.TemplateLines.md#template) | [Templates](Finance.Accounting.Templates.md) | The <see cref="Template"/> to which this TemplateLine belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Accounting.TemplateLines.md#id) | guid |  
| [ObjectVersion](Finance.Accounting.TemplateLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Accounting.TemplateLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| TemplateLineProperties | [TemplateLineProperties](Finance.Accounting.TemplateLineProperties.md) | List of `TemplateLineProperty`(Finance.Accounting.TemplateLineProperties.md) child objects, based on the `Finance.Accounting.TemplateLineProperty.TemplateLine`(Finance.Accounting.TemplateLineProperties.md#templateline) back reference 


## Attribute Details

### AmountColumnName

The name of the column within the amount rowset where the amount is located. `Required`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### AmountCondition

Condition for the amount. The line is accounted only when the condition is matched. The condition can be one of: null - no condition, the line should be accounted unconditionally; '+' - The amount should be positive; '-' - The amount should be negative. The amount is matched as returned from the source, before applying the Multiplier.

Type: **[AmountCondition](Finance.Accounting.TemplateLines.md#amountcondition) __nullable__**  
Category: **System**  
Allowed values for the `AmountCondition`(Finance.Accounting.TemplateLines.md#amountcondition) data attribute  
Allowed Values (Finance.Accounting.TemplateLinesRepository.AmountCondition Enum Members)  

| Value | Description |
| ---- | --- |
| Positive | Positive value. Stored as '+'. <br /> Database Value: '+' <br /> Model Value: 0 <br /> Domain API Value: 'Positive' |
| Negative | Negative value. Stored as '-'. <br /> Database Value: '-' <br /> Model Value: 1 <br /> Domain API Value: 'Negative' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AmountRowId

The id of the row from the amount rowset where the amount is located. null means to account one by one for all rows within the rowset. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### AmountRowName

The name of definition, specified in Amount_Row_Id. null means that no Amount_Row_Id is specified or there is no name.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### AmountSourceFilter

Filter that further specifies which rows from the amount rowset determine the amount. `Unit: obj.GetAmountSourceFilterEntityName()`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### AmountSourceName

The source rowset for the amount. For example: DocLines, DocHeader, Additional Amounts, Stock Types, etc. `Required`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### FilterXML

The line is accounted only when the filter is satisfied compared with the source document header. `Unit: obj.Template.Route.DocumentType.EntityName`

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive number of the line within the template. Determines the order of execution of the template lines. `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Template.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.Template.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Multiplier

Factor by which the amount from the source will be multiplied. `Required` `Default(1)`

Type: **decimal (18, 6)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **HiddenByDefault**  

### Notes

Notes for this TemplateLine.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ValidFromDate

Start date from which the accounting template line is valid. `Filter(multi eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidToDate

End date to which the accounting template line is valid. `Filter(multi eq;ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
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

### CreditAccount

The account which should be credited. `Required` `Filter(multi eq)`

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DebitAccount

The account which should be debited. `Required` `Filter(multi eq)`

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Template

The <see cref="Template"/> to which this TemplateLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Templates](Finance.Accounting.Templates.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Finance.Accounting.TemplateLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Accounting.TemplateLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Accounting_TemplateLines

Domain API Entity Type: 
Finance_Accounting_TemplateLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Accounting_TemplateLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Accounting_TemplateLines?$top=10>

