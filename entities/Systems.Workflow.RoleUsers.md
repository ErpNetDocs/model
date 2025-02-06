---
uid: Systems.Workflow.RoleUsers
---
# Systems.Workflow.RoleUsers Entity

**Namespace:** [Systems.Workflow](Systems.Workflow.md)  

The roles "played" by the security users. Entity: Wf_Role_Users
## Renamed
**New name:** [Systems.Security.RoleUsers](Systems.Security.RoleUsers.md)  



## Default Visualization
Default Display Text Format:  
_{User.Name:T}_  
Default Search Members:  
_User.Name_  
Name Data Member:  
_User.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Security.Users](Systems.Security.Users.md)  
Aggregate Root:  
[Systems.Security.Users](Systems.Security.Users.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Workflow.RoleUsers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Workflow.RoleUsers.md#id) | guid |  
| [IsLayoutAdmin](Systems.Workflow.RoleUsers.md#islayoutadmin) | boolean | Specifies whether the user can manage the layouts for the role. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.2.58` 
| [ObjectVersion](Systems.Workflow.RoleUsers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CompanyLocation](Systems.Workflow.RoleUsers.md#companylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | Specifies the Enterprise Company Location of the selected role. Null means that role is valid for all locations belonging to the Enterprise Company. `Filter(multi eq)` `Introduced in version 23.1.2.11` |
| [EnterpriseCompany](Systems.Workflow.RoleUsers.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | Specifies the Enterprise Company of the selected role. Null means that the role is valid for all Enterprise Companiеs. `Filter(multi eq)` `Introduced in version 23.1.2.11` |
| [Role](Systems.Workflow.RoleUsers.md#role) | [Roles](Systems.Security.Roles.md) | The role, played by the user. `Required` `Filter(multi eq)` |
| [User](Systems.Workflow.RoleUsers.md#user) | [Users](Systems.Security.Users.md) | The user, which plays the role. `Required` `Filter(multi eq)` `Owner` |


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
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsLayoutAdmin

Specifies whether the user can manage the layouts for the role. `Required` `Default(false)` `Filter(eq)` `Introduced in version 23.1.2.58`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### CompanyLocation

Specifies the Enterprise Company Location of the selected role. Null means that role is valid for all locations belonging to the Enterprise Company. `Filter(multi eq)` `Introduced in version 23.1.2.11`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

Specifies the Enterprise Company of the selected role. Null means that the role is valid for all Enterprise Companiеs. `Filter(multi eq)` `Introduced in version 23.1.2.11`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Role

The role, played by the user. `Required` `Filter(multi eq)`

_Type_: **[Roles](Systems.Security.Roles.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The user, which plays the role. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Users](Systems.Security.Users.md)**  
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

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Workflow.RoleUsers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Workflow.RoleUsers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Systems_Workflow_RoleUsers?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Systems_Workflow_RoleUsers?$top=10>

