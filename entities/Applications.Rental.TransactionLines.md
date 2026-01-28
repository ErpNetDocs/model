---
uid: Applications.Rental.TransactionLines
---
# Applications.Rental.TransactionLines


Contains all transactions of Record of Handover / Handing-Over Record lines.

## General
Namespace: [Applications.Rental](Applications.Rental.md)  
Repository: Applications.Rental.TransactionLines  
Base Table: Rent_Transaction_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {RentTransaction.EntityName}  
Search Members: RentTransaction.EntityName  
Name Member: RentTransaction.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Rental.Transactions](Applications.Rental.Transactions.md)  
Aggregate Root:  
[Applications.Rental.Transactions](Applications.Rental.Transactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Notes](Applications.Rental.TransactionLines.md#notes) | string (max) __nullable__ | Notes. 
| [NumberOfPeriods](Applications.Rental.TransactionLines.md#numberofperiods) | int32 __nullable__ | Number of periods calculated based on the Transaction Timestamps of the deliver and receive Transactions, and the Time Period Type defined for the asset. `Filter(eq;ge;le)` `Introduced in version 24.1.5.21` 
| [TransactionTimestamp](Applications.Rental.TransactionLines.md#transactiontimestamp) | datetime | Transaction Timestamp. `Required` `Filter(multi eq;ge;le)` 
| [TransactionType](Applications.Rental.TransactionLines.md#transactiontype) | [TransactionType](Applications.Rental.TransactionLines.md#transactiontype) | Transaction Type. `Required` `Filter(multi eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [LeaseContract](Applications.Rental.TransactionLines.md#leasecontract) | [LeaseContracts](Applications.Rental.LeaseContracts.md) | Lease Contract. `Required` `Filter(multi eq)` |
| [LesseeCustomer](Applications.Rental.TransactionLines.md#lesseecustomer) | [Customers](Crm.Sales.Customers.md) | Lessee Customer. `Required` `Filter(multi eq)` |
| [RentalAsset](Applications.Rental.TransactionLines.md#rentalasset) | [Assets](Applications.Rental.Assets.md) | Rental asset. `Required` `Filter(multi eq)` |
| [RentTransaction](Applications.Rental.TransactionLines.md#renttransaction) | [Transactions](Applications.Rental.Transactions.md) | The <see cref="Transaction"/> to which this TransactionLine belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Rental.TransactionLines.md#id) | guid |  
| [ObjectVersion](Applications.Rental.TransactionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Rental.TransactionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Notes

Notes.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### NumberOfPeriods

Number of periods calculated based on the Transaction Timestamps of the deliver and receive Transactions, and the Time Period Type defined for the asset. `Filter(eq;ge;le)` `Introduced in version 24.1.5.21`

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.CalculateNumberOfPeriods( obj.RentalAsset, obj.TransactionTimestamp, obj.TransactionType, obj.LeaseContract)`
### TransactionTimestamp

Transaction Timestamp. `Required` `Filter(multi eq;ge;le)`

Type: **datetime**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### TransactionType

Transaction Type. `Required` `Filter(multi eq;like)`

Type: **[TransactionType](Applications.Rental.TransactionLines.md#transactiontype)**  
Category: **System**  
Allowed values for the `TransactionType`(Applications.Rental.TransactionLines.md#transactiontype) data attribute  
Allowed Values (Applications.Rental.TransactionLinesRepository.TransactionType Enum Members)  

| Value | Description |
| ---- | --- |
| Deliver | Deliver value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 0 <br /> Domain API Value: 'Deliver' |
| Receive | Receive value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 1 <br /> Domain API Value: 'Receive' |
| WriteOffNotReturned | WriteOffNotReturned value. Stored as 'W'. <br /> Database Value: 'W' <br /> Model Value: 2 <br /> Domain API Value: 'WriteOffNotReturned' |
| StatusReport | StatusReport value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 3 <br /> Domain API Value: 'StatusReport' |

Supported Filters: **Equals, Like, EqualsIn**  
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

### LeaseContract

Lease Contract. `Required` `Filter(multi eq)`

Type: **[LeaseContracts](Applications.Rental.LeaseContracts.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### LesseeCustomer

Lessee Customer. `Required` `Filter(multi eq)`

Type: **[Customers](Crm.Sales.Customers.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### RentalAsset

Rental asset. `Required` `Filter(multi eq)`

Type: **[Assets](Applications.Rental.Assets.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### RentTransaction

The <see cref="Transaction"/> to which this TransactionLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Transactions](Applications.Rental.Transactions.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Applications.Rental.TransactionLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Rental.TransactionLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Rental_TransactionLines

Domain API Entity Type: 
Applications_Rental_TransactionLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Rental_TransactionLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Rental_TransactionLines?$top=10>

