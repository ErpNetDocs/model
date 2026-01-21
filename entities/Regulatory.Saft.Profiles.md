---
uid: Regulatory.Saft.Profiles
---
# Regulatory.Saft.Profiles Entity

**Namespace:** [Regulatory.Saft](Regulatory.Saft.md)  

SAF-T export profiles. Entity: Saft_Profiles (Introduced in version 26.2.0.42)

## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [AggregateLastUpdateTimeUtc](Regulatory.Saft.Profiles.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Saft.Profiles.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Regulatory.Saft.Profiles.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Saft.Profiles.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Regulatory.Saft.Profiles.md#id) | guid |  
| [IsActive](Regulatory.Saft.Profiles.md#isactive) | boolean | Indicates whether the current profile is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 26.2.0.53` 
| [Name](Regulatory.Saft.Profiles.md#name) | string (254) | Descriptive name of the SAF-T profile. `Required` `Filter(eq;like)` 
| [Notes](Regulatory.Saft.Profiles.md#notes) | string (max) __nullable__ | Additional information about the profile. `Filter(like)` 
| [ObjectVersion](Regulatory.Saft.Profiles.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

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

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

_Type_: **datetime**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

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

### IsActive

Indicates whether the current profile is active. `Required` `Default(true)` `Filter(eq)` `Introduced in version 26.2.0.53`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

Descriptive name of the SAF-T profile. `Required` `Filter(eq;like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### Notes

Additional information about the profile. `Filter(like)`

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

