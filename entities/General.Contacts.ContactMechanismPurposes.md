---
uid: General.Contacts.ContactMechanismPurposes
---
# General.Contacts.ContactMechanismPurposes


Contains user-defined purposes for processing contact mechanisms. Used for personal data management.

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.ContactMechanismPurposes  
Base Table: Cm_Contact_Mechanism_Purposes  
Introduced In Version: 18.2  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Contacts.ContactMechanismPurposes](General.Contacts.ContactMechanismPurposes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](General.Contacts.ContactMechanismPurposes.md#code) | string (16) | The unique code of the ContactMechanismPurpose. `Required` `Filter(eq;like)` `ORD` 
| [ContactMechanismType](General.Contacts.ContactMechanismPurposes.md#contactmechanismtype) | [ContactMechanismType](General.Contacts.ContactMechanismPurposes.md#contactmechanismtype) __nullable__ | When specified, allows the purpose to be specified only for contact mechanisms of the specified type.`Filter(multi eq)` 
| [Description](General.Contacts.ContactMechanismPurposes.md#description) | string (max) __nullable__ | The description of this ContactMechanismPurpose. `Filter(like)` 
| [Name](General.Contacts.ContactMechanismPurposes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the contact mechanism purpose (Multilanguage).`Required` `Filter(like)` 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.ContactMechanismPurposes.md#id) | guid |  
| [ObjectVersion](General.Contacts.ContactMechanismPurposes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Contacts.ContactMechanismPurposes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Contacts.ContactMechanismPurposes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Contacts.ContactMechanismPurposes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Contacts.ContactMechanismPurposes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

The unique code of the ContactMechanismPurpose. `Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### ContactMechanismType

When specified, allows the purpose to be specified only for contact mechanisms of the specified type.`Filter(multi eq)`

Type: **[ContactMechanismType](General.Contacts.ContactMechanismPurposes.md#contactmechanismtype) __nullable__**  
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
Show in UI: **ShownByDefault**  

### Description

The description of this ContactMechanismPurpose. `Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Name

Name of the contact mechanism purpose (Multilanguage).`Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
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

[!list limit=1000 erp.entity=General.Contacts.ContactMechanismPurposes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.ContactMechanismPurposes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_ContactMechanismPurposes

Domain API Entity Type: 
General_Contacts_ContactMechanismPurpose

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_ContactMechanismPurposes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_ContactMechanismPurposes?$top=10>

