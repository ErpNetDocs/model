---
uid: Applications.PersonalData.ProcessingConsents
---
# Applications.PersonalData.ProcessingConsents


Consents of data subjects for processing of their personal data.

## General
Namespace: [Applications.PersonalData](Applications.PersonalData.md)  
Repository: Applications.PersonalData.ProcessingConsents  
Base Table: Pdm_Processing_Consents  
Introduced In Version: 18.2  
API access:  ReadWrite  

## Visualization
Display Format: {ParentName}  
Search Members: ParentName  
Name Member: ParentName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.PersonalData.ProcessingConsents](Applications.PersonalData.ProcessingConsents.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowAddress](Applications.PersonalData.ProcessingConsents.md#allowaddress) | boolean | Allows the processing of the physical address. `Required` `Default(false)` `Filter(eq)` 
| [AllowBasicData](Applications.PersonalData.ProcessingConsents.md#allowbasicdata) | boolean | Allows the processing of basic (usually public) data: Name, AgeGroup21+, public profile picture, etc. `Required` `Default(false)` `Filter(eq)` 
| [AllowEmail](Applications.PersonalData.ProcessingConsents.md#allowemail) | boolean | Allows the processing of the email address. `Required` `Default(false)` `Filter(eq)` 
| [AllowOtherData](Applications.PersonalData.ProcessingConsents.md#allowotherdata) | string (max) __nullable__ | Comma-separated list of other types of data, which was allowed for processing with this consent. `Filter(eq)` 
| [AllowPhone](Applications.PersonalData.ProcessingConsents.md#allowphone) | boolean | Allows the processing of the telephone number. `Required` `Default(false)` `Filter(eq)` 
| [ConsentImage](Applications.PersonalData.ProcessingConsents.md#consentimage) | byte[] __nullable__ | If not null, it is a graphical image, containing additional information for the consent. 
| [ConsentText](Applications.PersonalData.ProcessingConsents.md#consenttext) | string (max) __nullable__ | The actual text of the consent. `Filter(like)` 
| [ConsentType](Applications.PersonalData.ProcessingConsents.md#consenttype) | [ConsentType](Applications.PersonalData.ProcessingConsents.md#consenttype) | The way the consent was given. O=Online; I=Implicit; V=Verbal; W=Written; E=Email; T=Other (should be stated in Notes). `Required` `Filter(eq)` 
| [GivenOnUtc](Applications.PersonalData.ProcessingConsents.md#givenonutc) | datetime | The date and time (in Utc), when the consent was given. `Required` `Filter(ge;le)` 
| [IsActive](Applications.PersonalData.ProcessingConsents.md#isactive) | boolean | Whether the consent is active or retracted. Once retracted, the consent record cannot be modified again and a new consent should be given. `Required` `Default(true)` `Filter(eq)` 
| [IsChild](Applications.PersonalData.ProcessingConsents.md#ischild) | boolean | Specifies whether the data subject is child, according to the local regulations. General regulations treat all persons below the age of 16 as child. `Required` `Default(false)` `Filter(eq)` 
| [Notes](Applications.PersonalData.ProcessingConsents.md#notes) | string (max) __nullable__ | Notes for this ProcessingConsent. 
| [ParentEmail](Applications.PersonalData.ProcessingConsents.md#parentemail) | string (50) __nullable__ | When a parental rights holder gives a consent for a child, contains the email of the parent. `Filter(like)` 
| [ParentName](Applications.PersonalData.ProcessingConsents.md#parentname) | string (50) __nullable__ | When a parental rights holder gives a consent for a child, contains the name of the parent. `Filter(eq;like)` 
| [ParentPhone](Applications.PersonalData.ProcessingConsents.md#parentphone) | string (50) __nullable__ | When a parental rights holder gives a consent for a child, contains the phone number of the parent. `Filter(like)` 
| [RetractedOnUtc](Applications.PersonalData.ProcessingConsents.md#retractedonutc) | datetime __nullable__ | The date and time (in Utc), when the consent was retracted. Null if the consent is not retracted. `Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Person](Applications.PersonalData.ProcessingConsents.md#person) | [Persons](General.Contacts.Persons.md) (nullable) | The person, for which the consent is given. Null when the consent is given by an online user, which is still not linked to a specific person record. `Filter(multi eq)` |
| [PersonalDataProcess](Applications.PersonalData.ProcessingConsents.md#personaldataprocess) | [PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable) | The process, which will be used to process the data. Null when the process is unknown, or there are multiple processes (not recommended) processing the data, listed in the Notes. `Filter(multi eq)` |
| [User](Applications.PersonalData.ProcessingConsents.md#user) | [Users](Systems.Security.Users.md) | The login user, for which the consent is given. Null when a consent is entered for a natural person, not through online user. `Required` `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.PersonalData.ProcessingConsents.md#id) | guid |  
| [ObjectVersion](Applications.PersonalData.ProcessingConsents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.PersonalData.ProcessingConsents.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.PersonalData.ProcessingConsents.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.PersonalData.ProcessingConsents.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.PersonalData.ProcessingConsents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AllowAddress

Allows the processing of the physical address. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### AllowBasicData

Allows the processing of basic (usually public) data: Name, AgeGroup21+, public profile picture, etc. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### AllowEmail

Allows the processing of the email address. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### AllowOtherData

Comma-separated list of other types of data, which was allowed for processing with this consent. `Filter(eq)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### AllowPhone

Allows the processing of the telephone number. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### ConsentImage

If not null, it is a graphical image, containing additional information for the consent.

Type: **byte[] __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ConsentText

The actual text of the consent. `Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ConsentType

The way the consent was given. O=Online; I=Implicit; V=Verbal; W=Written; E=Email; T=Other (should be stated in Notes). `Required` `Filter(eq)`

Type: **[ConsentType](Applications.PersonalData.ProcessingConsents.md#consenttype)**  
Category: **System**  
Allowed values for the `ConsentType`(Applications.PersonalData.ProcessingConsents.md#consenttype) data attribute  
Allowed Values (Applications.PersonalData.ProcessingConsentsRepository.ConsentType Enum Members)  

| Value | Description |
| ---- | --- |
| Online | Online value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 0 <br /> Domain API Value: 'Online' |
| Implicit | Implicit value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 1 <br /> Domain API Value: 'Implicit' |
| Verbal | Verbal value. Stored as 'V'. <br /> Database Value: 'V' <br /> Model Value: 2 <br /> Domain API Value: 'Verbal' |
| Written | Written value. Stored as 'W'. <br /> Database Value: 'W' <br /> Model Value: 3 <br /> Domain API Value: 'Written' |
| Email | Email value. Stored as 'E'. <br /> Database Value: 'E' <br /> Model Value: 4 <br /> Domain API Value: 'Email' |
| Other | Other value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 5 <br /> Domain API Value: 'Other' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### GivenOnUtc

The date and time (in Utc), when the consent was given. `Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Whether the consent is active or retracted. Once retracted, the consent record cannot be modified again and a new consent should be given. `Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### IsChild

Specifies whether the data subject is child, according to the local regulations. General regulations treat all persons below the age of 16 as child. `Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ProcessingConsent.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ParentEmail

When a parental rights holder gives a consent for a child, contains the email of the parent. `Filter(like)`

Type: **string (50) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### ParentName

When a parental rights holder gives a consent for a child, contains the name of the parent. `Filter(eq;like)`

Type: **string (50) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### ParentPhone

When a parental rights holder gives a consent for a child, contains the phone number of the parent. `Filter(like)`

Type: **string (50) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### RetractedOnUtc

The date and time (in Utc), when the consent was retracted. Null if the consent is not retracted. `Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
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


## Reference Details

### Person

The person, for which the consent is given. Null when the consent is given by an online user, which is still not linked to a specific person record. `Filter(multi eq)`

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PersonalDataProcess

The process, which will be used to process the data. Null when the process is unknown, or there are multiple processes (not recommended) processing the data, listed in the Notes. `Filter(multi eq)`

Type: **[PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### User

The login user, for which the consent is given. Null when a consent is entered for a natural person, not through online user. `Required` `Filter(multi eq)`

Type: **[Users](Systems.Security.Users.md)**  
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

[!list limit=1000 erp.entity=Applications.PersonalData.ProcessingConsents erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.PersonalData.ProcessingConsents erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_PersonalData_ProcessingConsents

Domain API Entity Type: 
Applications_PersonalData_ProcessingConsent

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_PersonalData_ProcessingConsents?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_PersonalData_ProcessingConsents?$top=10>

