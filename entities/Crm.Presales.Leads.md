---
uid: Crm.Presales.Leads
---
# Crm.Presales.Leads Entity

**Namespace:** [Crm.Presales](Crm.Presales.md)  

Leads are potential customers for your products. Because leads are usually processed in a hurry or imported from external lists, personal and company information is saved in a less structured way. With the advancement of the qualification process (including deduplication), the information is structured in the usual Person and Company entities. When successfully processed, leads can be converted to Opportunities. Entity: Crm_Leads (Introduced in version 21.1.3.78)

## Default Visualization
Default Display Text Format:  
_{PersonFirstName} {PersonLastName}_  
Default Search Members:  
_CompanyName_  
Name Data Member:  
_CompanyName_  
Category:  _Documents_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Presales.Leads](Crm.Presales.Leads.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompanyName](Crm.Presales.Leads.md#companyname) | string (64) __nullable__ | The name of the company, which the person works for (in relation to the current lead). `Filter(eq;like)` 
| [CreationTimestampUtc](Crm.Presales.Leads.md#creationtimestamputc) | datetime | System assigned date and time (in UTC), when the lead was initially created. `Required` `Filter(ge;le)` `ReadOnly` 
| [DisplayText](Crm.Presales.Leads.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Crm.Presales.Leads.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Presales.Leads.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Crm.Presales.Leads.md#id) | guid |  
| [MQLTimestampUtc](Crm.Presales.Leads.md#mqltimestamputc) | datetime __nullable__ | System assigned date and time (in UTC), when the lead was first promoted to Marketing Qualified Lead (MQL). `Filter(ge;le)` `ReadOnly` 
| [Notes](Crm.Presales.Leads.md#notes) | string (max) __nullable__ | Additional information or comments. `Filter(like)` `Introduced in version 25.1.2.6` 
| [ObjectVersion](Crm.Presales.Leads.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PersonEmail](Crm.Presales.Leads.md#personemail) | string (64) __nullable__ | The email address of the sales lead person. `Filter(eq;like)` 
| [PersonFirstName](Crm.Presales.Leads.md#personfirstname) | string (64) __nullable__ | The first name of the person, representing the sales lead. `Filter(eq;like)` 
| [PersonLastName](Crm.Presales.Leads.md#personlastname) | string (64) __nullable__ | The last name of the person, representing the sales lead. `Filter(eq;like)` 
| [PersonMobilePhone](Crm.Presales.Leads.md#personmobilephone) | string (32) __nullable__ | The mobile phone of the sales lead person. `Filter(like)` 
| [PersonSalutation](Crm.Presales.Leads.md#personsalutation) | string (16) __nullable__ | Salutation for the sales lead person. `Filter(eq;like)` 
| [PersonWebProfile](Crm.Presales.Leads.md#personwebprofile) | string (64) __nullable__ | Web address (including protocol like https) of the personal profile in a social or professional network. The address itself, as it is full valid Internet address, contains also the network name. `Filter(like)` 
| [PersonWorkPhone](Crm.Presales.Leads.md#personworkphone) | string (32) __nullable__ | The work phone of the sales lead person. `Filter(like)` 
| [RoleInCompany](Crm.Presales.Leads.md#roleincompany) | string (32) __nullable__ | The role of the person in the company. `Filter(eq;like)` 
| [SQLTimestampUtc](Crm.Presales.Leads.md#sqltimestamputc) | datetime __nullable__ | System assigned date and time (in UTC), when the lead was first promoted to Sales Qualified Lead. `Filter(ge;le)` `ReadOnly` 
| [SystemStage](Crm.Presales.Leads.md#systemstage) | [SystemStage](Crm.Presales.Leads.md#systemstage) | The system stage of the lead - New, Qualifying, Marketing Qualified Lead, Sales Qualified Lead, Closed. (NEW, QUA, MQL, SQL, CLO). `Required` `Default("NEW")` `Filter(multi eq)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssignedToSalesPerson](Crm.Presales.Leads.md#assignedtosalesperson) | [SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable) | Sales rep to whom this lead is assigned for further processing. null - not yet assigned. `Filter(multi eq)` |
| [Campaign](Crm.Presales.Leads.md#campaign) | [Campaigns](Crm.Marketing.Campaigns.md) | The marketing campaign under which the lead was generated. `Required` `Filter(multi eq)` |
| [ConvertedToDeal](Crm.Presales.Leads.md#convertedtodeal) | [Deals](Crm.Presales.Deals.md) (nullable) | Filled when the lead is converted to opportunity (deal). `Filter(multi eq)` |
| [EnterpriseCompany](Crm.Presales.Leads.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The enterprise company to which this lead belongs. `Required` `Filter(multi eq)` `Introduced in version 22.1.5.23` |
| [EnterpriseCompanyLocation](Crm.Presales.Leads.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The enterprise company location to which this lead belongs. `Filter(multi eq)` `Introduced in version 22.1.6.41` |
| [IdentifiedCompany](Crm.Presales.Leads.md#identifiedcompany) | [Companies](General.Contacts.Companies.md) (nullable) | Filled when the company is identified within our database. `Filter(multi eq)` |
| [IdentifiedPerson](Crm.Presales.Leads.md#identifiedperson) | [Persons](General.Contacts.Persons.md) (nullable) | Filled when the person is identified and recorded in our master records. `Filter(multi eq)` |
| [LeadUserStage](Crm.Presales.Leads.md#leaduserstage) | [LeadUserStages](Crm.Presales.LeadUserStages.md) (nullable) | The user-defined sub-stage of the lead. This also defines the step in the sales sequence and the next appropriate activity to engage the lead. null when the user stage is undefined (the pure System Stage defines the stage). `Filter(multi eq)` `ReadOnly` |
| [MarketingCompanySize](Crm.Presales.Leads.md#marketingcompanysize) | [CompanySizeClasses](Crm.Marketing.CompanySizeClasses.md) (nullable) | The size class of the company. `Filter(multi eq)` |
| [MarketingIndustry](Crm.Presales.Leads.md#marketingindustry) | [Industries](Crm.Marketing.Industries.md) (nullable) | The industry (for marketing purposes) of the lead. `Filter(multi eq)` |
| [MarketingSolution](Crm.Presales.Leads.md#marketingsolution) | [MarketingSolutions](Crm.Marketing.MarketingSolutions.md) (nullable) | The marketing solution, in which the lead is interested or which generated the lead. `Filter(multi eq)` |
| [OwnerUser](Crm.Presales.Leads.md#owneruser) | [Users](Systems.Security.Users.md) | The user, responsible for this record. `Required` `Filter(multi eq)` |
| [SalesArea](Crm.Presales.Leads.md#salesarea) | [Areas](General.Geography.Areas.md) (nullable) | The sales area, where the lead is located, when it is identified. This should also indicate the Time Zone. `Filter(multi eq)` |


## Attribute Details

### CompanyName

The name of the company, which the person works for (in relation to the current lead). `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### CreationTimestampUtc

System assigned date and time (in UTC), when the lead was initially created. `Required` `Filter(ge;le)` `ReadOnly`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`IIF( ( obj.MQLTimestampUtc == null), Convert( DateTime.UtcNow, Nullable`1), obj.MQLTimestampUtc)`

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

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### MQLTimestampUtc

System assigned date and time (in UTC), when the lead was first promoted to Marketing Qualified Lead (MQL). `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Additional information or comments. `Filter(like)` `Introduced in version 25.1.2.6`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
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

### PersonEmail

The email address of the sales lead person. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### PersonFirstName

The first name of the person, representing the sales lead. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### PersonLastName

The last name of the person, representing the sales lead. `Filter(eq;like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### PersonMobilePhone

The mobile phone of the sales lead person. `Filter(like)`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### PersonSalutation

Salutation for the sales lead person. `Filter(eq;like)`

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

### PersonWebProfile

Web address (including protocol like https) of the personal profile in a social or professional network. The address itself, as it is full valid Internet address, contains also the network name. `Filter(like)`

_Type_: **string (64) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### PersonWorkPhone

The work phone of the sales lead person. `Filter(like)`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### RoleInCompany

The role of the person in the company. `Filter(eq;like)`

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### SQLTimestampUtc

System assigned date and time (in UTC), when the lead was first promoted to Sales Qualified Lead. `Filter(ge;le)` `ReadOnly`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SystemStage

The system stage of the lead - New, Qualifying, Marketing Qualified Lead, Sales Qualified Lead, Closed. (NEW, QUA, MQL, SQL, CLO). `Required` `Default("NEW")` `Filter(multi eq)` `ReadOnly`

_Type_: **[SystemStage](Crm.Presales.Leads.md#systemstage)**  
_Category_: **System**  
Allowed values for the `SystemStage`(Crm.Presales.Leads.md#systemstage) data attribute  
_Allowed Values (Crm.Presales.LeadsRepository.SystemStage Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'NEW'. <br /> _Database Value:_ 'NEW' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Qualifying | Qualifying value. Stored as 'QUA'. <br /> _Database Value:_ 'QUA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Qualifying' |
| MarketingQualifiedLead | MarketingQualifiedLead value. Stored as 'MQL'. <br /> _Database Value:_ 'MQL' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'MarketingQualifiedLead' |
| SalesQualifiedLead | SalesQualifiedLead value. Stored as 'SQL'. <br /> _Database Value:_ 'SQL' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'SalesQualifiedLead' |
| Closed | Closed value. Stored as 'CLO'. <br /> _Database Value:_ 'CLO' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Default Value_: **New**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AssignedToSalesPerson

Sales rep to whom this lead is assigned for further processing. null - not yet assigned. `Filter(multi eq)`

_Type_: **[SalesPersons](Crm.SalesForce.SalesPersons.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Campaign

The marketing campaign under which the lead was generated. `Required` `Filter(multi eq)`

_Type_: **[Campaigns](Crm.Marketing.Campaigns.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ConvertedToDeal

Filled when the lead is converted to opportunity (deal). `Filter(multi eq)`

_Type_: **[Deals](Crm.Presales.Deals.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The enterprise company to which this lead belongs. `Required` `Filter(multi eq)` `Introduced in version 22.1.5.23`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompanyLocation

The enterprise company location to which this lead belongs. `Filter(multi eq)` `Introduced in version 22.1.6.41`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### IdentifiedCompany

Filled when the company is identified within our database. `Filter(multi eq)`

_Type_: **[Companies](General.Contacts.Companies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### IdentifiedPerson

Filled when the person is identified and recorded in our master records. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LeadUserStage

The user-defined sub-stage of the lead. This also defines the step in the sales sequence and the next appropriate activity to engage the lead. null when the user stage is undefined (the pure System Stage defines the stage). `Filter(multi eq)` `ReadOnly`

_Type_: **[LeadUserStages](Crm.Presales.LeadUserStages.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MarketingCompanySize

The size class of the company. `Filter(multi eq)`

_Type_: **[CompanySizeClasses](Crm.Marketing.CompanySizeClasses.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MarketingIndustry

The industry (for marketing purposes) of the lead. `Filter(multi eq)`

_Type_: **[Industries](Crm.Marketing.Industries.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MarketingSolution

The marketing solution, in which the lead is interested or which generated the lead. `Filter(multi eq)`

_Type_: **[MarketingSolutions](Crm.Marketing.MarketingSolutions.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OwnerUser

The user, responsible for this record. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SalesArea

The sales area, where the lead is located, when it is identified. This should also indicate the Time Zone. `Filter(multi eq)`

_Type_: **[Areas](General.Geography.Areas.md) (nullable)**  
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

