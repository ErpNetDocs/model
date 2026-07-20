---
uid: Regulatory.Saft.DeclarationExports
---
# Regulatory.Saft.DeclarationExports


Each record in the table represents a distinct SAF-T declaration export operation.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.DeclarationExports  
Base Table: Saft_Declaration_Exports  
Introduced In Version: 27.1.0.81  
API access:  ReadOnly  

## Visualization
Display Format: {CompanyName}  
Search Members: BeneficialOwnerCountryCode; CompanyName  
Code Member: BeneficialOwnerCountryCode  
Name Member: CompanyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Saft.SaftDeclarations](Regulatory.Saft.SaftDeclarations.md)  
Aggregate Root:  
[Regulatory.Saft.SaftDeclarations](Regulatory.Saft.SaftDeclarations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicationVersion](Regulatory.Saft.DeclarationExports.md#applicationversion) | string (64) | ERP.net Version Used to Generate the Export`Required` |
| [AuditFileDateCreated](Regulatory.Saft.DeclarationExports.md#auditfiledatecreated) | datetime | Creation date of odit file (value of AuditFileDateCreated)`Required` `Filter(ge;le)` |
| [BeneficialOwnerCountryCode](Regulatory.Saft.DeclarationExports.md#beneficialownercountrycode) | string (2) __nullable__ | Country Code of the Beneficial Owner |
| [BeneficialOwnerEGN](Regulatory.Saft.DeclarationExports.md#beneficialowneregn) | string (16) __nullable__ | Personal Identification Number of the Bulgarian Beneficial Owne |
| [BeneficialOwner<br />NameCyrillicBG](Regulatory.Saft.DeclarationExports.md#beneficialownernamecyrillicbg) | string (127) __nullable__ | Name of the Bulgarian Beneficial Owner |
| [BeneficialOwner<br />NameLatinForeign](Regulatory.Saft.DeclarationExports.md#beneficialownernamelatinforeign) | string (127) __nullable__ | Name of the Foreign Beneficial Owner |
| [CompanyCity](Regulatory.Saft.DeclarationExports.md#companycity) | string (64) __nullable__ | City or Other Locality |
| [CompanyCountryCode](Regulatory.Saft.DeclarationExports.md#companycountrycode) | string (2) __nullable__ | Country Code |
| [CompanyName](Regulatory.Saft.DeclarationExports.md#companyname) | string (254) __nullable__ | Official Name of the Taxable Person |
| [CompanyRegistrationNumber](Regulatory.Saft.DeclarationExports.md#companyregistrationnumber) | string (16) __nullable__ | Company Registration Number or Other Registration Number of the Taxable Person |
| [CompanyStreetName](Regulatory.Saft.DeclarationExports.md#companystreetname) | string (254) __nullable__ | Registered Address of the Taxable Person |
| [ContactPersonEmail](Regulatory.Saft.DeclarationExports.md#contactpersonemail) | string (64) __nullable__ | Email Address of the Contact Person |
| [ContactPersonJobTitle](Regulatory.Saft.DeclarationExports.md#contactpersonjobtitle) | string (127) __nullable__ | Position or Role of the Contact Person |
| [ContactPersonName](Regulatory.Saft.DeclarationExports.md#contactpersonname) | string (127) __nullable__ | Contact Person Name |
| [ContactPersonPhone](Regulatory.Saft.DeclarationExports.md#contactpersonphone) | string (20) __nullable__ | Contact Person Phone Number |
| [CreatedOn](Regulatory.Saft.DeclarationExports.md#createdon) | datetime | Date and time of record creation`Required` `Default(Now)` `Filter(ge;le)` |
| [DefaultCurrencyCode](Regulatory.Saft.DeclarationExports.md#defaultcurrencycode) | string (3) | Primary currency code of the SAF-T file.`Required` |
| [ErrorMessage](Regulatory.Saft.DeclarationExports.md#errormessage) | string (max) __nullable__ | Information about the error that occurred during failed generation. |
| [ExportType](Regulatory.Saft.DeclarationExports.md#exporttype) | [ExportType](Regulatory.Saft.DeclarationExports.md#exporttype) | Export type: monthly(M), annual(Y) or on-demand(D).`Required` `Filter(multi eq)` |
| [FileName](Regulatory.Saft.DeclarationExports.md#filename) | string (254) __nullable__ | Name of generated SAF-T file`Filter(like)` |
| [GeneratedByUserId](Regulatory.Saft.DeclarationExports.md#generatedbyuserid) | guid __nullable__ | User who started generation. `Filter(multi eq)` |
| [GeneratedOn](Regulatory.Saft.DeclarationExports.md#generatedon) | datetime __nullable__ | Date and Time of successful generation of report(data preparation).`Filter(ge;le)` |
| [IsPartOfGroup](Regulatory.Saft.DeclarationExports.md#ispartofgroup) | int32 __nullable__ | Indicates whether the company belongs to a group of enterprises. |
| [ReleasedEndTime](Regulatory.Saft.DeclarationExports.md#releasedendtime) | datetime | The end of the Released Time range used to select data.`Required` `Filter(ge;le)` |
| [ReleasedStartTime](Regulatory.Saft.DeclarationExports.md#releasedstarttime) | datetime | The beginning of the Released Time range used to select data.`Required` `Filter(ge;le)` |
| [SchemaVersion](Regulatory.Saft.DeclarationExports.md#schemaversion) | string (64) | The version of the SAF-T schema used to generate the file.`Required` |
| [SelectionEndDate](Regulatory.Saft.DeclarationExports.md#selectionenddate) | date | End Date of the Export Period`Required` `Filter(eq;ge;le)` |
| [SelectionStartDate](Regulatory.Saft.DeclarationExports.md#selectionstartdate) | date | Start Date of the Export Period`Required` `Filter(eq;ge;le)` |
| [Status](Regulatory.Saft.DeclarationExports.md#status) | [Status](Regulatory.Saft.DeclarationExports.md#status) | Current status: Pending(P), Generating(G), Completed(C), Failed(F), Cancelled(N)`Required` `Filter(multi eq)` |
| [TaxAccountingBasis](Regulatory.Saft.DeclarationExports.md#taxaccountingbasis) | string (20) | Accounting Basis Used in the SAF-T File`Required` `Filter(eq)` |
| [UltimateOwnerCountryCode](Regulatory.Saft.DeclarationExports.md#ultimateownercountrycode) | string (2) __nullable__ | Country Code of the Ultimate Owner |
| [UltimateOwnerName<br />CyrillicBG](Regulatory.Saft.DeclarationExports.md#ultimateownernamecyrillicbg) | string (127) __nullable__ | Name of the Bulgarian Ultimate Owner |
| [UltimateOwnerName<br />CyrillicForeign](Regulatory.Saft.DeclarationExports.md#ultimateownernamecyrillicforeign) | string (127) __nullable__ | Name of the Foreign Ultimate Owner in Cyrillic |
| [UltimateOwnerName<br />LatinForeign](Regulatory.Saft.DeclarationExports.md#ultimateownernamelatinforeign) | string (127) __nullable__ | Name of the Foreign Ultimate Owner in Latin Script |
| [UltimateOwnerUICBG](Regulatory.Saft.DeclarationExports.md#ultimateowneruicbg) | string (16) __nullable__ | UIC of the Bulgarian Ultimate Owner |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [SaftDeclaration](Regulatory.Saft.DeclarationExports.md#saftdeclaration) | [SaftDeclarations](Regulatory.Saft.SaftDeclarations.md) | SAF-T declaration |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.DeclarationExports.md#id) | guid |  |
| [ObjectVersion](Regulatory.Saft.DeclarationExports.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [DisplayText](Regulatory.Saft.DeclarationExports.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### ApplicationVersion

ERP.net Version Used to Generate the Export`Required`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### AuditFileDateCreated

Creation date of odit file (value of AuditFileDateCreated)`Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BeneficialOwnerCountryCode

Country Code of the Beneficial Owner

Type: **string (2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2**  
Show in UI: **ShownByDefault**  

### BeneficialOwnerEGN

Personal Identification Number of the Bulgarian Beneficial Owne

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### BeneficialOwnerNameCyrillicBG

Name of the Bulgarian Beneficial Owner

Type: **string (127) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **127**  
Show in UI: **ShownByDefault**  

### BeneficialOwnerNameLatinForeign

Name of the Foreign Beneficial Owner

Type: **string (127) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **127**  
Show in UI: **ShownByDefault**  

### CompanyCity

City or Other Locality

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### CompanyCountryCode

Country Code

Type: **string (2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2**  
Show in UI: **ShownByDefault**  

### CompanyName

Official Name of the Taxable Person

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### CompanyRegistrationNumber

Company Registration Number or Other Registration Number of the Taxable Person

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### CompanyStreetName

Registered Address of the Taxable Person

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ContactPersonEmail

Email Address of the Contact Person

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### ContactPersonJobTitle

Position or Role of the Contact Person

Type: **string (127) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **127**  
Show in UI: **ShownByDefault**  

### ContactPersonName

Contact Person Name

Type: **string (127) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **127**  
Show in UI: **ShownByDefault**  

### ContactPersonPhone

Contact Person Phone Number

Type: **string (20) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

### CreatedOn

Date and time of record creation`Required` `Default(Now)` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDateTime**  
Show in UI: **ShownByDefault**  

### DefaultCurrencyCode

Primary currency code of the SAF-T file.`Required`

Type: **string (3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **3**  
Show in UI: **ShownByDefault**  

### ErrorMessage

Information about the error that occurred during failed generation.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ExportType

Export type: monthly(M), annual(Y) or on-demand(D).`Required` `Filter(multi eq)`

Type: **[ExportType](Regulatory.Saft.DeclarationExports.md#exporttype)**  
Category: **System**  
Allowed values for the `ExportType`(Regulatory.Saft.DeclarationExports.md#exporttype) data attribute  
Allowed Values (Regulatory.Saft.DeclarationExportsRepository.ExportType Enum Members)  

| Value | Description |
| ---- | --- |
| Monthly | Monthly value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 0 <br /> Domain API Value: 'Monthly' |
| Annual | Annual value. Stored as 'Y'. <br /> Database Value: 'Y' <br /> Model Value: 1 <br /> Domain API Value: 'Annual' |
| OnDemand | OnDemand value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 2 <br /> Domain API Value: 'OnDemand' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FileName

Name of generated SAF-T file`Filter(like)`

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### GeneratedByUserId

User who started generation. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### GeneratedOn

Date and Time of successful generation of report(data preparation).`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsPartOfGroup

Indicates whether the company belongs to a group of enterprises.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReleasedEndTime

The end of the Released Time range used to select data.`Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReleasedStartTime

The beginning of the Released Time range used to select data.`Required` `Filter(ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SchemaVersion

The version of the SAF-T schema used to generate the file.`Required`

Type: **string (64)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### SelectionEndDate

End Date of the Export Period`Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SelectionStartDate

Start Date of the Export Period`Required` `Filter(eq;ge;le)`

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Status

Current status: Pending(P), Generating(G), Completed(C), Failed(F), Cancelled(N)`Required` `Filter(multi eq)`

Type: **[Status](Regulatory.Saft.DeclarationExports.md#status)**  
Category: **System**  
Allowed values for the `Status`(Regulatory.Saft.DeclarationExports.md#status) data attribute  
Allowed Values (Regulatory.Saft.DeclarationExportsRepository.Status Enum Members)  

| Value | Description |
| ---- | --- |
| Pending | Pending value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 0 <br /> Domain API Value: 'Pending' |
| Generating | Generating value. Stored as 'G'. <br /> Database Value: 'G' <br /> Model Value: 1 <br /> Domain API Value: 'Generating' |
| Completed | Completed value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 2 <br /> Domain API Value: 'Completed' |
| Failed | Failed value. Stored as 'F'. <br /> Database Value: 'F' <br /> Model Value: 3 <br /> Domain API Value: 'Failed' |
| Cancelled | Cancelled value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 4 <br /> Domain API Value: 'Cancelled' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TaxAccountingBasis

Accounting Basis Used in the SAF-T File`Required` `Filter(eq)`

Type: **string (20)**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

### UltimateOwnerCountryCode

Country Code of the Ultimate Owner

Type: **string (2) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2**  
Show in UI: **ShownByDefault**  

### UltimateOwnerNameCyrillicBG

Name of the Bulgarian Ultimate Owner

Type: **string (127) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **127**  
Show in UI: **ShownByDefault**  

### UltimateOwnerNameCyrillicForeign

Name of the Foreign Ultimate Owner in Cyrillic

Type: **string (127) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **127**  
Show in UI: **ShownByDefault**  

### UltimateOwnerNameLatinForeign

Name of the Foreign Ultimate Owner in Latin Script

Type: **string (127) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **127**  
Show in UI: **ShownByDefault**  

### UltimateOwnerUICBG

UIC of the Bulgarian Ultimate Owner

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

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

### SaftDeclaration

SAF-T declaration

Type: **[SaftDeclarations](Regulatory.Saft.SaftDeclarations.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.DeclarationExports erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.DeclarationExports erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_DeclarationExports

Domain API Entity Type: 
Regulatory_Saft_DeclarationExport

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_DeclarationExports?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_DeclarationExports?$top=10>

