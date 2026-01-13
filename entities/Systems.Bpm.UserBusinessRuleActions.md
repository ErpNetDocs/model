---
uid: Systems.Bpm.UserBusinessRuleActions
---
# Systems.Bpm.UserBusinessRuleActions Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Represents an action within a business rule. Entity: Sys_User_Business_Rule_Actions

## Default Visualization
Default Display Text Format:  
_{UserBusinessRule.Name:T}_  
Default Search Members:  
_UserBusinessRule.Name_  
Name Data Member:  
_UserBusinessRule.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  
Aggregate Root:  
[Systems.Bpm.UserBusinessRules](Systems.Bpm.UserBusinessRules.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActionNo](Systems.Bpm.UserBusinessRuleActions.md#actionno) | int32 | Consecutive number of the action, unique within the business rule. `Required` 
| [ActionType](Systems.Bpm.UserBusinessRuleActions.md#actiontype) | [ActionType](Systems.Bpm.UserBusinessRuleActions.md#actiontype) | Specifies the type of action to perform. `Required` 
| [DisplayText](Systems.Bpm.UserBusinessRuleActions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Bpm.UserBusinessRuleActions.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.UserBusinessRuleActions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Parameter1Type](Systems.Bpm.UserBusinessRuleActions.md#parameter1type) | [ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter1type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter1Value](Systems.Bpm.UserBusinessRuleActions.md#parameter1value) | string (256) __nullable__ | The actual value of the parameter. 
| [Parameter2Type](Systems.Bpm.UserBusinessRuleActions.md#parameter2type) | [ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter2type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter2Value](Systems.Bpm.UserBusinessRuleActions.md#parameter2value) | string (256) __nullable__ | The actual value of the parameter. 
| [Parameter3Type](Systems.Bpm.UserBusinessRuleActions.md#parameter3type) | [ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter3type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter3Value](Systems.Bpm.UserBusinessRuleActions.md#parameter3value) | string (256) __nullable__ | The actual value of the parameter. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [UserBusinessRule](Systems.Bpm.UserBusinessRuleActions.md#userbusinessrule) | [UserBusinessRules](Systems.Bpm.UserBusinessRules.md) | The business rule, for which the action is defined. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ActionNo

Consecutive number of the action, unique within the business rule. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.UserBusinessRule.Actions.Select( c => c.ActionNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.UserBusinessRule.Actions.Select( c => c.ActionNo).DefaultIfEmpty( 0).Max( ) + 1)`
### ActionType

Specifies the type of action to perform. `Required`

_Type_: **[ActionType](Systems.Bpm.UserBusinessRuleActions.md#actiontype)**  
_Category_: **System**  
Allowed values for the `ActionType`(Systems.Bpm.UserBusinessRuleActions.md#actiontype) data attribute  
_Allowed Values (Systems.Bpm.UserBusinessRuleActionsRepository.ActionType Enum Members)_  

| Value | Description |
| ---- | --- |
| SETVALUE | SETVALUE value. Stored as 'SETVALUE'. <br /> _Database Value:_ 'SETVALUE' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'SETVALUE' |
| FAIL | FAIL value. Stored as 'FAIL'. <br /> _Database Value:_ 'FAIL' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'FAIL' |
| SENDMAIL | SENDMAIL value. Stored as 'SENDMAIL'. <br /> _Database Value:_ 'SENDMAIL' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'SENDMAIL' |
| WARNING | WARNING value. Stored as 'WARNING'. <br /> _Database Value:_ 'WARNING' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'WARNING' |
| NOTIFYUSER | NOTIFYUSER value. Stored as 'NOTIFYUSER'. <br /> _Database Value:_ 'NOTIFYUSER' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'NOTIFYUSER' |
| WEBHOOK | WEBHOOK value. Stored as 'WEBHOOK'. <br /> _Database Value:_ 'WEBHOOK' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'WEBHOOK' |
| AISET | AISET value. Stored as 'AISET'. <br /> _Database Value:_ 'AISET' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'AISET' |
| AIVALIDATE | AIVALIDATE value. Stored as 'AIVALIDATE'. <br /> _Database Value:_ 'AIVALIDATE' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'AIVALIDATE' |
| AIWARNING | AIWARNING value. Stored as 'AIWARNING'. <br /> _Database Value:_ 'AIWARNING' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'AIWARNING' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
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

### Parameter1Type

The type of the parameter specifies how to obtain the parameter value.

_Type_: **[ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter1type) __nullable__**  
_Category_: **System**  
Generic enum type for ActionParameterType properties  
_Allowed Values (Systems.Bpm.ActionParameterType Enum Members)_  

| Value | Description |
| ---- | --- |
| Constant | Constant value. Stored as 'CONST'. <br /> _Database Value:_ 'CONST' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Constant' |
| Attribute | Attribute value. Stored as 'ATTRIB'. <br /> _Database Value:_ 'ATTRIB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Attribute' |
| Reference | Reference value. Stored as 'REF'. <br /> _Database Value:_ 'REF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Reference' |
| ChildList | ChildList value. Stored as 'CHILD'. <br /> _Database Value:_ 'CHILD' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'ChildList' |
| FormattedString | FormattedString value. Stored as 'FMTSTR'. <br /> _Database Value:_ 'FMTSTR' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'FormattedString' |
| Interpolate | Interpolate value. Stored as 'INTERPOLATE'. <br /> _Database Value:_ 'INTERPOLATE' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Interpolate' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Parameter1Value

The actual value of the parameter.

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### Parameter2Type

The type of the parameter specifies how to obtain the parameter value.

_Type_: **[ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter2type) __nullable__**  
_Category_: **System**  
Generic enum type for ActionParameterType properties  
_Allowed Values (Systems.Bpm.ActionParameterType Enum Members)_  

| Value | Description |
| ---- | --- |
| Constant | Constant value. Stored as 'CONST'. <br /> _Database Value:_ 'CONST' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Constant' |
| Attribute | Attribute value. Stored as 'ATTRIB'. <br /> _Database Value:_ 'ATTRIB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Attribute' |
| Reference | Reference value. Stored as 'REF'. <br /> _Database Value:_ 'REF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Reference' |
| ChildList | ChildList value. Stored as 'CHILD'. <br /> _Database Value:_ 'CHILD' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'ChildList' |
| FormattedString | FormattedString value. Stored as 'FMTSTR'. <br /> _Database Value:_ 'FMTSTR' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'FormattedString' |
| Interpolate | Interpolate value. Stored as 'INTERPOLATE'. <br /> _Database Value:_ 'INTERPOLATE' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Interpolate' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Parameter2Value

The actual value of the parameter.

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### Parameter3Type

The type of the parameter specifies how to obtain the parameter value.

_Type_: **[ActionParameterType](Systems.Bpm.UserBusinessRuleActions.md#parameter3type) __nullable__**  
_Category_: **System**  
Generic enum type for ActionParameterType properties  
_Allowed Values (Systems.Bpm.ActionParameterType Enum Members)_  

| Value | Description |
| ---- | --- |
| Constant | Constant value. Stored as 'CONST'. <br /> _Database Value:_ 'CONST' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Constant' |
| Attribute | Attribute value. Stored as 'ATTRIB'. <br /> _Database Value:_ 'ATTRIB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Attribute' |
| Reference | Reference value. Stored as 'REF'. <br /> _Database Value:_ 'REF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Reference' |
| ChildList | ChildList value. Stored as 'CHILD'. <br /> _Database Value:_ 'CHILD' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'ChildList' |
| FormattedString | FormattedString value. Stored as 'FMTSTR'. <br /> _Database Value:_ 'FMTSTR' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'FormattedString' |
| Interpolate | Interpolate value. Stored as 'INTERPOLATE'. <br /> _Database Value:_ 'INTERPOLATE' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Interpolate' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Parameter3Value

The actual value of the parameter.

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### UserBusinessRule

The business rule, for which the action is defined. `Required` `Filter(multi eq)` `Owner`

_Type_: **[UserBusinessRules](Systems.Bpm.UserBusinessRules.md)**  
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

