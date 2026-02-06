---
uid: Regulatory.Excise.MeasuringTransactions
---
# Regulatory.Excise.MeasuringTransactions


Transaction of product input or output, measured with specialized measuring device for excise purposes.

## General
Namespace: [Regulatory.Excise](Regulatory.Excise.md)  
Repository: Regulatory.Excise.MeasuringTransactions  
Base Table: Exc_Measuring_Transactions  
Introduced In Version: 21.1.1.9  
API access:  ReadWrite  

## Renames

Old name: Finance.Excise.MeasuringTransactions  
New name: Regulatory.Excise.MeasuringTransactions  
Version: 26.2.1.17  
Case: 39297  



## Visualization
Display Format: {TransactionNumber}: {MeasuringDeviceCode}  
Search Members: MeasuringDeviceCode  
Code Member: MeasuringDeviceCode  
Category:  Views  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Excise.MeasuringTransactions](Regulatory.Excise.MeasuringTransactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AlcoholDegree](Regulatory.Excise.MeasuringTransactions.md#alcoholdegree) | decimal (5, 2) __nullable__ | For alcoholic products, contains the percentage of pure alcohol. NULL when the transaction is not for alcoholic products. 
| [AlcoholDensity](Regulatory.Excise.MeasuringTransactions.md#alcoholdensity) | int32 __nullable__ | For alcoholic products, contains the average density for the whole transaction. The measurement unit is dependent on the applicable legislation. NULL for non-alcoholic products. 
| [AlcoholTemperature](Regulatory.Excise.MeasuringTransactions.md#alcoholtemperature) | int32 __nullable__ | For alcoholic products, contains the temperature of the fluid, when Alcohol Degree was calculated. The measurement unit is dependent on the national regulation (usually Celsius). NULL for non-alcoholic products. 
| [Direction](Regulatory.Excise.MeasuringTransactions.md#direction) | [Direction](Regulatory.Excise.MeasuringTransactions.md#direction) | The direction of the transaction - IN/OUT. 
| [EndTimeUtc](Regulatory.Excise.MeasuringTransactions.md#endtimeutc) | datetime | Ending time of the transaction (in UTC time). 
| [MeasuringDeviceCode](Regulatory.Excise.MeasuringTransactions.md#measuringdevicecode) | string (32) | The code of the measuring device, used to measure the transaction. 
| [Notes](Regulatory.Excise.MeasuringTransactions.md#notes) | string (max) __nullable__ | Notes for this MeasuringTransaction. 
| [Quantity](Regulatory.Excise.MeasuringTransactions.md#quantity) | [Quantity (12, 3)](../data-types.md#quantity) | The quantity of the product, measured with this transaction. 
| [StartTimeUtc](Regulatory.Excise.MeasuringTransactions.md#starttimeutc) | datetime | Starting time of the transaction (in UTC time). 
| [TotalCounterEnd](Regulatory.Excise.MeasuringTransactions.md#totalcounterend) | decimal (12, 3) __nullable__ | Total counter value at the end of the transaction 
| [TotalCounterStart](Regulatory.Excise.MeasuringTransactions.md#totalcounterstart) | decimal (12, 3) __nullable__ | Total counter value at the start of the transaction 
| [TransactionNumber](Regulatory.Excise.MeasuringTransactions.md#transactionnumber) | string (32) | Transaction number, unique for the measuring device. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](Regulatory.Excise.MeasuringTransactions.md#product) | [Products](General.Products.Products.md) | The product, which was being measured. |
| [QuantityUnit](Regulatory.Excise.MeasuringTransactions.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. |
| [TaxWarehouse](Regulatory.Excise.MeasuringTransactions.md#taxwarehouse) | [TaxWarehouses](Regulatory.Excise.TaxWarehouses.md) | The tax warehouse, where the transaction occurred. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Excise.MeasuringTransactions.md#id) | guid |  
| [ObjectVersion](Regulatory.Excise.MeasuringTransactions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Regulatory.Excise.MeasuringTransactions.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Regulatory.Excise.MeasuringTransactions.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Regulatory.Excise.MeasuringTransactions.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Regulatory.Excise.MeasuringTransactions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AlcoholDegree

For alcoholic products, contains the percentage of pure alcohol. NULL when the transaction is not for alcoholic products.

Type: **decimal (5, 2) __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AlcoholDensity

For alcoholic products, contains the average density for the whole transaction. The measurement unit is dependent on the applicable legislation. NULL for non-alcoholic products.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### AlcoholTemperature

For alcoholic products, contains the temperature of the fluid, when Alcohol Degree was calculated. The measurement unit is dependent on the national regulation (usually Celsius). NULL for non-alcoholic products.

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Direction

The direction of the transaction - IN/OUT.

Type: **[Direction](Regulatory.Excise.MeasuringTransactions.md#direction)**  
Category: **System**  
Allowed values for the `Direction`(Regulatory.Excise.MeasuringTransactions.md#direction) data attribute  
Allowed Values (Regulatory.Excise.MeasuringTransactionsRepository.Direction Enum Members)  

| Value | Description |
| ---- | --- |
| IN | IN value. Stored as 'I'. <br /> Database Value: 'I' <br /> Model Value: 0 <br /> Domain API Value: 'IN' |
| OUT | OUT value. Stored as 'O'. <br /> Database Value: 'O' <br /> Model Value: 1 <br /> Domain API Value: 'OUT' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### EndTimeUtc

Ending time of the transaction (in UTC time).

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### MeasuringDeviceCode

The code of the measuring device, used to measure the transaction.

Type: **string (32)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **32**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this MeasuringTransaction.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Quantity

The quantity of the product, measured with this transaction.

Type: **[Quantity (12, 3)](../data-types.md#quantity)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### StartTimeUtc

Starting time of the transaction (in UTC time).

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalCounterEnd

Total counter value at the end of the transaction

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TotalCounterStart

Total counter value at the start of the transaction

Type: **decimal (12, 3) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TransactionNumber

Transaction number, unique for the measuring device.

Type: **string (32)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **32**  
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

### Product

The product, which was being measured.

Type: **[Products](General.Products.Products.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### QuantityUnit

The measurement unit of Quantity.

Type: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TaxWarehouse

The tax warehouse, where the transaction occurred.

Type: **[TaxWarehouses](Regulatory.Excise.TaxWarehouses.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Regulatory.Excise.MeasuringTransactions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Excise.MeasuringTransactions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Excise_MeasuringTransactions

Domain API Entity Type: 
Regulatory_Excise_MeasuringTransaction

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Excise_MeasuringTransactions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Excise_MeasuringTransactions?$top=10>

