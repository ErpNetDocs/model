---
uid: HumanResources.Governance.GovernancePolicyRevisions
---
# HumanResources.Governance.GovernancePolicyRevisions


Policy revisions store the actual text of a policy as it applies for a specific period of time. Each revision represents a concrete version of the policy content, including its lifecycle state and the dates when it is valid. Policy revisions are used to determine which policy text is in force at a given moment and to preserve a stable history for reference and auditing.

## General
Namespace: [HumanResources.Governance](HumanResources.Governance.md)  
Repository: HumanResources.Governance.GovernancePolicyRevisions  
Base Table: Hrm_Governance_Policy_Revisions  
Introduced In Version: 26.2.0.88  
API access:  ReadWrite  

## Visualization
Display Format: {Policy.Name:T}  
Search Members: Policy.Name  
Name Member: Policy.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[HumanResources.Governance.GovernancePolicies](HumanResources.Governance.GovernancePolicies.md)  
Aggregate Root:  
[HumanResources.Governance.GovernancePolicies](HumanResources.Governance.GovernancePolicies.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [PolicyContent](HumanResources.Governance.GovernancePolicyRevisions.md#policycontent) | string (max) | Full policy text for this revision - single editable text (in MarkDown). This is the authoritative content used by humans and AI. 
| [State](HumanResources.Governance.GovernancePolicyRevisions.md#state) | [State](HumanResources.Governance.GovernancePolicyRevisions.md#state) | Lifecycle state of the revision. 
| [ValidFrom](HumanResources.Governance.GovernancePolicyRevisions.md#validfrom) | date __nullable__ | Date from which this revision is intended to apply. Required when State = Published or Retired. 
| [ValidTo](HumanResources.Governance.GovernancePolicyRevisions.md#validto) | date __nullable__ | Date until which this revision applies (NULL = open-ended). Typically set automatically when a newer revision becomes effective. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Policy](HumanResources.Governance.GovernancePolicyRevisions.md#policy) | [GovernancePolicies](HumanResources.Governance.GovernancePolicies.md) | Reference to the policy this revision belongs to. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](HumanResources.Governance.GovernancePolicyRevisions.md#id) | guid |  
| [ObjectVersion](HumanResources.Governance.GovernancePolicyRevisions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](HumanResources.Governance.GovernancePolicyRevisions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### PolicyContent

Full policy text for this revision - single editable text (in MarkDown). This is the authoritative content used by humans and AI.

Type: **string (max)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### State

Lifecycle state of the revision.

Type: **[State](HumanResources.Governance.GovernancePolicyRevisions.md#state)**  
Category: **System**  
Allowed values for the `State`(HumanResources.Governance.GovernancePolicyRevisions.md#state) data attribute  
Allowed Values (HumanResources.Governance.GovernancePolicyRevisionsRepository.State Enum Members)  

| Value | Description |
| ---- | --- |
| Draft | Draft. Stored as 'DRF'. <br /> Database Value: 'DRF' <br /> Model Value: 0 <br /> Domain API Value: 'Draft' |
| InReview | In Review. Stored as 'REV'. <br /> Database Value: 'REV' <br /> Model Value: 1 <br /> Domain API Value: 'InReview' |
| Accepted | Accepted. Stored as 'ACP'. <br /> Database Value: 'ACP' <br /> Model Value: 2 <br /> Domain API Value: 'Accepted' |
| Published | Published. Stored as 'PUB'. <br /> Database Value: 'PUB' <br /> Model Value: 3 <br /> Domain API Value: 'Published' |
| Retired | Retired. Stored as 'RET'. <br /> Database Value: 'RET' <br /> Model Value: 4 <br /> Domain API Value: 'Retired' |
| Cancelled | Cancelled. Stored as 'CNL'. <br /> Database Value: 'CNL' <br /> Model Value: 5 <br /> Domain API Value: 'Cancelled' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Draft**  
Show in UI: **ShownByDefault**  

### ValidFrom

Date from which this revision is intended to apply. Required when State = Published or Retired.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidTo

Date until which this revision applies (NULL = open-ended). Typically set automatically when a newer revision becomes effective.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### Policy

Reference to the policy this revision belongs to.

Type: **[GovernancePolicies](HumanResources.Governance.GovernancePolicies.md)**  
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

