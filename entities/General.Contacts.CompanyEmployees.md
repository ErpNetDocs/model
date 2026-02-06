---
uid: General.Contacts.CompanyEmployees
---
# General.Contacts.CompanyEmployees


Contains the company employee contracts.

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.CompanyEmployees  
Base Table: Cm_Company_Employees  
API access:  ReadWrite  

## Visualization
Display Format: {Person.PartyName:T}  
Search Members: ContractCode; Person.PartyName  
Code Member: ContractCode  
Name Member: Person.PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Contacts.Persons](General.Contacts.Persons.md)  
Aggregate Root:  
[General.Contacts.Persons](General.Contacts.Persons.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContractCode](General.Contacts.CompanyEmployees.md#contractcode) | string (16) __nullable__ | Number or code of this company employee's contract. One employee can have more than one contract with particular company.[Filter(eq;like)] [ORD] 
| [ContractEndDate](General.Contacts.CompanyEmployees.md#contractenddate) | datetime __nullable__ | End date of the employee contract, null if the contract is still valid.[Filter(ge;le)] 
| [ContractStartDate](General.Contacts.CompanyEmployees.md#contractstartdate) | datetime __nullable__ | Start date of the employee contract. Null if it is unkown.[Filter(ge;le)] 
| [IsActive](General.Contacts.CompanyEmployees.md#isactive) | boolean | Indicates whether the current Employee is active.[Required] [Default(true)] [Filter(eq)] [Introduced in version 24.1.5.22] 
| [Notes](General.Contacts.CompanyEmployees.md#notes) | string (254) __nullable__ | Notes for this CompanyEmployee. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Company](General.Contacts.CompanyEmployees.md#company) | [Companies](General.Contacts.Companies.md) | The company for which this employee works. |
| [CompanyDepartment](General.Contacts.CompanyEmployees.md#companydepartment) | [CompanyDepartments](General.Contacts.CompanyDepartments.md) (nullable) | The department in which this employee is working. NULL means this information is unknown |
| [Person](General.Contacts.CompanyEmployees.md#person) | [Persons](General.Contacts.Persons.md) | The personal data of the employee. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.CompanyEmployees.md#id) | guid |  
| [ObjectVersion](General.Contacts.CompanyEmployees.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Contacts.CompanyEmployees.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ContractCode

Number or code of this company employee's contract. One employee can have more than one contract with particular company.[Filter(eq;like)] [ORD]

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.ContractCode, e => ( e.Company == obj.Company), "00000")`

### ContractEndDate

End date of the employee contract, null if the contract is still valid.[Filter(ge;le)]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ContractStartDate

Start date of the employee contract. Null if it is unkown.[Filter(ge;le)]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current Employee is active.[Required] [Default(true)] [Filter(eq)] [Introduced in version 24.1.5.22]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this CompanyEmployee.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
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

### Company

The company for which this employee works.

Type: **[Companies](General.Contacts.Companies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### CompanyDepartment

The department in which this employee is working. NULL means this information is unknown

Type: **[CompanyDepartments](General.Contacts.CompanyDepartments.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Person

The personal data of the employee.

Type: **[Persons](General.Contacts.Persons.md)**  
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

