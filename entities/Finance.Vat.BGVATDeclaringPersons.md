---
uid: Finance.Vat.BGVATDeclaringPersons
---
# Finance.Vat.BGVATDeclaringPersons Entity

**Namespace:** [Finance.Vat](Finance.Vat.md)  

National data: Contains the persons, which are authorized to issue and sign VAT declarations. Entity: Nat_BG_VAT_Declaring_Persons

## Default Visualization
Default Display Text Format:  
_{EnterpriseCompany.Company.PartyName:T}_  
Default Search Members:  
_EnterpriseCompany.Company.PartyName_  
Name Data Member:  
_EnterpriseCompany.Company.PartyName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.EnterpriseCompanies](General.EnterpriseCompanies.md)  
Aggregate Root:  
[General.EnterpriseCompanies](General.EnterpriseCompanies.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DeclarerType](Finance.Vat.BGVATDeclaringPersons.md#declarertype) | [DeclarerType](Finance.Vat.BGVATDeclaringPersons.md#declarertype) | Type of the declaring person. A=Attorney, R=Representative. `Required` `Filter(eq)` 
| [DeclaringPersonAddress](Finance.Vat.BGVATDeclaringPersons.md#declaringpersonaddress) | string (150) | Address for correspondence of the declaring person. `Required` 
| [DeclaringPersonCity](Finance.Vat.BGVATDeclaringPersons.md#declaringpersoncity) | string (50) | City from the address for correspondence of the declaring person. `Required` 
| [DeclaringPersonPosition](Finance.Vat.BGVATDeclaringPersons.md#declaringpersonposition) | string (50) __nullable__ | Position of the declaring person in the enterprise company. 
| [DeclaringPersonPostcode](Finance.Vat.BGVATDeclaringPersons.md#declaringpersonpostcode) | string (4) | Postcode from the address for correspondence of the declaring person. `Required` 
| [DisplayText](Finance.Vat.BGVATDeclaringPersons.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Vat.BGVATDeclaringPersons.md#id) | guid |  
| [IsDefault](Finance.Vat.BGVATDeclaringPersons.md#isdefault) | boolean | True if this is the default person, which issues VAT declarations for this Enterprise Company. `Required` `Default(true)` 
| [ObjectVersion](Finance.Vat.BGVATDeclaringPersons.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Finance.Vat.BGVATDeclaringPersons.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company for which the person is presenting the declaration. `Required` `Filter(multi eq)` `Owner` |
| [Person](Finance.Vat.BGVATDeclaringPersons.md#person) | [Persons](General.Contacts.Persons.md) | The person that is presenting the declaration. `Required` `Filter(multi eq)` |


## Attribute Details

### DeclarerType

Type of the declaring person. A=Attorney, R=Representative. `Required` `Filter(eq)`

_Type_: **[DeclarerType](Finance.Vat.BGVATDeclaringPersons.md#declarertype)**  
_Category_: **System**  
Allowed values for the `DeclarerType`(Finance.Vat.BGVATDeclaringPersons.md#declarertype) data attribute  
_Allowed Values (Finance.Vat.BGVATDeclaringPersonsRepository.DeclarerType Enum Members)_  

| Value | Description |
| ---- | --- |
| Attorney | Attorney value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Attorney' |
| Representative | Representative value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Representative' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DeclaringPersonAddress

Address for correspondence of the declaring person. `Required`

_Type_: **string (150)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **150**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Person.GetValidAddress( ).Name`
### DeclaringPersonCity

City from the address for correspondence of the declaring person. `Required`

_Type_: **string (50)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### DeclaringPersonPosition

Position of the declaring person in the enterprise company.

_Type_: **string (50) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### DeclaringPersonPostcode

Postcode from the address for correspondence of the declaring person. `Required`

_Type_: **string (4)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **4**  
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

### IsDefault

True if this is the default person, which issues VAT declarations for this Enterprise Company. `Required` `Default(true)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company for which the person is presenting the declaration. `Required` `Filter(multi eq)` `Owner`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **HiddenByDefault**  

### Person

The person that is presenting the declaration. `Required` `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md)**  
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

