---
uid: Regulatory.Saft.Profiles
---
# Regulatory.Saft.Profiles


SAF-T export profiles

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.Profiles  
Base Table: Saft_Profiles  
Introduced In Version: 26.2.0.42  
API access:  ReadWrite  

## Visualization
Display Format: {Name}  
Search Members: Name  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  
  * [Regulatory.Saft.ProfileAccountByAdditionalAmounts](Regulatory.Saft.ProfileAccountByAdditionalAmounts.md)  
  * [Regulatory.Saft.ProfileAccountByProducts](Regulatory.Saft.ProfileAccountByProducts.md)  
  * [Regulatory.Saft.ProfileAccounts](Regulatory.Saft.ProfileAccounts.md)  
  * [Regulatory.Saft.ProfileCompanies](Regulatory.Saft.ProfileCompanies.md)  
  * [Regulatory.Saft.ProfileMeasurementUnits](Regulatory.Saft.ProfileMeasurementUnits.md)  
  * [Regulatory.Saft.ProfileParties](Regulatory.Saft.ProfileParties.md)  
  * [Regulatory.Saft.ProfilePaymentTypes](Regulatory.Saft.ProfilePaymentTypes.md)  
  * [Regulatory.Saft.ProfilePayments](Regulatory.Saft.ProfilePayments.md)  
  * [Regulatory.Saft.ProfileTaxCodeByAccounts](Regulatory.Saft.ProfileTaxCodeByAccounts.md)  
  * [Regulatory.Saft.ProfileTaxCodeByDealTypes](Regulatory.Saft.ProfileTaxCodeByDealTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Regulatory.Saft.Profiles.md#isactive) | boolean | Indicates whether the current profile is active. 
| [Name](Regulatory.Saft.Profiles.md#name) | string (254) | Descriptive name of the SAF-T profile. 
| [Notes](Regulatory.Saft.Profiles.md#notes) | string (max) __nullable__ | Additional information about the profile. 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.Profiles.md#id) | guid |  
| [ObjectVersion](Regulatory.Saft.Profiles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Saft.Profiles.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Saft.Profiles.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Saft.Profiles.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Saft.Profiles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| AccountByAdditionalAmounts | [ProfileAccountByAdditionalAmounts](Regulatory.Saft.ProfileAccountByAdditionalAmounts.md) | List of `ProfileAccount<br />ByAdditionalAmount`(Regulatory.Saft.ProfileAccount<br />ByAdditionalAmounts.md) child objects, based on the `Regulatory.Saft.ProfileAccount<br />ByAdditionalAmount.Profile`(Regulatory.Saft.ProfileAccount<br />ByAdditionalAmounts.md#profile) back reference 
| AccountByProducts | [ProfileAccountByProducts](Regulatory.Saft.ProfileAccountByProducts.md) | List of `ProfileAccountByProduct`(Regulatory.Saft.ProfileAccountByProducts.md) child objects, based on the `Regulatory.Saft.ProfileAccountByProduct.Profile`(Regulatory.Saft.ProfileAccountByProducts.md#profile) back reference 
| Accounts | [ProfileAccounts](Regulatory.Saft.ProfileAccounts.md) | List of `ProfileAccount`(Regulatory.Saft.ProfileAccounts.md) child objects, based on the `Regulatory.Saft.ProfileAccount.Profile`(Regulatory.Saft.ProfileAccounts.md#profile) back reference 
| Companies | [ProfileCompanies](Regulatory.Saft.ProfileCompanies.md) | List of `ProfileCompany`(Regulatory.Saft.ProfileCompanies.md) child objects, based on the `Regulatory.Saft.ProfileCompany.Profile`(Regulatory.Saft.ProfileCompanies.md#profile) back reference 
| MeasurementUnits | [ProfileMeasurementUnits](Regulatory.Saft.ProfileMeasurementUnits.md) | List of `ProfileMeasurementUnit`(Regulatory.Saft.ProfileMeasurementUnits.md) child objects, based on the `Regulatory.Saft.ProfileMeasurementUnit.Profile`(Regulatory.Saft.ProfileMeasurementUnits.md#profile) back reference 
| Parties | [ProfileParties](Regulatory.Saft.ProfileParties.md) | List of `ProfileParty`(Regulatory.Saft.ProfileParties.md) child objects, based on the `Regulatory.Saft.ProfileParty.Profile`(Regulatory.Saft.ProfileParties.md#profile) back reference 
| Payments | [ProfilePayments](Regulatory.Saft.ProfilePayments.md) | List of `ProfilePayment`(Regulatory.Saft.ProfilePayments.md) child objects, based on the `Regulatory.Saft.ProfilePayment.Profile`(Regulatory.Saft.ProfilePayments.md#profile) back reference 
| PaymentTypes | [ProfilePaymentTypes](Regulatory.Saft.ProfilePaymentTypes.md) | List of `ProfilePaymentType`(Regulatory.Saft.ProfilePaymentTypes.md) child objects, based on the `Regulatory.Saft.ProfilePaymentType.Profile`(Regulatory.Saft.ProfilePaymentTypes.md#profile) back reference 
| TaxCodeByAccounts | [ProfileTaxCodeByAccounts](Regulatory.Saft.ProfileTaxCodeByAccounts.md) | List of `ProfileTaxCodeByAccount`(Regulatory.Saft.ProfileTaxCodeByAccounts.md) child objects, based on the `Regulatory.Saft.ProfileTaxCodeByAccount.Profile`(Regulatory.Saft.ProfileTaxCodeByAccounts.md#profile) back reference 
| TaxCodeByDealTypes | [ProfileTaxCodeByDealTypes](Regulatory.Saft.ProfileTaxCodeByDealTypes.md) | List of `ProfileTaxCodeByDealType`(Regulatory.Saft.ProfileTaxCodeByDealTypes.md) child objects, based on the `Regulatory.Saft.ProfileTaxCodeByDealType.Profile`(Regulatory.Saft.ProfileTaxCodeByDealTypes.md#profile) back reference 


## Attribute Details

### IsActive

Indicates whether the current profile is active.

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Descriptive name of the SAF-T profile.

Type: **string (254)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Notes

Additional information about the profile.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
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

[!list limit=1000 erp.entity=Regulatory.Saft.Profiles erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.Profiles erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_Profiles

Domain API Entity Type: 
Regulatory_Saft_Profile

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_Profiles?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_Profiles?$top=10>

