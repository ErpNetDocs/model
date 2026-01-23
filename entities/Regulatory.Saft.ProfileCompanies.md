---
uid: Regulatory.Saft.ProfileCompanies
---
# Regulatory.Saft.ProfileCompanies Entity

**Namespace:** [Regulatory.Saft](Regulatory.Saft.md)  

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
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  
Aggregate Root:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContactPerson](Regulatory.Saft.ProfileCompanies.md#contactperson) | string (254) | Contact person for SAF-T-related matters. `Required` `Filter(eq;like)` 
| [ContactPersonEmail](Regulatory.Saft.ProfileCompanies.md#contactpersonemail) | string (254) | Email address for SAF-T correspondence. `Required` `Filter(eq;like)` 
| [ContactPersonJobTitle](Regulatory.Saft.ProfileCompanies.md#contactpersonjobtitle) | string (254) | Official job title of the contact person. `Required` `Filter(eq;like)` 
| [ContactPersonPhone](Regulatory.Saft.ProfileCompanies.md#contactpersonphone) | string (254) | Phone number for inquiries. `Required` `Filter(eq;like)` 
| [DisplayText](Regulatory.Saft.ProfileCompanies.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Regulatory.Saft.ProfileCompanies.md#id) | guid |  
| [IsPartOfGroup](Regulatory.Saft.ProfileCompanies.md#ispartofgroup) | [IsPartOfGroup](Regulatory.Saft.ProfileCompanies.md#ispartofgroup) | Indicate whether the company is part of a group. `Required` `Default(5)` `Filter(eq)` 
| [Notes](Regulatory.Saft.ProfileCompanies.md#notes) | string (max) __nullable__ | Internal notes, not included in the SAF-T file. `Filter(like)` 
| [ObjectVersion](Regulatory.Saft.ProfileCompanies.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [TaxAccountingBasis](Regulatory.Saft.ProfileCompanies.md#taxaccountingbasis) | [TaxAccountingBasis](Regulatory.Saft.ProfileCompanies.md#taxaccountingbasis) | Accounting basis: accrual, cash, or mixed. `Required` `Default("COM")` `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BeneficialOwnerCompany](Regulatory.Saft.ProfileCompanies.md#beneficialownercompany) | [Companies](General.Contacts.Companies.md) (nullable) | Legal entity that is the beneficial owner (if applicable). `Filter(multi eq)` |
| [BeneficialOwnerPerson](Regulatory.Saft.ProfileCompanies.md#beneficialownerperson) | [Persons](General.Contacts.Persons.md) (nullable) | Natural person who is the beneficial owner (if applicable). `Filter(multi eq)` |
| [EnterpriseCompany](Regulatory.Saft.ProfileCompanies.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Legal entity whose data will be exported to SAF-T. `Required` `Filter(multi eq)` |
| [Profile](Regulatory.Saft.ProfileCompanies.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | The SAF-T profile this company belongs to. `Required` `Filter(multi eq)` `Owner` |
| [UltimateOwnerCompany](Regulatory.Saft.ProfileCompanies.md#ultimateownercompany) | [Companies](General.Contacts.Companies.md) (nullable) | Legal entity that is the ultimate owner (if applicable). `Filter(multi eq)` `Introduced in version 26.2.1.19` |


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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsPartOfGroup

Indicate whether the company is part of a group. `Required` `Default(5)` `Filter(eq)`

_Type_: **[IsPartOfGroup](Regulatory.Saft.ProfileCompanies.md#ispartofgroup)**  
_Category_: **System**  
Allowed values for the `IsPartOfGroup`(Regulatory.Saft.ProfileCompanies.md#ispartofgroup) data attribute  
_Allowed Values (Regulatory.Saft.ProfileCompaniesRepository.IsPartOfGroup Enum Members)_  

| Value | Description |
| ---- | --- |
| HeadOfLocalGroup | Head of local group. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'HeadOfLocalGroup' |
| HeadOfMultinationalGroup | Head of multinational group. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'HeadOfMultinationalGroup' |
| PartOfLocalGroup | Part of local group. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'PartOfLocalGroup' |
| PartOfMultinationalGroup | Part of multinational group. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'PartOfMultinationalGroup' |
| NotPartOfAGroup | Not part of a group. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'NotPartOfAGroup' |

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

Accounting basis: accrual, cash, or mixed. `Required` `Default("COM")` `Filter(eq)`

_Type_: **[TaxAccountingBasis](Regulatory.Saft.ProfileCompanies.md#taxaccountingbasis)**  
_Category_: **System**  
Allowed values for the `TaxAccountingBasis`(Regulatory.Saft.ProfileCompanies.md#taxaccountingbasis) data attribute  
_Allowed Values (Regulatory.Saft.ProfileCompaniesRepository.TaxAccountingBasis Enum Members)_  

| Value | Description |
| ---- | --- |
| CommercialEntity | Commercial entity. Stored as 'COM'. <br /> _Database Value:_ 'COM' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'CommercialEntity' |
| CreditInstitution<br />OrNonBankFinancial<br />Institution | Credit institution or non-bank financial institution. Stored as 'BNK'. <br /> _Database Value:_ 'BNK' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'CreditInstitution<br />OrNonBankFinancial<br />Institution' |
| InsuranceCompany | Insurance company. Stored as 'INS'. <br /> _Database Value:_ 'INS' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'InsuranceCompany' |
| PublicSectorEntity | Public sector entity. Stored as 'PUB'. <br /> _Database Value:_ 'PUB' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'PublicSectorEntity' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **CommercialEntity**  
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

_Type_: **[Profiles](Regulatory.Saft.Profiles.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### UltimateOwnerCompany

Legal entity that is the ultimate owner (if applicable). `Filter(multi eq)` `Introduced in version 26.2.1.19`

_Type_: **[Companies](General.Contacts.Companies.md) (nullable)**  
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

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileCompanies erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileCompanies erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_ProfileCompanies

Domain API Entity Type: 
Regulatory_Saft_ProfileCompany

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_ProfileCompanies?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_ProfileCompanies?$top=10>

