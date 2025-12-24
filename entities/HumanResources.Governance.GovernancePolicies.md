---
uid: HumanResources.Governance.GovernancePolicies
---
# HumanResources.Governance.GovernancePolicies Entity

**Namespace:** [HumanResources.Governance](HumanResources.Governance.md)  

Policies represent the identity of an internal rule, policy, procedure, guideline, or job description. A policy defines what the rule is about, how it is named and classified, and how it is organized (e.g. in folders). The actual text of the policy and its changes over time are stored as separate policy revisions. Entity: Hrm_Governance_Policies (Introduced in version 26.2.0.88)

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [HumanResources.Governance.GovernancePolicies](HumanResources.Governance.GovernancePolicies.md)  
  * [HumanResources.Governance.GovernancePolicyRevisions](HumanResources.Governance.GovernancePolicyRevisions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](HumanResources.Governance.GovernancePolicies.md#code) | string (32) | Human-friendly unique identifier (e.g. HR-REMOTE-WORK). `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](HumanResources.Governance.GovernancePolicies.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](HumanResources.Governance.GovernancePolicies.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](HumanResources.Governance.GovernancePolicies.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](HumanResources.Governance.GovernancePolicies.md#id) | guid |  
| [IsActive](HumanResources.Governance.GovernancePolicies.md#isactive) | boolean | Indicates whether the policy is active as a concept. `Required` `Default(true)` `Filter(eq)` 
| [Name](HumanResources.Governance.GovernancePolicies.md#name) | [MultilanguageString (256)](../data-types.md#multilanguagestring) | Policy name as spoken by users (e.g. "Remote Work Policy"). `Required` `Filter(like)` 
| [ObjectVersion](HumanResources.Governance.GovernancePolicies.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PolicyKind](HumanResources.Governance.GovernancePolicies.md#policykind) | [PolicyKind](HumanResources.Governance.GovernancePolicies.md#policykind) | Classification of the policy. `Required` `Filter(eq)` 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Revisions | [GovernancePolicyRevisions](HumanResources.Governance.GovernancePolicyRevisions.md) | List of `GovernancePolicyRevision`(HumanResources.Governance.GovernancePolicyRevisions.md) child objects, based on the `HumanResources.Governance.GovernancePolicyRevision.Policy`(HumanResources.Governance.GovernancePolicyRevisions.md#policy) back reference 


## Attribute Details

### Code

Human-friendly unique identifier (e.g. HR-REMOTE-WORK). `Required` `Filter(eq;like)` `ORD`

_Type_: **string (32)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the policy is active as a concept. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

Policy name as spoken by users (e.g. "Remote Work Policy"). `Required` `Filter(like)`

_Type_: **[MultilanguageString (256)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PolicyKind

Classification of the policy. `Required` `Filter(eq)`

_Type_: **[PolicyKind](HumanResources.Governance.GovernancePolicies.md#policykind)**  
_Category_: **System**  
Allowed values for the `PolicyKind`(HumanResources.Governance.GovernancePolicies.md#policykind) data attribute  
_Allowed Values (HumanResources.Governance.GovernancePoliciesRepository.PolicyKind Enum Members)_  

| Value | Description |
| ---- | --- |
| JobDescription | Job Description. Stored as 'JOB'. <br /> _Database Value:_ 'JOB' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'JobDescription' |
| Guideline | Guideline. Stored as 'GDL'. <br /> _Database Value:_ 'GDL' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Guideline' |
| Rule | Rule. Stored as 'RUL'. <br /> _Database Value:_ 'RUL' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Rule' |
| Procedure | Procedure. Stored as 'PRC'. <br /> _Database Value:_ 'PRC' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Procedure' |
| Policy | Policy. Stored as 'POL'. <br /> _Database Value:_ 'POL' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Policy' |
| Other | Other. Stored as 'OTH'. <br /> _Database Value:_ 'OTH' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
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

[!list limit=1000 erp.entity=HumanResources.Governance.GovernancePolicies erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=HumanResources.Governance.GovernancePolicies erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
HumanResources_Governance_GovernancePolicies

Domain API Entity Type: 
HumanResources_Governance_GovernancePolicy

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/HumanResources_Governance_GovernancePolicies?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#HumanResources_Governance_GovernancePolicies?$top=10>

