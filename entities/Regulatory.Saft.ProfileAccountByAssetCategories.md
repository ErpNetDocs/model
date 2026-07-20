---
uid: Regulatory.Saft.ProfileAccountByAssetCategories
---
# Regulatory.Saft.ProfileAccountByAssetCategories


SAF-T accounts by fixed asset categories
Hint (EN): Maps the SAF-T account by fixed asset category for a selected SAF-T profile.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.ProfileAccountByAssetCategories  
Base Table: Saft_Profile_Account_By_Asset_Categories  
Introduced In Version: 27.1.0.81  
API access:  ReadWrite  

## Visualization
Display Format: {Profile.Name}  
Search Members: Profile.Name  
Name Member: Profile.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  
Aggregate Root:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Notes](Regulatory.Saft.ProfileAccountByAssetCategories.md#notes) | string (max) __nullable__ | Additional information or comments about the mapping.`Filter(like)` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountCodeEntry](Regulatory.Saft.ProfileAccountByAssetCategories.md#accountcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | The SAF-T account used during SAF-T generation for the selected fixed asset. |
| [AssetCategory](Regulatory.Saft.ProfileAccountByAssetCategories.md#assetcategory) | [AssetCategories](Finance.Assets.AssetCategories.md) | The ERP.net fixed asset category for which the SAF-T account is defined. |
| [Profile](Regulatory.Saft.ProfileAccountByAssetCategories.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | The SAF-T profile this mapping belongs to. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.ProfileAccountByAssetCategories.md#id) | guid |  |
| [ObjectVersion](Regulatory.Saft.ProfileAccountByAssetCategories.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [DisplayText](Regulatory.Saft.ProfileAccountByAssetCategories.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### Notes

Additional information or comments about the mapping.`Filter(like)`

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
Show in UI: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
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

### AccountCodeEntry

The SAF-T account used during SAF-T generation for the selected fixed asset.

Type: **[CodeEntries](Regulatory.Common.CodeEntries.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### AssetCategory

The ERP.net fixed asset category for which the SAF-T account is defined.

Type: **[AssetCategories](Finance.Assets.AssetCategories.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Profile

The SAF-T profile this mapping belongs to.

Type: **[Profiles](Regulatory.Saft.Profiles.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileAccountByAssetCategories erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileAccountByAssetCategories erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_ProfileAccountByAssetCategories

Domain API Entity Type: 
Regulatory_Saft_ProfileAccountByAssetCategory

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_ProfileAccountByAssetCategories?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_ProfileAccountByAssetCategories?$top=10>

