---
uid: Regulatory.Saft.ProfileCompanies
---
# Regulatory.Saft.ProfileCompanies


Companies, for which the SAF-T profile is applied.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.ProfileCompanies  
Base Table: Saft_Profile_Companies  
Introduced In Version: 26.2.0.42  
API access:  ReadWrite  

## Visualization
Display Format: {Profile.Name}  
Search Members: Profile.Name  
Name Member: Profile.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  
Aggregate Root:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContactPerson](Regulatory.Saft.ProfileCompanies.md#contactperson) | string (254) | Contact person for SAF-T-related matters. 
| [ContactPersonEmail](Regulatory.Saft.ProfileCompanies.md#contactpersonemail) | string (254) | Email address for SAF-T correspondence. 
| [ContactPersonJobTitle](Regulatory.Saft.ProfileCompanies.md#contactpersonjobtitle) | string (254) | Official job title of the contact person. 
| [ContactPersonPhone](Regulatory.Saft.ProfileCompanies.md#contactpersonphone) | string (254) | Phone number for inquiries. 
| [IsPartOfGroup](Regulatory.Saft.ProfileCompanies.md#ispartofgroup) | [IsPartOfGroup](Regulatory.Saft.ProfileCompanies.md#ispartofgroup) | Indicate whether the company is part of a group. 
| [Notes](Regulatory.Saft.ProfileCompanies.md#notes) | string (max) __nullable__ | Internal notes, not included in the SAF-T file. 
| [TaxAccountingBasis](Regulatory.Saft.ProfileCompanies.md#taxaccountingbasis) | [TaxAccountingBasis](Regulatory.Saft.ProfileCompanies.md#taxaccountingbasis) | Accounting basis: accrual, cash, or mixed. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BeneficialOwnerCompany](Regulatory.Saft.ProfileCompanies.md#beneficialownercompany) | [Companies](General.Contacts.Companies.md) (nullable) | Legal entity that is the beneficial owner (if applicable). |
| [BeneficialOwnerPerson](Regulatory.Saft.ProfileCompanies.md#beneficialownerperson) | [Persons](General.Contacts.Persons.md) (nullable) | Natural person who is the beneficial owner (if applicable). |
| [EnterpriseCompany](Regulatory.Saft.ProfileCompanies.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | Legal entity whose data will be exported to SAF-T. |
| [Profile](Regulatory.Saft.ProfileCompanies.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | The SAF-T profile this company belongs to. |
| [UltimateOwnerCompany](Regulatory.Saft.ProfileCompanies.md#ultimateownercompany) | [Companies](General.Contacts.Companies.md) (nullable) | Legal entity that is the ultimate owner (if applicable). |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.ProfileCompanies.md#id) | guid |  
| [ObjectVersion](Regulatory.Saft.ProfileCompanies.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Saft.ProfileCompanies.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ContactPerson

Contact person for SAF-T-related matters.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ContactPersonEmail

Email address for SAF-T correspondence.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ContactPersonJobTitle

Official job title of the contact person.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ContactPersonPhone

Phone number for inquiries.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### IsPartOfGroup

Indicate whether the company is part of a group.

Type: **[IsPartOfGroup](Regulatory.Saft.ProfileCompanies.md#ispartofgroup)**  
Category: **System**  
Allowed values for the `IsPartOfGroup`(Regulatory.Saft.ProfileCompanies.md#ispartofgroup) data attribute  
Allowed Values (Regulatory.Saft.ProfileCompaniesRepository.IsPartOfGroup Enum Members)  

| Value | Description |
| ---- | --- |
| HeadOfLocalGroup | Head of local group. Stored as 1. <br /> Database Value: 1 <br /> Model Value: 1 <br /> Domain API Value: 'HeadOfLocalGroup' |
| HeadOfMultinationalGroup | Head of multinational group. Stored as 2. <br /> Database Value: 2 <br /> Model Value: 2 <br /> Domain API Value: 'HeadOfMultinationalGroup' |
| PartOfLocalGroup | Part of local group. Stored as 3. <br /> Database Value: 3 <br /> Model Value: 3 <br /> Domain API Value: 'PartOfLocalGroup' |
| PartOfMultinationalGroup | Part of multinational group. Stored as 4. <br /> Database Value: 4 <br /> Model Value: 4 <br /> Domain API Value: 'PartOfMultinationalGroup' |
| NotPartOfAGroup | Not part of a group. Stored as 5. <br /> Database Value: 5 <br /> Model Value: 5 <br /> Domain API Value: 'NotPartOfAGroup' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **5**  
Show in UI: **ShownByDefault**  

### Notes

Internal notes, not included in the SAF-T file.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### TaxAccountingBasis

Accounting basis: accrual, cash, or mixed.

Type: **[TaxAccountingBasis](Regulatory.Saft.ProfileCompanies.md#taxaccountingbasis)**  
Category: **System**  
Allowed values for the `TaxAccountingBasis`(Regulatory.Saft.ProfileCompanies.md#taxaccountingbasis) data attribute  
Allowed Values (Regulatory.Saft.ProfileCompaniesRepository.TaxAccountingBasis Enum Members)  

| Value | Description |
| ---- | --- |
| CommercialEntity | Commercial entity. Stored as 'COM'. <br /> Database Value: 'COM' <br /> Model Value: 0 <br /> Domain API Value: 'CommercialEntity' |
| CreditInstitution<br />OrNonBankFinancial<br />Institution | Credit institution or non-bank financial institution. Stored as 'BNK'. <br /> Database Value: 'BNK' <br /> Model Value: 1 <br /> Domain API Value: 'CreditInstitution<br />OrNonBankFinancial<br />Institution' |
| InsuranceCompany | Insurance company. Stored as 'INS'. <br /> Database Value: 'INS' <br /> Model Value: 2 <br /> Domain API Value: 'InsuranceCompany' |
| PublicSectorEntity | Public sector entity. Stored as 'PUB'. <br /> Database Value: 'PUB' <br /> Model Value: 3 <br /> Domain API Value: 'PublicSectorEntity' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **CommercialEntity**  
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

### BeneficialOwnerCompany

Legal entity that is the beneficial owner (if applicable).

Type: **[Companies](General.Contacts.Companies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### BeneficialOwnerPerson

Natural person who is the beneficial owner (if applicable).

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

Legal entity whose data will be exported to SAF-T.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Profile

The SAF-T profile this company belongs to.

Type: **[Profiles](Regulatory.Saft.Profiles.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### UltimateOwnerCompany

Legal entity that is the ultimate owner (if applicable).

Type: **[Companies](General.Contacts.Companies.md) (nullable)**  
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

