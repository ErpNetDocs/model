---
uid: General.Contacts.CompanyEmployees
---
# General.Contacts.CompanyEmployees Entity

**Namespace:** [General.Contacts](General.Contacts.md)  

Contains the company employee contracts. Entity: Cm_Company_Employees

## Default Visualization
Default Display Text Format:  
_{Person.PartyName:T}_  
Default Search Members:  
_ContractCode; Person.PartyName_  
Code Data Member:  
_ContractCode_  
Name Data Member:  
_Person.PartyName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Contacts.Persons](General.Contacts.Persons.md)  
Aggregate Root:  
[General.Contacts.Persons](General.Contacts.Persons.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContractCode](General.Contacts.CompanyEmployees.md#contractcode) | string (16) __nullable__ | Contract number or code, unique within the company. One employee can have more than one contract. `Filter(eq;like)` `ORD` 
| [ContractEndDate](General.Contacts.CompanyEmployees.md#contractenddate) | datetime __nullable__ | End date of the employee contract, null if the contract is still valid. `Filter(ge;le)` 
| [ContractStartDate](General.Contacts.CompanyEmployees.md#contractstartdate) | datetime __nullable__ | Start date of the employee contract. Null if it is unkown. `Filter(ge;le)` 
| [DisplayText](General.Contacts.CompanyEmployees.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.Contacts.CompanyEmployees.md#id) | guid |  
| [IsActive](General.Contacts.CompanyEmployees.md#isactive) | boolean | Indicates whether the current Employee is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 24.1.5.22` 
| [Notes](General.Contacts.CompanyEmployees.md#notes) | string (254) __nullable__ | Notes for this CompanyEmployee. 
| [ObjectVersion](General.Contacts.CompanyEmployees.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Company](General.Contacts.CompanyEmployees.md#company) | [Companies](General.Contacts.Companies.md) | The company for which this employee works. `Required` `Filter(multi eq)` |
| [CompanyDepartment](General.Contacts.CompanyEmployees.md#companydepartment) | [CompanyDepartments](General.Contacts.CompanyDepartments.md) (nullable) | The department in which this employee is working. null means this information is unknown. `Filter(multi eq)` |
| [Person](General.Contacts.CompanyEmployees.md#person) | [Persons](General.Contacts.Persons.md) | The personal data of the employee. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ContractCode

Contract number or code, unique within the company. One employee can have more than one contract. `Filter(eq;like)` `ORD`

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.IncMax( o => o.ContractCode, e => ( e.Company == obj.Company), "00000")`

### ContractEndDate

End date of the employee contract, null if the contract is still valid. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ContractStartDate

Start date of the employee contract. Null if it is unkown. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

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

### IsActive

Indicates whether the current Employee is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 24.1.5.22`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this CompanyEmployee.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Company

The company for which this employee works. `Required` `Filter(multi eq)`

_Type_: **[Companies](General.Contacts.Companies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### CompanyDepartment

The department in which this employee is working. null means this information is unknown. `Filter(multi eq)`

_Type_: **[CompanyDepartments](General.Contacts.CompanyDepartments.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Person

The personal data of the employee. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Persons](General.Contacts.Persons.md)**  
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

[!list limit=1000 erp.entity=General.Contacts.CompanyEmployees erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.CompanyEmployees erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_CompanyEmployees

Domain API Entity Type: 
General_Contacts_CompanyEmployee

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_CompanyEmployees?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_CompanyEmployees?$top=10>

