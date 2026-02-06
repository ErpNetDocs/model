---
uid: Logistics.Inventory.SerialNumbers
---
# Logistics.Inventory.SerialNumbers


Serial numbers, used by the items. Rows are created on first occurrence of the serial number in a document. Rows can be deleted after deleting the last occurence of the serial number in a document.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.SerialNumbers  
Base Table: Inv_Serial_Numbers  
API access:  ReadWrite  

## Visualization
Display Format: {SerialNumberField}  
Search Members: SerialNumberField  
Name Member: Product.Name  
Category:  Views  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.Products](General.Products.Products.md)  
Aggregate Root:  
[General.Products.Products](General.Products.Products.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [SerialNumberField](Logistics.Inventory.SerialNumbers.md#serialnumberfield) | string (40) | The serial number text[Required] [Filter(multi eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](Logistics.Inventory.SerialNumbers.md#product) | [Products](General.Products.Products.md) | The product, to which the serial number is bound |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.SerialNumbers.md#id) | guid | Unique serial number Id 
| [ObjectVersion](Logistics.Inventory.SerialNumbers.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Inventory.SerialNumbers.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### SerialNumberField

The serial number text[Required] [Filter(multi eq;like)]

Type: **string (40)**  
Category: **System**  
Supported Filters: **Equals, Like, EqualsIn**  
Supports Order By: **False**  
Maximum Length: **40**  
Show in UI: **ShownByDefault**  

### Id

Unique serial number Id

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

### Product

The product, to which the serial number is bound

Type: **[Products](General.Products.Products.md)**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.SerialNumbers erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.SerialNumbers erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_SerialNumbers

Domain API Entity Type: 
Logistics_Inventory_SerialNumber

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_SerialNumbers?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_SerialNumbers?$top=10>

