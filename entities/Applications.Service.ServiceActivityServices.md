---
uid: Applications.Service.ServiceActivityServices
---
# Applications.Service.ServiceActivityServices


Contains the services, which were actually performed during the service activity (repair).

## General
Namespace: [Applications.Service](Applications.Service.md)  
Repository: Applications.Service.ServiceActivityServices  
Base Table: Srv_Service_Activity_Services  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {ServiceActivity.DocumentNo} {Service}  
Search Members: ServiceActivity.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceActivities](Applications.Service.ServiceActivities.md)  
Aggregate Root:  
[Applications.Service.ServiceActivities](Applications.Service.ServiceActivities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CoveredByGuarantee](Applications.Service.ServiceActivityServices.md#coveredbyguarantee) | boolean | True when the performed service is covered by the guarantee. `Required` `Default(false)` 
| [LineNo](Applications.Service.ServiceActivityServices.md#lineno) | int32 | Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` 
| [Notes](Applications.Service.ServiceActivityServices.md#notes) | string (254) __nullable__ | Short notes for the service. 
| [Quantity](Applications.Service.ServiceActivityServices.md#quantity) | [Quantity (9, 2)](../data-types.md#quantity) | The quantity of the service in the measurement unit of the service. `Unit: Service.MeasurementUnit` `Required` `Default(1)` 
| [ServiceName](Applications.Service.ServiceActivityServices.md#servicename) | string (254) | Description of the conducted service. The description may vary (contain additional information) from the standart name of the service. `Required` `Filter(like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Document](Applications.Service.ServiceActivityServices.md#document) | [ServiceActivities](Applications.Service.ServiceActivities.md) | The owner document. The <see cref="ServiceActivity"/> to which this ServiceActivityService belongs. `Required` `Filter(multi eq)` |
| [PerformedByPerson](Applications.Service.ServiceActivityServices.md#performedbyperson) | [Persons](General.Contacts.Persons.md) (nullable) | The id of the person from the enterprise company that actually performed the work. `Filter(multi eq)` |
| [Service](Applications.Service.ServiceActivityServices.md#service) | [Services](Applications.Service.Services.md) | The type of service that is conducted. `Required` `Filter(multi eq)` |
| [ServiceActivity](Applications.Service.ServiceActivityServices.md#serviceactivity) | [ServiceActivities](Applications.Service.ServiceActivities.md) | The <see cref="ServiceActivity"/> to which this ServiceActivityService belongs. `Required` `Filter(multi eq)` `Owner` |
| [ServiceObject](Applications.Service.ServiceActivityServices.md#serviceobject) | [ServiceObjects](Applications.Service.ServiceObjects.md) (nullable) | The service object that was serviced. null means that it is unknown or N/A. `Filter(multi eq)` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Service.ServiceActivityServices.md#id) | guid |  
| [ObjectVersion](Applications.Service.ServiceActivityServices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Service.ServiceActivityServices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ServiceActivity<br />AgreedServices | [ServiceActivityAgreedServices](Applications.Service.ServiceActivityAgreedServices.md) | List of `ServiceActivity<br />AgreedService`(Applications.Service.ServiceActivity<br />AgreedServices.md) child objects, based on the `Applications.Service.ServiceActivity<br />AgreedService.ServiceActivityService`(Applications.Service.ServiceActivity<br />AgreedServices.md#serviceactivityservice) back reference 


## Attribute Details

### CoveredByGuarantee

True when the performed service is covered by the guarantee. `Required` `Default(false)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ServiceActivity.Services.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.ServiceActivity.Services.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Short notes for the service.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### Quantity

The quantity of the service in the measurement unit of the service. `Unit: Service.MeasurementUnit` `Required` `Default(1)`

Type: **[Quantity (9, 2)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### ServiceName

Description of the conducted service. The description may vary (contain additional information) from the standart name of the service. `Required` `Filter(like)`

Type: **string (254)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Service.Name`
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

### Document

The owner document. The <see cref="ServiceActivity"/> to which this ServiceActivityService belongs. `Required` `Filter(multi eq)`

Type: **[ServiceActivities](Applications.Service.ServiceActivities.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### PerformedByPerson

The id of the person from the enterprise company that actually performed the work. `Filter(multi eq)`

Type: **[Persons](General.Contacts.Persons.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Service

The type of service that is conducted. `Required` `Filter(multi eq)`

Type: **[Services](Applications.Service.Services.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ServiceActivity

The <see cref="ServiceActivity"/> to which this ServiceActivityService belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ServiceActivities](Applications.Service.ServiceActivities.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ServiceObject

The service object that was serviced. null means that it is unknown or N/A. `Filter(multi eq)`

Type: **[ServiceObjects](Applications.Service.ServiceObjects.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.ServiceActivity.DefaultServiceObject`

Front-End Recalc Expressions:  
`obj.ServiceActivity.DefaultServiceObject`

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

[!list limit=1000 erp.entity=Applications.Service.ServiceActivityServices erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Service.ServiceActivityServices erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Service_ServiceActivityServices

Domain API Entity Type: 
Applications_Service_ServiceActivityService

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Service_ServiceActivityServices?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Service_ServiceActivityServices?$top=10>

