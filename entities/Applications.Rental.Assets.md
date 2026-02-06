---
uid: Applications.Rental.Assets
---
# Applications.Rental.Assets


Contains the rentable assets.

## General
Namespace: [Applications.Rental](Applications.Rental.md)  
Repository: Applications.Rental.Assets  
Base Table: Rent_Assets  
API access:  ReadWrite  

## Visualization
Display Format: {RentalAssetName}  
Search Members: RentalAssetCode; RentalAssetName  
Code Member: RentalAssetCode  
Name Member: RentalAssetName  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  RentalAssetTypeId  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Rental.Assets](Applications.Rental.Assets.md)  
  * [Applications.Rental.AssetConsumables](Applications.Rental.AssetConsumables.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsActive](Applications.Rental.Assets.md#isactive) | boolean | True if the asset is currently active and may be used in new documents. Deactivated assets are used only in reports.[Required] [Default(true)] [Filter(eq)] 
| [Notes](Applications.Rental.Assets.md#notes) | string (max) __nullable__ | Notes for this Asset. 
| [RentalAssetCode](Applications.Rental.Assets.md#rentalassetcode) | string (20) | Unique rental asset code[Required] [Filter(eq;like)] [ORD] 
| [RentalAssetName](Applications.Rental.Assets.md#rentalassetname) | string (254) | The name of the rental asset.[Required] [Filter(like)] 
| [StandardGuaranteeAmount](Applications.Rental.Assets.md#standardguaranteeamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | Standard default amount of the guarantee that is set for this asset when leased.[Currency: StandardGuarantee<br />AmountCurrency] [Filter(multi eq)] 
| [TimePeriodType](Applications.Rental.Assets.md#timeperiodtype) | [TimePeriodType](Applications.Rental.Assets.md#timeperiodtype) __nullable__ | Specifies the unit by which the periods of renting of this asset are measured.[Filter(multi eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountingAsset](Applications.Rental.Assets.md#accountingasset) | [Assets](Finance.Assets.Assets.md) (nullable) | If not empty, the field correspond with asset in finance module |
| [EnterpriseCompany](Applications.Rental.Assets.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not null, specifies that the asset is specific to a given enterprise company and may be used only in documents from this enterprise company. If null, the asset can be used in all enterprise companies. |
| [ManagedAsset](Applications.Rental.Assets.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable) | Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. |
| [Product](Applications.Rental.Assets.md#product) | [Products](General.Products.Products.md) (nullable) | Product which is used in the store transactions for this asset. |
| [RentalAssetGroup](Applications.Rental.Assets.md#rentalassetgroup) | [AssetGroups](Applications.Rental.AssetGroups.md) | The logical group of the rental asset. |
| [RentalAssetType](Applications.Rental.Assets.md#rentalassettype) | [AssetTypes](Applications.Rental.AssetTypes.md) | The type of the asset. |
| [SalesProduct](Applications.Rental.Assets.md#salesproduct) | [Products](General.Products.Products.md) (nullable) | Product which is used in the creation of Sales Orders to form the price of the service of renting this asset. |
| [SerialNumber](Applications.Rental.Assets.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number which in conjunction with the product for store operations allows for more accurate identification of the asset. |
| [StandardGuarantee<br />AmountCurrency](Applications.Rental.Assets.md#standardguaranteeamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Currency of the standard guarantee amount. |
| [WorkSchedule](Applications.Rental.Assets.md#workschedule) | [WorkSchedules](General.Resources.WorkSchedules.md) (nullable) | Work schedule, which is used to calculate how many days this assets has been rented for (used only when the asset's lease by mode is by days). |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Rental.Assets.md#id) | guid |  
| [ObjectVersion](Applications.Rental.Assets.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Applications.Rental.Assets.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Rental.Assets.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Applications.Rental.Assets.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Applications.Rental.Assets.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Consumables | [AssetConsumables](Applications.Rental.AssetConsumables.md) | List of `AssetConsumable`(Applications.Rental.AssetConsumables.md) child objects, based on the `Applications.Rental.AssetConsumable.RentalAsset`(Applications.Rental.AssetConsumables.md#rentalasset) back reference 


## Attribute Details

### IsActive

True if the asset is currently active and may be used in new documents. Deactivated assets are used only in reports.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this Asset.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RentalAssetCode

Unique rental asset code[Required] [Filter(eq;like)] [ORD]

Type: **string (20)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **20**  
Show in UI: **ShownByDefault**  

### RentalAssetName

The name of the rental asset.[Required] [Filter(like)]

Type: **string (254)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### StandardGuaranteeAmount

Standard default amount of the guarantee that is set for this asset when leased.[Currency: StandardGuaranteeAmountCurrency] [Filter(multi eq)]

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TimePeriodType

Specifies the unit by which the periods of renting of this asset are measured.[Filter(multi eq)]

Type: **[TimePeriodType](Applications.Rental.Assets.md#timeperiodtype) __nullable__**  
Category: **System**  
Allowed values for the `TimePeriodType`(Applications.Rental.Assets.md#timeperiodtype) data attribute  
Allowed Values (Applications.Rental.AssetsRepository.TimePeriodType Enum Members)  

| Value | Description |
| ---- | --- |
| OvernightStays | OvernightStays value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 0 <br /> Domain API Value: 'OvernightStays' |
| Months | Months value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 1 <br /> Domain API Value: 'Months' |
| FullDays | Total count of complete days.. Stored as 'F'. <br /> Database Value: 'F' <br /> Model Value: 2 <br /> Domain API Value: 'FullDays' |
| v_24HourPeriods | Started 24-hour periods.. Stored as 'H'. <br /> Database Value: 'H' <br /> Model Value: 3 <br /> Domain API Value: 'v_24HourPeriods' |

Supported Filters: **Equals, EqualsIn**  
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

### AccountingAsset

If not empty, the field correspond with asset in finance module

Type: **[Assets](Finance.Assets.Assets.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### EnterpriseCompany

When not null, specifies that the asset is specific to a given enterprise company and may be used only in documents from this enterprise company. If null, the asset can be used in all enterprise companies.

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ManagedAsset

Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset.

Type: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Product

Product which is used in the store transactions for this asset.

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.SerialNumber != null) AndAlso ( obj.SerialNumber.Product != obj.Product)), obj.SerialNumber.Product, obj.Product)`
### RentalAssetGroup

The logical group of the rental asset.

Type: **[AssetGroups](Applications.Rental.AssetGroups.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### RentalAssetType

The type of the asset.

Type: **[AssetTypes](Applications.Rental.AssetTypes.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SalesProduct

Product which is used in the creation of Sales Orders to form the price of the service of renting this asset.

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SerialNumber

Serial number which in conjunction with the product for store operations allows for more accurate identification of the asset.

Type: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( ( obj.SerialNumber != null) AndAlso ( obj.Product != obj.SerialNumber.Product)), null, obj.SerialNumber)`
### StandardGuaranteeAmountCurrency

Currency of the standard guarantee amount.

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### WorkSchedule

Work schedule, which is used to calculate how many days this assets has been rented for (used only when the asset's lease by mode is by days).

Type: **[WorkSchedules](General.Resources.WorkSchedules.md) (nullable)**  
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

[!list limit=1000 erp.entity=Applications.Rental.Assets erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Rental.Assets erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Rental_Assets

Domain API Entity Type: 
Applications_Rental_Asset

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Rental_Assets?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Rental_Assets?$top=10>

