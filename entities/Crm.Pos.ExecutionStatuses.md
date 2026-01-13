---
uid: Crm.Pos.ExecutionStatuses
---
# Crm.Pos.ExecutionStatuses Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

Defines user-configurable status values that describe sub-stages within a broader, system-defined execution stage (ExecutionStage). This allows businesses to model their unique operational workflows — such as food prep steps, service sessions, or treatment progress. Entity: Pos_Execution_Statuses (Introduced in version 25.1.3.45)

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pos.ExecutionStatuses](Crm.Pos.ExecutionStatuses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Crm.Pos.ExecutionStatuses.md#code) | string (16) | Unique short descriptive code of the user status. Used for display constrained devices, import/export matching, etc. `Required` `Filter(eq;like)` `ORD` 
| [DisplayText](Crm.Pos.ExecutionStatuses.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExecutionStage](Crm.Pos.ExecutionStatuses.md#executionstage) | [ExecutionStage](Crm.Pos.ExecutionStatuses.md#executionstage) | The system-defined stage under which is the current status. `Required` `Default("PND")` `Filter(multi eq)` 
| [ExternalId](Crm.Pos.ExecutionStatuses.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pos.ExecutionStatuses.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Crm.Pos.ExecutionStatuses.md#id) | guid |  
| [IsActive](Crm.Pos.ExecutionStatuses.md#isactive) | boolean | Indicates whether the POS execution status is currently active. `Required` `Default(true)` `Filter(eq)` 
| [Name](Crm.Pos.ExecutionStatuses.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the execution status. Should be action-oriented, e.g. reflect the NEXT action which should be taken (and not what is completed). For example, "Scheduled", "Ready-to-serve", etc. `Required` `Filter(eq;like)` 
| [ObjectVersion](Crm.Pos.ExecutionStatuses.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Ord](Crm.Pos.ExecutionStatuses.md#ord) | int32 | The sort order of the status within the stage. `Required` `Filter(eq;ge;le)` `ORD` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Crm.Pos.ExecutionStatuses.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When specified, means that the status applies only to the specified enterprise company. null means the status is applicable to all enterprise companies. `Filter(multi eq)` |
| [Location](Crm.Pos.ExecutionStatuses.md#location) | [Locations](Crm.Pos.Locations.md) (nullable) | When specified, means that the status applies only to the specified location. null means the status is applicable to all locations. `Filter(multi eq)` |


## Attribute Details

### Code

Unique short descriptive code of the user status. Used for display constrained devices, import/export matching, etc. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (16)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExecutionStage

The system-defined stage under which is the current status. `Required` `Default("PND")` `Filter(multi eq)`

_Type_: **[ExecutionStage](Crm.Pos.ExecutionStatuses.md#executionstage)**  
_Category_: **System**  
Allowed values for the `ExecutionStage`(Crm.Pos.ExecutionStatuses.md#executionstage) data attribute  
_Allowed Values (Crm.Pos.ExecutionStatusesRepository.ExecutionStage Enum Members)_  

| Value | Description |
| ---- | --- |
| Pending | Pending. Stored as 'PND'. <br /> _Database Value:_ 'PND' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Pending' |
| Prepare | Prepare. Stored as 'PRP'. <br /> _Database Value:_ 'PRP' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Prepare' |
| Deliver | Deliver. Stored as 'DEL'. <br /> _Database Value:_ 'DEL' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Deliver' |
| Finalize | Finalize. Stored as 'FIN'. <br /> _Database Value:_ 'FIN' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Finalize' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Pending**  
_Show in UI_: **ShownByDefault**  

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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Indicates whether the POS execution status is currently active. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

Name of the execution status. Should be action-oriented, e.g. reflect the NEXT action which should be taken (and not what is completed). For example, "Scheduled", "Ready-to-serve", etc. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Ord

The sort order of the status within the stage. `Required` `Filter(eq;ge;le)` `ORD`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **True**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.SetExecutionStatusOrd( obj.ExecutionStage)`

_Front-End Recalc Expressions:_  
`obj.SetExecutionStatusOrd( obj.ExecutionStage)`

## Reference Details

### EnterpriseCompany

When specified, means that the status applies only to the specified enterprise company. null means the status is applicable to all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Location

When specified, means that the status applies only to the specified location. null means the status is applicable to all locations. `Filter(multi eq)`

_Type_: **[Locations](Crm.Pos.Locations.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pos.ExecutionStatuses erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.ExecutionStatuses erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_ExecutionStatuses

Domain API Entity Type: 
Crm_Pos_ExecutionStatus

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_ExecutionStatuses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_ExecutionStatuses?$top=10>

