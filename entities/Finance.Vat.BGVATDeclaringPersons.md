---
uid: Finance.Vat.BGVATDeclaringPersons
---
# Finance.Vat.BGVATDeclaringPersons


National data: Contains the persons, which are authorized to issue and sign VAT declarations.

## General
Namespace: [Finance.Vat](Finance.Vat.md)  
Repository: Finance.Vat.BGVATDeclaringPersons  
Base Table: Nat_BG_VAT_Declaring_Persons  
API access:  ReadWrite  

## Visualization
Display Format: {EnterpriseCompany.Company.PartyName:T}  
Search Members: EnterpriseCompany.Company.PartyName  
Name Member: EnterpriseCompany.Company.PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.EnterpriseCompanies](General.EnterpriseCompanies.md)  
Aggregate Root:  
[General.EnterpriseCompanies](General.EnterpriseCompanies.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DeclarerType](Finance.Vat.BGVATDeclaringPersons.md#declarertype) | [DeclarerType](Finance.Vat.BGVATDeclaringPersons.md#declarertype) | Type of the declaring person. A=Attorney, R=Representative.`Required` `Filter(eq)` 
| [DeclaringPersonAddress](Finance.Vat.BGVATDeclaringPersons.md#declaringpersonaddress) | string (150) | Address for correspondence of the declaring person.`Required` 
| [DeclaringPersonCity](Finance.Vat.BGVATDeclaringPersons.md#declaringpersoncity) | string (50) | City from the address for correspondence of the declaring person.`Required` 
| [DeclaringPersonPosition](Finance.Vat.BGVATDeclaringPersons.md#declaringpersonposition) | string (50) __nullable__ | Position of the declaring person in the enterprise company. 
| [DeclaringPersonPostcode](Finance.Vat.BGVATDeclaringPersons.md#declaringpersonpostcode) | string (4) | Postcode from the address for correspondence of the declaring person.`Required` 
| [IsDefault](Finance.Vat.BGVATDeclaringPersons.md#isdefault) | boolean | True if this is the default person, which issues VAT declarations for this Enterprise Company.`Required` `Default(true)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Finance.Vat.BGVATDeclaringPersons.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company for which the person is presenting the declaration. |
| [Person](Finance.Vat.BGVATDeclaringPersons.md#person) | [Persons](General.Contacts.Persons.md) | The person that is presenting the declaration. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Vat.BGVATDeclaringPersons.md#id) | guid |  
| [ObjectVersion](Finance.Vat.BGVATDeclaringPersons.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Vat.BGVATDeclaringPersons.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### DeclarerType

Type of the declaring person. A=Attorney, R=Representative.`Required` `Filter(eq)`

Type: **[DeclarerType](Finance.Vat.BGVATDeclaringPersons.md#declarertype)**  
Category: **System**  
Allowed values for the `DeclarerType`(Finance.Vat.BGVATDeclaringPersons.md#declarertype) data attribute  
Allowed Values (Finance.Vat.BGVATDeclaringPersonsRepository.DeclarerType Enum Members)  

| Value | Description |
| ---- | --- |
| Attorney | Attorney value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'Attorney' |
| Representative | Representative value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Representative' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DeclaringPersonAddress

Address for correspondence of the declaring person.`Required`

Type: **string (150)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **150**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Person.GetValidAddress( ).Name`
### DeclaringPersonCity

City from the address for correspondence of the declaring person.`Required`

Type: **string (50)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### DeclaringPersonPosition

Position of the declaring person in the enterprise company.

Type: **string (50) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### DeclaringPersonPostcode

Postcode from the address for correspondence of the declaring person.`Required`

Type: **string (4)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **4**  
Show in UI: **ShownByDefault**  

### IsDefault

True if this is the default person, which issues VAT declarations for this Enterprise Company.`Required` `Default(true)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
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

### EnterpriseCompany

The enterprise company for which the person is presenting the declaration.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **HiddenByDefault**  

### Person

The person that is presenting the declaration.

Type: **[Persons](General.Contacts.Persons.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Finance.Vat.BGVATDeclaringPersons erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Vat.BGVATDeclaringPersons erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Vat_BGVATDeclaringPersons

Domain API Entity Type: 
Finance_Vat_BGVATDeclaringPerson

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Vat_BGVATDeclaringPersons?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Vat_BGVATDeclaringPersons?$top=10>

