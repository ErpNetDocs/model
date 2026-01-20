---
uid: Regulatory.Saft.ProfileAccounts
---
# Regulatory.Saft.ProfileAccounts Entity

**Namespace:** [Regulatory.Saft](Regulatory.Saft.md)  

GL Accounts to SAF-T mapping. Entity: Saft_Profile_Accounts (Introduced in version 26.2.0.42)

## Default Visualization
Default Display Text Format:  
_{Profile.Name}_  
Default Search Members:  
_Profile.Name_  
Name Data Member:  
_Profile.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

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
| [DisplayText](Regulatory.Saft.ProfileAccounts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Regulatory.Saft.ProfileAccounts.md#id) | guid |  
| [Notes](Regulatory.Saft.ProfileAccounts.md#notes) | string (max) __nullable__ | Additional details about the mapping. `Filter(like)` 
| [ObjectVersion](Regulatory.Saft.ProfileAccounts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [SignificantPropertyOrder](Regulatory.Saft.ProfileAccounts.md#significantpropertyorder) | int32 __nullable__ | Sequence number of the analytical property considered important for this account. For example, the code of the subject (customer or supplier) used to link transactions to a business partner. `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Account](Regulatory.Saft.ProfileAccounts.md#account) | [Accounts](Finance.Accounting.Accounts.md) | Internal general ledger account. `Required` `Filter(multi eq)` |
| [AccountCodeEntry](Regulatory.Saft.ProfileAccounts.md#accountcodeentry) | [CodeEntries](Regulatory.Common.CodeEntries.md) | The SAF-T account (account code) linked to the selected ERP.net account and used during SAF-T generation. `Required` `Filter(multi eq)` `Introduced in version 26.2.0.69` |
| [Profile](Regulatory.Saft.ProfileAccounts.md#profile) | [Profiles](Regulatory.Saft.Profiles.md) | SAF-T profile this mapping belongs to. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### AccountType

Account classification in SAF-T. `Required` `Filter(eq)`

_Type_: **[AccountType](Regulatory.Saft.ProfileAccounts.md#accounttype)**  
_Category_: **System**  
Allowed values for the `AccountType`(Regulatory.Saft.ProfileAccounts.md#accounttype) data attribute  
_Allowed Values (Regulatory.Saft.ProfileAccountsRepository.AccountType Enum Members)_  

| Value | Description |
| ---- | --- |
| Active | Active value. Stored as 'ACT'. <br /> _Database Value:_ 'ACT' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Active' |
| Passive | Passive value. Stored as 'PAS'. <br /> _Database Value:_ 'PAS' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Passive' |
| Bifunctional | Bifunctional value. Stored as 'BIF'. <br /> _Database Value:_ 'BIF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Bifunctional' |

_Supported Filters_: **Equals**  
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

### Notes

Additional details about the mapping. `Filter(like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### SignificantPropertyOrder

Sequence number of the analytical property considered important for this account. For example, the code of the subject (customer or supplier) used to link transactions to a business partner. `Filter(eq;ge;le)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Account

Internal general ledger account. `Required` `Filter(multi eq)`

_Type_: **[Accounts](Finance.Accounting.Accounts.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### AccountCodeEntry

The SAF-T account (account code) linked to the selected ERP.net account and used during SAF-T generation. `Required` `Filter(multi eq)` `Introduced in version 26.2.0.69`

_Type_: **[CodeEntries](Regulatory.Common.CodeEntries.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Profile

SAF-T profile this mapping belongs to. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Profiles](Regulatory.Saft.Profiles.md)**  
_Indexed_: **True**  
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

