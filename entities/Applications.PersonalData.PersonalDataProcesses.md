---
uid: Applications.PersonalData.PersonalDataProcesses
---
# Applications.PersonalData.PersonalDataProcesses


Represents processes, which process personal data, regulated by GDPR and other applicable laws.

## General
Namespace: [Applications.PersonalData](Applications.PersonalData.md)  
Repository: Applications.PersonalData.PersonalDataProcesses  
Base Table: Pdm_Personal_Data_Processes  
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
* [Applications.PersonalData.PersonalDataProcesses](Applications.PersonalData.PersonalDataProcesses.md)  
  * [Applications.PersonalData.JointControllers](Applications.PersonalData.JointControllers.md)  
  * [Applications.PersonalData.PersonalDataProcessRecipients](Applications.PersonalData.PersonalDataProcessRecipients.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Applications.PersonalData.PersonalDataProcesses.md#code) | string (16) | Unique process code. 
| [ContainsSensitiveData](Applications.PersonalData.PersonalDataProcesses.md#containssensitivedata) | boolean | True if sensitive personal data is processed (racial, political, criminal, biometric, etc). 
| [DataSubjectCategory](Applications.PersonalData.PersonalDataProcesses.md#datasubjectcategory) | [DataSubjectCategory](Applications.PersonalData.PersonalDataProcesses.md#datasubjectcategory) | The category of data subjects (persons), whose data is processed. EMP=Employees; JOB=Job Candidates; CON=Contractors; CUS=Customers; SUP=Suppliers; PAR=Partners; OTH=Other. 
| [Description](Applications.PersonalData.PersonalDataProcesses.md#description) | string (max) __nullable__ | Description of the process. 
| [DiscontinuationDate](Applications.PersonalData.PersonalDataProcesses.md#discontinuationdate) | date __nullable__ | The date on which the process was discontinued. Null if the process is still active. 
| [EstablishDate](Applications.PersonalData.PersonalDataProcesses.md#establishdate) | date | The data on which the process was established and started functioning. 
| [LegalBasisForProcessing](Applications.PersonalData.PersonalDataProcesses.md#legalbasisforprocessing) | [LegalBasisForProcessing](Applications.PersonalData.PersonalDataProcesses.md#legalbasisforprocessing) | The basis on which the data is processed. INT=Legitimate Interest; CST=Consent; CTR=Contract; LEG=Legal Compliance; VIT=Vital Interests; PUB=Public Interest; 
| [ListOfDataCategories](Applications.PersonalData.PersonalDataProcesses.md#listofdatacategories) | string (254) | Comma-separated list of categories of personal data (both sensitive and non-sensitive) processed by this process. Common sensitive types of data include racial, political views, religion, trade union membership, sex life, criminal records, etc. 
| [ListOfDataRecipient<br />Categories](Applications.PersonalData.PersonalDataProcesses.md#listofdatarecipientcategories) | string (254) __nullable__ | Comma-separated list of types of data users. Usual categories include Staff, Public Authority, Contractor, etc. 
| [ListOfProcessingPurposes](Applications.PersonalData.PersonalDataProcesses.md#listofprocessingpurposes) | string (254) __nullable__ | Comma-separated list of processing purposes. Common purposes include Invoicing, Newsletter, Notifications, Repeatable Orders, etc. 
| [ListOfTechnicalMeasures](Applications.PersonalData.PersonalDataProcesses.md#listoftechnicalmeasures) | string (254) __nullable__ | Comma-separated list of technical measures taken to keep the data privacy. Common measures include Pseudonymisation, Encryption, Data Access Audit, etc. 
| [ListOfTransfers<br />ToThirdCountries](Applications.PersonalData.PersonalDataProcesses.md#listoftransferstothirdcountries) | string (254) __nullable__ | Comma-separated list of third countries, to which data is sent. 
| [ListOfUsedSoftware](Applications.PersonalData.PersonalDataProcesses.md#listofusedsoftware) | string (254) __nullable__ | Comma-separated list of the names of the software products used to process the data. 
| [Name](Applications.PersonalData.PersonalDataProcesses.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the process (Multilanguage). 
| [Notes](Applications.PersonalData.PersonalDataProcesses.md#notes) | string (max) __nullable__ | Notes for this PersonalDataProcess. 
| [ProcessingRole](Applications.PersonalData.PersonalDataProcesses.md#processingrole) | [ProcessingRole](Applications.PersonalData.PersonalDataProcesses.md#processingrole) | The role of the enterprise company in the process - Controller or Processor. The controller owns the personal data process. The processor operates on behalf of the controller. C=Controller; P=Processor.  
| [RetentionPeriodMonths](Applications.PersonalData.PersonalDataProcesses.md#retentionperiodmonths) | int32 __nullable__ | The period in months, for which the data is kept. Null when the period is unknown or N/A. 
| [ThirdCountryTransfers<br />Safeguards](Applications.PersonalData.PersonalDataProcesses.md#thirdcountrytransferssafeguards) | string (254) __nullable__ | Description of safeguards, taken to protect personal data in case of third country transfers. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompany](Applications.PersonalData.PersonalDataProcesses.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company, which owns the process. |
| [ProcessOwnerPerson](Applications.PersonalData.PersonalDataProcesses.md#processownerperson) | [Persons](General.Contacts.Persons.md) | The owner and responsible person for the process. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.PersonalData.PersonalDataProcesses.md#id) | guid |  
| [ObjectVersion](Applications.PersonalData.PersonalDataProcesses.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.PersonalData.PersonalDataProcesses.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.PersonalData.PersonalDataProcesses.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.PersonalData.PersonalDataProcesses.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.PersonalData.PersonalDataProcesses.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| JointControllers | [JointControllers](Applications.PersonalData.JointControllers.md) | List of `JointController`(Applications.PersonalData.JointControllers.md) child objects, based on the `Applications.PersonalData.JointController.PersonalDataProcess`(Applications.PersonalData.JointControllers.md#personaldataprocess) back reference 
| Recipients | [PersonalDataProcessRecipients](Applications.PersonalData.PersonalDataProcessRecipients.md) | List of `PersonalDataProcess<br />Recipient`(Applications.PersonalData.PersonalDataProcess<br />Recipients.md) child objects, based on the `Applications.PersonalData.PersonalDataProcess<br />Recipient.PersonalDataProcess`(Applications.PersonalData.PersonalDataProcess<br />Recipients.md#personaldataprocess) back reference 


## Attribute Details

### Code

Unique process code.

Type: **string (16)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### ContainsSensitiveData

True if sensitive personal data is processed (racial, political, criminal, biometric, etc).

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DataSubjectCategory

The category of data subjects (persons), whose data is processed. EMP=Employees; JOB=Job Candidates; CON=Contractors; CUS=Customers; SUP=Suppliers; PAR=Partners; OTH=Other.

Type: **[DataSubjectCategory](Applications.PersonalData.PersonalDataProcesses.md#datasubjectcategory)**  
Category: **System**  
Allowed values for the `DataSubjectCategory`(Applications.PersonalData.PersonalDataProcesses.md#datasubjectcategory) data attribute  
Allowed Values (Applications.PersonalData.PersonalDataProcessesRepository.DataSubjectCategory Enum Members)  

| Value | Description |
| ---- | --- |
| Employees | Employees value. Stored as 'EMP'. <br /> Database Value: 'EMP' <br /> Model Value: 0 <br /> Domain API Value: 'Employees' |
| JobCandidates | JobCandidates value. Stored as 'JOB'. <br /> Database Value: 'JOB' <br /> Model Value: 1 <br /> Domain API Value: 'JobCandidates' |
| Contractors | Contractors value. Stored as 'CON'. <br /> Database Value: 'CON' <br /> Model Value: 2 <br /> Domain API Value: 'Contractors' |
| Customers | Customers value. Stored as 'CUS'. <br /> Database Value: 'CUS' <br /> Model Value: 3 <br /> Domain API Value: 'Customers' |
| Suppliers | Suppliers value. Stored as 'SUP'. <br /> Database Value: 'SUP' <br /> Model Value: 4 <br /> Domain API Value: 'Suppliers' |
| Partners | Partners value. Stored as 'PAR'. <br /> Database Value: 'PAR' <br /> Model Value: 5 <br /> Domain API Value: 'Partners' |
| Other | Other value. Stored as 'OTH'. <br /> Database Value: 'OTH' <br /> Model Value: 6 <br /> Domain API Value: 'Other' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Description

Description of the process.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### DiscontinuationDate

The date on which the process was discontinued. Null if the process is still active.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EstablishDate

The data on which the process was established and started functioning.

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### LegalBasisForProcessing

The basis on which the data is processed. INT=Legitimate Interest; CST=Consent; CTR=Contract; LEG=Legal Compliance; VIT=Vital Interests; PUB=Public Interest;

Type: **[LegalBasisForProcessing](Applications.PersonalData.PersonalDataProcesses.md#legalbasisforprocessing)**  
Category: **System**  
Allowed values for the `LegalBasisForProcessing`(Applications.PersonalData.PersonalDataProcesses.md#legalbasisforprocessing) data attribute  
Allowed Values (Applications.PersonalData.PersonalDataProcessesRepository.LegalBasisForProcessing Enum Members)  

| Value | Description |
| ---- | --- |
| LegitimateInterest | LegitimateInterest value. Stored as 'INT'. <br /> Database Value: 'INT' <br /> Model Value: 0 <br /> Domain API Value: 'LegitimateInterest' |
| Consent | Consent value. Stored as 'CST'. <br /> Database Value: 'CST' <br /> Model Value: 1 <br /> Domain API Value: 'Consent' |
| Contract | Contract value. Stored as 'CTR'. <br /> Database Value: 'CTR' <br /> Model Value: 2 <br /> Domain API Value: 'Contract' |
| LegalCompliance | LegalCompliance value. Stored as 'LEG'. <br /> Database Value: 'LEG' <br /> Model Value: 3 <br /> Domain API Value: 'LegalCompliance' |
| VitalInterest | VitalInterest value. Stored as 'VIT'. <br /> Database Value: 'VIT' <br /> Model Value: 4 <br /> Domain API Value: 'VitalInterest' |
| PublicInterest | PublicInterest value. Stored as 'PUB'. <br /> Database Value: 'PUB' <br /> Model Value: 5 <br /> Domain API Value: 'PublicInterest' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ListOfDataCategories

Comma-separated list of categories of personal data (both sensitive and non-sensitive) processed by this process. Common sensitive types of data include racial, political views, religion, trade union membership, sex life, criminal records, etc.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ListOfDataRecipientCategories

Comma-separated list of types of data users. Usual categories include Staff, Public Authority, Contractor, etc.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ListOfProcessingPurposes

Comma-separated list of processing purposes. Common purposes include Invoicing, Newsletter, Notifications, Repeatable Orders, etc.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ListOfTechnicalMeasures

Comma-separated list of technical measures taken to keep the data privacy. Common measures include Pseudonymisation, Encryption, Data Access Audit, etc.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ListOfTransfersToThirdCountries

Comma-separated list of third countries, to which data is sent.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ListOfUsedSoftware

Comma-separated list of the names of the software products used to process the data.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Name

Name of the process (Multilanguage).

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this PersonalDataProcess.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ProcessingRole

The role of the enterprise company in the process - Controller or Processor. The controller owns the personal data process. The processor operates on behalf of the controller. C=Controller; P=Processor.

Type: **[ProcessingRole](Applications.PersonalData.PersonalDataProcesses.md#processingrole)**  
Category: **System**  
Allowed values for the `ProcessingRole`(Applications.PersonalData.PersonalDataProcesses.md#processingrole) data attribute  
Allowed Values (Applications.PersonalData.PersonalDataProcessesRepository.ProcessingRole Enum Members)  

| Value | Description |
| ---- | --- |
| Controller | Controller value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'Controller' |
| Processor | Processor value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 1 <br /> Domain API Value: 'Processor' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Controller**  
Show in UI: **ShownByDefault**  

### RetentionPeriodMonths

The period in months, for which the data is kept. Null when the period is unknown or N/A.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ThirdCountryTransfersSafeguards

Description of safeguards, taken to protect personal data in case of third country transfers.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
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

### EnterpriseCompany

The enterprise company, which owns the process.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProcessOwnerPerson

The owner and responsible person for the process.

Type: **[Persons](General.Contacts.Persons.md)**  
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

