---
uid: Applications.Rental.TransactionLines
---
# Applications.Rental.TransactionLines Entity

**Namespace:** [Applications.Rental](Applications.Rental.md)  

Contains all transactions of Record of Handover / Handing-Over Record lines. Entity: Rent_Transaction_Lines

## Default Visualization
Default Display Text Format:  
_{RentTransaction.EntityName}_  
Default Search Members:  
_RentTransaction.EntityName_  
Name Data Member:  
_RentTransaction.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Rental.Transactions](Applications.Rental.Transactions.md)  
Aggregate Root:  
[Applications.Rental.Transactions](Applications.Rental.Transactions.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Applications.Rental.TransactionLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Applications.Rental.TransactionLines.md#id) | guid |  
| [Notes](Applications.Rental.TransactionLines.md#notes) | string (max) __nullable__ | Notes. 
| [NumberOfPeriods](Applications.Rental.TransactionLines.md#numberofperiods) | int32 __nullable__ | Number of periods calculated based on the Transaction Timestamps of the deliver and receive Transactions, and the Time Period Type defined for the asset. `Filter(eq;ge;le)` `Introduced in version 24.1.5.21` 
| [ObjectVersion](Applications.Rental.TransactionLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [TransactionTimestamp](Applications.Rental.TransactionLines.md#transactiontimestamp) | datetime | Transaction Timestamp. `Required` `Filter(multi eq;ge;le)` 
| [TransactionType](Applications.Rental.TransactionLines.md#transactiontype) | [TransactionType](Applications.Rental.TransactionLines.md#transactiontype) | Transaction Type. `Required` `Filter(multi eq;like)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [LeaseContract](Applications.Rental.TransactionLines.md#leasecontract) | [LeaseContracts](Applications.Rental.LeaseContracts.md) | Lease Contract. `Required` `Filter(multi eq)` |
| [LesseeCustomer](Applications.Rental.TransactionLines.md#lesseecustomer) | [Customers](Crm.Sales.Customers.md) | Lessee Customer. `Required` `Filter(multi eq)` |
| [RentalAsset](Applications.Rental.TransactionLines.md#rentalasset) | [Assets](Applications.Rental.Assets.md) | Rental asset. `Required` `Filter(multi eq)` |
| [RentTransaction](Applications.Rental.TransactionLines.md#renttransaction) | [Transactions](Applications.Rental.Transactions.md) | The <see cref="Transaction"/> to which this TransactionLine belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
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

### Notes

Notes.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### NumberOfPeriods

Number of periods calculated based on the Transaction Timestamps of the deliver and receive Transactions, and the Time Period Type defined for the asset. `Filter(eq;ge;le)` `Introduced in version 24.1.5.21`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.CalculateNumberOfPeriods( obj.RentalAsset, obj.TransactionTimestamp, obj.TransactionType, obj.LeaseContract)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### TransactionTimestamp

Transaction Timestamp. `Required` `Filter(multi eq;ge;le)`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TransactionType

Transaction Type. `Required` `Filter(multi eq;like)`

_Type_: **[TransactionType](Applications.Rental.TransactionLines.md#transactiontype)**  
_Category_: **System**  
Allowed values for the `TransactionType`(Applications.Rental.TransactionLines.md#transactiontype) data attribute  
_Allowed Values (Applications.Rental.TransactionLinesRepository.TransactionType Enum Members)_  

| Value | Description |
| ---- | --- |
| Deliver | Deliver value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Deliver' |
| Receive | Receive value. Stored as 'R'. <br /> _Database Value:_ 'R' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Receive' |
| WriteOffNotReturned | WriteOffNotReturned value. Stored as 'W'. <br /> _Database Value:_ 'W' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'WriteOffNotReturned' |
| StatusReport | StatusReport value. Stored as 'S'. <br /> _Database Value:_ 'S' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'StatusReport' |

_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### LeaseContract

Lease Contract. `Required` `Filter(multi eq)`

_Type_: **[LeaseContracts](Applications.Rental.LeaseContracts.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### LesseeCustomer

Lessee Customer. `Required` `Filter(multi eq)`

_Type_: **[Customers](Crm.Sales.Customers.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### RentalAsset

Rental asset. `Required` `Filter(multi eq)`

_Type_: **[Assets](Applications.Rental.Assets.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### RentTransaction

The <see cref="Transaction"/> to which this TransactionLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Transactions](Applications.Rental.Transactions.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
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

