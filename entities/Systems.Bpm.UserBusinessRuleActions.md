---
uid: Systems.Bpm.UserBusinessRuleActions
---
# Systems.Bpm.UserBusinessRuleActions


Represents an action within a business rule.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.UserBusinessRuleActions  
Base Table: Sys_User_Business_Rule_Actions  
API access:  ReadWrite  

## Visualization
Display Format: {UserBusinessRule.Name:T}  
Search Members: UserBusinessRule.Name  
Name Member: UserBusinessRule.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  
Aggregate Root:  
[Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActionNo](Systems.Bpm.UserBusinessRuleActions.md#actionno) | int32 | Consecutive number of the action, unique within the business rule. 
| [ActionType](Systems.Bpm.UserBusinessRuleActions.md#actiontype) | [ActionType](Systems.Bpm.UserBusinessRuleActions.md#actiontype) | Specifies the type of action to perform. 
| [Parameter1Type](Systems.Bpm.UserBusinessRuleActions.md#parameter1type) | [ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter1type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter1Value](Systems.Bpm.UserBusinessRuleActions.md#parameter1value) | string (256) __nullable__ | The actual value of the parameter. 
| [Parameter2Type](Systems.Bpm.UserBusinessRuleActions.md#parameter2type) | [ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter2type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter2Value](Systems.Bpm.UserBusinessRuleActions.md#parameter2value) | string (256) __nullable__ | The actual value of the parameter. 
| [Parameter3Type](Systems.Bpm.UserBusinessRuleActions.md#parameter3type) | [ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter3type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter3Value](Systems.Bpm.UserBusinessRuleActions.md#parameter3value) | string (256) __nullable__ | The actual value of the parameter. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [UserBusinessRule](Systems.Bpm.UserBusinessRuleActions.md#userbusinessrule) | [UserBusinessRules](Systems.Bpm.UserBusinessRules.md) | The business rule, for which the action is defined. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.UserBusinessRuleActions.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.UserBusinessRuleActions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Bpm.UserBusinessRuleActions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ActionNo

Consecutive number of the action, unique within the business rule.

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.UserBusinessRule.Actions.Select( c => c.ActionNo).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.UserBusinessRule.Actions.Select( c => c.ActionNo).DefaultIfEmpty( 0).Max( ) + 1)`
### ActionType

Specifies the type of action to perform.

Type: **[ActionType](Systems.Bpm.UserBusinessRuleActions.md#actiontype)**  
Category: **System**  
Allowed values for the `ActionType`(Systems.Bpm.UserBusinessRuleActions.md#actiontype) data attribute  
Allowed Values (Systems.Bpm.UserBusinessRuleActionsRepository.ActionType Enum Members)  

| Value | Description |
| ---- | --- |
| SETVALUE | SETVALUE value. Stored as 'SETVALUE'. <br /> Database Value: 'SETVALUE' <br /> Model Value: 0 <br /> Domain API Value: 'SETVALUE' |
| FAIL | FAIL value. Stored as 'FAIL'. <br /> Database Value: 'FAIL' <br /> Model Value: 1 <br /> Domain API Value: 'FAIL' |
| SENDMAIL | SENDMAIL value. Stored as 'SENDMAIL'. <br /> Database Value: 'SENDMAIL' <br /> Model Value: 2 <br /> Domain API Value: 'SENDMAIL' |
| WARNING | WARNING value. Stored as 'WARNING'. <br /> Database Value: 'WARNING' <br /> Model Value: 3 <br /> Domain API Value: 'WARNING' |
| NOTIFYUSER | NOTIFYUSER value. Stored as 'NOTIFYUSER'. <br /> Database Value: 'NOTIFYUSER' <br /> Model Value: 4 <br /> Domain API Value: 'NOTIFYUSER' |
| WEBHOOK | WEBHOOK value. Stored as 'WEBHOOK'. <br /> Database Value: 'WEBHOOK' <br /> Model Value: 5 <br /> Domain API Value: 'WEBHOOK' |
| AISET | AISET value. Stored as 'AISET'. <br /> Database Value: 'AISET' <br /> Model Value: 6 <br /> Domain API Value: 'AISET' |
| AIVALIDATE | AIVALIDATE value. Stored as 'AIVALIDATE'. <br /> Database Value: 'AIVALIDATE' <br /> Model Value: 7 <br /> Domain API Value: 'AIVALIDATE' |
| AIWARNING | AIWARNING value. Stored as 'AIWARNING'. <br /> Database Value: 'AIWARNING' <br /> Model Value: 8 <br /> Domain API Value: 'AIWARNING' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Parameter1Type

The type of the parameter specifies how to obtain the parameter value.

Type: **[ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter1type) __nullable__**  
Category: **System**  
Generic enum type for ActionParameterType properties  
Allowed Values (Systems.Bpm.ActionParameterType Enum Members)  

| Value | Description |
| ---- | --- |
| Constant | Constant value. Stored as 'CONST'. <br /> Database Value: 'CONST' <br /> Model Value: 0 <br /> Domain API Value: 'Constant' |
| Attribute | Attribute value. Stored as 'ATTRIB'. <br /> Database Value: 'ATTRIB' <br /> Model Value: 1 <br /> Domain API Value: 'Attribute' |
| Reference | Reference value. Stored as 'REF'. <br /> Database Value: 'REF' <br /> Model Value: 2 <br /> Domain API Value: 'Reference' |
| ChildList | ChildList value. Stored as 'CHILD'. <br /> Database Value: 'CHILD' <br /> Model Value: 3 <br /> Domain API Value: 'ChildList' |
| FormattedString | FormattedString value. Stored as 'FMTSTR'. <br /> Database Value: 'FMTSTR' <br /> Model Value: 4 <br /> Domain API Value: 'FormattedString' |
| Interpolate | Interpolate value. Stored as 'INTERPOLATE'. <br /> Database Value: 'INTERPOLATE' <br /> Model Value: 5 <br /> Domain API Value: 'Interpolate' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Parameter1Value

The actual value of the parameter.

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### Parameter2Type

The type of the parameter specifies how to obtain the parameter value.

Type: **[ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter2type) __nullable__**  
Category: **System**  
Generic enum type for ActionParameterType properties  
Allowed Values (Systems.Bpm.ActionParameterType Enum Members)  

| Value | Description |
| ---- | --- |
| Constant | Constant value. Stored as 'CONST'. <br /> Database Value: 'CONST' <br /> Model Value: 0 <br /> Domain API Value: 'Constant' |
| Attribute | Attribute value. Stored as 'ATTRIB'. <br /> Database Value: 'ATTRIB' <br /> Model Value: 1 <br /> Domain API Value: 'Attribute' |
| Reference | Reference value. Stored as 'REF'. <br /> Database Value: 'REF' <br /> Model Value: 2 <br /> Domain API Value: 'Reference' |
| ChildList | ChildList value. Stored as 'CHILD'. <br /> Database Value: 'CHILD' <br /> Model Value: 3 <br /> Domain API Value: 'ChildList' |
| FormattedString | FormattedString value. Stored as 'FMTSTR'. <br /> Database Value: 'FMTSTR' <br /> Model Value: 4 <br /> Domain API Value: 'FormattedString' |
| Interpolate | Interpolate value. Stored as 'INTERPOLATE'. <br /> Database Value: 'INTERPOLATE' <br /> Model Value: 5 <br /> Domain API Value: 'Interpolate' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Parameter2Value

The actual value of the parameter.

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### Parameter3Type

The type of the parameter specifies how to obtain the parameter value.

Type: **[ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter3type) __nullable__**  
Category: **System**  
Generic enum type for ActionParameterType properties  
Allowed Values (Systems.Bpm.ActionParameterType Enum Members)  

| Value | Description |
| ---- | --- |
| Constant | Constant value. Stored as 'CONST'. <br /> Database Value: 'CONST' <br /> Model Value: 0 <br /> Domain API Value: 'Constant' |
| Attribute | Attribute value. Stored as 'ATTRIB'. <br /> Database Value: 'ATTRIB' <br /> Model Value: 1 <br /> Domain API Value: 'Attribute' |
| Reference | Reference value. Stored as 'REF'. <br /> Database Value: 'REF' <br /> Model Value: 2 <br /> Domain API Value: 'Reference' |
| ChildList | ChildList value. Stored as 'CHILD'. <br /> Database Value: 'CHILD' <br /> Model Value: 3 <br /> Domain API Value: 'ChildList' |
| FormattedString | FormattedString value. Stored as 'FMTSTR'. <br /> Database Value: 'FMTSTR' <br /> Model Value: 4 <br /> Domain API Value: 'FormattedString' |
| Interpolate | Interpolate value. Stored as 'INTERPOLATE'. <br /> Database Value: 'INTERPOLATE' <br /> Model Value: 5 <br /> Domain API Value: 'Interpolate' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Parameter3Value

The actual value of the parameter.

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
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

### UserBusinessRule

The business rule, for which the action is defined.

Type: **[UserBusinessRules](Systems.Bpm.UserBusinessRules.md)**  
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

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRuleActions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRuleActions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_UserBusinessRuleActions

Domain API Entity Type: 
Systems_Bpm_UserBusinessRuleAction

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_UserBusinessRuleActions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_UserBusinessRuleActions?$top=10>

