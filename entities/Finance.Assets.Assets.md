---
uid: Finance.Assets.Assets
---
# Finance.Assets.Assets Entity

**Namespace:** [Finance.Assets](Finance.Assets.md)  

The fixed assets. Entity: Ast_Assets

## Default Visualization
Default Display Text Format:  
_{Name:T}_  
Default Search Members:  
_Code; Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  
Layout category attribute:  _AssetCategoryId_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Finance.Assets.Assets](Finance.Assets.Assets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Finance.Assets.Assets.md#code) | string (20) | The unique code of the Asset. `Required` `Filter(eq;like)` `ORD` 
| [DeploymentDate](Finance.Assets.Assets.md#deploymentdate) | datetime __nullable__ | Date, when the asset is first deployed. Null if the asset is not deployed yet. `Filter(ge;le)` 
| [DisplayText](Finance.Assets.Assets.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExternalId](Finance.Assets.Assets.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Finance.Assets.Assets.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [Id](Finance.Assets.Assets.md#id) | guid |  
| [IsActive](Finance.Assets.Assets.md#isactive) | boolean | Checked if the assets is active and can be used in documents. The inactive assets can be used only for reports. `Required` `Default(true)` `Filter(eq)` 
| [Name](Finance.Assets.Assets.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of this Asset. `Required` `Filter(like)` 
| [Notes](Finance.Assets.Assets.md#notes) | string (254) __nullable__ | Notes for this Asset. 
| [ObjectVersion](Finance.Assets.Assets.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PurchaseDate](Finance.Assets.Assets.md#purchasedate) | datetime | Original purchase date of the asset. `Required` `Filter(ge;le)` 
| [SerialNumber](Finance.Assets.Assets.md#serialnumber) | string (30) __nullable__ | Serial number of the asset. `Filter(eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AssetCategory](Finance.Assets.Assets.md#assetcategory) | [AssetCategories](Finance.Assets.AssetCategories.md) | The category of this asset. The category may determine default values for the depreciation plans for the different valuation models for this asset. `Required` `Filter(multi eq)` |
| [AssetGroup](Finance.Assets.Assets.md#assetgroup) | [AssetGroups](Finance.Assets.AssetGroups.md) (nullable) | The asset group to which this asset belongs. `Filter(multi eq)` |
| [EnterpriseCompany](Finance.Assets.Assets.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) | The Enterprise Company to which this Asset applies. `Required` `Filter(multi eq)` |
| [ManagedAsset](Finance.Assets.Assets.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable) | Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74` |
| [PrimaryValuationModel](Finance.Assets.Assets.md#primaryvaluationmodel) | [ValuationModels](Finance.Assets.ValuationModels.md) | Obsolete. Not used. `Required` `Filter(multi eq)` |
| [ValuationCurrency](Finance.Assets.Assets.md#valuationcurrency) | [Currencies](General.Currencies.Currencies.md) | Currency in which changes of the asset values (purchase value, depreciation value and etc.) are stored. `Required` `Filter(multi eq)` |


## Attribute Details

### Code

The unique code of the Asset. `Required` `Filter(eq;like)` `ORD`

_Type_: **string (20)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **True**  
_Maximum Length_: **20**  
_Show in UI_: **ShownByDefault**  

### DeploymentDate

Date, when the asset is first deployed. Null if the asset is not deployed yet. `Filter(ge;le)`

_Type_: **datetime __nullable__**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

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

Checked if the assets is active and can be used in documents. The inactive assets can be used only for reports. `Required` `Default(true)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **True**  
_Show in UI_: **ShownByDefault**  

### Name

The name of this Asset. `Required` `Filter(like)`

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Asset.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### PurchaseDate

Original purchase date of the asset. `Required` `Filter(ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### SerialNumber

Serial number of the asset. `Filter(eq)`

_Type_: **string (30) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AssetCategory

The category of this asset. The category may determine default values for the depreciation plans for the different valuation models for this asset. `Required` `Filter(multi eq)`

_Type_: **[AssetCategories](Finance.Assets.AssetCategories.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### AssetGroup

The asset group to which this asset belongs. `Filter(multi eq)`

_Type_: **[AssetGroups](Finance.Assets.AssetGroups.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### EnterpriseCompany

The Enterprise Company to which this Asset applies. `Required` `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### ManagedAsset

Link to a managed asset definition from the asset management module. It is used to manage, track and maintain the asset. `Filter(multi eq)` `Introduced in version 24.1.4.74`

_Type_: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md) (nullable)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PrimaryValuationModel

Obsolete. Not used. `Required` `Filter(multi eq)`

_Type_: **[ValuationModels](Finance.Assets.ValuationModels.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ValuationCurrency

Currency in which changes of the asset values (purchase value, depreciation value and etc.) are stored. `Required` `Filter(multi eq)`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
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

[!list limit=1000 erp.entity=Finance.Assets.Assets erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Assets.Assets erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Assets_Assets

Domain API Entity Type: 
Finance_Assets_Asset

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Assets_Assets?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Assets_Assets?$top=10>

