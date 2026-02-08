---
uid: General.Contacts.PartyBankAccounts
---
# General.Contacts.PartyBankAccounts


The bank accounts of a party.

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.PartyBankAccounts  
Base Table: Gen_Party_Bank_Accounts  
API access:  ReadWrite  

## Visualization
Display Format: {BankBranchName:T}  
Search Members: BankAccountCode; BankBranchName  
Code Member: BankAccountCode  
Name Member: BankBranchName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Contacts.Parties](General.Contacts.Parties.md)  
Aggregate Root:  
[General.Contacts.Parties](General.Contacts.Parties.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BankAccountCode](General.Contacts.PartyBankAccounts.md#bankaccountcode) | string (50) | The code of the account, usually the IBAN code`Required` `Filter(eq;like)` 
| [BankAddress](General.Contacts.PartyBankAccounts.md#bankaddress) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The address of the bank or the bank branch office. Required (not-null) only for own accounts for printing or exporting bank payments 
| [BankBranchName](General.Contacts.PartyBankAccounts.md#bankbranchname) | [MultilanguageString (100)](../data-types.md#multilanguagestring) __nullable__ | The name of the branch office of the bank, where the account is located. Required (not-null) only for own accounts for printing or exporting bank payments 
| [BankCode](General.Contacts.PartyBankAccounts.md#bankcode) | string (30) __nullable__ | The code of the bank, usually the BIC code`Filter(eq)` 
| [BankName](General.Contacts.PartyBankAccounts.md#bankname) | [MultilanguageString (100)](../data-types.md#multilanguagestring) __nullable__ | The full name of the bank`Filter(like)` 
| [IsDefault](General.Contacts.PartyBankAccounts.md#isdefault) | boolean | 1 if the this is the default account for the party. Only one default per party is allowed`Required` `Default(false)` `Filter(eq)` 
| [Notes](General.Contacts.PartyBankAccounts.md#notes) | string (254) __nullable__ | Notes for this PartyBankAccount. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Party](General.Contacts.PartyBankAccounts.md#party) | [Parties](General.Contacts.Parties.md) | The <see cref="Party"/> to which this PartyBankAccount belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.PartyBankAccounts.md#id) | guid |  
| [ObjectVersion](General.Contacts.PartyBankAccounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Contacts.PartyBankAccounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### BankAccountCode

The code of the account, usually the IBAN code`Required` `Filter(eq;like)`

Type: **string (50)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **50**  
Show in UI: **ShownByDefault**  

### BankAddress

The address of the bank or the bank branch office. Required (not-null) only for own accounts for printing or exporting bank payments

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BankBranchName

The name of the branch office of the bank, where the account is located. Required (not-null) only for own accounts for printing or exporting bank payments

Type: **[MultilanguageString (100)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### BankCode

The code of the bank, usually the BIC code`Filter(eq)`

Type: **string (30) __nullable__**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **30**  
Show in UI: **ShownByDefault**  

### BankName

The full name of the bank`Filter(like)`

Type: **[MultilanguageString (100)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsDefault

1 if the this is the default account for the party. Only one default per party is allowed`Required` `Default(false)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes for this PartyBankAccount.

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **HiddenByDefault**  

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

### Party

The <see cref="Party"/> to which this PartyBankAccount belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[Parties](General.Contacts.Parties.md)**  
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

[!list limit=1000 erp.entity=General.Contacts.PartyBankAccounts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.PartyBankAccounts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_PartyBankAccounts

Domain API Entity Type: 
General_Contacts_PartyBankAccount

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_PartyBankAccounts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_PartyBankAccounts?$top=10>

