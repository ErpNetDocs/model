---
uid: Applications.PersonalData.ProcessingConsents
---
# Applications.PersonalData.ProcessingConsents Entity

**Namespace:** [Applications.PersonalData](Applications.PersonalData.md)  

Consents of data subjects for processing of their personal data. Entity: Pdm_Processing_Consents (Introduced in version 18.2)

## Default Visualization
Default Display Text Format:  
_{ParentName}_  
Default Search Members:  
_ParentName_  
Name Data Member:  
_ParentName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Applications.PersonalData.ProcessingConsents.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Applications.PersonalData.ProcessingConsents.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.PersonalData.ProcessingConsents.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [GivenOnUtc](Applications.PersonalData.ProcessingConsents.md#givenonutc) | datetime | The date and time (in Utc), when the consent was given. `Required` `Filter(ge;le)` 
| [Id](Applications.PersonalData.ProcessingConsents.md#id) | guid |  
| [IsActive](Applications.PersonalData.ProcessingConsents.md#isactive) | boolean | Whether the consent is active or retracted. Once retracted, the consent record cannot be modified again and a new consent should be given. `Required` `Default(true)` `Filter(eq)` 
| [IsChild](Applications.PersonalData.ProcessingConsents.md#ischild) | boolean | Specifies whether the data subject is child, according to the local regulations. General regulations treat all persons below the age of 16 as child. `Required` `Default(false)` `Filter(eq)` 
| [Notes](Applications.PersonalData.ProcessingConsents.md#notes) | string (max) __nullable__ | Notes for this ProcessingConsent. 
| [ObjectVersion](Applications.PersonalData.ProcessingConsents.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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


## Attribute Details

### AllowAddress

Allows the processing of the physical address. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### AllowBasicData

Allows the processing of basic (usually public) data: Name, AgeGroup21+, public profile picture, etc. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### AllowEmail

Allows the processing of the email address. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### AllowOtherData

Comma-separated list of other types of data, which was allowed for processing with this consent. `Filter(eq)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### AllowPhone

Allows the processing of the telephone number. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### ConsentImage

If not null, it is a graphical image, containing additional information for the consent.

_Type_: **byte[] __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ConsentText

The actual text of the consent. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ConsentType

The way the consent was given. O=Online; I=Implicit; V=Verbal; W=Written; E=Email; T=Other (should be stated in Notes). `Required` `Filter(eq)`

_Type_: **[ConsentType](Applications.PersonalData.ProcessingConsents.md#consenttype)**  
_Category_: **System**  
Allowed values for the `ConsentType`(Applications.PersonalData.ProcessingConsents.md#consenttype) data attribute  
_Allowed Values (Applications.PersonalData.ProcessingConsentsRepository.ConsentType Enum Members)_  

| Value | Description |
| ---- | --- |
| Online | Online value. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Online' |
| Implicit | Implicit value. Stored as 'I'. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Implicit' |
| Verbal | Verbal value. Stored as 'V'. <br /> _Database Value:_ 'V' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Verbal' |
| Written | Written value. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Written' |
| Email | Email value. Stored as 'E'. <br /> _Database Value:_ 'E' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Email' |
| Other | Other value. Stored as 'T'. <br /> _Database Value:_ 'T' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

_Type_: **string**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### GivenOnUtc

The date and time (in Utc), when the consent was given. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsActive

Whether the consent is active or retracted. Once retracted, the consent record cannot be modified again and a new consent should be given. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### IsChild

Specifies whether the data subject is child, according to the local regulations. General regulations treat all persons below the age of 16 as child. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this ProcessingConsent.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

### ParentEmail

When a parental rights holder gives a consent for a child, contains the email of the parent. `Filter(like)`

_Type_: **string (50) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### ParentName

When a parental rights holder gives a consent for a child, contains the name of the parent. `Filter(eq;like)`

_Type_: **string (50) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### ParentPhone

When a parental rights holder gives a consent for a child, contains the phone number of the parent. `Filter(like)`

_Type_: **string (50) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### RetractedOnUtc

The date and time (in Utc), when the consent was retracted. Null if the consent is not retracted. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Person

The person, for which the consent is given. Null when the consent is given by an online user, which is still not linked to a specific person record. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PersonalDataProcess

The process, which will be used to process the data. Null when the process is unknown, or there are multiple processes (not recommended) processing the data, listed in the Notes. `Filter(multi eq)`

_Type_: **[PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### User

The login user, for which the consent is given. Null when a consent is entered for a natural person, not through online user. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
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

