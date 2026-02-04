---
uid: Systems.Bpm.UserBusinessRuleEvents
---
# Systems.Bpm.UserBusinessRuleEvents


Represents event registration of a business rule.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.UserBusinessRuleEvents  
Base Table: Sys_User_Business_Rule_Events  
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
| [EventParameter](Systems.Bpm.UserBusinessRuleEvents.md#eventparameter) | string (128) __nullable__ | Registration parameter. The meaning is determined by the event. Usually - attribute name, document state, etc. 
| [EventType](Systems.Bpm.UserBusinessRuleEvents.md#eventtype) | [EventType](Systems.Bpm.UserBusinessRuleEvents.md#eventtype) | The event for which to register the business rule. 
| [ExecutionPriority](Systems.Bpm.UserBusinessRuleEvents.md#executionpriority) | [RuleExecutionPriority](Systems.Bpm.UserBusinessRuleEvents.md#executionpriority) | Execution priority. Lower values indicate earlier priorities. Possible values - 30-Early, 50-Normal, 70-Late. 
| [Layer](Systems.Bpm.UserBusinessRuleEvents.md#layer) | [Layer](Systems.Bpm.UserBusinessRuleEvents.md#layer) | Specifies the layer on which to register the event. Allowed values = FTE-FrontEnd, BKE-BackEnd. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [UserBusinessRule](Systems.Bpm.UserBusinessRuleEvents.md#userbusinessrule) | [UserBusinessRules](Systems.Bpm.UserBusinessRules.md) | The rule, which will be registered for the event. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.UserBusinessRuleEvents.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.UserBusinessRuleEvents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Bpm.UserBusinessRuleEvents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### EventParameter

Registration parameter. The meaning is determined by the event. Usually - attribute name, document state, etc.

Type: **string (128) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **128**  
Show in UI: **ShownByDefault**  

### EventType

The event for which to register the business rule.

Type: **[EventType](Systems.Bpm.UserBusinessRuleEvents.md#eventtype)**  
Category: **System**  
Allowed values for the `EventType`(Systems.Bpm.UserBusinessRuleEvents.md#eventtype) data attribute  
Allowed Values (Systems.Bpm.UserBusinessRuleEventsRepository.EventType Enum Members)  

| Value | Description |
| ---- | --- |
| AGGREGATECLIENTCOMMIT | Occurs for the aggregate root when saving a change of an aggregate object, but only when the change is made by a client application. If the change is made by the server, the event will not be triggered.. Stored as 'AGGREGATECLIENTCOMMIT'. <br /> Database Value: 'AGGREGATECLIENTCOMMIT' <br /> Model Value: 0 <br /> Domain API Value: 'AGGREGATECLIENTCOMMIT' |
| ATTRIBUTECHANGED | Occurs after the attribute's value is changed. The attribute's name is specified in the 'Event Parameter' field.. Stored as 'ATTRIBUTECHANGED'. <br /> Database Value: 'ATTRIBUTECHANGED' <br /> Model Value: 1 <br /> Domain API Value: 'ATTRIBUTECHANGED' |
| ATTRIBUTECHANGING | Occurs before the attribute's value is changed. The attribute's name is specified in the 'Event Parameter' field.. Stored as 'ATTRIBUTECHANGING'. <br /> Database Value: 'ATTRIBUTECHANGING' <br /> Model Value: 2 <br /> Domain API Value: 'ATTRIBUTECHANGING' |
| CLIENTCOMMIT | Occurs when saving a change of the object, when the change is made by a client application. If the change is made by the server, the event will not be triggered.. Stored as 'CLIENTCOMMIT'. <br /> Database Value: 'CLIENTCOMMIT' <br /> Model Value: 3 <br /> Domain API Value: 'CLIENTCOMMIT' |
| COMMIT | Occurs when saving a change of the object.. Stored as 'COMMIT'. <br /> Database Value: 'COMMIT' <br /> Model Value: 4 <br /> Domain API Value: 'COMMIT' |
| STATECHANGED | Occurs when the document state is changed. The state is specified in the 'Event Parameter' field. Possible parameter values are 'PLANNED', 'FIRMPLANNED', 'RELEASED', 'COMPLETED' and 'CLOSED'.. Stored as 'STATECHANGED'. <br /> Database Value: 'STATECHANGED' <br /> Model Value: 5 <br /> Domain API Value: 'STATECHANGED' |
| STATECHANGING | Occurs during the document state change. The state is specified in the 'Event Parameter' field. Possible parameter values are 'PLANNING', 'FIRMPLANNING', 'RELEASING', 'COMPLETING' and 'CLOSING'.. Stored as 'STATECHANGING'. <br /> Database Value: 'STATECHANGING' <br /> Model Value: 6 <br /> Domain API Value: 'STATECHANGING' |
| VOIDING | Occurs during the voiding of a document.. Stored as 'VOIDING'. <br /> Database Value: 'VOIDING' <br /> Model Value: 7 <br /> Domain API Value: 'VOIDING' |
| CREATENEW | Occurs when a new object is created. Used to fill custom defaults.. Stored as 'CREATENEW'. <br /> Database Value: 'CREATENEW' <br /> Model Value: 8 <br /> Domain API Value: 'CREATENEW' |
| COMMITTED | COMMITTED value. Stored as 'COMMITTED'. <br /> Database Value: 'COMMITTED' <br /> Model Value: 9 <br /> Domain API Value: 'COMMITTED' |
| CLIENTCOMMITTED | CLIENTCOMMITTED value. Stored as 'CLIENTCOMMITTED'. <br /> Database Value: 'CLIENTCOMMITTED' <br /> Model Value: 10 <br /> Domain API Value: 'CLIENTCOMMITTED' |
| AGGREGATECLIENTCOMMITTED | AGGREGATECLIENTCOMMITTED value. Stored as 'AGGREGATECLIENTCOMMITTED'. <br /> Database Value: 'AGGREGATECLIENTCOMMITTED' <br /> Model Value: 11 <br /> Domain API Value: 'AGGREGATECLIENTCOMMITTED' |
| BEFORERECALCULATE | The event occurs before every recalculation of the amounts in the document for each object in the document aggregate. . Stored as 'BEFORERECALCULATE '. <br /> Database Value: 'BEFORERECALCULATE ' <br /> Model Value: 12 <br /> Domain API Value: 'BEFORERECALCULATE' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ExecutionPriority

Execution priority. Lower values indicate earlier priorities. Possible values - 30-Early, 50-Normal, 70-Late.

Type: **[RuleExecutionPriority](Systems.Bpm.UserBusinessRuleEvents.md#executionpriority)**  
Category: **System**  
Allowed Values (Aloe.SystemFrameworks.Domain.BusinessLogic.RuleExecutionPriority Enum Members)  

| Value | Description |
| ---- | --- |
| Early | Database Value: 30 <br /> Model Value: 30 <br /> Domain API Value: 'Early' |
| Normal | Database Value: 50 <br /> Model Value: 50 <br /> Domain API Value: 'Normal' |
| Late | Database Value: 70 <br /> Model Value: 70 <br /> Domain API Value: 'Late' |
| SystemLateUpdate | Database Value: 150 <br /> Model Value: 150 <br /> Domain API Value: 'SystemLateUpdate' |
| SystemLateValidate | Database Value: 200 <br /> Model Value: 200 <br /> Domain API Value: 'SystemLateValidate' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **50**  
Show in UI: **ShownByDefault**  

### Layer

Specifies the layer on which to register the event. Allowed values = FTE-FrontEnd, BKE-BackEnd.

Type: **[Layer](Systems.Bpm.UserBusinessRuleEvents.md#layer)**  
Category: **System**  
Allowed values for the `Layer`(Systems.Bpm.UserBusinessRuleEvents.md#layer) data attribute  
Allowed Values (Systems.Bpm.UserBusinessRuleEventsRepository.Layer Enum Members)  

| Value | Description |
| ---- | --- |
| FrontEnd | FrontEnd value. Stored as 'FTE'. <br /> Database Value: 'FTE' <br /> Model Value: 0 <br /> Domain API Value: 'FrontEnd' |
| BackEnd | BackEnd value. Stored as 'BKE'. <br /> Database Value: 'BKE' <br /> Model Value: 1 <br /> Domain API Value: 'BackEnd' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **BackEnd**  
Show in UI: **CannotBeShown**  

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

The rule, which will be registered for the event.

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

