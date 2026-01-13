---
uid: Applications.Rental.LeaseContractLines
---
# Applications.Rental.LeaseContractLines Entity

**Namespace:** [Applications.Rental](Applications.Rental.md)  

The detail lines of rental contracts. Each line contains rental conditions for one asset of the rental contract. Entity: Rent_Lease_Contract_Lines

## Default Visualization
Default Display Text Format:  
_{LeaseContract.EntityName}_  
Default Search Members:  
_LeaseContract.EntityName_  
Name Data Member:  
_LeaseContract.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Applications.Rental.LeaseContracts](Applications.Rental.LeaseContracts.md)  
Aggregate Root:  
[Applications.Rental.LeaseContracts](Applications.Rental.LeaseContracts.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Applications.Rental.LeaseContractLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [EndDate](Applications.Rental.LeaseContractLines.md#enddate) | date | Ending date of lease of this asset. `Required` `Filter(multi eq;ge;le)` 
| [GuaranteeAmount](Applications.Rental.LeaseContractLines.md#guaranteeamount) | [Amount (14, 2)](../data-types.md#amount) __nullable__ | Deposit amount in the currency of the document which is given for this asset during its period of lease. `Currency: LeaseContract.Currency` 
| [Id](Applications.Rental.LeaseContractLines.md#id) | guid |  
| [LineNo](Applications.Rental.LeaseContractLines.md#lineno) | int32 | Consecutive number of the line within the lease contract. `Required` `Filter(eq;ge;le)` 
| [LineNotes](Applications.Rental.LeaseContractLines.md#linenotes) | string (max) __nullable__ | Notes for this line. 
| [NumberOfPeriods](Applications.Rental.LeaseContractLines.md#numberofperiods) | int32 __nullable__ | Number of periods calculated based on the Start Date and End Date of the lease, and the Time Period Type defined for the asset. `Filter(eq;ge;le)` `Introduced in version 24.1.5.21` 
| [ObjectVersion](Applications.Rental.LeaseContractLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [StartDate](Applications.Rental.LeaseContractLines.md#startdate) | date | Starting date of lease for this asset. `Required` `Filter(multi eq;ge;le)` 
| [TimePeriodType](Applications.Rental.LeaseContractLines.md#timeperiodtype) | [TimePeriodType](Applications.Rental.LeaseContractLines.md#timeperiodtype) __nullable__ | Specifies the unit by which the periods of renting of this asset are measured. `Filter(multi eq)` `Introduced in version 24.1.5.31` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [LeaseContract](Applications.Rental.LeaseContractLines.md#leasecontract) | [LeaseContracts](Applications.Rental.LeaseContracts.md) | The <see cref="LeaseContract"/> to which this LeaseContractLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [RentalAsset](Applications.Rental.LeaseContractLines.md#rentalasset) | [Assets](Applications.Rental.Assets.md) | The asset which is rented with the current contract. `Required` `Filter(multi eq)` |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Consumables | [LeaseContractLineConsumables](Applications.Rental.LeaseContractLineConsumables.md) | List of `LeaseContract<br />LineConsumable`(Applications.Rental.LeaseContractLine<br />Consumables.md) child objects, based on the `Applications.Rental.LeaseContractLine<br />Consumable.LeaseLine`(Applications.Rental.LeaseContractLine<br />Consumables.md#leaseline) back reference 


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### EndDate

Ending date of lease of this asset. `Required` `Filter(multi eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.LeaseContract.EndDate`

_Front-End Recalc Expressions:_  
`obj.LeaseContract.EndDate`
### GuaranteeAmount

Deposit amount in the currency of the document which is given for this asset during its period of lease. `Currency: LeaseContract.Currency`

_Type_: **[Amount (14, 2)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### LineNo

Consecutive number of the line within the lease contract. `Required` `Filter(eq;ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.LeaseContract.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.LeaseContract.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### LineNotes

Notes for this line.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### NumberOfPeriods

Number of periods calculated based on the Start Date and End Date of the lease, and the Time Period Type defined for the asset. `Filter(eq;ge;le)` `Introduced in version 24.1.5.21`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.CalculateNumberOfPeriods( obj.RentalAsset, obj.StartDate, obj.EndDate, obj.TimePeriodType)`
### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### StartDate

Starting date of lease for this asset. `Required` `Filter(multi eq;ge;le)`

_Type_: **date**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.LeaseContract.StartDate`

_Front-End Recalc Expressions:_  
`obj.LeaseContract.StartDate`
### TimePeriodType

Specifies the unit by which the periods of renting of this asset are measured. `Filter(multi eq)` `Introduced in version 24.1.5.31`

_Type_: **[TimePeriodType](Applications.Rental.LeaseContractLines.md#timeperiodtype) __nullable__**  
_Category_: **System**  
Allowed values for the `TimePeriodType`(Applications.Rental.LeaseContractLines.md#timeperiodtype) data attribute  
_Allowed Values (Applications.Rental.LeaseContractLinesRepository.TimePeriodType Enum Members)_  

| Value | Description |
| ---- | --- |
| OvernightStays | OvernightStays value. Stored as 'D'. <br /> _Database Value:_ 'D' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'OvernightStays' |
| Months | Months value. Stored as 'M'. <br /> _Database Value:_ 'M' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Months' |
| FullDays | Total count of complete days. Stored as 'F'. <br /> _Database Value:_ 'F' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'FullDays' |
| v_24HourPeriods | Started 24-Hour periods.. Stored as 'H'. <br /> _Database Value:_ 'H' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'v_24HourPeriods' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`Convert( obj.RentalAsset.TimePeriodType, Nullable`1)`

## Reference Details

### LeaseContract

The <see cref="LeaseContract"/> to which this LeaseContractLine belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[LeaseContracts](Applications.Rental.LeaseContracts.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### RentalAsset

The asset which is rented with the current contract. `Required` `Filter(multi eq)`

_Type_: **[Assets](Applications.Rental.Assets.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

