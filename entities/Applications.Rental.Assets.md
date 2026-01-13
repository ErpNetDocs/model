---
uid: Applications.Rental.Assets
---
# Applications.Rental.Assets Entity

**Namespace:** [Applications.Rental](Applications.Rental.md)  

Contains the rentable assets. Entity: Rent_Assets

## Default Visualization
Default Display Text Format:  
_{RentalAssetName}_  
Default Search Members:  
_RentalAssetCode; RentalAssetName_  
Code Data Member:  
_RentalAssetCode_  
Name Data Member:  
_RentalAssetName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  
Layout category attribute:  _RentalAssetTypeId_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Applications.Rental.Assets](Applications.Rental.Assets.md)  
  * [Applications.Rental.AssetConsumables](Applications.Rental.AssetConsumables.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Applications.Rental.Assets.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Applications.Rental.Assets.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Applications.Rental.Assets.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Applications.Rental.Assets.md#id) | guid |  
| [IsActive](Applications.Rental.Assets.md#isactive) | boolean | True if the asset is currently active and may be used in new documents. Deactivated assets are used only in reports. `Required` `Default(true)` `Filter(eq)` 
| [Notes](Applications.Rental.Assets.md#notes) | string (max) __nullable__ | Notes for this Asset. 
| [ObjectVersion](Applications.Rental.Assets.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [RentalAssetCode](Applications.Rental.Assets.md#rentalassetcode) | string (20) | Unique rental asset code. `Required` `Filter(eq;like)` `ORD` 
| [RentalAssetName](Applications.Rental.Assets.md#rentalassetname) | string (254) | The name of the rental asset. `Required` `Filter(like)` 
| [StandardGuaranteeAmount](Applications.Rental.Assets.md#standardguaranteeamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | Standard default amount of the guarantee that is set for this asset when leased. `Currency: StandardGuarantee<br />AmountCurrency` `Filter(multi eq)` 
| [TimePeriodType](Applications.Rental.Assets.md#timeperiodtype) | [TimePeriodType](Applications.Rental.Assets.md#timeperiodtype) __nullable__ | Specifies the unit by which the periods of renting of this asset are measured. `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountingAsset](Applications.Rental.Assets.md#accountingasset) | [Assets](Finance.Assets.Assets.md) (nullable) | When not null identifies the corresponding accounting asset. `Filter(multi eq)` |
| [EnterpriseCompany](Applications.Rental.Assets.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | When not null, specifies that the asset is specific to a given enterprise company and may be used only in documents from this enterprise company. If null, the asset can be used in all enterprise companies. `Filter(multi eq)` |
| [ManagedAsset](Applications.Rental.Assets.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable) | Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74` |
| [Product](Applications.Rental.Assets.md#product) | [Products](General.Products.Products.md) (nullable) | Product which is used in the store transactions for this asset. `Filter(multi eq)` |
| [RentalAssetGroup](Applications.Rental.Assets.md#rentalassetgroup) | [AssetGroups](Applications.Rental.AssetGroups.md) | The logical group of the rental asset. `Required` `Filter(multi eq)` |
| [RentalAssetType](Applications.Rental.Assets.md#rentalassettype) | [AssetTypes](Applications.Rental.AssetTypes.md) | The type of the asset. `Required` `Filter(multi eq)` |
| [SalesProduct](Applications.Rental.Assets.md#salesproduct) | [Products](General.Products.Products.md) (nullable) | Product which is used in the creation of Sales Orders to form the price of the service of renting this asset. `Filter(multi eq)` |
| [SerialNumber](Applications.Rental.Assets.md#serialnumber) | [SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable) | Serial number which in conjunction with the product for store operations allows for more accurate identification of the asset. `Filter(multi eq)` |
| [StandardGuarantee<br />AmountCurrency](Applications.Rental.Assets.md#standardguaranteeamountcurrency) | [Currencies](General.Currencies.Currencies.md) (nullable) | Currency of the standard guarantee amount. `Filter(multi eq)` |
| [WorkSchedule](Applications.Rental.Assets.md#workschedule) | [WorkSchedules](General.Resources.WorkSchedules.md) (nullable) | Work schedule, which is used to calculate how many days this assets has been rented for (used only when the asset's lease by mode is by days). `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Consumables | [AssetConsumables](Applications.Rental.AssetConsumables.md) | List of `AssetConsumable`(Applications.Rental.AssetConsumables.md) child objects, based on the `Applications.Rental.AssetConsumable.RentalAsset`(Applications.Rental.AssetConsumables.md#rentalasset) back reference 


## Attribute Details

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

True if the asset is currently active and may be used in new documents. Deactivated assets are used only in reports. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Asset.

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

### RentalAssetCode

Unique rental asset code. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (20)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **20**  
_Show in UI_: **ShownByDefault**  

### RentalAssetName

The name of the rental asset. `Required` `Filter(like)`

_Type_: **string (254)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### StandardGuaranteeAmount

Standard default amount of the guarantee that is set for this asset when leased. `Currency: StandardGuaranteeAmountCurrency` `Filter(multi eq)`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TimePeriodType

Specifies the unit by which the periods of renting of this asset are measured. `Filter(multi eq)`

_Type_: **[TimePeriodType](Applications.Rental.Assets.md#timeperiodtype) __nullable__**  
_Category_: **System**  
Allowed values for the `TimePeriodType`(Applications.Rental.Assets.md#timeperiodtype) data attribute  
_Allowed Values (Applications.Rental.AssetsRepository.TimePeriodType Enum Members)_  

| Value | Description |
| ---- | --- |
| OvernightStays | OvernightStays value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'OvernightStays' |
| Months | Months value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Months' |
| FullDays | Total count of complete days.. Stored as 'F'. <br /> _Database Value:_ 'F' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'FullDays' |
| v_24HourPeriods | Started 24-hour periods.. Stored as 'H'. <br /> _Database Value:_ 'H' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'v_24HourPeriods' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AccountingAsset

When not null identifies the corresponding accounting asset. `Filter(multi eq)`

_Type_: **[Assets](Finance.Assets.Assets.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

When not null, specifies that the asset is specific to a given enterprise company and may be used only in documents from this enterprise company. If null, the asset can be used in all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ManagedAsset

Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74`

_Type_: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Product

Product which is used in the store transactions for this asset. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.SerialNumber != null) AndAlso ( obj.SerialNumber.Product != obj.Product)), obj.SerialNumber.Product, obj.Product)`
### RentalAssetGroup

The logical group of the rental asset. `Required` `Filter(multi eq)`

_Type_: **[AssetGroups](Applications.Rental.AssetGroups.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### RentalAssetType

The type of the asset. `Required` `Filter(multi eq)`

_Type_: **[AssetTypes](Applications.Rental.AssetTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SalesProduct

Product which is used in the creation of Sales Orders to form the price of the service of renting this asset. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

Serial number which in conjunction with the product for store operations allows for more accurate identification of the asset. `Filter(multi eq)`

_Type_: **[SerialNumbers](Logistics.Inventory.SerialNumbers.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.SerialNumber != null) AndAlso ( obj.Product != obj.SerialNumber.Product)), null, obj.SerialNumber)`
### StandardGuaranteeAmountCurrency

Currency of the standard guarantee amount. `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WorkSchedule

Work schedule, which is used to calculate how many days this assets has been rented for (used only when the asset's lease by mode is by days). `Filter(multi eq)`

_Type_: **[WorkSchedules](General.Resources.WorkSchedules.md) (nullable)**  
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

