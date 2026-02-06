---
uid: General.Contacts.CompanyDivisions
---
# General.Contacts.CompanyDivisions


Stores company divisions structure. The divisions are parties and as such, can be organized hierarchically mixed with other structuring mechanisms. The departments and divisions are parallel and different structuring mechanisms for the companies.

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.CompanyDivisions  
Inherited From: [General.Contacts.Parties](General.Contacts.Parties.md)  
Base Table: Cm_Company_Divisions  
API access:  ReadWrite  

## Visualization
Display Format: {PartyName:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  PartyType  

## Track Changes  
Min level:  4 - Track object attribute and blob changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Contacts.CompanyDivisions](General.Contacts.CompanyDivisions.md)  
  * [General.Contacts.PartyContactMechanisms](General.Contacts.PartyContactMechanisms.md)  
  * [General.Contacts.PartyRelationships](General.Contacts.PartyRelationships.md)  
  * [General.Contacts.PartyApplicableLegislations](General.Contacts.PartyApplicableLegislations.md)  
  * [General.Contacts.PartyBankAccounts](General.Contacts.PartyBankAccounts.md)  
  * [General.Contacts.PartyLocationNumbers](General.Contacts.PartyLocationNumbers.md)  
  * [General.Contacts.PartyPictures](General.Contacts.PartyPictures.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](General.Contacts.CompanyDivisions.md#code) | string (10) | The unique code of the division in the company [Required] [Filter(eq;like)] 
| [GLN](General.Contacts.CompanyDivisions.md#gln) | string (13) __nullable__ | Global Location Number used by EDI systems. `Filter(multi eq)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [IsActive](General.Contacts.CompanyDivisions.md#isactive) | boolean | Specifies whether the current party is active in the system or not. `Required` `Default(true)` `Filter(eq)` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [Name](General.Contacts.CompanyDivisions.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Multi-language company divsion name[Required] [Filter(eq;like)] 
| [PartyCode](General.Contacts.CompanyDivisions.md#partycode) | string (16) | The unique code of the party. `Required` `Filter(multi eq;like)` `ORD` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyCreationTime](General.Contacts.CompanyDivisions.md#partycreationtime) | datetime __nullable__ | Date and time when the Party was created. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyCreationUser](General.Contacts.CompanyDivisions.md#partycreationuser) | string (64) __nullable__ | Login name of the user, who created the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyName](General.Contacts.CompanyDivisions.md#partyname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the party. `Required` `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyNotes](General.Contacts.CompanyDivisions.md#partynotes) | string (254) __nullable__ | Notes for this Party. (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyType](General.Contacts.CompanyDivisions.md#partytype) | [PartyType](General.Contacts.CompanyDivisions.md#partytype) | Type of party. Currently supported are P=Person, C=Company, S=Store, L=Company Location, V=Division. `Required` `Default("P")` `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUniqueNumber](General.Contacts.CompanyDivisions.md#partyuniquenumber) | string (16) __nullable__ | Unique number of the party (National number for persons, Registration number for companies). `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUpdateTime](General.Contacts.CompanyDivisions.md#partyupdatetime) | datetime __nullable__ | Date and time when the Party was last updated. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUpdateUser](General.Contacts.CompanyDivisions.md#partyupdateuser) | string (64) __nullable__ | Login name of the user, who last updated the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AdministrativeRegion](General.Contacts.CompanyDivisions.md#administrativeregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable) | The administrative region in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [Area](General.Contacts.CompanyDivisions.md#area) | [Areas](General.Geography.Areas.md) (nullable) | The area in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [Company](General.Contacts.CompanyDivisions.md#company) | [Companies](General.Contacts.Companies.md) | The owner company of the division |
| [DefaultProductCodingSystem](General.Contacts.CompanyDivisions.md#defaultproductcodingsystem) | [CodingSystems](General.Products.CodingSystems.md) (nullable) | When not null, specifies coding system for products, which is required by the party. The coding system is used primarily for document printouts and document import/exports. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [ParentParty](General.Contacts.CompanyDivisions.md#parentparty) | [Parties](General.Contacts.Parties.md) (nullable) | Organizational unit (branch from the hierarchy of all parties) to which this party is referred to. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.CompanyDivisions.md#id) | guid |  
| [ObjectVersion](General.Contacts.CompanyDivisions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Contacts.CompanyDivisions.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Contacts.CompanyDivisions.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Contacts.CompanyDivisions.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Contacts.CompanyDivisions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ApplicableLegislations | [PartyApplicableLegislations](General.Contacts.PartyApplicableLegislations.md) | List of `PartyApplicable<br />Legislation`(General.Contacts.PartyApplicable<br />Legislations.md) child objects, based on the `General.Contacts.PartyApplicableLegislation.Party`(General.Contacts.PartyApplicable<br />Legislations.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| BankAccounts | [PartyBankAccounts](General.Contacts.PartyBankAccounts.md) | List of `PartyBankAccount`(General.Contacts.PartyBankAccounts.md) child objects, based on the `General.Contacts.PartyBankAccount.Party`(General.Contacts.PartyBankAccounts.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| ContactMechanisms | [PartyContactMechanisms](General.Contacts.PartyContactMechanisms.md) | List of `PartyContactMechanism`(General.Contacts.PartyContactMechanisms.md) child objects, based on the `General.Contacts.PartyContactMechanism.Party`(General.Contacts.PartyContactMechanisms.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| LocationNumbers | [PartyLocationNumbers](General.Contacts.PartyLocationNumbers.md) | List of `PartyLocationNumber`(General.Contacts.PartyLocationNumbers.md) child objects, based on the `General.Contacts.PartyLocationNumber.Party`(General.Contacts.PartyLocationNumbers.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Pictures | [PartyPictures](General.Contacts.PartyPictures.md) | List of `PartyPicture`(General.Contacts.PartyPictures.md) child objects, based on the `General.Contacts.PartyPicture.Party`(General.Contacts.PartyPictures.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Relationships | [PartyRelationships](General.Contacts.PartyRelationships.md) | List of `PartyRelationship`(General.Contacts.PartyRelationships.md) child objects, based on the `General.Contacts.PartyRelationship.FromParty`(General.Contacts.PartyRelationships.md#fromparty) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 


## Attribute Details

### Code

The unique code of the division in the company [Required] [Filter(eq;like)]

Type: **string (10)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **10**  
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

### Name

Multi-language company divsion name[Required] [Filter(eq;like)]

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
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

Type: **[PartyType](General.Contacts.CompanyDivisions.md#partytype)**  
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

### Company

The owner company of the division

Type: **[Companies](General.Contacts.Companies.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultProductCodingSystem

When not null, specifies coding system for products, which is required by the party. The coding system is used primarily for document printouts and document import/exports. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[CodingSystems](General.Products.CodingSystems.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Contacts.CompanyDivisions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.CompanyDivisions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_CompanyDivisions

Domain API Entity Type: 
General_Contacts_CompanyDivision

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_CompanyDivisions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_CompanyDivisions?$top=10>

