---
uid: General.Activities.ActivityParticipants
---
# General.Activities.ActivityParticipants Entity

**Namespace:** [General.Activities](General.Activities.md)  

Contains the additional participants in the activities. These are the participating users, besides the user to which the activitiy is assigned. Entity: Cm_Activity_Participants

## Renames

Old name: **General.Contacts.ActivityParticipants**  
New name: **General.Activities.ActivityParticipants**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Activity.EntityName}_  
Default Search Members:  
_Activity.EntityName_  
Name Data Member:  
_Activity.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Activities.Activities](General.Activities.Activities.md)  
Aggregate Root:  
[General.Activities.Activities](General.Activities.Activities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](General.Activities.ActivityParticipants.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Email](General.Activities.ActivityParticipants.md#email) | string (254) __nullable__ | Participant email. Used to identify the participant and is required when syncing with external services. `Filter(multi eq;like)` `Introduced in version 24.1.4.87` 
| [Id](General.Activities.ActivityParticipants.md#id) | guid |  
| [Notes](General.Activities.ActivityParticipants.md#notes) | string (255) __nullable__ | Notes for this ActivityParticipant. 
| [ObjectVersion](General.Activities.ActivityParticipants.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [WorkLoadPercent](General.Activities.ActivityParticipants.md#workloadpercent) | decimal (3, 2) | The planned work load of the participant for this activity. `Required` `Default(1)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Activity](General.Activities.ActivityParticipants.md#activity) | [Activities](General.Activities.Activities.md) | The <see cref="Activity"/> to which this ActivityParticipant belongs. `Required` `Filter(multi eq)` `Owner` |
| [ParticipantPerson](General.Activities.ActivityParticipants.md#participantperson) | [Persons](General.Contacts.Persons.md) (nullable) | The person, participating in an activity. `Filter(multi eq)` |
| [User](General.Activities.ActivityParticipants.md#user) | [Users](Systems.Security.Users.md) (nullable) | The user associated with the Person participating in the activity. `Filter(multi eq)` `Introduced in version 24.1.5.15` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Email

Participant email. Used to identify the participant and is required when syncing with external services. `Filter(multi eq;like)` `Introduced in version 24.1.4.87`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`GetRelatedUserEmailAddress( obj.ParticipantPerson)`

_Front-End Recalc Expressions:_  
`GetRelatedUserEmailAddress( obj.ParticipantPerson)`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Notes for this ActivityParticipant.

_Type_: **string (255) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **255**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### WorkLoadPercent

The planned work load of the participant for this activity. `Required` `Default(1)`

_Type_: **decimal (3, 2)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Activity

The <see cref="Activity"/> to which this ActivityParticipant belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Activities](General.Activities.Activities.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ParticipantPerson

The person, participating in an activity. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The user associated with the Person participating in the activity. `Filter(multi eq)` `Introduced in version 24.1.5.15`

_Type_: **[Users](Systems.Security.Users.md) (nullable)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=General.Activities.ActivityParticipants erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Activities.ActivityParticipants erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Activities_ActivityParticipants

Domain API Entity Type: 
General_Activities_ActivityParticipant

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Activities_ActivityParticipants?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Activities_ActivityParticipants?$top=10>

