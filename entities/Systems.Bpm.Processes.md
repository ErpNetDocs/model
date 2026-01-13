---
uid: Systems.Bpm.Processes
---
# Systems.Bpm.Processes Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Contains the business process diagrams. Entity: Wf_Processes

## Renames

Old name: **Systems.Workflow.Processes**  
New name: **Systems.Bpm.Processes**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _SystemData_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Systems.Bpm.Processes](Systems.Bpm.Processes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTime](Systems.Bpm.Processes.md#creationtime) | datetime __nullable__ | Date and time when the Process was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](Systems.Bpm.Processes.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Process. `ReadOnly` 
| [DisplayText](Systems.Bpm.Processes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Systems.Bpm.Processes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Systems.Bpm.Processes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Systems.Bpm.Processes.md#id) | guid |  
| [IsLandscape](Systems.Bpm.Processes.md#islandscape) | boolean | Specifies whether the process diagram is intended to be viewed in landscape mode. `Required` `Default(true)` 
| [Name](Systems.Bpm.Processes.md#name) | [MultilanguageString (128)](../data-types.md#multilanguagestring) | The name of this Process. `Required` `Filter(eq;like)` 
| [Notes](Systems.Bpm.Processes.md#notes) | string (2000) __nullable__ | Notes for this Process. 
| [ObjectVersion](Systems.Bpm.Processes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SchemaFormat](Systems.Bpm.Processes.md#schemaformat) | string (1) | Application specific format of the Schema Layout. `Required` `Default("D")` 
| [SchemaLayout](Systems.Bpm.Processes.md#schemalayout) | string (max) | Contains the actual presentation layout of the business process. The layout is stored in the format, specified by Schema Format. `Required` 
| [StartEvent](Systems.Bpm.Processes.md#startevent) | string (3) __nullable__ | USR=User created; EML=Email receive (still not supported). null means that there is no starting event for this process. 
| [StartRoleId](Systems.Bpm.Processes.md#startroleid) | guid __nullable__ | When Start_Event='USR' then specifies the role which the user must play in order to start the process. null when Start_Event&lt;&gt;'USR'. `Filter(multi eq)` 
| [Thumbnail](Systems.Bpm.Processes.md#thumbnail) | byte[] __nullable__ | Contains the visual thumbnail of the presentation of the business process. It is stored in bitmap (BMP) format. 
| [UpdateTime](Systems.Bpm.Processes.md#updatetime) | datetime __nullable__ | Date and time when the Process was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](Systems.Bpm.Processes.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Process. `ReadOnly` 


## Attribute Details

### CreationTime

Date and time when the Process was created. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Process. `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  

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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsLandscape

Specifies whether the process diagram is intended to be viewed in landscape mode. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

The name of this Process. `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString (128)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Process.

_Type_: **string (2000) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2000**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### SchemaFormat

Application specific format of the Schema Layout. `Required` `Default("D")`

_Type_: **string (1)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **1**  
_Default Value_: **D**  
_Show in UI_: **ShownByDefault**  

### SchemaLayout

Contains the actual presentation layout of the business process. The layout is stored in the format, specified by Schema Format. `Required`

_Type_: **string (max)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### StartEvent

USR=User created; EML=Email receive (still not supported). null means that there is no starting event for this process.

_Type_: **string (3) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **3**  
_Show in UI_: **ShownByDefault**  

### StartRoleId

When Start_Event='USR' then specifies the role which the user must play in order to start the process. null when Start_Event&lt;&gt;'USR'. `Filter(multi eq)`

_Type_: **guid __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Thumbnail

Contains the visual thumbnail of the presentation of the business process. It is stored in bitmap (BMP) format.

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **CannotBeShown**  

### UpdateTime

Date and time when the Process was last updated. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Process. `ReadOnly`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **HiddenByDefault**  


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

[!list limit=1000 erp.entity=Systems.Bpm.Processes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.Processes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_Processes

Domain API Entity Type: 
Systems_Bpm_Process

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_Processes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_Processes?$top=10>

