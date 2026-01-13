---
uid: General.Contacts.PartyContactMechanisms
---
# General.Contacts.PartyContactMechanisms Entity

**Namespace:** [General.Contacts](General.Contacts.md)  
**Inherited From:** [General.Contacts.ContactMechanisms](General.Contacts.ContactMechanisms.md)  

Specifies the contact mechanisms, which are attached to the parties. Currently each contact mechanism is attached to strictly one party. Entity: Cm_Party_Contact_Mechanisms

## Default Visualization
Default Display Text Format:  
_{ContactMechanismType}: {Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](General.Contacts.PartyContactMechanisms.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FromDate](General.Contacts.PartyContactMechanisms.md#fromdate) | datetime __nullable__ | The first date when the contact mechanism was valid. null means unknown date. `Default(Today)` `Filter(eq;ge;le)` 
| [Id](General.Contacts.PartyContactMechanisms.md#id) | guid |  
| [IsActive](General.Contacts.PartyContactMechanisms.md#isactive) | boolean | True if the contact mechanism is currently active and can be used to contact the party. `Required` `Default(true)` `Filter(eq)` 
| [IsDefault](General.Contacts.PartyContactMechanisms.md#isdefault) | boolean | True - when this is the default contact mechanism for this party; false - otherwise. `Required` `Default(false)` `Filter(eq)` 
| [LineOrd](General.Contacts.PartyContactMechanisms.md#lineord) | int32 | Consecutive number of the contact information. The number is unique within the party. `Required` 
| [Name](General.Contacts.PartyContactMechanisms.md#name) | string (254) | Contact mechanism description. `Required` `Filter(eq;like)` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md)) 
| [NonSolicitation](General.Contacts.PartyContactMechanisms.md#nonsolicitation) | boolean | If true then Don't use the mechanism for solicitation purposes. `Required` `Default(false)` `Filter(eq)` 
| [Notes](General.Contacts.PartyContactMechanisms.md#notes) | string (254) __nullable__ | Notes for this PartyContactMechanism. 
| [ObjectVersion](General.Contacts.PartyContactMechanisms.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ThruDate](General.Contacts.PartyContactMechanisms.md#thrudate) | datetime __nullable__ | The last date on which the contact mechanism was valid for the party. null if the contact mechanism is still valid. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AdministrativeRegion](General.Contacts.PartyContactMechanisms.md#administrativeregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable) | The administrative region, where the contact mechanism is situated. Null if this is unknown or N/A. `Filter(multi eq)` `Introduced in version 18.2` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md)) |
| [ContactMechanism](General.Contacts.PartyContactMechanisms.md#contactmechanism) | [ContactMechanisms](General.Contacts.ContactMechanisms.md) | Returns this `PartyContactMechanism`(General.Contacts.PartyContactMechanisms.md). DO NOT USE! Kept for backward compatibility.             When a contact mechanism is set, the old inner contact mechanism becomes an orphan.              If the orphan is newly added in this transaction it is deleted. |
| [ContactMechanismPurpose](General.Contacts.PartyContactMechanisms.md#contactmechanismpurpose) | [ContactMechanismPurposes](General.Contacts.ContactMechanismPurposes.md) (nullable) | The purpose of this contact mechanism. Unique within the party. Can be used to seek for specific contact mechanisms. `Filter(multi eq)` `Introduced in version 18.2` |
| [GeoPoint](General.Contacts.PartyContactMechanisms.md#geopoint) | [GeoPoints](General.Geography.GeoPoints.md) (nullable) | The geographical point, where the contact mechanism is situated. Null if this is unknown or N/A. `Filter(multi eq)` `Introduced in version 18.2` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md)) |
| [Party](General.Contacts.PartyContactMechanisms.md#party) | [Parties](General.Contacts.Parties.md) | The party, having the contact mechanism. `Required` `Filter(multi eq)` `Owner` |
| [PersonalDataProcess](General.Contacts.PartyContactMechanisms.md#personaldataprocess) | [PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable) | The personal data process, which is used to process the current data. Null when the data is not personal or when the process is unknown. `Filter(multi eq)` `Introduced in version 18.2` |


## Attribute Details

### ContactMechanismType

A=Address; E=e-mail; T=Telephone. `Required` `Default("A")` `Filter(multi eq)` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md))

_Type_: **[ContactMechanismType](General.Contacts.PartyContactMechanisms.md#contactmechanismtype)**  
_Category_: **System**  
Allowed values for the `ContactMechanismType`(General.Contacts.ContactMechanisms.md#contactmechanismtype) data attribute  
_Allowed Values (General.Contacts.ContactMechanismsRepository.ContactMechanismType Enum Members)_  

| Value | Description |
| ---- | --- |
| Address | Address value. Stored as 'A'. <br /> _Database Value:_ 'A' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Address' |
| Mail | Mail value. Stored as 'E'. <br /> _Database Value:_ 'E' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Mail' |
| Fax | Fax value. Stored as 'F'. <br /> _Database Value:_ 'F' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Fax' |
| MobilePhone | MobilePhone value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'MobilePhone' |
| Other | Other value. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Other' |
| Telephone | Telephone value. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Telephone' |
| WebSite | WebSite value. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'WebSite' |
| PostalCode | PostalCode value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'PostalCode' |
| WebProfile | WebProfile value. Stored as 'X'. <br /> _Database Value:_ 'X' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'WebProfile' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **Address**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FromDate

The first date when the contact mechanism was valid. null means unknown date. `Default(Today)` `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDate**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

True if the contact mechanism is currently active and can be used to contact the party. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### IsDefault

True - when this is the default contact mechanism for this party; false - otherwise. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### LineOrd

Consecutive number of the contact information. The number is unique within the party. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.Party.ContactMechanisms.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.Party.ContactMechanisms.Select( c => c.LineOrd).DefaultIfEmpty( 0).Max( ) + 1)`
### Name

Contact mechanism description. `Required` `Filter(eq;like)` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md))

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### NonSolicitation

If true then Don't use the mechanism for solicitation purposes. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this PartyContactMechanism.

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

### ThruDate

The last date on which the contact mechanism was valid for the party. null if the contact mechanism is still valid. `Filter(eq;ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AdministrativeRegion

The administrative region, where the contact mechanism is situated. Null if this is unknown or N/A. `Filter(multi eq)` `Introduced in version 18.2` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md))

_Type_: **[AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ContactMechanism

Returns this `PartyContactMechanism`(General.Contacts.PartyContactMechanisms.md). DO NOT USE! Kept for backward compatibility.             When a contact mechanism is set, the old inner contact mechanism becomes an orphan.              If the orphan is newly added in this transaction it is deleted.

_Type_: **[ContactMechanisms](General.Contacts.ContactMechanisms.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **CannotBeShown**  

### ContactMechanismPurpose

The purpose of this contact mechanism. Unique within the party. Can be used to seek for specific contact mechanisms. `Filter(multi eq)` `Introduced in version 18.2`

_Type_: **[ContactMechanismPurposes](General.Contacts.ContactMechanismPurposes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### GeoPoint

The geographical point, where the contact mechanism is situated. Null if this is unknown or N/A. `Filter(multi eq)` `Introduced in version 18.2` (Inherited from [ContactMechanisms](General.Contacts.ContactMechanisms.md))

_Type_: **[GeoPoints](General.Geography.GeoPoints.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Party

The party, having the contact mechanism. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Parties](General.Contacts.Parties.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### PersonalDataProcess

The personal data process, which is used to process the current data. Null when the data is not personal or when the process is unknown. `Filter(multi eq)` `Introduced in version 18.2`

_Type_: **[PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable)**  
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

