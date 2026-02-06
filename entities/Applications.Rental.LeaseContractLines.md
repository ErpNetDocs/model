---
uid: Applications.Rental.LeaseContractLines
---
# Applications.Rental.LeaseContractLines


The detail lines of rental contracts. Each line contains rental conditions for one asset of the rental contract.

## General
Namespace: [Applications.Rental](Applications.Rental.md)  
Repository: Applications.Rental.LeaseContractLines  
Base Table: Rent_Lease_Contract_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LeaseContract.EntityName}  
Search Members: LeaseContract.EntityName  
Name Member: LeaseContract.EntityName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Rental.LeaseContracts](Applications.Rental.LeaseContracts.md)  
Aggregate Root:  
[Applications.Rental.LeaseContracts](Applications.Rental.LeaseContracts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [EndDate](Applications.Rental.LeaseContractLines.md#enddate) | date | Ending date of lease of this asset[Required] [Filter(multi eq;ge;le)] 
| [GuaranteeAmount](Applications.Rental.LeaseContractLines.md#guaranteeamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | Deposit amount in the currency of the document which is given for this asset during its period of lease.[Currency: LeaseContract.Currency] 
| [LineNo](Applications.Rental.LeaseContractLines.md#lineno) | int32 | Consecutive number of the line within the lease contract.[Required] [Filter(eq;ge;le)] 
| [LineNotes](Applications.Rental.LeaseContractLines.md#linenotes) | string (max) __nullable__ | Notes for this line. 
| [NumberOfPeriods](Applications.Rental.LeaseContractLines.md#numberofperiods) | int32 __nullable__ | Number of periods calculated based on the Start Date and End Date of the lease, and the Time Period Type defined for the asset.[Filter(eq;ge;le)] [Introduced in version 24.1.5.21] 
| [StartDate](Applications.Rental.LeaseContractLines.md#startdate) | date | Starting date of lease for this asset[Required] [Filter(multi eq;ge;le)] 
| [TimePeriodType](Applications.Rental.LeaseContractLines.md#timeperiodtype) | [TimePeriodType](Applications.Rental.LeaseContractLines.md#timeperiodtype) __nullable__ | Specifies the unit by which the periods of renting of this asset are measured.[Filter(multi eq)] [Introduced in version 24.1.5.31] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [LeaseContract](Applications.Rental.LeaseContractLines.md#leasecontract) | [LeaseContracts](Applications.Rental.LeaseContracts.md) | The <see cref="LeaseContract"/> to which this LeaseContractLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [RentalAsset](Applications.Rental.LeaseContractLines.md#rentalasset) | [Assets](Applications.Rental.Assets.md) | The asset which is rented with the current contract. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Applications.Rental.LeaseContractLines.md#id) | guid |  
| [ObjectVersion](Applications.Rental.LeaseContractLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Applications.Rental.LeaseContractLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Consumables | [LeaseContractLineConsumables](Applications.Rental.LeaseContractLineConsumables.md) | List of `LeaseContract<br />LineConsumable`(Applications.Rental.LeaseContractLine<br />Consumables.md) child objects, based on the `Applications.Rental.LeaseContractLine<br />Consumable.LeaseLine`(Applications.Rental.LeaseContractLine<br />Consumables.md#leaseline) back reference 


## Attribute Details

### EndDate

Ending date of lease of this asset[Required] [Filter(multi eq;ge;le)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.LeaseContract.EndDate`

Front-End Recalc Expressions:  
`obj.LeaseContract.EndDate`
### GuaranteeAmount

Deposit amount in the currency of the document which is given for this asset during its period of lease.[Currency: LeaseContract.Currency]

Type: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive number of the line within the lease contract.[Required] [Filter(eq;ge;le)]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.LeaseContract.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.LeaseContract.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineNotes

Notes for this line.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### NumberOfPeriods

Number of periods calculated based on the Start Date and End Date of the lease, and the Time Period Type defined for the asset.[Filter(eq;ge;le)] [Introduced in version 24.1.5.21]

Type: **int32 __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`obj.CalculateNumberOfPeriods( obj.RentalAsset, obj.StartDate, obj.EndDate, obj.TimePeriodType)`
### StartDate

Starting date of lease for this asset[Required] [Filter(multi eq;ge;le)]

Type: **date**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.LeaseContract.StartDate`

Front-End Recalc Expressions:  
`obj.LeaseContract.StartDate`
### TimePeriodType

Specifies the unit by which the periods of renting of this asset are measured.[Filter(multi eq)] [Introduced in version 24.1.5.31]

Type: **[TimePeriodType](Applications.Rental.LeaseContractLines.md#timeperiodtype) __nullable__**  
Category: **System**  
Allowed values for the `TimePeriodType`(Applications.Rental.LeaseContractLines.md#timeperiodtype) data attribute  
Allowed Values (Applications.Rental.LeaseContractLinesRepository.TimePeriodType Enum Members)  

| Value | Description |
| ---- | --- |
| OvernightStays | OvernightStays value. Stored as 'D'. <br /> Database Value: 'D' <br /> Model Value: 0 <br /> Domain API Value: 'OvernightStays' |
| Months | Months value. Stored as 'M'. <br /> Database Value: 'M' <br /> Model Value: 1 <br /> Domain API Value: 'Months' |
| FullDays | Total count of complete days. Stored as 'F'. <br /> Database Value: 'F' <br /> Model Value: 2 <br /> Domain API Value: 'FullDays' |
| v_24HourPeriods | Started 24-Hour periods.. Stored as 'H'. <br /> Database Value: 'H' <br /> Model Value: 3 <br /> Domain API Value: 'v_24HourPeriods' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`Convert( obj.RentalAsset.TimePeriodType, Nullable`1)`
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

The <see cref="LeaseContract"/> to which this LeaseContractLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[LeaseContracts](Applications.Rental.LeaseContracts.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### RentalAsset

The asset which is rented with the current contract.

Type: **[Assets](Applications.Rental.Assets.md)**  
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

[!list limit=1000 erp.entity=Applications.Rental.LeaseContractLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Applications.Rental.LeaseContractLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Applications_Rental_LeaseContractLines

Domain API Entity Type: 
Applications_Rental_LeaseContractLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Applications_Rental_LeaseContractLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Applications_Rental_LeaseContractLines?$top=10>

