---
uid: General.Contacts.PartyBankAccounts
---
# General.Contacts.PartyBankAccounts Entity

**Namespace:** [General.Contacts](General.Contacts.md)  

The bank accounts of a party. Entity: Gen_Party_Bank_Accounts

## Default Visualization
Default Display Text Format:  
_{BankBranchName:T}_  
Default Search Members:  
_BankAccountCode; BankBranchName_  
Code Data Member:  
_BankAccountCode_  
Name Data Member:  
_BankBranchName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Contacts.Parties](General.Contacts.Parties.md)  
Aggregate Root:  
[General.Contacts.Parties](General.Contacts.Parties.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [BankAccountCode](General.Contacts.PartyBankAccounts.md#bankaccountcode) | string (50) | The code of the account, usually the IBAN code. `Required` `Filter(eq;like)` 
| [BankAddress](General.Contacts.PartyBankAccounts.md#bankaddress) | [MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__ | The address of the bank or the bank branch office. Required (not-null) only for own accounts for printing or exporting bank payments. 
| [BankBranchName](General.Contacts.PartyBankAccounts.md#bankbranchname) | [MultilanguageString (100)](../data-types.md#multilanguagestring) __nullable__ | The name of the branch office of the bank, where the account is located. Required (not-null) only for own accounts for printing or exporting bank payments. 
| [BankCode](General.Contacts.PartyBankAccounts.md#bankcode) | string (30) __nullable__ | The code of the bank, usually the BIC code. `Filter(eq)` 
| [BankName](General.Contacts.PartyBankAccounts.md#bankname) | [MultilanguageString (100)](../data-types.md#multilanguagestring) __nullable__ | The full name of the bank. `Filter(like)` 
| [DisplayText](General.Contacts.PartyBankAccounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.Contacts.PartyBankAccounts.md#id) | guid |  
| [IsDefault](General.Contacts.PartyBankAccounts.md#isdefault) | boolean | True if the this is the default account for the party. Only one default per party is allowed. `Required` `Default(false)` `Filter(eq)` 
| [Notes](General.Contacts.PartyBankAccounts.md#notes) | string (254) __nullable__ | Notes for this PartyBankAccount. 
| [ObjectVersion](General.Contacts.PartyBankAccounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Party](General.Contacts.PartyBankAccounts.md#party) | [Parties](General.Contacts.Parties.md) | The <see cref="Party"/> to which this PartyBankAccount belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### BankAccountCode

The code of the account, usually the IBAN code. `Required` `Filter(eq;like)`

_Type_: **string (50)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Maximum Length_: **50**  
_Show in UI_: **ShownByDefault**  

### BankAddress

The address of the bank or the bank branch office. Required (not-null) only for own accounts for printing or exporting bank payments.

_Type_: **[MultilanguageString (254)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BankBranchName

The name of the branch office of the bank, where the account is located. Required (not-null) only for own accounts for printing or exporting bank payments.

_Type_: **[MultilanguageString (100)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### BankCode

The code of the bank, usually the BIC code. `Filter(eq)`

_Type_: **string (30) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Maximum Length_: **30**  
_Show in UI_: **ShownByDefault**  

### BankName

The full name of the bank. `Filter(like)`

_Type_: **[MultilanguageString (100)](../data-types.md#multilanguagestring) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

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

### IsDefault

True if the this is the default account for the party. Only one default per party is allowed. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this PartyBankAccount.

_Type_: **string (254) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **254**  
_Show in UI_: **HiddenByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  


## Reference Details

### Party

The <see cref="Party"/> to which this PartyBankAccount belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Parties](General.Contacts.Parties.md)**  
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

