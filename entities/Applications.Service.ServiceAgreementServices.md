---
uid: Applications.Service.ServiceAgreementServices
---
# Applications.Service.ServiceAgreementServices


Contains the free services, included in the service agreement.

## General
Namespace: [Applications.Service](Applications.Service.md)  
Repository: Applications.Service.ServiceAgreementServices  
Base Table: Srv_Service_Agreement_Services  
API access:  ReadWrite  

## Visualization
Display Format: {ServiceAgreement.EntityName}  
Search Members: ServiceAgreement.EntityName  
Name Member: ServiceAgreement.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Service.ServiceAgreements](Applications.Service.ServiceAgreements.md)  
Aggregate Root:  
[Applications.Service.ServiceAgreements](Applications.Service.ServiceAgreements.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EndDate](Applications.Service.ServiceAgreementServices.md#enddate) | datetime __nullable__ | End date to which the agreedment for the service or product holds.`Filter(ge;le)` 
| [LineNo](Applications.Service.ServiceAgreementServices.md#lineno) | int32 | Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc.`Required` 
| [Quantity](Applications.Service.ServiceAgreementServices.md#quantity) | [Quantity (18, 3)](../data-types.md#quantity) | Quantity of the agreed servcice or product`Unit: QuantityUnit` `Required` 
| [StartDate](Applications.Service.ServiceAgreementServices.md#startdate) | datetime __nullable__ | Start date from which the agreedment for the service or product holds.`Filter(ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [QuantityUnit](Applications.Service.ServiceAgreementServices.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. |
| [Service](Applications.Service.ServiceAgreementServices.md#service) | [Services](Applications.Service.Services.md) (nullable) | Paid or agreed in advance service that won't be invoiced after service activities (if 'Service' is filled then 'Service product' must be blank). |
| [ServiceAgreement](Applications.Service.ServiceAgreementServices.md#serviceagreement) | [ServiceAgreements](Applications.Service.ServiceAgreements.md) | The <see cref="ServiceAgreement"/> to which this ServiceAgreementService belongs. `Required` `Filter(multi eq)` `Owner` |
| [ServiceProduct](Applications.Service.ServiceAgreementServices.md#serviceproduct) | [Products](General.Products.Products.md) (nullable) | Paid or agreed in advance product that will be substracted from the invoiced products from service activities (if 'Service product' is filled then 'Service' must be blank). |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Service.ServiceAgreementServices.md#id) | guid |  
| [ObjectVersion](Applications.Service.ServiceAgreementServices.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Service.ServiceAgreementServices.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### EndDate

End date to which the agreedment for the service or product holds.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive line number, unique within the document. Usually is increasing in steps of 10, like in 10, 20, 30, etc.`Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.ServiceAgreement.Services.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.ServiceAgreement.Services.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Quantity

Quantity of the agreed servcice or product`Unit: QuantityUnit` `Required`

Type: **[Quantity (18, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StartDate

Start date from which the agreedment for the service or product holds.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### QuantityUnit

The measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.Service.MeasurementUnit.IfNullThen( obj.ServiceProduct.MeasurementUnit).IfNullThen( obj.QuantityUnit)`
### Service

Paid or agreed in advance service that won't be invoiced after service activities (if 'Service' is filled then 'Service product' must be blank).

Type: **[Services](Applications.Service.Services.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.ServiceProduct != null), null, obj.Service)`
### ServiceAgreement

The <see cref="ServiceAgreement"/> to which this ServiceAgreementService belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ServiceAgreements](Applications.Service.ServiceAgreements.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### ServiceProduct

Paid or agreed in advance product that will be substracted from the invoiced products from service activities (if 'Service product' is filled then 'Service' must be blank).

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.Service != null), null, obj.ServiceProduct)`

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

[!list limit=1000 erp.entity=Applications.Service.ServiceAgreementServices erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Service.ServiceAgreementServices erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Service_ServiceAgreementServices

Domain API Entity Type: 
Applications_Service_ServiceAgreementService

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Service_ServiceAgreementServices?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Service_ServiceAgreementServices?$top=10>

