---
uid: General.Products.MeasurementUnits
---
# General.Products.MeasurementUnits


Contains all measurement units, grouped in categories. Each category has one base unit (with ratio 1/1) and unlimited number of derived units with fixed ratio to the base unit.

## General
Namespace: [General.Products](General.Products.md)  
Repository: General.Products.MeasurementUnits  
Base Table: Gen_Measurement_Units  
API access:  ReadWrite  

## Renames

Old name: General.MeasurementUnits  
New name: General.Products.MeasurementUnits  
Version: 24.1.5.35  
Case: 35911  



## Visualization
Display Format: {Name:T}  
Search Members: Code; Name  
Code Member: Code  
Name Member: Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.MeasurementCategories](General.Products.MeasurementCategories.md)  
Aggregate Root:  
[General.Products.MeasurementCategories](General.Products.MeasurementCategories.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](General.Products.MeasurementUnits.md#code) | string (16) __nullable__ | When not null, contains unique measurement unit code.[Filter(eq;like)] [ORD] 
| [Description](General.Products.MeasurementUnits.md#description) | [MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__ | Full multi-language description of the measurement unit. 
| [Divisor](General.Products.MeasurementUnits.md#divisor) | decimal (9, 3) | Divisor of the relative value of the measurement unit against other units (divisor when converting to base)[Required] [Default(1)] 
| [IsDefaultUnit](General.Products.MeasurementUnits.md#isdefaultunit) | boolean | 1 if this measurement unit is the default measurement unit within the category. There can be only one default measurement unit within a category[Required] [Default(false)] [Filter(eq)] 
| [Multiplier](General.Products.MeasurementUnits.md#multiplier) | decimal (9, 3) | Multiplier of the relative value of the measurement unit against other units (multiplier when converting to base)[Required] [Default(1)] 
| [Name](General.Products.MeasurementUnits.md#name) | [MultilanguageString (64)](../data-types.md#multilanguagestring) | Name of the measurement unit[Required] [Filter(eq;like)] 
| [SystemUnit](General.Products.MeasurementUnits.md#systemunit) | [SystemUnit](General.Products.MeasurementUnits.md#systemunit) __nullable__ | Not NULL only when this is one of the system measurement units. N=NetKG; G=GrossKG; V=VolumeL; H=HeightM; W=WidthM, L=LengthM, P=Piece, T=TimeH[Filter(eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MeasurementCategory](General.Products.MeasurementUnits.md#measurementcategory) | [MeasurementCategories](General.Products.MeasurementCategories.md) | Base measurement category Id |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](General.Products.MeasurementUnits.md#id) | guid | Unique measurement unit Id 
| [ObjectVersion](General.Products.MeasurementUnits.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](General.Products.MeasurementUnits.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

When not null, contains unique measurement unit code.[Filter(eq;like)] [ORD]

Type: **string (16) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### Description

Full multi-language description of the measurement unit.

Type: **[MultilanguageString (max)](../data-types.md#multilanguagestring) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Divisor

Divisor of the relative value of the measurement unit against other units (divisor when converting to base)[Required] [Default(1)]

Type: **decimal (9, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### IsDefaultUnit

1 if this measurement unit is the default measurement unit within the category. There can be only one default measurement unit within a category[Required] [Default(false)] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **False**  
Show in UI: **ShownByDefault**  

### Multiplier

Multiplier of the relative value of the measurement unit against other units (multiplier when converting to base)[Required] [Default(1)]

Type: **decimal (9, 3)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **1**  
Show in UI: **ShownByDefault**  

### Name

Name of the measurement unit[Required] [Filter(eq;like)]

Type: **[MultilanguageString (64)](../data-types.md#multilanguagestring)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### SystemUnit

Not NULL only when this is one of the system measurement units. N=NetKG; G=GrossKG; V=VolumeL; H=HeightM; W=WidthM, L=LengthM, P=Piece, T=TimeH[Filter(eq;like)]

Type: **[SystemUnit](General.Products.MeasurementUnits.md#systemunit) __nullable__**  
Category: **System**  
Allowed values for the `SystemUnit`(General.Products.MeasurementUnits.md#systemunit) data attribute  
Allowed Values (General.Products.MeasurementUnitsRepository.SystemUnit Enum Members)  

| Value | Description |
| ---- | --- |
| GrossKilograms | GrossKilograms value. Stored as 'G'. <br /> Database Value: 'G' <br /> Model Value: 0 <br /> Domain API Value: 'GrossKilograms' |
| HeightMeters | HeightMeters value. Stored as 'H'. <br /> Database Value: 'H' <br /> Model Value: 1 <br /> Domain API Value: 'HeightMeters' |
| LengthMeters | LengthMeters value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 2 <br /> Domain API Value: 'LengthMeters' |
| NetKilograms | NetKilograms value. Stored as 'N'. <br /> Database Value: 'N' <br /> Model Value: 3 <br /> Domain API Value: 'NetKilograms' |
| Pieces | Pieces value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 4 <br /> Domain API Value: 'Pieces' |
| VolumeLiters | VolumeLiters value. Stored as 'V'. <br /> Database Value: 'V' <br /> Model Value: 5 <br /> Domain API Value: 'VolumeLiters' |
| WidthMeters | WidthMeters value. Stored as 'W'. <br /> Database Value: 'W' <br /> Model Value: 6 <br /> Domain API Value: 'WidthMeters' |
| TimeHours | TimeHours value. Stored as 'T'. <br /> Database Value: 'T' <br /> Model Value: 7 <br /> Domain API Value: 'TimeHours' |

Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Id

Unique measurement unit Id

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

### MeasurementCategory

Base measurement category Id

Type: **[MeasurementCategories](General.Products.MeasurementCategories.md)**  
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

[!list limit=1000 erp.entity=General.Products.MeasurementUnits erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Products.MeasurementUnits erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
General_Products_MeasurementUnits

Domain API Entity Type: 
General_Products_MeasurementUnit

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/General_Products_MeasurementUnits?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#General_Products_MeasurementUnits?$top=10>

