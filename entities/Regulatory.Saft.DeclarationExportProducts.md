---
uid: Regulatory.Saft.DeclarationExportProducts
---
# Regulatory.Saft.DeclarationExportProducts


Contains Products included in SAF-T export

## General
Namespace: [Regulatory.Saft](Regulatory.Saft.md)  
Repository: Regulatory.Saft.DeclarationExportProducts  
Base Table: Saft_Declaration_Export_Products  
Introduced In Version: 27.1.0.86  
API access:  ReadWrite  

## Visualization
Display Format: {SaftDeclarationExport.CompanyName}  
Search Members: ProductCode; SaftDeclarationExport.CompanyName  
Code Member: ProductCode  
Name Member: SaftDeclarationExport.CompanyName  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  0 - Do not track changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Saft.DeclarationExports](Regulatory.Saft.DeclarationExports.md)  
Aggregate Root:  
[Regulatory.Saft.SaftDeclarations](Regulatory.Saft.SaftDeclarations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Description](Regulatory.Saft.DeclarationExportProducts.md#description) | string (256) __nullable__ | Description |
| [ExportSequence](Regulatory.Saft.DeclarationExportProducts.md#exportsequence) | int32 | Monotonc sequence within Declaration Export`Required` `Filter(ge;le)` `ORD` `Introduced in version 27.1.0.89` |
| [ProductCode](Regulatory.Saft.DeclarationExportProducts.md#productcode) | string (70) | Product code`Required` |
| [ProductCommodityCode](Regulatory.Saft.DeclarationExportProducts.md#productcommoditycode) | string (35) | Product Commodity Code`Required` |
| [UOMBase](Regulatory.Saft.DeclarationExportProducts.md#uombase) | string (35) | UOM Base`Required` |
| [UOMStandard](Regulatory.Saft.DeclarationExportProducts.md#uomstandard) | string (9) | UOM Standard`Required` |
| [UOMToUOMBaseConversion<br />Factor](Regulatory.Saft.DeclarationExportProducts.md#uomtouombaseconversionfactor) | string (35) | UOM To UOM Base Conversion Factor`Required` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [SaftDeclarationExport](Regulatory.Saft.DeclarationExportProducts.md#saftdeclarationexport) | [DeclarationExports](Regulatory.Saft.DeclarationExports.md) | Saft Declaration Export |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Regulatory.Saft.DeclarationExportProducts.md#id) | guid |  |
| [ObjectVersion](Regulatory.Saft.DeclarationExportProducts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [DisplayText](Regulatory.Saft.DeclarationExportProducts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |


## Attribute Details

### Description

Description

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### ExportSequence

Monotonc sequence within Declaration Export`Required` `Filter(ge;le)` `ORD` `Introduced in version 27.1.0.89`

Type: **int32**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

### ProductCode

Product code`Required`

Type: **string (70)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **70**  
Show in UI: **ShownByDefault**  

### ProductCommodityCode

Product Commodity Code`Required`

Type: **string (35)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **35**  
Show in UI: **ShownByDefault**  

### UOMBase

UOM Base`Required`

Type: **string (35)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **35**  
Show in UI: **ShownByDefault**  

### UOMStandard

UOM Standard`Required`

Type: **string (9)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **9**  
Show in UI: **ShownByDefault**  

### UOMToUOMBaseConversionFactor

UOM To UOM Base Conversion Factor`Required`

Type: **string (35)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **35**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

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

### SaftDeclarationExport

Saft Declaration Export

Type: **[DeclarationExports](Regulatory.Saft.DeclarationExports.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

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


### GetOrCreateExtensibleDataObject

Gets an existing extensible data object associated with the specified entity, or creates a new one if none exists. The newly created extensible data object is immediately commited to the database.  
Return Type: **[ExtensibleDataObjects](Systems.Core.ExtensibleDataObjects.md)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

### GetPropertyAllowedValues

Gets the allowed values for the specified property for this entity object.  
Return Type: **Collection Of ErpNet.Model.OData.ValueTextPair**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **propertyName**  
    The name of the attribute or reference  
    Type: string  

  * **search**  
    The search text - searches by display text. Can contain wildcard character %.  
    Type: string  
    Optional: True  
    Default Value: null  

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



## Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.DeclarationExportProducts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Saft.DeclarationExportProducts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Saft_DeclarationExportProducts

Domain API Entity Type: 
Regulatory_Saft_DeclarationExportProduct

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Saft_DeclarationExportProducts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Saft_DeclarationExportProducts?$top=10>

