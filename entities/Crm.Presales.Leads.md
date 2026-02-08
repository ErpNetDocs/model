---
uid: Crm.Presales.Leads
---
# Crm.Presales.Leads


Leads are potential customers for your products. Because leads are usually processed in a hurry or imported from external lists, personal and company information is saved in a less structured way. With the advancement of the qualification process (including deduplication), the information is structured in the usual Person and Company entities. When successfully processed, leads can be converted to Opportunities.

## General
Namespace: [Crm.Presales](Crm.Presales.md)  
Repository: Crm.Presales.Leads  
Base Table: Crm_Leads  
Introduced In Version: 21.1.3.78  
API access:  ReadWrite  

## Visualization
Display Format: {PersonFirstName} {PersonLastName}  
Search Members: CompanyName  
Name Member: CompanyName  
Category:  Documents  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Presales.Leads](Crm.Presales.Leads.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompanyName](Crm.Presales.Leads.md#companyname) | string (64) __nullable__ | The name of the company, which the person works for (in relation to the current lead).`Filter(eq;like)` 
| [CreationTimestampUtc](Crm.Presales.Leads.md#creationtimestamputc) | datetime | System assigned date and time (in UTC), when the lead was initially created.`Required` `Filter(ge;le)` `ReadOnly` 
| [MQLTimestampUtc](Crm.Presales.Leads.md#mqltimestamputc) | datetime __nullable__ | System assigned date and time (in UTC), when the lead was first promoted to Marketing Qualified Lead (MQL).`Filter(ge;le)` `ReadOnly` 
| [Notes](Crm.Presales.Leads.md#notes) | string (max) __nullable__ | Additional information or comments.`Filter(like)` `Introduced in version 25.1.2.6` 
| [PersonEmail](Crm.Presales.Leads.md#personemail) | string (64) __nullable__ | The email address of the sales lead person.`Filter(eq;like)` 
| [PersonFirstName](Crm.Presales.Leads.md#personfirstname) | string (64) __nullable__ | The first name of the person, representing the sales lead.`Filter(eq;like)` 
| [PersonLastName](Crm.Presales.Leads.md#personlastname) | string (64) __nullable__ | The last name of the person, representing the sales lead.`Filter(eq;like)` 
| [PersonMobilePhone](Crm.Presales.Leads.md#personmobilephone) | string (32) __nullable__ | The mobile phone of the sales lead person.`Filter(like)` 
| [PersonSalutation](Crm.Presales.Leads.md#personsalutation) | string (16) __nullable__ | Salutation for the sales lead person.`Filter(eq;like)` 
| [PersonWebProfile](Crm.Presales.Leads.md#personwebprofile) | string (64) __nullable__ | Web address (including protocol like https) of the personal profile in a social or professional network. The address itself, as it is full valid Internet address, contains also the network name.`Filter(like)` 
| [PersonWorkPhone](Crm.Presales.Leads.md#personworkphone) | string (32) __nullable__ | The work phone of the sales lead person.`Filter(like)` 
| [RoleInCompany](Crm.Presales.Leads.md#roleincompany) | string (32) __nullable__ | The role of the person in the company.`Filter(eq;like)` 
| [SQLTimestampUtc](Crm.Presales.Leads.md#sqltimestamputc) | datetime __nullable__ | System assigned date and time (in UTC), when the lead was first promoted to Sales Qualified Lead.`Filter(ge;le)` `ReadOnly` 
| [SystemStage](Crm.Presales.Leads.md#systemstage) | [SystemStage](Crm.Presales.Leads.md#systemstage) | The system stage of the lead - New, Qualifying, Marketing Qualified Lead, Sales Qualified Lead, Closed. (NEW, QUA, MQL, SQL, CLO)`Required` `Default(&quot;NEW&quot;)` `Filter(multi eq)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToSalesPerson](Crm.Presales.Leads.md#assignedtosalesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable) | Sales rep to whom this lead is assigned for further processing. NULL - not yet assigned. |
| [Campaign](Crm.Presales.Leads.md#campaign) | [Campaigns](Crm.Marketing.Campaigns.md) | The marketing campaign under which the lead was generated. |
| [ConvertedToDeal](Crm.Presales.Leads.md#convertedtodeal) | [Deals](Crm.Presales.Deals.md) (nullable) | Filled when the lead is converted to opportunity (deal). |
| [EnterpriseCompany](Crm.Presales.Leads.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company to which this lead belongs. |
| [EnterpriseCompanyLocation](Crm.Presales.Leads.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The enterprise company location to which this lead belongs. |
| [IdentifiedCompany](Crm.Presales.Leads.md#identifiedcompany) | [Companies](General.Contacts.Companies.md) (nullable) | Filled when the company is identified within our database. |
| [IdentifiedPerson](Crm.Presales.Leads.md#identifiedperson) | [Persons](General.Contacts.Persons.md) (nullable) | Filled when the person is identified and recorded in our master records. |
| [LeadUserStage](Crm.Presales.Leads.md#leaduserstage) | [LeadUserStages](Crm.Presales.LeadUserStages.md) (nullable) | The user-defined sub-stage of the lead. This also defines the step in the sales sequence and the next appropriate activity to engage the lead. NULL when the user stage is undefined (the pure System Stage defines the stage). |
| [MarketingCompanySize](Crm.Presales.Leads.md#marketingcompanysize) | [CompanySizeClasses](Crm.Marketing.CompanySizeClasses.md) (nullable) | The size class of the company. |
| [MarketingIndustry](Crm.Presales.Leads.md#marketingindustry) | [Industries](Crm.Marketing.Industries.md) (nullable) | The industry (for marketing purposes) of the lead. |
| [MarketingSolution](Crm.Presales.Leads.md#marketingsolution) | [MarketingSolutions](Crm.Marketing.MarketingSolutions.md) (nullable) | The marketing solution, in which the lead is interested or which generated the lead. |
| [OwnerUser](Crm.Presales.Leads.md#owneruser) | [Users](Systems.Security.Users.md) | The user, responsible for this record. |
| [SalesArea](Crm.Presales.Leads.md#salesarea) | [Areas](General.Geography.Areas.md) (nullable) | The sales area, where the lead is located, when it is identified. This should also indicate the Time Zone. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Presales.Leads.md#id) | guid |  
| [ObjectVersion](Crm.Presales.Leads.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Presales.Leads.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Presales.Leads.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Presales.Leads.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Presales.Leads.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### CompanyName

The name of the company, which the person works for (in relation to the current lead).`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### CreationTimestampUtc

System assigned date and time (in UTC), when the lead was initially created.`Required` `Filter(ge;le)` `ReadOnly`

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`IIF( ( obj.MQLTimestampUtc == null), Convert( DateTime.UtcNow, Nullable`1), obj.MQLTimestampUtc)`

### MQLTimestampUtc

System assigned date and time (in UTC), when the lead was first promoted to Marketing Qualified Lead (MQL).`Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Additional information or comments.`Filter(like)` `Introduced in version 25.1.2.6`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PersonEmail

The email address of the sales lead person.`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### PersonFirstName

The first name of the person, representing the sales lead.`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### PersonLastName

The last name of the person, representing the sales lead.`Filter(eq;like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### PersonMobilePhone

The mobile phone of the sales lead person.`Filter(like)`

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### PersonSalutation

Salutation for the sales lead person.`Filter(eq;like)`

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### PersonWebProfile

Web address (including protocol like https) of the personal profile in a social or professional network. The address itself, as it is full valid Internet address, contains also the network name.`Filter(like)`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### PersonWorkPhone

The work phone of the sales lead person.`Filter(like)`

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### RoleInCompany

The role of the person in the company.`Filter(eq;like)`

Type: **string (32) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### SQLTimestampUtc

System assigned date and time (in UTC), when the lead was first promoted to Sales Qualified Lead.`Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SystemStage

The system stage of the lead - New, Qualifying, Marketing Qualified Lead, Sales Qualified Lead, Closed. (NEW, QUA, MQL, SQL, CLO)`Required` `Default(&quot;NEW&quot;)` `Filter(multi eq)` `ReadOnly`

Type: **[SystemStage](Crm.Presales.Leads.md#systemstage)**  
Category: **System**  
Allowed values for the `SystemStage`(Crm.Presales.Leads.md#systemstage) data attribute  
Allowed Values (Crm.Presales.LeadsRepository.SystemStage Enum Members)  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'NEW'. <br /> Database Value: 'NEW' <br /> Model Value: 0 <br /> Domain API Value: 'New' |
| Qualifying | Qualifying value. Stored as 'QUA'. <br /> Database Value: 'QUA' <br /> Model Value: 1 <br /> Domain API Value: 'Qualifying' |
| MarketingQualifiedLead | MarketingQualifiedLead value. Stored as 'MQL'. <br /> Database Value: 'MQL' <br /> Model Value: 2 <br /> Domain API Value: 'MarketingQualifiedLead' |
| SalesQualifiedLead | SalesQualifiedLead value. Stored as 'SQL'. <br /> Database Value: 'SQL' <br /> Model Value: 3 <br /> Domain API Value: 'SalesQualifiedLead' |
| Closed | Closed value. Stored as 'CLO'. <br /> Database Value: 'CLO' <br /> Model Value: 4 <br /> Domain API Value: 'Closed' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **New**  
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

### AssignedToSalesPerson

Sales rep to whom this lead is assigned for further processing. NULL - not yet assigned.

Type: **[SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Campaign

The marketing campaign under which the lead was generated.

Type: **[Campaigns](Crm.Marketing.Campaigns.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ConvertedToDeal

Filled when the lead is converted to opportunity (deal).

Type: **[Deals](Crm.Presales.Deals.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

The enterprise company to which this lead belongs.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompanyLocation

The enterprise company location to which this lead belongs.

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IdentifiedCompany

Filled when the company is identified within our database.

Type: **[Companies](General.Contacts.Companies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IdentifiedPerson

Filled when the person is identified and recorded in our master records.

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LeadUserStage

The user-defined sub-stage of the lead. This also defines the step in the sales sequence and the next appropriate activity to engage the lead. NULL when the user stage is undefined (the pure System Stage defines the stage).

Type: **[LeadUserStages](Crm.Presales.LeadUserStages.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MarketingCompanySize

The size class of the company.

Type: **[CompanySizeClasses](Crm.Marketing.CompanySizeClasses.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MarketingIndustry

The industry (for marketing purposes) of the lead.

Type: **[Industries](Crm.Marketing.Industries.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### MarketingSolution

The marketing solution, in which the lead is interested or which generated the lead.

Type: **[MarketingSolutions](Crm.Marketing.MarketingSolutions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### OwnerUser

The user, responsible for this record.

Type: **[Users](Systems.Security.Users.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SalesArea

The sales area, where the lead is located, when it is identified. This should also indicate the Time Zone.

Type: **[Areas](General.Geography.Areas.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Presales.Leads erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Presales.Leads erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Presales_Leads

Domain API Entity Type: 
Crm_Presales_Lead

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Presales_Leads?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Presales_Leads?$top=10>

