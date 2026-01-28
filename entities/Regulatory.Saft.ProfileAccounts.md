---
uid: Regulatory.Saft.ProfileAccounts
---
# Regulatory.Saft.ProfileAccounts


GL Accounts to SAF-T mapping.

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.ProfileAccounts  
Base Table: Saft_Profile_Accounts  
Introduced In Version: 26.2.0.42  
API access:  ReadWrite  

## Visualization
Display Format: {Profile.Name}  
Search Members: Profile.Name  
Name Member: Profile.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  
Aggregate Root:  
[Regulatory.Saft.Profiles](Regulatory.Saft.Profiles.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AccountType](Regulatory.Saft.ProfileAccounts.md#accounttype) | [AccountType](Regulatory.Saft.ProfileAccounts.md#accounttype) | Account classification in SAF-T. `Required` `Filter(eq)` 
| [Notes](Regulatory.Saft.ProfileAccounts.md#notes) | string (max) __nullable__ | Additional details about the mapping. `Filter(like)` 
| [SignificantPropertyOrder](Regulatory.Saft.ProfileAccounts.md#significantpropertyorder) | int32 __nullable__ | Sequence number of the analytical property considered important for this account. For example, the code of the subject (customer or supplier) used to link transactions to a business partner. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Regulatory.Saft.ProfileAccounts.md#account) | [Accounts](Finance.Accounting.Accounts.md) | Internal general ledger account. `Required` `Filter(multi eq)` |
| [AccountCodeEntry](Regulatory.Saft.ProfileAccounts.md#accountcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | The SAF-T account (account code) linked to the selected ERP.net account and used during SAF-T generation. `Required` `Filter(multi eq)` `Introduced in version 26.2.0.69` |
| [Profile](Regulatory.Saft.ProfileAccounts.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | SAF-T profile this mapping belongs to. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.ProfileAccounts.md#id) | guid |  
| [ObjectVersion](Regulatory.Saft.ProfileAccounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Regulatory.Saft.ProfileAccounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### AccountType

Account classification in SAF-T. `Required` `Filter(eq)`

Type: **[AccountType](Regulatory.Saft.ProfileAccounts.md#accounttype)**  
Category: **System**  
Allowed values for the `AccountType`(Regulatory.Saft.ProfileAccounts.md#accounttype) data attribute  
Allowed Values (Regulatory.Saft.ProfileAccountsRepository.AccountType Enum Members)  

| Value | Description |
| ---- | --- |
| Active | Active value. Stored as 'ACT'. <br /> Database Value: 'ACT' <br /> Model Value: 0 <br /> Domain API Value: 'Active' |
| Passive | Passive value. Stored as 'PAS'. <br /> Database Value: 'PAS' <br /> Model Value: 1 <br /> Domain API Value: 'Passive' |
| Bifunctional | Bifunctional value. Stored as 'BIF'. <br /> Database Value: 'BIF' <br /> Model Value: 2 <br /> Domain API Value: 'Bifunctional' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Additional details about the mapping. `Filter(like)`

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### SignificantPropertyOrder

Sequence number of the analytical property considered important for this account. For example, the code of the subject (customer or supplier) used to link transactions to a business partner. `Filter(eq;ge;le)`

Type: **int32 __nullable__**  
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

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Account

Internal general ledger account. `Required` `Filter(multi eq)`

Type: **[Accounts](Finance.Accounting.Accounts.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### AccountCodeEntry

The SAF-T account (account code) linked to the selected ERP.net account and used during SAF-T generation. `Required` `Filter(multi eq)` `Introduced in version 26.2.0.69`

Type: **[CodeEntries](Regulatory.Common.CodeEntries.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Profile

SAF-T profile this mapping belongs to. `Required` `Filter(multi eq)` `Owner`

Type: **[Profiles](Regulatory.Saft.Profiles.md)**  
Indexed: **True**  
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

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileAccounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.ProfileAccounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_ProfileAccounts

Domain API Entity Type: 
Regulatory_Saft_ProfileAccount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_ProfileAccounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_ProfileAccounts?$top=10>

