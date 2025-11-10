---
uid: Finance.Saft.ProfileCompanies
---
# Finance.Saft.ProfileCompanies Entity

**Namespace:** [Finance.Saft](Finance.Saft.md)  

Companies, for which the SAF-T profile is applied. Entity: Saft_Profile_Companies (Introduced in version 26.2.0.42)

## Default Visualization
Default Display Text Format:  
_{Profile.Name}_  
Default Search Members:  
_Profile.Name_  
Name Data Member:  
_Profile.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Saft.Profiles](Finance.Saft.Profiles.md)  
Aggregate Root:  
[Finance.Saft.Profiles](Finance.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContactPerson](Finance.Saft.ProfileCompanies.md#contactperson) | string (254) | Contact person for SAF-T-related matters. `Required` `Filter(eq;like)` 
| [ContactPersonEmail](Finance.Saft.ProfileCompanies.md#contactpersonemail) | string (254) | Email address for SAF-T correspondence. `Required` `Filter(eq;like)` 
| [ContactPersonJobTitle](Finance.Saft.ProfileCompanies.md#contactpersonjobtitle) | string (254) | Official job title of the contact person. `Required` `Filter(eq;like)` 
| [ContactPersonPhone](Finance.Saft.ProfileCompanies.md#contactpersonphone) | string (254) | Phone number for inquiries. `Required` `Filter(eq;like)` 
| [DisplayText](Finance.Saft.ProfileCompanies.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Finance.Saft.ProfileCompanies.md#id) | guid |  
| [IsPartOfGroup](Finance.Saft.ProfileCompanies.md#ispartofgroup) | [IsPartOfGroup](Finance.Saft.ProfileCompanies.md#ispartofgroup) | Indicate whether the company is part of a group. `Required` `Default(5)` `Filter(eq)` 
| [Notes](Finance.Saft.ProfileCompanies.md#notes) | string (max) __nullable__ | Internal notes, not included in the SAF-T file. `Filter(like)` 
| [ObjectVersion](Finance.Saft.ProfileCompanies.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [TaxAccountingBasis](Finance.Saft.ProfileCompanies.md#taxaccountingbasis) | [TaxAccountingBasis](Finance.Saft.ProfileCompanies.md#taxaccountingbasis) | Accounting basis: accrual, cash, or mixed. `Required` `Default("ACC")` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BeneficialOwnerCompany](Finance.Saft.ProfileCompanies.md#beneficialownercompany) | [Companies](General.Contacts.Companies.md) (nullable) | Legal entity that is the beneficial owner (if applicable). `Filter(multi eq)` |
| [BeneficialOwnerPerson](Finance.Saft.ProfileCompanies.md#beneficialownerperson) | [Persons](General.Contacts.Persons.md) (nullable) | Natural person who is the beneficial owner (if applicable). `Filter(multi eq)` |
| [EnterpriseCompany](Finance.Saft.ProfileCompanies.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Legal entity whose data will be exported to SAF-T. `Required` `Filter(multi eq)` |
| [Profile](Finance.Saft.ProfileCompanies.md#profile) | [Profiles](Finance.Saft.Profiles.md) | The SAF-T profile this company belongs to. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ContactPerson

Contact person for SAF-T-related matters. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ContactPersonEmail

Email address for SAF-T correspondence. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ContactPersonJobTitle

Official job title of the contact person. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ContactPersonPhone

Phone number for inquiries. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
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
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsPartOfGroup

Indicate whether the company is part of a group. `Required` `Default(5)` `Filter(eq)`

_Type_: **[IsPartOfGroup](Finance.Saft.ProfileCompanies.md#ispartofgroup)**  
_Category_: **System**  
Allowed values for the `IsPartOfGroup`(Finance.Saft.ProfileCompanies.md#ispartofgroup) data attribute  
_Allowed Values (Finance.Saft.ProfileCompaniesRepository.IsPartOfGroup Enum Members)_  

| Value | Description |
| ---- | --- |
| HeadOfLocalGroup | HeadOfLocalGroup value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'HeadOfLocalGroup' |
| HeadOfMultinationalGroup | HeadOfMultinationalGroup value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'HeadOfMultinationalGroup' |
| PartOfLocalGroup | PartOfLocalGroup value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'PartOfLocalGroup' |
| PartOfMultinationalGroup | PartOfMultinationalGroup value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'PartOfMultinationalGroup' |
| NotPartOfAGroup | NotPartOfAGroup value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'NotPartOfAGroup' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **5**  
_Show in UI_: **ShownByDefault**  

### Notes

Internal notes, not included in the SAF-T file. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### TaxAccountingBasis

Accounting basis: accrual, cash, or mixed. `Required` `Default("ACC")` `Filter(eq)`

_Type_: **[TaxAccountingBasis](Finance.Saft.ProfileCompanies.md#taxaccountingbasis)**  
_Category_: **System**  
Allowed values for the `TaxAccountingBasis`(Finance.Saft.ProfileCompanies.md#taxaccountingbasis) data attribute  
_Allowed Values (Finance.Saft.ProfileCompaniesRepository.TaxAccountingBasis Enum Members)_  

| Value | Description |
| ---- | --- |
| ACCRUAL | ACCRUAL. Stored as 'ACC'. <br /> _Database Value:_ 'ACC' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ACCRUAL' |
| Cash | Cash. Stored as 'CSH'. <br /> _Database Value:_ 'CSH' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Cash' |
| Mixed | Mixed. Stored as 'MIX'. <br /> _Database Value:_ 'MIX' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Mixed' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **ACCRUAL**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### BeneficialOwnerCompany

Legal entity that is the beneficial owner (if applicable). `Filter(multi eq)`

_Type_: **[Companies](General.Contacts.Companies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### BeneficialOwnerPerson

Natural person who is the beneficial owner (if applicable). `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

Legal entity whose data will be exported to SAF-T. `Required` `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Profile

The SAF-T profile this company belongs to. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Profiles](Finance.Saft.Profiles.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Finance.Saft.ProfileCompanies erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Saft.ProfileCompanies erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Saft_ProfileCompanies

Domain API Entity Type: 
Finance_Saft_ProfileCompany

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Saft_ProfileCompanies?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Saft_ProfileCompanies?$top=10>

