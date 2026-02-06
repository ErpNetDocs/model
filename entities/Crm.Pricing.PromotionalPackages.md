---
uid: Crm.Pricing.PromotionalPackages
---
# Crm.Pricing.PromotionalPackages


Promotional packages are packages of products, which are sold together at a special pricing and discount conditions.

## General
Namespace: [Crm.Pricing](Crm.Pricing.md)  
Repository: Crm.Pricing.PromotionalPackages  
Base Table: Crm_Promotional_Packages  
API access:  ReadWrite  

## Renames

Old name: Crm.PromotionalPackages  
New name: Crm.Pricing.PromotionalPackages  
Version: 25.1.1.36  
Case: 37717  



## Visualization
Display Format: {Name}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Crm.Pricing.PromotionalPackages](Crm.Pricing.PromotionalPackages.md)  
  * [Crm.Pricing.PromotionalPackageLines](Crm.Pricing.PromotionalPackageLines.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Active](Crm.Pricing.PromotionalPackages.md#active) | boolean | Package status: 1 = the offer is available for new documents; 0 = otherwise[Required] [Default(true)] [Filter(eq)] 
| [Code](Crm.Pricing.PromotionalPackages.md#code) | string (20) | Unique code of the promotional package[Required] [Filter(eq;like)] [ORD] 
| [Name](Crm.Pricing.PromotionalPackages.md#name) | string (254) | The name of this PromotionalPackage. `Required` `Filter(eq;like)` `ORD` 
| [ValidForCustomerFilterXML](Crm.Pricing.PromotionalPackages.md#validforcustomerfilterxml) | dataaccessfilter __nullable__ | Customer filter for clients. The package is valid only for the customers, that match the filter[Unit: Crm.Sales.CustomersRepository.TableName] 
| [ValidForDistribution<br />ChannelFilterX<br />ML](Crm.Pricing.PromotionalPackages.md#validfordistributionchannelfilterxml) | dataaccessfilter __nullable__ | When not NULL, the package is valid only if the specified distribution channel of the sales order matches the filter.[Unit: Marketing.DistributionChannels<br />Repository.TableName] 
| [ValidForShipTo<br />CustomerFilter<br />XML](Crm.Pricing.PromotionalPackages.md#validforshiptocustomerfilterxml) | dataaccessfilter __nullable__ | The package is valid only for the ship to customers, that match the filter[Unit: Crm.Sales.CustomersRepository.TableName] 
| [ValidFromDate](Crm.Pricing.PromotionalPackages.md#validfromdate) | date __nullable__ | The date from which the promotional pakage is valid[Filter(eq;ge;le)] 
| [ValidToDate](Crm.Pricing.PromotionalPackages.md#validtodate) | date __nullable__ | The date to which(inclusive) the promotional pakage is valid[Filter(eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Campaign](Crm.Pricing.PromotionalPackages.md#campaign) | [Campaigns](Crm.Marketing.Campaigns.md) (nullable) | Тhe marketing campaign to which the current definition belongs. |
| [DocumentAmountType](Crm.Pricing.PromotionalPackages.md#documentamounttype) | [DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable) | The document amount type that is used as а category. When specified, triggers the recording of the applied discount amount from the promotional package in the Document Distributed Amounts panel in sales orders. |
| [EnterpriseCompany](Crm.Pricing.PromotionalPackages.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not NULL, indicates that the package is valid only for the specified enterprise company. |
| [EnterpriseCompanyLocation](Crm.Pricing.PromotionalPackages.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The Enterprise Company Location to which this PromotionalPackage applies, or null if it is for all enterprise company locations. `Filter(multi eq)` |
| [ValidForCustomer](Crm.Pricing.PromotionalPackages.md#validforcustomer) | [Customers](Crm.Sales.Customers.md) (nullable) | Client for which the promotional pakage is valid |
| [ValidForDistribution<br />Channel](Crm.Pricing.PromotionalPackages.md#validfordistributionchannel) | [DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable) | When not NULL, the package is valid only for the specified distribution channel of the sales order |
| [ValidForPriceList](Crm.Pricing.PromotionalPackages.md#validforpricelist) | [PriceLists](Crm.Pricing.PriceLists.md) (nullable) | Price list for which the promotional pakage is valid |
| [ValidForShipToCustomer](Crm.Pricing.PromotionalPackages.md#validforshiptocustomer) | [Customers](Crm.Sales.Customers.md) (nullable) | When not NULL, specifies that the package is valid only when the sales document is for the specified Ship To Customer. |
| [ValidForTargetGroup](Crm.Pricing.PromotionalPackages.md#validfortargetgroup) | [TargetGroups](Crm.Marketing.TargetGroups.md) (nullable) | Target group for which the promotional pakage is valid |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Crm.Pricing.PromotionalPackages.md#id) | guid |  
| [ObjectVersion](Crm.Pricing.PromotionalPackages.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Crm.Pricing.PromotionalPackages.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Crm.Pricing.PromotionalPackages.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Crm.Pricing.PromotionalPackages.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Crm.Pricing.PromotionalPackages.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Lines | [PromotionalPackageLines](Crm.Pricing.PromotionalPackageLines.md) | List of `PromotionalPackageLine`(Crm.Pricing.PromotionalPackageLines.md) child objects, based on the `Crm.Pricing.PromotionalPackageLine.PromotionalPackage`(Crm.Pricing.PromotionalPackageLines.md#promotionalpackage) back reference 


## Attribute Details

### Active

Package status: 1 = the offer is available for new documents; 0 = otherwise[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Code

Unique code of the promotional package[Required] [Filter(eq;like)] [ORD]

Type: **string (20)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Code, null, "00000")`

### Name

The name of this PromotionalPackage. `Required` `Filter(eq;like)` `ORD`

Type: **string (254)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### ValidForCustomerFilterXML

Customer filter for clients. The package is valid only for the customers, that match the filter[Unit: Crm.Sales.CustomersRepository.TableName]

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidForDistributionChannelFilterXML

When not NULL, the package is valid only if the specified distribution channel of the sales order matches the filter.[Unit: Marketing.DistributionChannelsRepository.TableName]

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidForShipToCustomerFilterXML

The package is valid only for the ship to customers, that match the filter[Unit: Crm.Sales.CustomersRepository.TableName]

Type: **dataaccessfilter __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidFromDate

The date from which the promotional pakage is valid[Filter(eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidToDate

The date to which(inclusive) the promotional pakage is valid[Filter(eq;ge;le)]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### Campaign

Тhe marketing campaign to which the current definition belongs.

Type: **[Campaigns](Crm.Marketing.Campaigns.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DocumentAmountType

The document amount type that is used as а category. When specified, triggers the recording of the applied discount amount from the promotional package in the Document Distributed Amounts panel in sales orders.

Type: **[DocumentAmountTypes](Systems.Documents.DocumentAmountTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

When not NULL, indicates that the package is valid only for the specified enterprise company.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompanyLocation

The Enterprise Company Location to which this PromotionalPackage applies, or null if it is for all enterprise company locations. `Filter(multi eq)`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ValidForCustomer

Client for which the promotional pakage is valid

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ValidForDistributionChannel

When not NULL, the package is valid only for the specified distribution channel of the sales order

Type: **[DistributionChannels](Crm.Marketing.DistributionChannels.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ValidForPriceList

Price list for which the promotional pakage is valid

Type: **[PriceLists](Crm.Pricing.PriceLists.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ValidForShipToCustomer

When not NULL, specifies that the package is valid only when the sales document is for the specified Ship To Customer.

Type: **[Customers](Crm.Sales.Customers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ValidForTargetGroup

Target group for which the promotional pakage is valid

Type: **[TargetGroups](Crm.Marketing.TargetGroups.md) (nullable)**  
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

[!list limit=1000 erp.entity=Crm.Pricing.PromotionalPackages erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pricing.PromotionalPackages erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pricing_PromotionalPackages

Domain API Entity Type: 
Crm_Pricing_PromotionalPackage

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pricing_PromotionalPackages?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pricing_PromotionalPackages?$top=10>

