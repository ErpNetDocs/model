---
uid: General.Contacts.PartyApplicableLegislations
---
# General.Contacts.PartyApplicableLegislations


Specifies a legislation, which is applicable for a party. A single party can have more than one applicable legislations.

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.PartyApplicableLegislations  
Base Table: Gen_Party_Applicable_Legislations  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Renames

Old name: General.PartyApplicableLegislations  
New name: General.Contacts.PartyApplicableLegislations  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {Party.PartyName:T}  
Search Members: Party.PartyName  
Name Member: Party.PartyName  
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
| [ApplicableLegislation](General.Contacts.PartyApplicableLegislations.md#applicablelegislation) | [ApplicableLegislation](General.Contacts.PartyApplicableLegislations.md#applicablelegislation) | A legislation, which applies to the specified party. The list of legislations is system defined, and contains legislations for which system rules are currently defined. For example: US, UK, EU, DE, FR, ES, IT, BG, MK, RO, GR, etc. 
| [Notes](General.Contacts.PartyApplicableLegislations.md#notes) | string (254) __nullable__ | Notes for this PartyApplicableLegislation. `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Party](General.Contacts.PartyApplicableLegislations.md#party) | [Parties](General.Contacts.Parties.md) | The <see cref="Party"/> to which this PartyApplicableLegislation belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.PartyApplicableLegislations.md#id) | guid |  
| [ObjectVersion](General.Contacts.PartyApplicableLegislations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Contacts.PartyApplicableLegislations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ApplicableLegislation

A legislation, which applies to the specified party. The list of legislations is system defined, and contains legislations for which system rules are currently defined. For example: US, UK, EU, DE, FR, ES, IT, BG, MK, RO, GR, etc.

Type: **[ApplicableLegislation](General.Contacts.PartyApplicableLegislations.md#applicablelegislation)**  
Category: **System**  
Allowed values for the `ApplicableLegislation`(General.Contacts.PartyApplicableLegislations.md#applicablelegislation) data attribute  
Allowed Values (General.Contacts.PartyApplicableLegislationsRepository.ApplicableLegislation Enum Members)  

| Value | Description |
| ---- | --- |
| UnitedArabEmirates | UnitedArabEmirates value. Stored as 'AE'. <br /> Database Value: 'AE' <br /> Model Value: 0 <br /> Domain API Value: 'UnitedArabEmirates' |
| Australia | Australia value. Stored as 'AU'. <br /> Database Value: 'AU' <br /> Model Value: 1 <br /> Domain API Value: 'Australia' |
| Bulgaria | Bulgaria value. Stored as 'BG'. <br /> Database Value: 'BG' <br /> Model Value: 2 <br /> Domain API Value: 'Bulgaria' |
| Canada | Canada value. Stored as 'CA'. <br /> Database Value: 'CA' <br /> Model Value: 3 <br /> Domain API Value: 'Canada' |
| China | China value. Stored as 'CN'. <br /> Database Value: 'CN' <br /> Model Value: 4 <br /> Domain API Value: 'China' |
| CzechRepublic | CzechRepublic value. Stored as 'CZ'. <br /> Database Value: 'CZ' <br /> Model Value: 5 <br /> Domain API Value: 'CzechRepublic' |
| Germany | Germany value. Stored as 'DE'. <br /> Database Value: 'DE' <br /> Model Value: 6 <br /> Domain API Value: 'Germany' |
| Spain | Spain value. Stored as 'ES'. <br /> Database Value: 'ES' <br /> Model Value: 7 <br /> Domain API Value: 'Spain' |
| EuropeanUnion | EuropeanUnion value. Stored as 'EU'. <br /> Database Value: 'EU' <br /> Model Value: 8 <br /> Domain API Value: 'EuropeanUnion' |
| France | France value. Stored as 'FR'. <br /> Database Value: 'FR' <br /> Model Value: 9 <br /> Domain API Value: 'France' |
| Greece | Greece value. Stored as 'GR'. <br /> Database Value: 'GR' <br /> Model Value: 10 <br /> Domain API Value: 'Greece' |
| Hungary | Hungary value. Stored as 'HU'. <br /> Database Value: 'HU' <br /> Model Value: 11 <br /> Domain API Value: 'Hungary' |
| India | India value. Stored as 'IN'. <br /> Database Value: 'IN' <br /> Model Value: 12 <br /> Domain API Value: 'India' |
| Italy | Italy value. Stored as 'IT'. <br /> Database Value: 'IT' <br /> Model Value: 13 <br /> Domain API Value: 'Italy' |
| Japan | Japan value. Stored as 'JP'. <br /> Database Value: 'JP' <br /> Model Value: 14 <br /> Domain API Value: 'Japan' |
| Macedonia | Macedonia value. Stored as 'MK'. <br /> Database Value: 'MK' <br /> Model Value: 15 <br /> Domain API Value: 'Macedonia' |
| Poland | Poland value. Stored as 'PL'. <br /> Database Value: 'PL' <br /> Model Value: 16 <br /> Domain API Value: 'Poland' |
| Portugal | Portugal value. Stored as 'PT'. <br /> Database Value: 'PT' <br /> Model Value: 17 <br /> Domain API Value: 'Portugal' |
| Romania | Romania value. Stored as 'RO'. <br /> Database Value: 'RO' <br /> Model Value: 18 <br /> Domain API Value: 'Romania' |
| Serbia | Serbia value. Stored as 'RS'. <br /> Database Value: 'RS' <br /> Model Value: 19 <br /> Domain API Value: 'Serbia' |
| Russia | Russia value. Stored as 'RU'. <br /> Database Value: 'RU' <br /> Model Value: 20 <br /> Domain API Value: 'Russia' |
| Turkey | Turkey value. Stored as 'TR'. <br /> Database Value: 'TR' <br /> Model Value: 21 <br /> Domain API Value: 'Turkey' |
| UnitedKingdom | UnitedKingdom value. Stored as 'UK'. <br /> Database Value: 'UK' <br /> Model Value: 22 <br /> Domain API Value: 'UnitedKingdom' |
| UnitedStates | UnitedStates value. Stored as 'US'. <br /> Database Value: 'US' <br /> Model Value: 23 <br /> Domain API Value: 'UnitedStates' |
| SouthAfrica | SouthAfrica value. Stored as 'ZA'. <br /> Database Value: 'ZA' <br /> Model Value: 24 <br /> Domain API Value: 'SouthAfrica' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this PartyApplicableLegislation. `Filter(like)`

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
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

### Party

The <see cref="Party"/> to which this PartyApplicableLegislation belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Parties](General.Contacts.Parties.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=General.Contacts.PartyApplicableLegislations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.PartyApplicableLegislations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_PartyApplicableLegislations

Domain API Entity Type: 
General_Contacts_PartyApplicableLegislation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_PartyApplicableLegislations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_PartyApplicableLegislations?$top=10>

