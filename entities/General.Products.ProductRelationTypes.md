---
uid: General.Products.ProductRelationTypes
---
# General.Products.ProductRelationTypes


List of user-defined product relations types. Each relation type has associated system type.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductRelationTypes  
Base Table: Gen_Product_Relation_Types  
Introduced In Version: 26.2.0.8  
API access:  ReadWrite  

## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Settings  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.Products.ProductRelationTypes](General.Products.ProductRelationTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](General.Products.ProductRelationTypes.md#code) | string (16) | Code of the relation type. 
| [Name](General.Products.ProductRelationTypes.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the relation type. 
| [Notes](General.Products.ProductRelationTypes.md#notes) | string (max) __nullable__ | Notes 
| [SystemType](General.Products.ProductRelationTypes.md#systemtype) | [SystemType](General.Products.ProductRelationTypes.md#systemtype) | System type of the relation type. 


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductRelationTypes.md#id) | guid |  
| [ObjectVersion](General.Products.ProductRelationTypes.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](General.Products.ProductRelationTypes.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](General.Products.ProductRelationTypes.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](General.Products.ProductRelationTypes.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](General.Products.ProductRelationTypes.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

Code of the relation type.

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### Name

Name of the relation type.

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Notes

Notes

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### SystemType

System type of the relation type.

Type: **[SystemType](General.Products.ProductRelationTypes.md#systemtype)**  
Category: **System**  
Allowed values for the `SystemType`(General.Products.ProductRelationTypes.md#systemtype) data attribute  
Allowed Values (General.Products.ProductRelationTypesRepository.SystemType Enum Members)  

| Value | Description |
| ---- | --- |
| Generic | Generic. Stored as 'GEN'. <br /> Database Value: 'GEN' <br /> Model Value: 0 <br /> Domain API Value: 'Generic' |
| Replacement | Replacement. Stored as 'RPL'. <br /> Database Value: 'RPL' <br /> Model Value: 1 <br /> Domain API Value: 'Replacement' |
| Merchandising | Merchandising. Stored as 'MRC'. <br /> Database Value: 'MRC' <br /> Model Value: 2 <br /> Domain API Value: 'Merchandising' |
| Fitment | Fitment. Stored as 'FIT'. <br /> Database Value: 'FIT' <br /> Model Value: 3 <br /> Domain API Value: 'Fitment' |

Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **Generic**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
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

[!list limit=1000 erp.entity=General.Products.ProductRelationTypes erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductRelationTypes erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductRelationTypes

Domain API Entity Type: 
General_Products_ProductRelationType

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductRelationTypes?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductRelationTypes?$top=10>

