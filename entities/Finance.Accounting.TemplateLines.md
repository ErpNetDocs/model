---
uid: Finance.Accounting.TemplateLines
---
# Finance.Accounting.TemplateLines Entity

**Namespace:** [Finance.Accounting](Finance.Accounting.md)  

Each template line contains the posting to a single set of debit and credit account. It also specifies the way to calculate the amount. Entity: Acc_Template_Lines

## Default Visualization
Default Display Text Format:  
_{AmountColumnName}_  
Default Search Members:  
_AmountColumnName_  
Name Data Member:  
_AmountColumnName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Finance.Accounting.TemplateLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FilterXML](Finance.Accounting.TemplateLines.md#filterxml) | dataaccessfilter __nullable__ | The line is accounted only when the filter is satisfied compared with the source document header. `Unit: obj.Template.Route.DocumentType.EntityName` 
| [Id](Finance.Accounting.TemplateLines.md#id) | guid |  
| [LineNo](Finance.Accounting.TemplateLines.md#lineno) | int32 | Consecutive number of the line within the template. Determines the order of execution of the template lines. `Required` 
| [Multiplier](Finance.Accounting.TemplateLines.md#multiplier) | decimal (18, 6) | Factor by which the amount from the source will be multiplied. `Required` `Default(1)` 
| [Notes](Finance.Accounting.TemplateLines.md#notes) | string (254) __nullable__ | Notes for this TemplateLine. 
| [ObjectVersion](Finance.Accounting.TemplateLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ValidFromDate](Finance.Accounting.TemplateLines.md#validfromdate) | datetime __nullable__ | Start date from which the accounting template line is valid. `Filter(multi eq;ge;le)` 
| [ValidToDate](Finance.Accounting.TemplateLines.md#validtodate) | datetime __nullable__ | End date to which the accounting template line is valid. `Filter(multi eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreditAccount](Finance.Accounting.TemplateLines.md#creditaccount) | [Accounts](Finance.Accounting.Accounts.md) | The account which should be credited. `Required` `Filter(multi eq)` |
| [DebitAccount](Finance.Accounting.TemplateLines.md#debitaccount) | [Accounts](Finance.Accounting.Accounts.md) | The account which should be debited. `Required` `Filter(multi eq)` |
| [Template](Finance.Accounting.TemplateLines.md#template) | [Templates](Finance.Accounting.Templates.md) | The <see cref="Template"/> to which this TemplateLine belongs. `Required` `Filter(multi eq)` `Owner` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| TemplateLineProperties | [TemplateLineProperties](Finance.Accounting.TemplateLineProperties.md) | List of `TemplateLineProperty`(Finance.Accounting.TemplateLineProperties.md) child objects, based on the `Finance.Accounting.TemplateLineProperty.TemplateLine`(Finance.Accounting.TemplateLineProperties.md#templateline) back reference 


## Attribute Details

### AmountColumnName

The name of the column within the amount rowset where the amount is located. `Required`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### AmountCondition

Condition for the amount. The line is accounted only when the condition is matched. The condition can be one of: null - no condition, the line should be accounted unconditionally; '+' - The amount should be positive; '-' - The amount should be negative. The amount is matched as returned from the source, before applying the Multiplier.

_Type_: **[AmountCondition](Finance.Accounting.TemplateLines.md#amountcondition) __nullable__**  
_Category_: **System**  
Allowed values for the `AmountCondition`(Finance.Accounting.TemplateLines.md#amountcondition) data attribute  
_Allowed Values (Finance.Accounting.TemplateLinesRepository.AmountCondition Enum Members)_  

| Value | Description |
| ---- | --- |
| Positive | Positive value. Stored as '+'. <br /> _Database Value:_ '+' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Positive' |
| Negative | Negative value. Stored as '-'. <br /> _Database Value:_ '-' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Negative' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### AmountRowId

The id of the row from the amount rowset where the amount is located. null means to account one by one for all rows within the rowset. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### AmountRowName

The name of definition, specified in Amount_Row_Id. null means that no Amount_Row_Id is specified or there is no name.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### AmountSourceFilter

Filter that further specifies which rows from the amount rowset determine the amount. `Unit: obj.GetAmountSourceFilterEntityName()`

_Type_: **dataaccessfilter __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### AmountSourceName

The source rowset for the amount. For example: DocLines, DocHeader, Additional Amounts, Stock Types, etc. `Required`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FilterXML

The line is accounted only when the filter is satisfied compared with the source document header. `Unit: obj.Template.Route.DocumentType.EntityName`

_Type_: **dataaccessfilter __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Consecutive number of the line within the template. Determines the order of execution of the template lines. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Template.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.Template.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Multiplier

Factor by which the amount from the source will be multiplied. `Required` `Default(1)`

_Type_: **decimal (18, 6)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **HiddenByDefault**  

### Notes

Notes for this TemplateLine.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ValidFromDate

Start date from which the accounting template line is valid. `Filter(multi eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ValidToDate

End date to which the accounting template line is valid. `Filter(multi eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CreditAccount

The account which should be credited. `Required` `Filter(multi eq)`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### DebitAccount

The account which should be debited. `Required` `Filter(multi eq)`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Template

The <see cref="Template"/> to which this TemplateLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Templates](Finance.Accounting.Templates.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

