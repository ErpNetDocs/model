---
uid: Applications.PersonalData.PersonalDataProcesses
---
# Applications.PersonalData.PersonalDataProcesses Entity

**Namespace:** [Applications.PersonalData](Applications.PersonalData.md)  

Represents processes, which process personal data, regulated by GDPR and other applicable laws. Entity: Pdm_Personal_Data_Processes (Introduced in version 18.2)

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Settings_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.PersonalData.PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md)  
  * [Applications.PersonalData.JointControllers](Applications.PersonalData.JointControllers.md)  
  * [Applications.PersonalData.PersonalDataProcessRecipients](Applications.PersonalData.PersonalDataProcessRecipients.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AggregateLastUpdateTimeUtc](Applications.PersonalData.PersonalDataProcesses.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [Code](Applications.PersonalData.PersonalDataProcesses.md#code) | string (16) | Unique process code. `Required` `Filter(eq;like)` 
| [ContainsSensitiveData](Applications.PersonalData.PersonalDataProcesses.md#containssensitivedata) | boolean | True if sensitive personal data is processed (racial, political, criminal, biometric, etc). `Required` `Filter(eq)` 
| [DataSubjectCategory](Applications.PersonalData.PersonalDataProcesses.md#datasubjectcategory) | [DataSubjectCategory](Applications.PersonalData.PersonalDataProcesses.md#datasubjectcategory) | The category of data subjects (persons), whose data is processed. EMP=Employees; JOB=Job Candidates; CON=Contractors; CUS=Customers; SUP=Suppliers; PAR=Partners; OTH=Other. `Required` 
| [Description](Applications.PersonalData.PersonalDataProcesses.md#description) | string (max) __nullable__ | Description of the process. 
| [DiscontinuationDate](Applications.PersonalData.PersonalDataProcesses.md#discontinuationdate) | date __nullable__ | The date on which the process was discontinued. Null if the process is still active. `Filter(eq;ge;le)` 
| [DisplayText](Applications.PersonalData.PersonalDataProcesses.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EstablishDate](Applications.PersonalData.PersonalDataProcesses.md#establishdate) | date | The data on which the process was established and started functioning. `Required` `Default(Now)` `Filter(eq;ge;le)` 
| [ExternalId](Applications.PersonalData.PersonalDataProcesses.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.PersonalData.PersonalDataProcesses.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Applications.PersonalData.PersonalDataProcesses.md#id) | guid |  
| [LegalBasisForProcessing](Applications.PersonalData.PersonalDataProcesses.md#legalbasisforprocessing) | [LegalBasisForProcessing](Applications.PersonalData.PersonalDataProcesses.md#legalbasisforprocessing) | The basis on which the data is processed. INT=Legitimate Interest; CST=Consent; CTR=Contract; LEG=Legal Compliance; VIT=Vital Interests; PUB=Public Interest;. `Required` `Filter(eq)` 
| [ListOfDataCategories](Applications.PersonalData.PersonalDataProcesses.md#listofdatacategories) | string (254) | Comma-separated list of categories of personal data (both sensitive and non-sensitive) processed by this process. Common sensitive types of data include racial, political views, religion, trade union membership, sex life, criminal records, etc. `Required` `Filter(eq)` 
| [ListOfDataRecipient<br />Categories](Applications.PersonalData.PersonalDataProcesses.md#listofdatarecipientcategories) | string (254) __nullable__ | Comma-separated list of types of data users. Usual categories include Staff, Public Authority, Contractor, etc. `Filter(eq;like)` 
| [ListOfProcessingPurposes](Applications.PersonalData.PersonalDataProcesses.md#listofprocessingpurposes) | string (254) __nullable__ | Comma-separated list of processing purposes. Common purposes include Invoicing, Newsletter, Notifications, Repeatable Orders, etc. `Filter(eq;like)` 
| [ListOfTechnicalMeasures](Applications.PersonalData.PersonalDataProcesses.md#listoftechnicalmeasures) | string (254) __nullable__ | Comma-separated list of technical measures taken to keep the data privacy. Common measures include Pseudonymisation, Encryption, Data Access Audit, etc. `Filter(eq)` 
| [ListOfTransfers<br />ToThirdCountries](Applications.PersonalData.PersonalDataProcesses.md#listoftransferstothirdcountries) | string (254) __nullable__ | Comma-separated list of third countries, to which data is sent. `Filter(eq;like)` 
| [ListOfUsedSoftware](Applications.PersonalData.PersonalDataProcesses.md#listofusedsoftware) | string (254) __nullable__ | Comma-separated list of the names of the software products used to process the data. `Filter(eq;like)` 
| [Name](Applications.PersonalData.PersonalDataProcesses.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the process (Multilanguage). `Required` `Filter(eq;like)` 
| [Notes](Applications.PersonalData.PersonalDataProcesses.md#notes) | string (max) __nullable__ | Notes for this PersonalDataProcess. 
| [ObjectVersion](Applications.PersonalData.PersonalDataProcesses.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ProcessingRole](Applications.PersonalData.PersonalDataProcesses.md#processingrole) | [ProcessingRole](Applications.PersonalData.PersonalDataProcesses.md#processingrole) | The role of the enterprise company in the process - Controller or Processor. The controller owns the personal data process. The processor operates on behalf of the controller. C=Controller; P=Processor. . `Required` `Default("C")` `Filter(eq)` 
| [RetentionPeriodMonths](Applications.PersonalData.PersonalDataProcesses.md#retentionperiodmonths) | int32 __nullable__ | The period in months, for which the data is kept. Null when the period is unknown or N/A. `Filter(eq)` 
| [ThirdCountryTransfers<br />Safeguards](Applications.PersonalData.PersonalDataProcesses.md#thirdcountrytransferssafeguards) | string (254) __nullable__ | Description of safeguards, taken to protect personal data in case of third country transfers. `Filter(eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Applications.PersonalData.PersonalDataProcesses.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company, which owns the process. `Required` `Filter(multi eq)` |
| [ProcessOwnerPerson](Applications.PersonalData.PersonalDataProcesses.md#processownerperson) | [Persons](General.Contacts.Persons.md) | The owner and responsible person for the process. `Required` `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| JointControllers | [JointControllers](Applications.PersonalData.JointControllers.md) | List of `JointController`(Applications.PersonalData.JointControllers.md) child objects, based on the `Applications.PersonalData.JointController.PersonalDataProcess`(Applications.PersonalData.JointControllers.md#personaldataprocess) back reference 
| Recipients | [PersonalDataProcessRecipients](Applications.PersonalData.PersonalDataProcessRecipients.md) | List of `PersonalDataProcess<br />Recipient`(Applications.PersonalData.PersonalDataProcess<br />Recipients.md) child objects, based on the `Applications.PersonalData.PersonalDataProcess<br />Recipient.PersonalDataProcess`(Applications.PersonalData.PersonalDataProcess<br />Recipients.md#personaldataprocess) back reference 


## Attribute Details

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Code

Unique process code. `Required` `Filter(eq;like)`

_Type_: **string (16)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### ContainsSensitiveData

True if sensitive personal data is processed (racial, political, criminal, biometric, etc). `Required` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DataSubjectCategory

The category of data subjects (persons), whose data is processed. EMP=Employees; JOB=Job Candidates; CON=Contractors; CUS=Customers; SUP=Suppliers; PAR=Partners; OTH=Other. `Required`

_Type_: **[DataSubjectCategory](Applications.PersonalData.PersonalDataProcesses.md#datasubjectcategory)**  
_Category_: **System**  
Allowed values for the `DataSubjectCategory`(Applications.PersonalData.PersonalDataProcesses.md#datasubjectcategory) data attribute  
_Allowed Values (Applications.PersonalData.PersonalDataProcessesRepository.DataSubjectCategory Enum Members)_  

| Value | Description |
| ---- | --- |
| Employees | Employees value. Stored as 'EMP'. <br /> _Database Value:_ 'EMP' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Employees' |
| JobCandidates | JobCandidates value. Stored as 'JOB'. <br /> _Database Value:_ 'JOB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'JobCandidates' |
| Contractors | Contractors value. Stored as 'CON'. <br /> _Database Value:_ 'CON' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Contractors' |
| Customers | Customers value. Stored as 'CUS'. <br /> _Database Value:_ 'CUS' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Customers' |
| Suppliers | Suppliers value. Stored as 'SUP'. <br /> _Database Value:_ 'SUP' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Suppliers' |
| Partners | Partners value. Stored as 'PAR'. <br /> _Database Value:_ 'PAR' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Partners' |
| Other | Other value. Stored as 'OTH'. <br /> _Database Value:_ 'OTH' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Other' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Description

Description of the process.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### DiscontinuationDate

The date on which the process was discontinued. Null if the process is still active. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EstablishDate

The data on which the process was established and started functioning. `Required` `Default(Now)` `Filter(eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LegalBasisForProcessing

The basis on which the data is processed. INT=Legitimate Interest; CST=Consent; CTR=Contract; LEG=Legal Compliance; VIT=Vital Interests; PUB=Public Interest;. `Required` `Filter(eq)`

_Type_: **[LegalBasisForProcessing](Applications.PersonalData.PersonalDataProcesses.md#legalbasisforprocessing)**  
_Category_: **System**  
Allowed values for the `LegalBasisForProcessing`(Applications.PersonalData.PersonalDataProcesses.md#legalbasisforprocessing) data attribute  
_Allowed Values (Applications.PersonalData.PersonalDataProcessesRepository.LegalBasisForProcessing Enum Members)_  

| Value | Description |
| ---- | --- |
| LegitimateInterest | LegitimateInterest value. Stored as 'INT'. <br /> _Database Value:_ 'INT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'LegitimateInterest' |
| Consent | Consent value. Stored as 'CST'. <br /> _Database Value:_ 'CST' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Consent' |
| Contract | Contract value. Stored as 'CTR'. <br /> _Database Value:_ 'CTR' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Contract' |
| LegalCompliance | LegalCompliance value. Stored as 'LEG'. <br /> _Database Value:_ 'LEG' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'LegalCompliance' |
| VitalInterest | VitalInterest value. Stored as 'VIT'. <br /> _Database Value:_ 'VIT' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'VitalInterest' |
| PublicInterest | PublicInterest value. Stored as 'PUB'. <br /> _Database Value:_ 'PUB' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'PublicInterest' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ListOfDataCategories

Comma-separated list of categories of personal data (both sensitive and non-sensitive) processed by this process. Common sensitive types of data include racial, political views, religion, trade union membership, sex life, criminal records, etc. `Required` `Filter(eq)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ListOfDataRecipientCategories

Comma-separated list of types of data users. Usual categories include Staff, Public Authority, Contractor, etc. `Filter(eq;like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ListOfProcessingPurposes

Comma-separated list of processing purposes. Common purposes include Invoicing, Newsletter, Notifications, Repeatable Orders, etc. `Filter(eq;like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ListOfTechnicalMeasures

Comma-separated list of technical measures taken to keep the data privacy. Common measures include Pseudonymisation, Encryption, Data Access Audit, etc. `Filter(eq)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ListOfTransfersToThirdCountries

Comma-separated list of third countries, to which data is sent. `Filter(eq;like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ListOfUsedSoftware

Comma-separated list of the names of the software products used to process the data. `Filter(eq;like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Name

Name of the process (Multilanguage). `Required` `Filter(eq;like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this PersonalDataProcess.

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

### ProcessingRole

The role of the enterprise company in the process - Controller or Processor. The controller owns the personal data process. The processor operates on behalf of the controller. C=Controller; P=Processor. . `Required` `Default("C")` `Filter(eq)`

_Type_: **[ProcessingRole](Applications.PersonalData.PersonalDataProcesses.md#processingrole)**  
_Category_: **System**  
Allowed values for the `ProcessingRole`(Applications.PersonalData.PersonalDataProcesses.md#processingrole) data attribute  
_Allowed Values (Applications.PersonalData.PersonalDataProcessesRepository.ProcessingRole Enum Members)_  

| Value | Description |
| ---- | --- |
| Controller | Controller value. Stored as 'C'. <br /> _Database Value:_ 'C' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Controller' |
| Processor | Processor value. Stored as 'P'. <br /> _Database Value:_ 'P' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Processor' |

_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **Controller**  
_Show in UI_: **ShownByDefault**  

### RetentionPeriodMonths

The period in months, for which the data is kept. Null when the period is unknown or N/A. `Filter(eq)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ThirdCountryTransfersSafeguards

Description of safeguards, taken to protect personal data in case of third country transfers. `Filter(eq;like)`

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### EnterpriseCompany

The enterprise company, which owns the process. `Required` `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProcessOwnerPerson

The owner and responsible person for the process. `Required` `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md)**  
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

[!list limit=1000 erp.entity=Applications.PersonalData.PersonalDataProcesses erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.PersonalData.PersonalDataProcesses erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_PersonalData_PersonalDataProcesses

Domain API Entity Type: 
Applications_PersonalData_PersonalDataProcess

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_PersonalData_PersonalDataProcesses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_PersonalData_PersonalDataProcesses?$top=10>

