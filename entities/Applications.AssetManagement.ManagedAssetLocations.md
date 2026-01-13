---
uid: Applications.AssetManagement.ManagedAssetLocations
---
# Applications.AssetManagement.ManagedAssetLocations Entity

**Namespace:** [Applications.AssetManagement](Applications.AssetManagement.md)  

Contains the locations to which the assets are assigned at various moments in time. Entity: Eam_Managed_Asset_Locations (Introduced in version 19.1)

## Default Visualization
Default Display Text Format:  
_{ManagedAsset.Name:T}_  
Default Search Members:  
_ManagedAsset.Name_  
Name Data Member:  
_ManagedAsset.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  
Aggregate Root:  
[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Applications.AssetManagement.ManagedAssetLocations.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FromDate](Applications.AssetManagement.ManagedAssetLocations.md#fromdate) | date | The date on which the asset is assigned to the location. `Required` `Default(Now)` `Filter(ge;le)` 
| [Id](Applications.AssetManagement.ManagedAssetLocations.md#id) | guid |  
| [Notes](Applications.AssetManagement.ManagedAssetLocations.md#notes) | string (max) __nullable__ | Might contain additional notes for the exact location of the asset within the enterprise company location. 
| [ObjectVersion](Applications.AssetManagement.ManagedAssetLocations.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [EnterpriseCompanyLocation](Applications.AssetManagement.ManagedAssetLocations.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) | The enterprise company location, where the asset is assigned. `Required` `Filter(multi eq)` |
| [ManagedAsset](Applications.AssetManagement.ManagedAssetLocations.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The asset, whose location is recorded. `Required` `Filter(multi eq)` `Owner` |
| [ResponsiblePerson](Applications.AssetManagement.ManagedAssetLocations.md#responsibleperson) | [Persons](General.Contacts.Persons.md) (nullable) | The responsible person, to which the asset is assigned. null when the asset is not assigned to any particular responsible person. `Filter(multi eq)` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FromDate

The date on which the asset is assigned to the location. `Required` `Default(Now)` `Filter(ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **CurrentDateTime**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Might contain additional notes for the exact location of the asset within the enterprise company location.

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


## Reference Details

### EnterpriseCompanyLocation

The enterprise company location, where the asset is assigned. `Required` `Filter(multi eq)`

_Type_: **[CompanyLocations](General.Contacts.CompanyLocations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ManagedAsset

The asset, whose location is recorded. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### ResponsiblePerson

The responsible person, to which the asset is assigned. null when the asset is not assigned to any particular responsible person. `Filter(multi eq)`

_Type_: **[Persons](General.Contacts.Persons.md) (nullable)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssetLocations erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssetLocations erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_AssetManagement_ManagedAssetLocations

Domain API Entity Type: 
Applications_AssetManagement_ManagedAssetLocation

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_AssetManagement_ManagedAssetLocations?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_ManagedAssetLocations?$top=10>

