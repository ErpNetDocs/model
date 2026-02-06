---
uid: General.Products.ProductGroupRangeProperties
---
# General.Products.ProductGroupRangeProperties


When specified for a product group, provides a way for automatical creation of new products, based on altering a set of values of some user-defined properties. Each value combination is used to create a new, unique product within the group.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.ProductGroupRangeProperties  
Base Table: Gen_Product_Group_Range_Properties  
API access:  ReadWrite  

## Visualization
Display Format: {ProductGroup.Name:T}  
Search Members: ProductGroup.Name  
Name Member: ProductGroup.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  
Aggregate Root:  
[General.Products.ProductGroups](General.Products.ProductGroups.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [FromPropertyValue](General.Products.ProductGroupRangeProperties.md#frompropertyvalue) | string (254) __nullable__ | Starting value of the range of alternative values. Used only when Rage Type = R (range). 
| [PropertyValuesList](General.Products.ProductGroupRangeProperties.md#propertyvalueslist) | string (max) __nullable__ | Contains the enumeration of all values in the alternating value set. Used only when Rage Type = E (enumeratio). 
| [RangeType](General.Products.ProductGroupRangeProperties.md#rangetype) | [RangeType](General.Products.ProductGroupRangeProperties.md#rangetype) | Specifies the method of the creation of the value set: R - by range from-to; E - by enumeration of all values;[Required] [Default(&quot;R&quot;)] 
| [ToPropertyValue](General.Products.ProductGroupRangeProperties.md#topropertyvalue) | string (254) __nullable__ | Ending value of the range of alternative values. Used only when Rage Type = R (range). 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProductGroup](General.Products.ProductGroupRangeProperties.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) | The <see cref="ProductGroup"/> to which this ProductGroupRangeProperty belongs. `Required` `Filter(multi eq)` `Owner` |
| [Property](General.Products.ProductGroupRangeProperties.md#property) | [CustomProperties](Systems.Bpm.CustomProperties.md) | The property whose values will be altered. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.ProductGroupRangeProperties.md#id) | guid |  
| [ObjectVersion](General.Products.ProductGroupRangeProperties.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Products.ProductGroupRangeProperties.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### FromPropertyValue

Starting value of the range of alternative values. Used only when Rage Type = R (range).

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### PropertyValuesList

Contains the enumeration of all values in the alternating value set. Used only when Rage Type = E (enumeratio).

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### RangeType

Specifies the method of the creation of the value set: R - by range from-to; E - by enumeration of all values;[Required] [Default(&quot;R&quot;)]

Type: **[RangeType](General.Products.ProductGroupRangeProperties.md#rangetype)**  
Category: **System**  
Allowed values for the `RangeType`(General.Products.ProductGroupRangeProperties.md#rangetype) data attribute  
Allowed Values (General.Products.ProductGroupRangePropertiesRepository.RangeType Enum Members)  

| Value | Description |
| ---- | --- |
| Range | Range value. Stored as 'R'. <br /> Database Value: 'R' <br /> Model Value: 0 <br /> Domain API Value: 'Range' |
| List | List value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 1 <br /> Domain API Value: 'List' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Range**  
Show in UI: **ShownByDefault**  

### ToPropertyValue

Ending value of the range of alternative values. Used only when Rage Type = R (range).

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
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

### ProductGroup

The <see cref="ProductGroup"/> to which this ProductGroupRangeProperty belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[ProductGroups](General.Products.ProductGroups.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Property

The property whose values will be altered.

Type: **[CustomProperties](Systems.Bpm.CustomProperties.md)**  
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

[!list limit=1000 erp.entity=General.Products.ProductGroupRangeProperties erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.ProductGroupRangeProperties erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_ProductGroupRangeProperties

Domain API Entity Type: 
General_Products_ProductGroupRangeProperty

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_ProductGroupRangeProperties?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_ProductGroupRangeProperties?$top=10>

