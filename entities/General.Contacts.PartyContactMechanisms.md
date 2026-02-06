---
uid: General.Contacts.PartyContactMechanisms
---
# General.Contacts.PartyContactMechanisms


Specifies the contact mechanisms, which are attached to the parties. Currently each contact mechanism is attached to strictly one party.

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.PartyContactMechanisms  
Inherited From: [General.Contacts.ContactMechanisms](General.Contacts.ContactMechanisms.md)  
Base Table: Cm_Party_Contact_Mechanisms  
API access:  ReadWrite  

## Visualization
Display Format: {ContactMechanismType}: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Contacts.Parties](General.Contacts.Parties.md)  
Aggregate Root:  
[General.Contacts.Parties](General.Contacts.Parties.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ContactMechanismType](General.Contacts.PartyContactMechanisms.md#contactmechanismtype) | [ContactMechanismType](General.Contacts.PartyContactMechanisms.md#contactmechanismtype) | A=Address; E=e-mail; T=Telephone. `Required` `Default("A")` `Filter(multi eq)` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md)) 
| [FromDate](General.Contacts.PartyContactMechanisms.md#fromdate) | datetime __nullable__ | The first date when the contact mechanism was valid. NULL means unknown date[Default(Today)] [Filter(eq;ge;le)] 
| [IsActive](General.Contacts.PartyContactMechanisms.md#isactive) | boolean | True if the contact mechanism is currently active and can be used to contact the party.[Required] [Default(true)] [Filter(eq)] 
| [IsDefault](General.Contacts.PartyContactMechanisms.md#isdefault) | boolean | 1 - when this is the default contact mechanism for this party; 0 - otherwise[Required] [Default(false)] [Filter(eq)] 
| [LineOrd](General.Contacts.PartyContactMechanisms.md#lineord) | int32 | Consecutive number of the contact information. The number is unique within the party.[Required] 
| [Name](General.Contacts.PartyContactMechanisms.md#name) | string (254) | Contact mechanism description. `Required` `Filter(eq;like)` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md)) 
| [NonSolicitation](General.Contacts.PartyContactMechanisms.md#nonsolicitation) | boolean | If 1 then Don't use the mechanism for solicitation purposes[Required] [Default(false)] [Filter(eq)] 
| [Notes](General.Contacts.PartyContactMechanisms.md#notes) | string (254) __nullable__ | Notes for this PartyContactMechanism. 
| [ThruDate](General.Contacts.PartyContactMechanisms.md#thrudate) | datetime __nullable__ | The last date on which the contact mechanism was valid for the party. NULL if the contact mechanism is still valid[Filter(eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AdministrativeRegion](General.Contacts.PartyContactMechanisms.md#administrativeregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable) | The administrative region, where the contact mechanism is situated. Null if this is unknown or N/A. `Filter(multi eq)` `Introduced in version 18.2` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md)) |
| [ContactMechanism](General.Contacts.PartyContactMechanisms.md#contactmechanism) | [ContactMechanisms](General.Contacts.ContactMechanisms.md) | The contact mechanism of the party |
| [ContactMechanismPurpose](General.Contacts.PartyContactMechanisms.md#contactmechanismpurpose) | [ContactMechanismPurposes](General.Contacts.ContactMechanismPurposes.md) (nullable) | The purpose of this contact mechanism. Unique within the party. Can be used to seek for specific contact mechanisms. |
| [GeoPoint](General.Contacts.PartyContactMechanisms.md#geopoint) | [GeoPoints](General.Geography.GeoPoints.md) (nullable) | The geographical point, where the contact mechanism is situated. Null if this is unknown or N/A. `Filter(multi eq)` `Introduced in version 18.2` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md)) |
| [Party](General.Contacts.PartyContactMechanisms.md#party) | [Parties](General.Contacts.Parties.md) | The party, having the contact mechanism |
| [PersonalDataProcess](General.Contacts.PartyContactMechanisms.md#personaldataprocess) | [PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable) | The personal data process, which is used to process the current data. Null when the data is not personal or when the process is unknown. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.PartyContactMechanisms.md#id) | guid | Unique party contact mechanism Id 
| [ObjectVersion](General.Contacts.PartyContactMechanisms.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Contacts.PartyContactMechanisms.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ContactMechanismType

A=Address; E=e-mail; T=Telephone. `Required` `Default("A")` `Filter(multi eq)` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md))

Type: **[ContactMechanismType](General.Contacts.PartyContactMechanisms.md#contactmechanismtype)**  
Category: **System**  
Allowed values for the `ContactMechanismType`(General.Contacts.ContactMechanisms.md#contactmechanismtype) data attribute  
Allowed Values (General.Contacts.ContactMechanismsRepository.ContactMechanismType Enum Members)  

| Value | Description |
| ---- | --- |
| Address | Address value. Stored as 'A'. <br /> Database Value: 'A' <br /> Model Value: 0 <br /> Domain API Value: 'Address' |
| Mail | Mail value. Stored as 'E'. <br /> Database Value: 'E' <br /> Model Value: 1 <br /> Domain API Value: 'Mail' |
| Fax | Fax value. Stored as 'F'. <br /> Database Value: 'F' <br /> Model Value: 2 <br /> Domain API Value: 'Fax' |
| MobilePhone | MobilePhone value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 3 <br /> Domain API Value: 'MobilePhone' |
| Other | Other value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 4 <br /> Domain API Value: 'Other' |
| Telephone | Telephone value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 5 <br /> Domain API Value: 'Telephone' |
| WebSite | WebSite value. Stored as 'W'. <br /> Database Value: 'W' <br /> Model Value: 6 <br /> Domain API Value: 'WebSite' |
| PostalCode | PostalCode value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 7 <br /> Domain API Value: 'PostalCode' |
| WebProfile | WebProfile value. Stored as 'X'. <br /> Database Value: 'X' <br /> Model Value: 8 <br /> Domain API Value: 'WebProfile' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Address**  
Show in UI: **ShownByDefault**  

### FromDate

The first date when the contact mechanism was valid. NULL means unknown date[Default(Today)] [Filter(eq;ge;le)]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### IsActive

True if the contact mechanism is currently active and can be used to contact the party.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### IsDefault

1 - when this is the default contact mechanism for this party; 0 - otherwise[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LineOrd

Consecutive number of the contact information. The number is unique within the party.[Required]

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.Party.ContactMechanisms.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

Front-End Recalc Expressions:  
`( obj.Party.ContactMechanisms.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### Name

Contact mechanism description. `Required` `Filter(eq;like)` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md))

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### NonSolicitation

If 1 then Don't use the mechanism for solicitation purposes[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this PartyContactMechanism.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ThruDate

The last date on which the contact mechanism was valid for the party. NULL if the contact mechanism is still valid[Filter(eq;ge;le)]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Unique party contact mechanism Id

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

### AdministrativeRegion

The administrative region, where the contact mechanism is situated. Null if this is unknown or N/A. `Filter(multi eq)` `Introduced in version 18.2` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md))

Type: **[AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ContactMechanism

The contact mechanism of the party

Type: **[ContactMechanisms](General.Contacts.ContactMechanisms.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **CannotBeShown**  

### ContactMechanismPurpose

The purpose of this contact mechanism. Unique within the party. Can be used to seek for specific contact mechanisms.

Type: **[ContactMechanismPurposes](General.Contacts.ContactMechanismPurposes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### GeoPoint

The geographical point, where the contact mechanism is situated. Null if this is unknown or N/A. `Filter(multi eq)` `Introduced in version 18.2` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md))

Type: **[GeoPoints](General.Geography.GeoPoints.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Party

The party, having the contact mechanism

Type: **[Parties](General.Contacts.Parties.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### PersonalDataProcess

The personal data process, which is used to process the current data. Null when the data is not personal or when the process is unknown.

Type: **[PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.Contacts.PartyContactMechanisms erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.PartyContactMechanisms erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_PartyContactMechanisms

Domain API Entity Type: 
General_Contacts_PartyContactMechanism

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_PartyContactMechanisms?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_PartyContactMechanisms?$top=10>

