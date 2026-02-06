---
uid: General.EnterpriseCompanies
---
# General.EnterpriseCompanies


The companies in the enterprise that issue documents

## General
Namespace: [General](General.md)  
Repository: General.EnterpriseCompanies  
Base Table: Gen_Enterprise_Companies  
API access:  ReadWrite  

## Visualization
Display Format: {Company.PartyName:T}  
Search Members: Company.RegistrationNumber; Company.PartyName  
Code Member: Company.RegistrationNumber  
Name Member: Company.PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  3 - Track object and attribute changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.EnterpriseCompanies](General.EnterpriseCompanies.md)  
  * [Applications.Fleet.Crews](Applications.Fleet.Crews.md)  
    * [Applications.Fleet.CrewMembers](Applications.Fleet.CrewMembers.md)  
  * [Applications.Fleet.VehicleSets](Applications.Fleet.VehicleSets.md)  
    * [Applications.Fleet.VehicleSetVehicles](Applications.Fleet.VehicleSetVehicles.md)  
  * [General.Geography.MapPoints](General.Geography.MapPoints.md)  
  * [Finance.Vat.BGVATDeclaringPersons](Finance.Vat.BGVATDeclaringPersons.md)  
  * [Projects.Classic.Resources](Projects.Classic.Resources.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BIStartDate](General.EnterpriseCompanies.md#bistartdate) | datetime __nullable__ | Defines the period for which BI extracts data. BI includes documents with "Document Date" greater than or equal to "BI Start Date". 
| [DefaultCostingMethod](General.EnterpriseCompanies.md#defaultcostingmethod) | [DefaultCostingMethod](General.EnterpriseCompanies.md#defaultcostingmethod) | Default method for cost evaluation (if not specified in the product). Currently supported: EXP - Explicit lot specifying; AVG - Average cost 
| [DefaultCustomer<br />CreditLimitBase](General.EnterpriseCompanies.md#defaultcustomercreditlimitbase) | [Amount (18, 2)](../data-types.md#amount) __nullable__ | Customer credit limit, which is used by default when creating new customers. It is specified in the base currency of the enterprise company. 
| [DefaultLanguage](General.EnterpriseCompanies.md#defaultlanguage) | [DefaultLanguage](General.EnterpriseCompanies.md#defaultlanguage) __nullable__ | The default language for multi-language names in the definitions (like Customer_Name, Product_Name, ...). 
| [EditPeriodStartDate](General.EnterpriseCompanies.md#editperiodstartdate) | datetime __nullable__ | Start date of the priod when the documents can be edited 
| [EndDateOfClosed<br />AccountingPeriod](General.EnterpriseCompanies.md#enddateofclosedaccountingperiod) | date __nullable__ | Indicates the date before which all accounting vouchers are permanently closed. 
| [IsActive](General.EnterpriseCompanies.md#isactive) | boolean | Indicates whether the current Enterprise company  is active. 
| [PrintImagesRetentionMonths](General.EnterpriseCompanies.md#printimagesretentionmonths) | int32 | A period of months for which the printed images of the documents will be kept. 
| [ReportingCurrencyEndDate](General.EnterpriseCompanies.md#reportingcurrencyenddate) | date __nullable__ | Defines the cutoff date up to which the equivalent amount in the reporting currency is calculated. 
| [ReportingCurrency<br />ProcessedDate](General.EnterpriseCompanies.md#reportingcurrencyprocesseddate) | date __nullable__ | Shows the last document date for which reporting currency values were calculated by the system job 'Calculate Historical Reporting Currency Amounts'. The next execution of the job will start from the day after this date. 
| [ReportingCurrencyRate](General.EnterpriseCompanies.md#reportingcurrencyrate) | decimal (18, 6) __nullable__ | Exchange rate used to convert values from the base currency to the reporting currency. The amount in base currency is multiplied by this rate to get the reporting currency amount. This rate is used only for historical data (before the Reporting Currency Start Date). 
| [ReportingCurrencyStartDate](General.EnterpriseCompanies.md#reportingcurrencystartdate) | date __nullable__ | Defines the date from which the reporting currency is calculated using the exchange rate entered in each document. Before this date, reporting values are derived using a default rate due to missing historical exchange data. 
| [UIBaseColor](General.EnterpriseCompanies.md#uibasecolor) | int32 __nullable__ | Base color of the current theme 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](General.EnterpriseCompanies.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this EnterpriseCompany. An empty value means that all users have unlimited permissions. `Filter(multi eq)` |
| [AdvanceProduct](General.EnterpriseCompanies.md#advanceproduct) | [Products](General.Products.Products.md) (nullable) | Product that is used for handling advances in trade documents. |
| [BaseCurrency](General.EnterpriseCompanies.md#basecurrency) | [Currencies](General.Currencies.Currencies.md) | The base currency for summary reporting for this company. |
| [Company](General.EnterpriseCompanies.md#company) | [Companies](General.Contacts.Companies.md) | Contains the base company data on which this enterprise company is based. |
| [ExchangeDifference<br />CreditAccount](General.EnterpriseCompanies.md#exchangedifferencecreditaccount) | [Accounts](Finance.Accounting.Accounts.md) (nullable) | Account for balancing accounting vouchers with credit difference due to currency exchanges |
| [ExchangeDifference<br />DebitAccount](General.EnterpriseCompanies.md#exchangedifferencedebitaccount) | [Accounts](Finance.Accounting.Accounts.md) (nullable) | Account for balancing accounting vouchers with debit difference due to currency exchanges |
| [ReportingCurrency](General.EnterpriseCompanies.md#reportingcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Used for preparing accounting reports in a currency required for internal or external reporting purposes. |
| [VATDocumentAmountType](General.EnterpriseCompanies.md#vatdocumentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | The document amount that is used to determine the amount of the VAT entries when they are generated. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.EnterpriseCompanies.md#id) | guid |  
| [ObjectVersion](General.EnterpriseCompanies.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.EnterpriseCompanies.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.EnterpriseCompanies.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.EnterpriseCompanies.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.EnterpriseCompanies.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| BGVATDeclaringPersons | [BGVATDeclaringPersons](Finance.Vat.BGVATDeclaringPersons.md) | List of `BGVATDeclaringPerson`(Finance.Vat.BGVATDeclaringPersons.md) child objects, based on the `Finance.Vat.BGVATDeclaringPerson.EnterpriseCompany`(Finance.Vat.BGVATDeclaringPersons.md#enterprisecompany) back reference 
| Crews | [Crews](Applications.Fleet.Crews.md) | List of `Crew`(Applications.Fleet.Crews.md) child objects, based on the `Applications.Fleet.Crew.EnterpriseCompany`(Applications.Fleet.Crews.md#enterprisecompany) back reference 
| MapPoints | [MapPoints](General.Geography.MapPoints.md) | List of `MapPoint`(General.Geography.MapPoints.md) child objects, based on the `General.Geography.MapPoint.EnterpriseCompany`(General.Geography.MapPoints.md#enterprisecompany) back reference 
| Resources | [Resources](Projects.Classic.Resources.md) | List of `Resource`(Projects.Classic.Resources.md) child objects, based on the `Projects.Classic.Resource.EnterpriseCompany`(Projects.Classic.Resources.md#enterprisecompany) back reference 
| VehicleSets | [VehicleSets](Applications.Fleet.VehicleSets.md) | List of `VehicleSet`(Applications.Fleet.VehicleSets.md) child objects, based on the `Applications.Fleet.VehicleSet.EnterpriseCompany`(Applications.Fleet.VehicleSets.md#enterprisecompany) back reference 


## Attribute Details

### BIStartDate

Defines the period for which BI extracts data. BI includes documents with "Document Date" greater than or equal to "BI Start Date".

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DefaultCostingMethod

Default method for cost evaluation (if not specified in the product). Currently supported: EXP - Explicit lot specifying; AVG - Average cost

Type: **[DefaultCostingMethod](General.EnterpriseCompanies.md#defaultcostingmethod)**  
Category: **System**  
Allowed values for the `DefaultCostingMethod`(General.EnterpriseCompanies.md#defaultcostingmethod) data attribute  
Allowed Values (General.EnterpriseCompaniesRepository.DefaultCostingMethod Enum Members)  

| Value | Description |
| ---- | --- |
| AverageCost | AverageCost value. Stored as 'AVG'. <br /> Database Value: 'AVG' <br /> Model Value: 0 <br /> Domain API Value: 'AverageCost' |
| ExplicitlySpecifyLot | ExplicitlySpecifyLot value. Stored as 'EXP'. <br /> Database Value: 'EXP' <br /> Model Value: 1 <br /> Domain API Value: 'ExplicitlySpecifyLot' |
| SetByBlockedForDocument | SetByBlockedForDocument value. Stored as 'BLD'. <br /> Database Value: 'BLD' <br /> Model Value: 2 <br /> Domain API Value: 'SetByBlockedForDocument' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **AverageCost**  
Show in UI: **ShownByDefault**  

### DefaultCustomerCreditLimitBase

Customer credit limit, which is used by default when creating new customers. It is specified in the base currency of the enterprise company.

Type: **[Amount (18, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DefaultLanguage

The default language for multi-language names in the definitions (like Customer_Name, Product_Name, ...).

Type: **[DefaultLanguage](General.EnterpriseCompanies.md#defaultlanguage) __nullable__**  
Category: **System**  
Allowed values for the `DefaultLanguage`(General.EnterpriseCompanies.md#defaultlanguage) data attribute  
Allowed Values (General.EnterpriseCompaniesRepository.DefaultLanguage Enum Members)  

| Value | Description |
| ---- | --- |
| Bulgarian | Bulgarian value. Stored as 'bg'. <br /> Database Value: 'bg' <br /> Model Value: 0 <br /> Domain API Value: 'Bulgarian' |
| English | English value. Stored as 'en'. <br /> Database Value: 'en' <br /> Model Value: 1 <br /> Domain API Value: 'English' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **English**  
Show in UI: **CannotBeShown**  

### EditPeriodStartDate

Start date of the priod when the documents can be edited

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EndDateOfClosedAccountingPeriod

Indicates the date before which all accounting vouchers are permanently closed.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsActive

Indicates whether the current Enterprise company  is active.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### PrintImagesRetentionMonths

A period of months for which the printed images of the documents will be kept.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Default Value: **60**  
Show in UI: **ShownByDefault**  

### ReportingCurrencyEndDate

Defines the cutoff date up to which the equivalent amount in the reporting currency is calculated.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReportingCurrencyProcessedDate

Shows the last document date for which reporting currency values were calculated by the system job 'Calculate Historical Reporting Currency Amounts'. The next execution of the job will start from the day after this date.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReportingCurrencyRate

Exchange rate used to convert values from the base currency to the reporting currency. The amount in base currency is multiplied by this rate to get the reporting currency amount. This rate is used only for historical data (before the Reporting Currency Start Date).

Type: **decimal (18, 6) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ReportingCurrencyStartDate

Defines the date from which the reporting currency is calculated using the exchange rate entered in each document. Before this date, reporting values are derived using a default rate due to missing historical exchange data.

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### UIBaseColor

Base color of the current theme

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
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

### AccessKey

The access key, containing the permissions for this EnterpriseCompany. An empty value means that all users have unlimited permissions. `Filter(multi eq)`

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
### AdvanceProduct

Product that is used for handling advances in trade documents.

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### BaseCurrency

The base currency for summary reporting for this company.

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Company

Contains the base company data on which this enterprise company is based.

Type: **[Companies](General.Contacts.Companies.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ExchangeDifferenceCreditAccount

Account for balancing accounting vouchers with credit difference due to currency exchanges

Type: **[Accounts](Finance.Accounting.Accounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExchangeDifferenceDebitAccount

Account for balancing accounting vouchers with debit difference due to currency exchanges

Type: **[Accounts](Finance.Accounting.Accounts.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ReportingCurrency

Used for preparing accounting reports in a currency required for internal or external reporting purposes.

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### VATDocumentAmountType

The document amount that is used to determine the amount of the VAT entries when they are generated.

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
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

[!list limit=1000 erp.entity=General.EnterpriseCompanies erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.EnterpriseCompanies erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_EnterpriseCompanies

Domain API Entity Type: 
General_EnterpriseCompany

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_EnterpriseCompanies?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_EnterpriseCompanies?$top=10>

