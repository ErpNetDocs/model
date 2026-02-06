---
uid: General.Contacts.PartyLocationNumbers
---
# General.Contacts.PartyLocationNumbers


Location numbers for a party. Depending on the partner with which we are doing an exchange, our location number might be different.

## General
Namespace: [General.Contacts](General.Contacts.md)  
Repository: General.Contacts.PartyLocationNumbers  
Base Table: Gen_Party_Location_Numbers  
Introduced In Version: 19.1  
API access:  ReadWrite  

## Renames

Old name: General.PartyLocationNumbers  
New name: General.Contacts.PartyLocationNumbers  
Version: 25.1.0.64  
Case: 37169  



## Visualization
Display Format: {Party.PartyName:T}  
Search Members: LocationNumber; Party.PartyName  
Code Member: LocationNumber  
Name Member: Party.PartyName  
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
| [LocationCodingSystem](General.Contacts.PartyLocationNumbers.md#locationcodingsystem) | [LocationCodingSystem](General.Contacts.PartyLocationNumbers.md#locationcodingsystem) | The coding system for which we are defining the location number.[Required] [Default(&quot;GLN&quot;)] [Filter(multi eq)] 
| [LocationNumber](General.Contacts.PartyLocationNumbers.md#locationnumber) | string (16) | The location number of Party.[Required] [Filter(multi eq;like)] [ORD] 
| [PartnerLocationNumber](General.Contacts.PartyLocationNumbers.md#partnerlocationnumber) | string (16) __nullable__ | The location number of the partner party for which we define the main Party location number. The location number of the main Party might be different depending on the location number of the partner party. NULL means that the location number is not dependent on the partner location number.[Filter(multi eq)] 
| [Significance](General.Contacts.PartyLocationNumbers.md#significance) | int32 | Order of significance of the location number within the main Party. If there are multiple location numbers, only the most significant is used. 0 is the least significant and higher numbers indicate higher significance.[Required] [Default(0)] [Filter(multi eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [PartnerParty](General.Contacts.PartyLocationNumbers.md#partnerparty) | [Parties](General.Contacts.Parties.md) (nullable) | The party with which we are doing exchange. Depending on the Partner Party, the main Party might have different location number. NULL means that the location number is not dependent on the Partner Party. |
| [Party](General.Contacts.PartyLocationNumbers.md#party) | [Parties](General.Contacts.Parties.md) | The party for which we are defining the location number. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Contacts.PartyLocationNumbers.md#id) | guid |  
| [ObjectVersion](General.Contacts.PartyLocationNumbers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Contacts.PartyLocationNumbers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### LocationCodingSystem

The coding system for which we are defining the location number.[Required] [Default(&quot;GLN&quot;)] [Filter(multi eq)]

Type: **[LocationCodingSystem](General.Contacts.PartyLocationNumbers.md#locationcodingsystem)**  
Category: **System**  
Allowed values for the `LocationCodingSystem`(General.Contacts.PartyLocationNumbers.md#locationcodingsystem) data attribute  
Allowed Values (General.Contacts.PartyLocationNumbersRepository.LocationCodingSystem Enum Members)  

| Value | Description |
| ---- | --- |
| GLN | GS1 Global Location Number (GLN). Stored as 'GLN'. <br /> Database Value: 'GLN' <br /> Model Value: 0 <br /> Domain API Value: 'GLN' |
| Internal | Internal coding system. Stored as 'INT'. <br /> Database Value: 'INT' <br /> Model Value: 1 <br /> Domain API Value: 'Internal' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **GLN**  
Show in UI: **ShownByDefault**  

### LocationNumber

The location number of Party.[Required] [Filter(multi eq;like)] [ORD]

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### PartnerLocationNumber

The location number of the partner party for which we define the main Party location number. The location number of the main Party might be different depending on the location number of the partner party. NULL means that the location number is not dependent on the partner location number.[Filter(multi eq)]

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### Significance

Order of significance of the location number within the main Party. If there are multiple location numbers, only the most significant is used. 0 is the least significant and higher numbers indicate higher significance.[Required] [Default(0)] [Filter(multi eq;ge;le)]

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Default Value: **0**  
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

### PartnerParty

The party with which we are doing exchange. Depending on the Partner Party, the main Party might have different location number. NULL means that the location number is not dependent on the Partner Party.

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Party

The party for which we are defining the location number.

Type: **[Parties](General.Contacts.Parties.md)**  
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

[!list limit=1000 erp.entity=General.Contacts.PartyLocationNumbers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Contacts.PartyLocationNumbers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Contacts_PartyLocationNumbers

Domain API Entity Type: 
General_Contacts_PartyLocationNumber

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Contacts_PartyLocationNumbers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Contacts_PartyLocationNumbers?$top=10>

