---
uid: Logistics.Wms.WarehouseProcesses
---
# Logistics.Wms.WarehouseProcesses


Contains warehouse process configurations used to determine which Warehouse Process is applicable to a Warehouse Requisition. Configurations are evaluated in ascending order of Process No. Only the first process that matches all specified criteria is selected; subsequent processes are not considered. More specific configurations should therefore be ordered before more general ones. A configuration can optionally be limited by managed warehouse, party, and validity period, while the Warehouse Requisition document type is required. The execution of the selected process is defined by the steps configured for it.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehouseProcesses  
Base Table: Wms_Warehouse_Processes  
Introduced In Version: 27.1.1.5  
API access:  ReadWrite  

## Visualization
Display Format: {Id}: {WarehouseProcessId}  
Search Members:   
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  1 - Track last changes only  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.WarehouseProcesses](Logistics.Wms.WarehouseProcesses.md)  
  * [Logistics.Wms.WarehouseProcessSteps](Logistics.Wms.WarehouseProcessSteps.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ActiveFrom](Logistics.Wms.WarehouseProcesses.md#activefrom) | datetime __nullable__ | Specifies the date and time from which the warehouse process configuration can be used. If empty, no start date restriction is applied.`Filter(ge;le)` |
| [ActiveTo](Logistics.Wms.WarehouseProcesses.md#activeto) | datetime __nullable__ | Specifies the date and time until which the warehouse process configuration can be used. If empty, no end date restriction is applied.`Filter(ge;le)` |
| [DocumentTypeId](Logistics.Wms.WarehouseProcesses.md#documenttypeid) | guid __nullable__ | Specifies the Warehouse Requisition document type for which the process is applicable. `Filter(multi eq)` `Introduced in version 27.1.1.77` |
| [IsActive](Logistics.Wms.WarehouseProcesses.md#isactive) | boolean | Specifies whether the warehouse process configuration can participate in process selection. Inactive configurations are not considered.`Required` `Default(true)` `Filter(eq)` |
| [Notes](Logistics.Wms.WarehouseProcesses.md#notes) | string (max) __nullable__ | Additional information or comments about the warehouse process configuration. |
| [ProcessNo](Logistics.Wms.WarehouseProcesses.md#processno) | int32 | Determines the order in which warehouse process configurations are checked for applicability to the Warehouse Requisition. Configurations with lower numbers are checked first.`Required` `ORD` `Introduced in version 27.1.1.51` |

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Party](Logistics.Wms.WarehouseProcesses.md#party) | [Parties](General.Contacts.Parties.md) (nullable) | Specifies the party for which the process is applicable. If empty, the process is not restricted to a specific party. |
| [SystemsDocuments<br />WarehouseProcess](Logistics.Wms.WarehouseProcesses.md#systemsdocumentswarehouseprocess) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | Unique identifier of the Warehouse Process. `Required` `Default(New Guid)` `Filter(multi eq;ge;le)` |
| [Warehouse](Logistics.Wms.WarehouseProcesses.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | Specifies the managed warehouse for which the warehouse process is applicable. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ObjectVersion](Logistics.Wms.WarehouseProcesses.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. |
| [ExternalId](Logistics.Wms.WarehouseProcesses.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] |
| [ExternalSystem](Logistics.Wms.WarehouseProcesses.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] |
| [AggregateLastUpdateTimeUtc](Logistics.Wms.WarehouseProcesses.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] |
| [AdditionalDataJson](Logistics.Wms.WarehouseProcesses.md#additionaldatajson) | string | Extensible JSON object for storing this entity&apos;s custom or optional attributes. Each application or service must store its data in a separate top-level object identified by the owning application, service, or functional domain. Applications must preserve top-level objects owned by other applications or services. Maximum length: 32,000 characters. [Introduced in version 26.3.100.4] |
| [DisplayText](Logistics.Wms.WarehouseProcesses.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. |

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| Steps | [WarehouseProcessSteps](Logistics.Wms.WarehouseProcessSteps.md) | List of `WarehouseProcessStep`(Logistics.Wms.WarehouseProcessSteps.md) child objects, based on the `Logistics.Wms.WarehouseProcessStep.WarehouseProcess`(Logistics.Wms.WarehouseProcessSteps.md#warehouseprocess) back reference 


## Attribute Details

### ActiveFrom

Specifies the date and time from which the warehouse process configuration can be used. If empty, no start date restriction is applied.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ActiveTo

Specifies the date and time until which the warehouse process configuration can be used. If empty, no end date restriction is applied.`Filter(ge;le)`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DocumentTypeId

Specifies the Warehouse Requisition document type for which the process is applicable. `Filter(multi eq)` `Introduced in version 27.1.1.77`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the warehouse process configuration can participate in process selection. Inactive configurations are not considered.`Required` `Default(true)` `Filter(eq)`

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Notes

Additional information or comments about the warehouse process configuration.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### ProcessNo

Determines the order in which warehouse process configurations are checked for applicability to the Warehouse Requisition. Configurations with lower numbers are checked first.`Required` `ORD` `Introduced in version 27.1.1.51`

Type: **int32**  
Indexed: **True**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **True**  
Show in UI: **ShownByDefault**  

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

### AdditionalDataJson

Extensible JSON object for storing this entity&apos;s custom or optional attributes. Each application or service must store its data in a separate top-level object identified by the owning application, service, or functional domain. Applications must preserve top-level objects owned by other applications or services. Maximum length: 32,000 characters. [Introduced in version 26.3.100.4]

Type: **string**  
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

Specifies the party for which the process is applicable. If empty, the process is not restricted to a specific party.

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SystemsDocumentsWarehouseProcess

Unique identifier of the Warehouse Process. `Required` `Default(New Guid)` `Filter(multi eq;ge;le)`

Type: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **HiddenByDefault**  

### Warehouse

Specifies the managed warehouse for which the warehouse process is applicable.

Type: **[Warehouses](Logistics.Wms.Warehouses.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseProcesses erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseProcesses erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehouseProcesses

Domain API Entity Type: 
Logistics_Wms_WarehouseProcess

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseProcesses?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseProcesses?$top=10>

