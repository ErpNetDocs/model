---
uid: Systems.Bpm.UserBusinessRuleEvents
---
# Systems.Bpm.UserBusinessRuleEvents Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Represents event registration of a business rule. Entity: Sys_User_Business_Rule_Events

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
| [DisplayText](Systems.Bpm.UserBusinessRuleEvents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EventParameter](Systems.Bpm.UserBusinessRuleEvents.md#eventparameter) | string (128) __nullable__ | Registration parameter. The meaning is determined by the event. Usually - attribute name, document state, etc. 
| [EventType](Systems.Bpm.UserBusinessRuleEvents.md#eventtype) | [EventType](Systems.Bpm.UserBusinessRuleEvents.md#eventtype) | The event for which to register the business rule. `Required` 
| [ExecutionPriority](Systems.Bpm.UserBusinessRuleEvents.md#executionpriority) | [RuleExecutionPriority](Systems.Bpm.UserBusinessRuleEvents.md#executionpriority) | Execution priority. Lower values indicate earlier priorities. Possible values - 30-Early, 50-Normal, 70-Late. `Required` `Default(50)` 
| [Id](Systems.Bpm.UserBusinessRuleEvents.md#id) | guid |  
| [Layer](Systems.Bpm.UserBusinessRuleEvents.md#layer) | [Layer](Systems.Bpm.UserBusinessRuleEvents.md#layer) | Specifies the layer on which to register the event. Allowed values = FTE-FrontEnd, BKE-BackEnd. `Required` `Default("BKE")` 
| [ObjectVersion](Systems.Bpm.UserBusinessRuleEvents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [UserBusinessRule](Systems.Bpm.UserBusinessRuleEvents.md#userbusinessrule) | [UserBusinessRules](Systems.Bpm.UserBusinessRules.md) | The rule, which will be registered for the event. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EventParameter

Registration parameter. The meaning is determined by the event. Usually - attribute name, document state, etc.

_Type_: **string (128) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **128**  
_Show in UI_: **ShownByDefault**  

### EventType

The event for which to register the business rule. `Required`

_Type_: **[EventType](Systems.Bpm.UserBusinessRuleEvents.md#eventtype)**  
_Category_: **System**  
Allowed values for the `EventType`(Systems.Bpm.UserBusinessRuleEvents.md#eventtype) data attribute  
_Allowed Values (Systems.Bpm.UserBusinessRuleEventsRepository.EventType Enum Members)_  

| Value | Description |
| ---- | --- |
| AGGREGATECLIENTCOMMIT | Occurs for the aggregate root when saving a change of an aggregate object, but only when the change is made by a client application. If the change is made by the server, the event will not be triggered.. Stored as 'AGGREGATECLIENTCOMMIT'. <br /> _Database Value:_ 'AGGREGATECLIENTCOMMIT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AGGREGATECLIENTCOMMIT' |
| ATTRIBUTECHANGED | Occurs after the attribute's value is changed. The attribute's name is specified in the 'Event Parameter' field.. Stored as 'ATTRIBUTECHANGED'. <br /> _Database Value:_ 'ATTRIBUTECHANGED' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ATTRIBUTECHANGED' |
| ATTRIBUTECHANGING | Occurs before the attribute's value is changed. The attribute's name is specified in the 'Event Parameter' field.. Stored as 'ATTRIBUTECHANGING'. <br /> _Database Value:_ 'ATTRIBUTECHANGING' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'ATTRIBUTECHANGING' |
| CLIENTCOMMIT | Occurs when saving a change of the object, when the change is made by a client application. If the change is made by the server, the event will not be triggered.. Stored as 'CLIENTCOMMIT'. <br /> _Database Value:_ 'CLIENTCOMMIT' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'CLIENTCOMMIT' |
| COMMIT | Occurs when saving a change of the object.. Stored as 'COMMIT'. <br /> _Database Value:_ 'COMMIT' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'COMMIT' |
| STATECHANGED | Occurs when the document state is changed. The state is specified in the 'Event Parameter' field. Possible parameter values are 'PLANNED', 'FIRMPLANNED', 'RELEASED', 'COMPLETED' and 'CLOSED'.. Stored as 'STATECHANGED'. <br /> _Database Value:_ 'STATECHANGED' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'STATECHANGED' |
| STATECHANGING | Occurs during the document state change. The state is specified in the 'Event Parameter' field. Possible parameter values are 'PLANNING', 'FIRMPLANNING', 'RELEASING', 'COMPLETING' and 'CLOSING'.. Stored as 'STATECHANGING'. <br /> _Database Value:_ 'STATECHANGING' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'STATECHANGING' |
| VOIDING | Occurs during the voiding of a document.. Stored as 'VOIDING'. <br /> _Database Value:_ 'VOIDING' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'VOIDING' |
| CREATENEW | Occurs when a new object is created. Used to fill custom defaults.. Stored as 'CREATENEW'. <br /> _Database Value:_ 'CREATENEW' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'CREATENEW' |
| COMMITTED | COMMITTED value. Stored as 'COMMITTED'. <br /> _Database Value:_ 'COMMITTED' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'COMMITTED' |
| CLIENTCOMMITTED | CLIENTCOMMITTED value. Stored as 'CLIENTCOMMITTED'. <br /> _Database Value:_ 'CLIENTCOMMITTED' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'CLIENTCOMMITTED' |
| AGGREGATECLIENTCOMMITTED | AGGREGATECLIENTCOMMITTED value. Stored as 'AGGREGATECLIENTCOMMITTED'. <br /> _Database Value:_ 'AGGREGATECLIENTCOMMITTED' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'AGGREGATECLIENTCOMMITTED' |
| BEFORERECALCULATE | The event occurs before every recalculation of the amounts in the document for each object in the document aggregate. . Stored as 'BEFORERECALCULATE '. <br /> _Database Value:_ 'BEFORERECALCULATE ' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'BEFORERECALCULATE' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ExecutionPriority

Execution priority. Lower values indicate earlier priorities. Possible values - 30-Early, 50-Normal, 70-Late. `Required` `Default(50)`

_Type_: **[RuleExecutionPriority](Systems.Bpm.UserBusinessRuleEvents.md#executionpriority)**  
_Category_: **System**  
_Allowed Values (Aloe.SystemFrameworks.Domain.BusinessLogic.RuleExecutionPriority Enum Members)_  

| Value | Description |
| ---- | --- |
| Early | _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Early' |
| Normal | _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'Normal' |
| Late | _Database Value:_ 70 <br /> _Model Value:_ 70 <br /> _Domain API Value:_ 'Late' |
| SystemLateUpdate | _Database Value:_ 150 <br /> _Model Value:_ 150 <br /> _Domain API Value:_ 'SystemLateUpdate' |
| SystemLateValidate | _Database Value:_ 200 <br /> _Model Value:_ 200 <br /> _Domain API Value:_ 'SystemLateValidate' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **50**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Layer

Specifies the layer on which to register the event. Allowed values = FTE-FrontEnd, BKE-BackEnd. `Required` `Default("BKE")`

_Type_: **[Layer](Systems.Bpm.UserBusinessRuleEvents.md#layer)**  
_Category_: **System**  
Allowed values for the `Layer`(Systems.Bpm.UserBusinessRuleEvents.md#layer) data attribute  
_Allowed Values (Systems.Bpm.UserBusinessRuleEventsRepository.Layer Enum Members)_  

| Value | Description |
| ---- | --- |
| FrontEnd | FrontEnd value. Stored as 'FTE'. <br /> _Database Value:_ 'FTE' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'FrontEnd' |
| BackEnd | BackEnd value. Stored as 'BKE'. <br /> _Database Value:_ 'BKE' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'BackEnd' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **BackEnd**  
_Show in UI_: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### UserBusinessRule

The rule, which will be registered for the event. `Required` `Filter(multi eq)` `Owner`

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

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRuleEvents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.UserBusinessRuleEvents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_UserBusinessRuleEvents

Domain API Entity Type: 
Systems_Bpm_UserBusinessRuleEvent

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_UserBusinessRuleEvents?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_UserBusinessRuleEvents?$top=10>

