---
uid: Applications.AssetManagement.ManagedAssetLinks
---
# Applications.AssetManagement.ManagedAssetLinks


Used to associate the Managed Asset with a set of assets comprising of a Fixed Asset, a Rental Asset, a Service Object and a Vehicle. Indicates the currently managed set and dates of management.

## General
Namespace: [Applications.AssetManagement](Applications.AssetManagement.md)  
Repository: Applications.AssetManagement.ManagedAssetLinks  
Base Table: Eam_Managed_Asset_Links  
Introduced In Version: 25.1.2.68  
API access:  ReadWrite  

## Visualization
Display Format: {ManagedAsset.Name:T}  
Search Members: ManagedAsset.Name  
Name Member: ManagedAsset.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  
Aggregate Root:  
[Applications.AssetManagement.ManagedAssets](Applications.AssetManagement.ManagedAssets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EndDate](Applications.AssetManagement.ManagedAssetLinks.md#enddate) | datetime __nullable__ | End date of asset group management. NULL means that end date is not set or unknown.[Filter(eq;ge;le)] 
| [FromDate](Applications.AssetManagement.ManagedAssetLinks.md#fromdate) | datetime | Start date of asset group management.[Required] [Default(Today)] [Filter(eq;ge;le)] 
| [IsCurrent](Applications.AssetManagement.ManagedAssetLinks.md#iscurrent) | boolean | Indicates that this group of assets is currently being managed.[Required] [Default(true)] [Filter(eq)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [FixedAsset](Applications.AssetManagement.ManagedAssetLinks.md#fixedasset) | [Assets](Finance.Assets.Assets.md) (nullable) | The linked fixed asset that is managed. NULL means that no fixed asset is linked. |
| [ManagedAsset](Applications.AssetManagement.ManagedAssetLinks.md#managedasset) | [ManagedAssets](Applications.AssetManagement.ManagedAssets.md) | The managed asset under which the assets are managed. |
| [RentalAsset](Applications.AssetManagement.ManagedAssetLinks.md#rentalasset) | [Assets](Applications.Rental.Assets.md) (nullable) | The linked rental asset that is managed. NULL means that no rental asset is linked. |
| [ServiceObject](Applications.AssetManagement.ManagedAssetLinks.md#serviceobject) | [ServiceObjects](Applications.Service.ServiceObjects.md) (nullable) | The linked service object that is managed. NULL means that no service object is linked. |
| [Vehicle](Applications.AssetManagement.ManagedAssetLinks.md#vehicle) | [Vehicles](Applications.Fleet.Vehicles.md) (nullable) | The linked vehicle that is managed. NULL means that no vehicle is linked. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.AssetManagement.ManagedAssetLinks.md#id) | guid |  
| [ObjectVersion](Applications.AssetManagement.ManagedAssetLinks.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.AssetManagement.ManagedAssetLinks.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### EndDate

End date of asset group management. NULL means that end date is not set or unknown.[Filter(eq;ge;le)]

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### FromDate

Start date of asset group management.[Required] [Default(Today)] [Filter(eq;ge;le)]

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **CurrentDate**  
Show in UI: **ShownByDefault**  

### IsCurrent

Indicates that this group of assets is currently being managed.[Required] [Default(true)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### FixedAsset

The linked fixed asset that is managed. NULL means that no fixed asset is linked.

Type: **[Assets](Finance.Assets.Assets.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ManagedAsset

The managed asset under which the assets are managed.

Type: **[ManagedAssets](Applications.AssetManagement.ManagedAssets.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### RentalAsset

The linked rental asset that is managed. NULL means that no rental asset is linked.

Type: **[Assets](Applications.Rental.Assets.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ServiceObject

The linked service object that is managed. NULL means that no service object is linked.

Type: **[ServiceObjects](Applications.Service.ServiceObjects.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Vehicle

The linked vehicle that is managed. NULL means that no vehicle is linked.

Type: **[Vehicles](Applications.Fleet.Vehicles.md) (nullable)**  
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

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssetLinks erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.AssetManagement.ManagedAssetLinks erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_AssetManagement_ManagedAssetLinks

Domain API Entity Type: 
Applications_AssetManagement_ManagedAssetLink

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_AssetManagement_ManagedAssetLinks?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_AssetManagement_ManagedAssetLinks?$top=10>

