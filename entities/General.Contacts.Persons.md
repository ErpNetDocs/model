---
uid: General.Contacts.Persons
---
# General.Contacts.Persons


Personal records. Requires related party record

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.Persons  
Inherited From: [General.Contacts.Parties](General.Contacts.Parties.md)  
Base Table: Cm_Persons  
Introduced In Version: 22.1.6.13  
API access:  ReadWrite  

## Visualization
Display Format: {PartyName:T}  
Search Members: NationalNumber; PartyName  
Code Member: NationalNumber  
Name Member: PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  PartyType  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Contacts.Persons](General.Contacts.Persons.md)  
  * [General.Contacts.CompanyEmployees](General.Contacts.CompanyEmployees.md)  
  * [General.Contacts.PartyContactMechanisms](General.Contacts.PartyContactMechanisms.md)  
  * [General.Contacts.PartyRelationships](General.Contacts.PartyRelationships.md)  
  * [General.Contacts.PartyApplicableLegislations](General.Contacts.PartyApplicableLegislations.md)  
  * [General.Contacts.PartyBankAccounts](General.Contacts.PartyBankAccounts.md)  
  * [General.Contacts.PartyLocationNumbers](General.Contacts.PartyLocationNumbers.md)  
  * [General.Contacts.PartyPictures](General.Contacts.PartyPictures.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BirthDate](General.Contacts.Persons.md#birthdate) | datetime __nullable__ | Birth date. NULL means unknown`Filter(ge;le)` 
| [City](General.Contacts.Persons.md#city) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | City from the legal registration address for the person`Filter(like)` 
| [CreationTime](General.Contacts.Persons.md#creationtime) | datetime __nullable__ | Date and time when the Person was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](General.Contacts.Persons.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Person. `Filter(like)` `ReadOnly` 
| [FirstName](General.Contacts.Persons.md#firstname) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | First name of the person.`Filter(eq;like)` 
| [Gender](General.Contacts.Persons.md#gender) | [Gender](General.Contacts.Persons.md#gender) __nullable__ | Person gender. M=Male;F=Female;O=Other;N=Prefer not to say;NULL=not known/not provided`Filter(eq)` 
| [GLN](General.Contacts.Persons.md#gln) | string (13) __nullable__ | Global Location Number used by EDI systems. `Filter(multi eq)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [IsActive](General.Contacts.Persons.md#isactive) | boolean | Specifies whether the current party is active in the system or not. `Required` `Default(true)` `Filter(eq)` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [LastName](General.Contacts.Persons.md#lastname) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | Last name of the person.`Filter(eq;like)` 
| [MiddleName](General.Contacts.Persons.md#middlename) | [MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__ | Middle name of the person.`Filter(eq;like)` 
| [NationalNumber](General.Contacts.Persons.md#nationalnumber) | string (16) __nullable__ | Government assigned unique personal number. NULL means unknown`Filter(eq;like)` 
| [Notes](General.Contacts.Persons.md#notes) | string (254) __nullable__ | Internal notes for the person 
| [PartyCode](General.Contacts.Persons.md#partycode) | string (16) | The unique code of the party. `Required` `Filter(multi eq;like)` `ORD` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyCreationTime](General.Contacts.Persons.md#partycreationtime) | datetime __nullable__ | Date and time when the Party was created. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyCreationUser](General.Contacts.Persons.md#partycreationuser) | string (64) __nullable__ | Login name of the user, who created the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyName](General.Contacts.Persons.md#partyname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the party. `Required` `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyNotes](General.Contacts.Persons.md#partynotes) | string (254) __nullable__ | Notes for this Party. (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyType](General.Contacts.Persons.md#partytype) | [PartyType](General.Contacts.Persons.md#partytype) | Type of party. Currently supported are P=Person, C=Company, S=Store, L=Company Location, V=Division. `Required` `Default("P")` `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUniqueNumber](General.Contacts.Persons.md#partyuniquenumber) | string (16) __nullable__ | Unique number of the party (National number for persons, Registration number for companies). `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUpdateTime](General.Contacts.Persons.md#partyupdatetime) | datetime __nullable__ | Date and time when the Party was last updated. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUpdateUser](General.Contacts.Persons.md#partyupdateuser) | string (64) __nullable__ | Login name of the user, who last updated the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PassportIssuingDate](General.Contacts.Persons.md#passportissuingdate) | datetime __nullable__ | Date of issuing the passport. NULL means unknown`Filter(ge;le)` 
| [PassportNumber](General.Contacts.Persons.md#passportnumber) | string (14) __nullable__ | Current passport number. NULL means unknown`Filter(eq)` 
| [Title](General.Contacts.Persons.md#title) | [MultilanguageString (32)](../data-types.md#multilanguagestring) __nullable__ | The persons title. It may be one of the standard titles - Mr., Mrs., etc., but it can also contains professional or academic qualification. 
| [UpdateTime](General.Contacts.Persons.md#updatetime) | datetime __nullable__ | Date and time when the Person was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](General.Contacts.Persons.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Person. `Filter(like)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AdministrativeRegion](General.Contacts.Persons.md#administrativeregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable) | The administrative region in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [Area](General.Contacts.Persons.md#area) | [Areas](General.Geography.Areas.md) (nullable) | The area in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [DefaultProductCodingSystem](General.Contacts.Persons.md#defaultproductcodingsystem) | [CodingSystems](General.Products.CodingSystems.md) (nullable) | When not null, specifies coding system for products, which is required by the party. The coding system is used primarily for document printouts and document import/exports. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [Nationality](General.Contacts.Persons.md#nationality) | [Countries](General.Geography.Countries.md) (nullable) | Person's nationality. NULL means the default (same as enterprise) nationality |
| [ParentParty](General.Contacts.Persons.md#parentparty) | [Parties](General.Contacts.Parties.md) (nullable) | Organizational unit (branch from the hierarchy of all parties) to which this party is referred to. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.Persons.md#id) | guid |  
| [ObjectVersion](General.Contacts.Persons.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Contacts.Persons.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Contacts.Persons.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Contacts.Persons.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Contacts.Persons.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ApplicableLegislations | [PartyApplicableLegislations](General.Contacts.PartyApplicableLegislations.md) | List of `PartyApplicable<br />Legislation`(General.Contacts.PartyApplicable<br />Legislations.md) child objects, based on the `General.Contacts.PartyApplicableLegislation.Party`(General.Contacts.PartyApplicable<br />Legislations.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| BankAccounts | [PartyBankAccounts](General.Contacts.PartyBankAccounts.md) | List of `PartyBankAccount`(General.Contacts.PartyBankAccounts.md) child objects, based on the `General.Contacts.PartyBankAccount.Party`(General.Contacts.PartyBankAccounts.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| CompanyEmployees | [CompanyEmployees](General.Contacts.CompanyEmployees.md) | List of `CompanyEmployee`(General.Contacts.CompanyEmployees.md) child objects, based on the `General.Contacts.CompanyEmployee.Person`(General.Contacts.CompanyEmployees.md#person) back reference 
| ContactMechanisms | [PartyContactMechanisms](General.Contacts.PartyContactMechanisms.md) | List of `PartyContactMechanism`(General.Contacts.PartyContactMechanisms.md) child objects, based on the `General.Contacts.PartyContactMechanism.Party`(General.Contacts.PartyContactMechanisms.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| LocationNumbers | [PartyLocationNumbers](General.Contacts.PartyLocationNumbers.md) | List of `PartyLocationNumber`(General.Contacts.PartyLocationNumbers.md) child objects, based on the `General.Contacts.PartyLocationNumber.Party`(General.Contacts.PartyLocationNumbers.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Pictures | [PartyPictures](General.Contacts.PartyPictures.md) | List of `PartyPicture`(General.Contacts.PartyPictures.md) child objects, based on the `General.Contacts.PartyPicture.Party`(General.Contacts.PartyPictures.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Relationships | [PartyRelationships](General.Contacts.PartyRelationships.md) | List of `PartyRelationship`(General.Contacts.PartyRelationships.md) child objects, based on the `General.Contacts.PartyRelationship.FromParty`(General.Contacts.PartyRelationships.md#fromparty) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 


## Attribute Details

### BirthDate

Birth date. NULL means unknown`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### City

City from the legal registration address for the person`Filter(like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### CreationTime

Date and time when the Person was created. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Person. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### FirstName

First name of the person.`Filter(eq;like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Gender

Person gender. M=Male;F=Female;O=Other;N=Prefer not to say;NULL=not known/not provided`Filter(eq)`

Type: **[Gender](General.Contacts.Persons.md#gender) __nullable__**  
Category: **System**  
Allowed values for the `Gender`(General.Contacts.Persons.md#gender) data attribute  
Allowed Values (General.Contacts.PersonsRepository.Gender Enum Members)  

| Value | Description |
| ---- | --- |
| Female | Female value. Stored as 'F'. <br /> Database Value: 'F' <br /> Model Value: 0 <br /> Domain API Value: 'Female' |
| Male | Male value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 1 <br /> Domain API Value: 'Male' |
| Other | Other value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 2 <br /> Domain API Value: 'Other' |
| PreferNotToSay | PreferNotToSay value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 3 <br /> Domain API Value: 'PreferNotToSay' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### GLN

Global Location Number used by EDI systems. `Filter(multi eq)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (13) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **13**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the current party is active in the system or not. `Required` `Default(true)` `Filter(eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### LastName

Last name of the person.`Filter(eq;like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MiddleName

Middle name of the person.`Filter(eq;like)`

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### NationalNumber

Government assigned unique personal number. NULL means unknown`Filter(eq;like)`

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### Notes

Internal notes for the person

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### PartyCode

The unique code of the party. `Required` `Filter(multi eq;like)` `ORD` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.PartyCode, null, "00000")`

### PartyCreationTime

Date and time when the Party was created. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PartyCreationUser

Login name of the user, who created the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### PartyName

The name of the party. `Required` `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PartyNotes

Notes for this Party. (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### PartyType

Type of party. Currently supported are P=Person, C=Company, S=Store, L=Company Location, V=Division. `Required` `Default("P")` `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[PartyType](General.Contacts.Persons.md#partytype)**  
Category: **System**  
Allowed values for the PartyType data attribute  
Allowed Values (General.Contacts.PartiesRepository.PartyType Enum Members)  

| Value | Description |
| ---- | --- |
| Company | Company value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'Company' |
| CompanyLocation | CompanyLocation value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 1 <br /> Domain API Value: 'CompanyLocation' |
| Person | Person value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 2 <br /> Domain API Value: 'Person' |
| Store | Store value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 3 <br /> Domain API Value: 'Store' |
| CompanyDivision | CompanyDivision value. Stored as 'V'. <br /> Database Value: 'V' <br /> Model Value: 4 <br /> Domain API Value: 'CompanyDivision' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Person**  
Show in UI: **ShownByDefault**  

### PartyUniqueNumber

Unique number of the party (National number for persons, Registration number for companies). `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### PartyUpdateTime

Date and time when the Party was last updated. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PartyUpdateUser

Login name of the user, who last updated the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### PassportIssuingDate

Date of issuing the passport. NULL means unknown`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PassportNumber

Current passport number. NULL means unknown`Filter(eq)`

Type: **string (14) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **14**  
Show in UI: **ShownByDefault**  

### Title

The persons title. It may be one of the standard titles - Mr., Mrs., etc., but it can also contains professional or academic qualification.

Type: **[MultilanguageString (32)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UpdateTime

Date and time when the Person was last updated. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Person. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### AdministrativeRegion

The administrative region in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Area

The area in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[Areas](General.Geography.Areas.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultProductCodingSystem

When not null, specifies coding system for products, which is required by the party. The coding system is used primarily for document printouts and document import/exports. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[CodingSystems](General.Products.CodingSystems.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Nationality

Person's nationality. NULL means the default (same as enterprise) nationality

Type: **[Countries](General.Geography.Countries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ParentParty

Organizational unit (branch from the hierarchy of all parties) to which this party is referred to. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=General.Contacts.Persons erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.Persons erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_Persons

Domain API Entity Type: 
General_Contacts_Person

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_Persons?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_Persons?$top=10>

