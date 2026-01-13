---
uid: HumanResources.Governance.GovernancePolicyRevisions
---
# HumanResources.Governance.GovernancePolicyRevisions Entity

**Namespace:** [HumanResources.Governance](HumanResources.Governance.md)  

Policy revisions store the actual text of a policy as it applies for a specific period of time. Each revision represents a concrete version of the policy content, including its lifecycle state and the dates when it is valid. Policy revisions are used to determine which policy text is in force at a given moment and to preserve a stable history for reference and auditing. Entity: Hrm_Governance_Policy_Revisions (Introduced in version 26.2.0.88)

## Default Visualization
Default Display Text Format:  
_{Policy.Name:T}_  
Default Search Members:  
_Policy.Name_  
Name Data Member:  
_Policy.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[HumanResources.Governance.GovernancePolicies](HumanResources.Governance.GovernancePolicies.md)  
Aggregate Root:  
[HumanResources.Governance.GovernancePolicies](HumanResources.Governance.GovernancePolicies.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](HumanResources.Governance.GovernancePolicyRevisions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](HumanResources.Governance.GovernancePolicyRevisions.md#id) | guid |  
| [ObjectVersion](HumanResources.Governance.GovernancePolicyRevisions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PolicyContent](HumanResources.Governance.GovernancePolicyRevisions.md#policycontent) | string (max) | Full policy text for this revision - single editable text (in MarkDown). This is the authoritative content used by humans and AI. `Required` `Filter(like)` 
| [State](HumanResources.Governance.GovernancePolicyRevisions.md#state) | [State](HumanResources.Governance.GovernancePolicyRevisions.md#state) | Lifecycle state of the revision. `Required` `Default("DRF")` 
| [ValidFrom](HumanResources.Governance.GovernancePolicyRevisions.md#validfrom) | date __nullable__ | Date from which this revision is intended to apply. Required when State = Published or Retired. `Filter(eq;ge;le)` 
| [ValidTo](HumanResources.Governance.GovernancePolicyRevisions.md#validto) | date __nullable__ | Date until which this revision applies (null = open-ended). Typically set automatically when a newer revision becomes effective. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Policy](HumanResources.Governance.GovernancePolicyRevisions.md#policy) | [GovernancePolicies](HumanResources.Governance.GovernancePolicies.md) | Reference to the policy this revision belongs to. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

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

### PolicyContent

Full policy text for this revision - single editable text (in MarkDown). This is the authoritative content used by humans and AI. `Required` `Filter(like)`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### State

Lifecycle state of the revision. `Required` `Default("DRF")`

_Type_: **[State](HumanResources.Governance.GovernancePolicyRevisions.md#state)**  
_Category_: **System**  
Allowed values for the `State`(HumanResources.Governance.GovernancePolicyRevisions.md#state) data attribute  
_Allowed Values (HumanResources.Governance.GovernancePolicyRevisionsRepository.State Enum Members)_  

| Value | Description |
| ---- | --- |
| Draft | Draft. Stored as 'DRF'. <br /> _Database Value:_ 'DRF' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Draft' |
| InReview | In Review. Stored as 'REV'. <br /> _Database Value:_ 'REV' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'InReview' |
| Accepted | Accepted. Stored as 'ACP'. <br /> _Database Value:_ 'ACP' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Accepted' |
| Published | Published. Stored as 'PUB'. <br /> _Database Value:_ 'PUB' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Published' |
| Retired | Retired. Stored as 'RET'. <br /> _Database Value:_ 'RET' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Retired' |
| Cancelled | Cancelled. Stored as 'CNL'. <br /> _Database Value:_ 'CNL' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Cancelled' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **Draft**  
_Show in UI_: **ShownByDefault**  

### ValidFrom

Date from which this revision is intended to apply. Required when State = Published or Retired. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ValidTo

Date until which this revision applies (null = open-ended). Typically set automatically when a newer revision becomes effective. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Policy

Reference to the policy this revision belongs to. `Required` `Filter(multi eq)` `Owner`

_Type_: **[GovernancePolicies](HumanResources.Governance.GovernancePolicies.md)**  
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

[!list limit=1000 erp.entity=HumanResources.Governance.GovernancePolicyRevisions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=HumanResources.Governance.GovernancePolicyRevisions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
HumanResources_Governance_GovernancePolicyRevisions

Domain API Entity Type: 
HumanResources_Governance_GovernancePolicyRevision

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/HumanResources_Governance_GovernancePolicyRevisions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#HumanResources_Governance_GovernancePolicyRevisions?$top=10>

