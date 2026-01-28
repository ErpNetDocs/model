---
uid: Systems.Security.RoleUsers
---
# Systems.Security.RoleUsers


The roles "played" by the security users.

## General
Namespace: [Systems.Security](Systems.Security.md)  
Repository: Systems.Security.RoleUsers  
Base Table: Wf_Role_Users  
API access:  ReadWrite  

## Renames

Old name: Systems.Workflow.RoleUsers  
New name: Systems.Security.RoleUsers  
Version: 24.1.101.1  
Case: 36967  



## Visualization
Display Format: {User.Name:T}  
Search Members: User.Name  
Name Member: User.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.Users](Systems.Security.Users.md)  
Aggregate Root:  
[Systems.Security.Users](Systems.Security.Users.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsLayoutAdmin](Systems.Security.RoleUsers.md#islayoutadmin) | boolean | Specifies whether the user can manage the layouts for the role. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.2.58` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompanyLocation](Systems.Security.RoleUsers.md#companylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | Specifies the Enterprise Company Location of the selected role. Null means that role is valid for all locations belonging to the Enterprise Company. `Filter(multi eq)` `Introduced in version 23.1.2.11` |
| [EnterpriseCompany](Systems.Security.RoleUsers.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Specifies the Enterprise Company of the selected role. Null means that the role is valid for all Enterprise Companiеs. `Filter(multi eq)` `Introduced in version 23.1.2.11` |
| [Role](Systems.Security.RoleUsers.md#role) | [Roles](Systems.Security.Roles.md) | The role, played by the user. `Required` `Filter(multi eq)` |
| [User](Systems.Security.RoleUsers.md#user) | [Users](Systems.Security.Users.md) | The user, which plays the role. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Security.RoleUsers.md#id) | guid |  
| [ObjectVersion](Systems.Security.RoleUsers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Security.RoleUsers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### IsLayoutAdmin

Specifies whether the user can manage the layouts for the role. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.2.58`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
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

### CompanyLocation

Specifies the Enterprise Company Location of the selected role. Null means that role is valid for all locations belonging to the Enterprise Company. `Filter(multi eq)` `Introduced in version 23.1.2.11`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Specifies the Enterprise Company of the selected role. Null means that the role is valid for all Enterprise Companiеs. `Filter(multi eq)` `Introduced in version 23.1.2.11`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Role

The role, played by the user. `Required` `Filter(multi eq)`

Type: **[Roles](Systems.Security.Roles.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The user, which plays the role. `Required` `Filter(multi eq)` `Owner`

Type: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Systems.Security.RoleUsers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Security.RoleUsers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Security_RoleUsers

Domain API Entity Type: 
Systems_Security_RoleUser

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Security_RoleUsers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Security_RoleUsers?$top=10>

