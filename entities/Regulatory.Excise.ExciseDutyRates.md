---
uid: Regulatory.Excise.ExciseDutyRates
---
# Regulatory.Excise.ExciseDutyRates


Duty rates are specified by the taxation and customs authorities. They are the basis for the calculation of the excise amount (based on the calculation algorithm, specified in the Product Category).

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.ExciseDutyRates  
Base Table: Exc_Excise_Duty_Rates  
Introduced In Version: 21.1.3.87  
API access:  ReadWrite  

## Renames

Old name: Finance.Excise.ExciseDutyRates  
New name: Regulatory.Excise.ExciseDutyRates  
Version: 26.2.1.17  
Case: 39297  



## Visualization
Display Format: {Id}: {ExciseProductId}  
Search Members:   
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.ExciseDutyRates](Regulatory.Excise.ExciseDutyRates.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ExciseDutyRateField](Regulatory.Excise.ExciseDutyRates.md#excisedutyratefield) | decimal (10, 6) | The rate which should be applied for the specified product and purpose.[Required] [Default(0)] [Filter(eq;ge;le)] 
| [Notes](Regulatory.Excise.ExciseDutyRates.md#notes) | string (max) __nullable__ | Notes for this ExciseDutyRate. 
| [ValidFrom](Regulatory.Excise.ExciseDutyRates.md#validfrom) | date __nullable__ | The date from which the excise duty rate becomes effective. If a newer rate with a later start date exists for the same product, the previous one is considered automatically ended.[Filter(eq;ge;le)] [Introduced in version 25.1.3.7] 
| [ValidTo](Regulatory.Excise.ExciseDutyRates.md#validto) | date __nullable__ | Optional. If entered, it limits the validity period of the rate. If left empty, the rate remains valid until a new one with a later start date is defined or it is manually closed.[Filter(eq;ge;le)] [Introduced in version 25.1.3.7] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ExciseMeasurementUnit](Regulatory.Excise.ExciseDutyRates.md#excisemeasurementunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit which should be used in the excise calculation. This is only for verification purposes. |
| [ExciseProduct](Regulatory.Excise.ExciseDutyRates.md#exciseproduct) | [ExciseProducts](Regulatory.Excise.ExciseProducts.md) | The excise product for which the rate is applied. |
| [ExcisePurposeCode](Regulatory.Excise.ExciseDutyRates.md#excisepurposecode) | [ExcisePurposeCodes](Regulatory.Excise.ExcisePurposeCodes.md) | The purpose for which the rate is applied. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.ExciseDutyRates.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.ExciseDutyRates.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Excise.ExciseDutyRates.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.ExciseDutyRates.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.ExciseDutyRates.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Excise.ExciseDutyRates.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ExciseDutyRateField

The rate which should be applied for the specified product and purpose.[Required] [Default(0)] [Filter(eq;ge;le)]

Type: **decimal (10, 6)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this ExciseDutyRate.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ValidFrom

The date from which the excise duty rate becomes effective. If a newer rate with a later start date exists for the same product, the previous one is considered automatically ended.[Filter(eq;ge;le)] [Introduced in version 25.1.3.7]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ValidTo

Optional. If entered, it limits the validity period of the rate. If left empty, the rate remains valid until a new one with a later start date is defined or it is manually closed.[Filter(eq;ge;le)] [Introduced in version 25.1.3.7]

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
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

### ExciseMeasurementUnit

The measurement unit which should be used in the excise calculation. This is only for verification purposes.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExciseProduct

The excise product for which the rate is applied.

Type: **[ExciseProducts](Regulatory.Excise.ExciseProducts.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ExcisePurposeCode

The purpose for which the rate is applied.

Type: **[ExcisePurposeCodes](Regulatory.Excise.ExcisePurposeCodes.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseDutyRates erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.ExciseDutyRates erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_ExciseDutyRates

Domain API Entity Type: 
Regulatory_Excise_ExciseDutyRate

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_ExciseDutyRates?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_ExciseDutyRates?$top=10>

