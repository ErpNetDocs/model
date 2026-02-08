---
uid: Logistics.Wms.WarehousePolicies
---
# Logistics.Wms.WarehousePolicies


Warehouse Policies is a hierarchical system for applying policies to warehouse operations.

## General
Namespace: [Logistics.Wms](Logistics.Wms.md)  
Repository: Logistics.Wms.WarehousePolicies  
Base Table: Wms_Warehouse_Policies  
Introduced In Version: 22.1.4.23  
API access:  ReadWrite  

## Visualization
Display Format: {Warehouse} {Code}  
Search Members: Code; Warehouse.Name  
Code Member: Code  
Name Member: Warehouse.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  
Aggregate Root:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Logistics.Wms.WarehousePolicies.md#code) | string (16) | The unique code of the warehouse policy.`Required` `Introduced in version 22.1.6.60` 
| [FromDate](Logistics.Wms.WarehousePolicies.md#fromdate) | date __nullable__ | When set, specifies the activation date of the policy.`Filter(eq;ge;le)` 
| [Importance](Logistics.Wms.WarehousePolicies.md#importance) | int32 | The importance of the policy, relative to other applicable policies. Higher numbers indicate higher importance.`Required` `Default(0)` `Filter(eq;ge;le)` 
| [Note](Logistics.Wms.WarehousePolicies.md#note) | string (max) __nullable__ | Notes 
| [PolicyKind](Logistics.Wms.WarehousePolicies.md#policykind) | [PolicyKind](Logistics.Wms.WarehousePolicies.md#policykind) | The kind of policy, which is being applied.`Required` `Filter(multi eq)` 
| [ToDate](Logistics.Wms.WarehousePolicies.md#todate) | date __nullable__ | When set, specifies the de-activation date of the policy.`Filter(eq;ge;le)` 
| [Value](Logistics.Wms.WarehousePolicies.md#value) | string (64) | The value specified for the policy. For boolean policies, allowed values are "true" and "false".`Required` `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](Logistics.Wms.WarehousePolicies.md#product) | [Products](General.Products.Products.md) (nullable) | When set, specifies that the policy will apply to the specified product only. |
| [ProductGroup](Logistics.Wms.WarehousePolicies.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | When set, specifies that the policy will apply to the specified product group only. |
| [ProductType](Logistics.Wms.WarehousePolicies.md#producttype) | [ProductTypes](General.Products.ProductTypes.md) (nullable) | When set, specifies that the policy will apply to the specified product type only. |
| [Warehouse](Logistics.Wms.WarehousePolicies.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse for which the policy is defined. |
| [Zone](Logistics.Wms.WarehousePolicies.md#zone) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable) | When set, specifies that the policy will apply to the specified zone and its sub-zones. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Wms.WarehousePolicies.md#id) | guid |  
| [ObjectVersion](Logistics.Wms.WarehousePolicies.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Logistics.Wms.WarehousePolicies.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### Code

The unique code of the warehouse policy.`Required` `Introduced in version 22.1.6.60`

Type: **string (16)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.GetNextDefaultCode( )`

### FromDate

When set, specifies the activation date of the policy.`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Importance

The importance of the policy, relative to other applicable policies. Higher numbers indicate higher importance.`Required` `Default(0)` `Filter(eq;ge;le)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### Note

Notes

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### PolicyKind

The kind of policy, which is being applied.`Required` `Filter(multi eq)`

Type: **[PolicyKind](Logistics.Wms.WarehousePolicies.md#policykind)**  
Category: **System**  
Allowed values for the `PolicyKind`(Logistics.Wms.WarehousePolicies.md#policykind) data attribute  
Allowed Values (Logistics.Wms.WarehousePoliciesRepository.PolicyKind Enum Members)  

| Value | Description |
| ---- | --- |
| AllowLineSkip | Allow skipping of an order line when executing (allow quantity = 0). Stored as 'ALS'. <br /> Database Value: 'ALS' <br /> Model Value: 0 <br /> Domain API Value: 'AllowLineSkip' |
| AllowLocationChange | Allow executing from a different location than the ordered.. Stored as 'ALC'. <br /> Database Value: 'ALC' <br /> Model Value: 1 <br /> Domain API Value: 'AllowLocationChange' |
| AllowLotChange | Allow executing with a different lot than the ordered.. Stored as 'ATC'. <br /> Database Value: 'ATC' <br /> Model Value: 2 <br /> Domain API Value: 'AllowLotChange' |
| AllowProductChange | Allow executing with а different product than the ordered.. Stored as 'APC'. <br /> Database Value: 'APC' <br /> Model Value: 3 <br /> Domain API Value: 'AllowProductChange' |
| AllowUnitChange | Allow executing of a quantity in a different measurement unit than the ordered.. Stored as 'AUC'. <br /> Database Value: 'AUC' <br /> Model Value: 4 <br /> Domain API Value: 'AllowUnitChange' |
| DekittingControllingLevel | Specifies the level of control during the dekitting of the composite product.. Stored as 'DCL'. <br /> Database Value: 'DCL' <br /> Model Value: 5 <br /> Domain API Value: 'DekittingControllingLevel' |
| GS1SSCCCompanyPrefix | Specifies the GS1 company prefix issued by the national GS1 organization. A digit number used when generating SSCC codes.. Stored as 'GCP'. <br /> Database Value: 'GCP' <br /> Model Value: 6 <br /> Domain API Value: 'GS1SSCCCompanyPrefix' |
| GS1SSCCNextSerial | Specifies the next reference serial number used when generating SSCC codes. А digit number acting as a counter: e.g. 0000001, 0000002… .. Stored as 'GNS'. <br /> Database Value: 'GNS' <br /> Model Value: 7 <br /> Domain API Value: 'GS1SSCCNextSerial' |
| KittingControllingLevel | Specifies the level of control during the kitting of the composite product’s components.. Stored as 'KCL'. <br /> Database Value: 'KCL' <br /> Model Value: 8 <br /> Domain API Value: 'KittingControllingLevel' |
| RequireDestinationScan | Require scanning of the destination location when moving/receiving. Stored as 'RDS'. <br /> Database Value: 'RDS' <br /> Model Value: 9 <br /> Domain API Value: 'RequireDestinationScan' |
| RequireProductScan | Require scanning of the product. Stored as 'RPS'. <br /> Database Value: 'RPS' <br /> Model Value: 10 <br /> Domain API Value: 'RequireProductScan' |
| RequireSourceScan | Require scanning of the source location when moving/dispatching. Stored as 'RSS'. <br /> Database Value: 'RSS' <br /> Model Value: 11 <br /> Domain API Value: 'RequireSourceScan' |
| ZoneType | Specifies the type of zone. Eg for receiving, shipping, packing, etc.. Stored as 'ZTY'. <br /> Database Value: 'ZTY' <br /> Model Value: 12 <br /> Domain API Value: 'ZoneType' |
| CustomRouting | Specifies a custom routing, based on a user-defined attribute of the locations. The policy specifies the code of the user-defined attribute, whose values contain the sequence of the route. The custom routing is employed by the Suggest Routing function and can be defined only at warehouse level.. Stored as 'CRO'. <br /> Database Value: 'CRO' <br /> Model Value: 13 <br /> Domain API Value: 'CustomRouting' |
| UnassignedOrders<br />SectionVisibility | Show or hide the Unassigned Orders section in the warehouse orders list.. Stored as 'UOS'. <br /> Database Value: 'UOS' <br /> Model Value: 14 <br /> Domain API Value: 'UnassignedOrders<br />SectionVisibility' |
| StartedByOthers<br />SectionVisibility | Show or hide the Started by Others section in the warehouse orders list.. Stored as 'SOS'. <br /> Database Value: 'SOS' <br /> Model Value: 15 <br /> Domain API Value: 'StartedByOthers<br />SectionVisibility' |
| AssignedToOthers<br />SectionVisibility | Show or hide the Assign to Others section in the warehouse orders list.. Stored as 'AOS'. <br /> Database Value: 'AOS' <br /> Model Value: 16 <br /> Domain API Value: 'AssignedToOthers<br />SectionVisibility' |
| LogisticUnitScreen<br />Visibility | Always show, hide, or use the default behavior on the logistic unit screen when executing warehouse order lines.. Stored as 'LUS'. <br /> Database Value: 'LUS' <br /> Model Value: 17 <br /> Domain API Value: 'LogisticUnitScreen<br />Visibility' |
| BarcodeScanEnters<br />QuantityOfOnePce | If no quantity is entered, scanning a barcode in the SCAN field enters 1 PCE.. Stored as 'QOP'. <br /> Database Value: 'QOP' <br /> Model Value: 18 <br /> Domain API Value: 'BarcodeScanEnters<br />QuantityOfOnePce' |
| RoutingAlgorithm | RoutingAlgorithm value. Stored as 'RAL'. <br /> Database Value: 'RAL' <br /> Model Value: 19 <br /> Domain API Value: 'RoutingAlgorithm' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### ToDate

When set, specifies the de-activation date of the policy.`Filter(eq;ge;le)`

Type: **date __nullable__**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Value

The value specified for the policy. For boolean policies, allowed values are "true" and "false".`Required` `Filter(eq;ge;le)`

Type: **string (64)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan**  
Supports Order By: **False**  
Maximum Length: **64**  
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

### Product

When set, specifies that the policy will apply to the specified product only.

Type: **[Products](General.Products.Products.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductGroup

When set, specifies that the policy will apply to the specified product group only.

Type: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ProductType

When set, specifies that the policy will apply to the specified product type only.

Type: **[ProductTypes](General.Products.ProductTypes.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Warehouse

The warehouse for which the policy is defined.

Type: **[Warehouses](Logistics.Wms.Warehouses.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Zone

When set, specifies that the policy will apply to the specified zone and its sub-zones.

Type: **[WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Wms.WarehousePolicies erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehousePolicies erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Wms_WarehousePolicies

Domain API Entity Type: 
Logistics_Wms_WarehousePolicy

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Wms_WarehousePolicies?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehousePolicies?$top=10>

