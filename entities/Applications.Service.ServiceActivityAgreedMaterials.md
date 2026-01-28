---
uid: Applications.Service.ServiceActivityAgreedMaterials
---
# Applications.Service.ServiceActivityAgreedMaterials


Contains the materials, which were agreed for this service activity (repair), before its starting.

## General
Namespace: [Applications.Service](Applications.Service.md)  
Repository: Applications.Service.ServiceActivityAgreedMaterials  
Base Table: Srv_Service_Activity_Agreed_Materials  
API access:  ReadWrite  

## Visualization
Display Format: {ServiceActivityMaterial.ServiceActivity.EntityName}  
Search Members: ServiceActivityMaterial.ServiceActivity.EntityName  
Name Member: ServiceActivityMaterial.ServiceActivity.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceActivityMaterials](Applications.Service.ServiceActivityMaterials.md)  
Aggregate Root:  
[Applications.Service.ServiceActivities](Applications.Service.ServiceActivities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AgreedQuantity](Applications.Service.ServiceActivityAgreedMaterials.md#agreedquantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity from the service agreement material line that is accounted for this service activity material line. `Unit: ServiceAgreementMaterial.QuantityUnit` `Required` `Default(0)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ServiceActivityMaterial](Applications.Service.ServiceActivityAgreedMaterials.md#serviceactivitymaterial) | [ServiceActivityMaterials](Applications.Service.ServiceActivityMaterials.md) | The <see cref="ServiceActivity<br />Material"/> to which this ServiceActivity<br />AgreedMaterial belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner` |
| [ServiceAgreementMaterial](Applications.Service.ServiceActivityAgreedMaterials.md#serviceagreementmaterial) | [ServiceAgreementMaterials](Applications.Service.ServiceAgreementMaterials.md) | Service agreement material line that records the paid or agreed in advance material. `Required` `Filter(multi eq)` `ReadOnly` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Service.ServiceActivityAgreedMaterials.md#id) | guid |  
| [ObjectVersion](Applications.Service.ServiceActivityAgreedMaterials.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Service.ServiceActivityAgreedMaterials.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AgreedQuantity

Quantity from the service agreement material line that is accounted for this service activity material line. `Unit: ServiceAgreementMaterial.QuantityUnit` `Required` `Default(0)` `ReadOnly`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
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

### ServiceActivityMaterial

The <see cref="ServiceActivityMaterial"/> to which this ServiceActivityAgreedMaterial belongs. `Required` `Filter(multi eq)` `ReadOnly` `Owner`

Type: **[ServiceActivityMaterials](Applications.Service.ServiceActivityMaterials.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ServiceAgreementMaterial

Service agreement material line that records the paid or agreed in advance material. `Required` `Filter(multi eq)` `ReadOnly`

Type: **[ServiceAgreementMaterials](Applications.Service.ServiceAgreementMaterials.md)**  
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

[!list limit=1000 erp.entity=Applications.Service.ServiceActivityAgreedMaterials erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Service.ServiceActivityAgreedMaterials erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Service_ServiceActivityAgreedMaterials

Domain API Entity Type: 
Applications_Service_ServiceActivityAgreedMaterial

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Service_ServiceActivityAgreedMaterials?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Service_ServiceActivityAgreedMaterials?$top=10>

