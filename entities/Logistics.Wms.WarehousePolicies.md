---
uid: Logistics.Wms.WarehousePolicies
---
# Logistics.Wms.WarehousePolicies Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

Warehouse Policies is a hierarchical system for applying policies to warehouse operations. Entity: Wms_Warehouse_Policies (Introduced in version 22.1.4.23)

## Default Visualization
Default Display Text Format:  
_{Warehouse} {Code}_  
Default Search Members:  
_Code; Warehouse.Name_  
Code Data Member:  
_Code_  
Name Data Member:  
_Warehouse.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  
Aggregate Root:  
[Logistics.Wms.Warehouses](Logistics.Wms.Warehouses.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Code](Logistics.Wms.WarehousePolicies.md#code) | string (16) | The unique code of the warehouse policy. `Required` `Introduced in version 22.1.6.60` 
| [DisplayText](Logistics.Wms.WarehousePolicies.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FromDate](Logistics.Wms.WarehousePolicies.md#fromdate) | date __nullable__ | When set, specifies the activation date of the policy. `Filter(eq;ge;le)` 
| [Id](Logistics.Wms.WarehousePolicies.md#id) | guid |  
| [Importance](Logistics.Wms.WarehousePolicies.md#importance) | int32 | The importance of the policy, relative to other applicable policies. Higher numbers indicate higher importance. `Required` `Default(0)` `Filter(eq;ge;le)` 
| [Note](Logistics.Wms.WarehousePolicies.md#note) | string (max) __nullable__ | Notes. 
| [ObjectVersion](Logistics.Wms.WarehousePolicies.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [PolicyKind](Logistics.Wms.WarehousePolicies.md#policykind) | [PolicyKind](Logistics.Wms.WarehousePolicies.md#policykind) | The kind of policy, which is being applied. `Required` `Filter(multi eq)` 
| [ToDate](Logistics.Wms.WarehousePolicies.md#todate) | date __nullable__ | When set, specifies the de-activation date of the policy. `Filter(eq;ge;le)` 
| [Value](Logistics.Wms.WarehousePolicies.md#value) | string (64) | The value specified for the policy. For boolean policies, allowed values are "true" and "false". `Required` `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](Logistics.Wms.WarehousePolicies.md#product) | [Products](General.Products.Products.md) (nullable) | When set, specifies that the policy will apply to the specified product only. `Filter(multi eq)` |
| [ProductGroup](Logistics.Wms.WarehousePolicies.md#productgroup) | [ProductGroups](General.Products.ProductGroups.md) (nullable) | When set, specifies that the policy will apply to the specified product group only. `Filter(multi eq)` `Introduced in version 22.1.4.36` |
| [ProductType](Logistics.Wms.WarehousePolicies.md#producttype) | [ProductTypes](General.Products.ProductTypes.md) (nullable) | When set, specifies that the policy will apply to the specified product type only. `Filter(multi eq)` |
| [Warehouse](Logistics.Wms.WarehousePolicies.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) | The warehouse for which the policy is defined. . `Required` `Filter(multi eq)` `ReadOnly` `Owner` |
| [Zone](Logistics.Wms.WarehousePolicies.md#zone) | [WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable) | When set, specifies that the policy will apply to the specified zone and its sub-zones. `Filter(multi eq)` |


## Attribute Details

### Code

The unique code of the warehouse policy. `Required` `Introduced in version 22.1.6.60`

_Type_: **string (16)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.GetNextDefaultCode( )`

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### FromDate

When set, specifies the activation date of the policy. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Importance

The importance of the policy, relative to other applicable policies. Higher numbers indicate higher importance. `Required` `Default(0)` `Filter(eq;ge;le)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### Note

Notes.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
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

### PolicyKind

The kind of policy, which is being applied. `Required` `Filter(multi eq)`

_Type_: **[PolicyKind](Logistics.Wms.WarehousePolicies.md#policykind)**  
_Category_: **System**  
Allowed values for the `PolicyKind`(Logistics.Wms.WarehousePolicies.md#policykind) data attribute  
_Allowed Values (Logistics.Wms.WarehousePoliciesRepository.PolicyKind Enum Members)_  

| Value | Description |
| ---- | --- |
| AllowLineSkip | Allow skipping of an order line when executing (allow quantity = 0). Stored as 'ALS'. <br /> _Database Value:_ 'ALS' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'AllowLineSkip' |
| AllowLocationChange | Allow executing from a different location than the ordered.. Stored as 'ALC'. <br /> _Database Value:_ 'ALC' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'AllowLocationChange' |
| AllowLotChange | Allow executing with a different lot than the ordered.. Stored as 'ATC'. <br /> _Database Value:_ 'ATC' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'AllowLotChange' |
| AllowProductChange | Allow executing with а different product than the ordered.. Stored as 'APC'. <br /> _Database Value:_ 'APC' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'AllowProductChange' |
| AllowUnitChange | Allow executing of a quantity in a different measurement unit than the ordered.. Stored as 'AUC'. <br /> _Database Value:_ 'AUC' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'AllowUnitChange' |
| DekittingControllingLevel | Specifies the level of control during the dekitting of the composite product.. Stored as 'DCL'. <br /> _Database Value:_ 'DCL' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'DekittingControllingLevel' |
| GS1SSCCCompanyPrefix | Specifies the GS1 company prefix issued by the national GS1 organization. A digit number used when generating SSCC codes.. Stored as 'GCP'. <br /> _Database Value:_ 'GCP' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'GS1SSCCCompanyPrefix' |
| GS1SSCCNextSerial | Specifies the next reference serial number used when generating SSCC codes. А digit number acting as a counter: e.g. 0000001, 0000002… .. Stored as 'GNS'. <br /> _Database Value:_ 'GNS' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'GS1SSCCNextSerial' |
| KittingControllingLevel | Specifies the level of control during the kitting of the composite product’s components.. Stored as 'KCL'. <br /> _Database Value:_ 'KCL' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'KittingControllingLevel' |
| RequireDestinationScan | Require scanning of the destination location when moving/receiving. Stored as 'RDS'. <br /> _Database Value:_ 'RDS' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'RequireDestinationScan' |
| RequireProductScan | Require scanning of the product. Stored as 'RPS'. <br /> _Database Value:_ 'RPS' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'RequireProductScan' |
| RequireSourceScan | Require scanning of the source location when moving/dispatching. Stored as 'RSS'. <br /> _Database Value:_ 'RSS' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'RequireSourceScan' |
| ZoneType | Specifies the type of zone. Eg for receiving, shipping, packing, etc.. Stored as 'ZTY'. <br /> _Database Value:_ 'ZTY' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'ZoneType' |
| CustomRouting | Specifies a custom routing, based on a user-defined attribute of the locations. The policy specifies the code of the user-defined attribute, whose values contain the sequence of the route. The custom routing is employed by the Suggest Routing function and can be defined only at warehouse level.. Stored as 'CRO'. <br /> _Database Value:_ 'CRO' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'CustomRouting' |
| UnassignedOrders<br />SectionVisibility | Show or hide the Unassigned Orders section in the warehouse orders list.. Stored as 'UOS'. <br /> _Database Value:_ 'UOS' <br /> _Model Value:_ 14 <br /> _Domain API Value:_ 'UnassignedOrders<br />SectionVisibility' |
| StartedByOthers<br />SectionVisibility | Show or hide the Started by Others section in the warehouse orders list.. Stored as 'SOS'. <br /> _Database Value:_ 'SOS' <br /> _Model Value:_ 15 <br /> _Domain API Value:_ 'StartedByOthers<br />SectionVisibility' |
| AssignedToOthers<br />SectionVisibility | Show or hide the Assign to Others section in the warehouse orders list.. Stored as 'AOS'. <br /> _Database Value:_ 'AOS' <br /> _Model Value:_ 16 <br /> _Domain API Value:_ 'AssignedToOthers<br />SectionVisibility' |
| LogisticUnitScreen<br />Visibility | Always show, hide, or use the default behavior on the logistic unit screen when executing warehouse order lines.. Stored as 'LUS'. <br /> _Database Value:_ 'LUS' <br /> _Model Value:_ 17 <br /> _Domain API Value:_ 'LogisticUnitScreen<br />Visibility' |
| BarcodeScanEnters<br />QuantityOfOnePce | If no quantity is entered, scanning a barcode in the SCAN field enters 1 PCE.. Stored as 'QOP'. <br /> _Database Value:_ 'QOP' <br /> _Model Value:_ 18 <br /> _Domain API Value:_ 'BarcodeScanEnters<br />QuantityOfOnePce' |
| RoutingAlgorithm | RoutingAlgorithm value. Stored as 'RAL'. <br /> _Database Value:_ 'RAL' <br /> _Model Value:_ 19 <br /> _Domain API Value:_ 'RoutingAlgorithm' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ToDate

When set, specifies the de-activation date of the policy. `Filter(eq;ge;le)`

_Type_: **date __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Value

The value specified for the policy. For boolean policies, allowed values are "true" and "false". `Required` `Filter(eq;ge;le)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Product

When set, specifies that the policy will apply to the specified product only. `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductGroup

When set, specifies that the policy will apply to the specified product group only. `Filter(multi eq)` `Introduced in version 22.1.4.36`

_Type_: **[ProductGroups](General.Products.ProductGroups.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProductType

When set, specifies that the policy will apply to the specified product type only. `Filter(multi eq)`

_Type_: **[ProductTypes](General.Products.ProductTypes.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Warehouse

The warehouse for which the policy is defined. . `Required` `Filter(multi eq)` `ReadOnly` `Owner`

_Type_: **[Warehouses](Logistics.Wms.Warehouses.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### Zone

When set, specifies that the policy will apply to the specified zone and its sub-zones. `Filter(multi eq)`

_Type_: **[WarehouseZones](Logistics.Wms.WarehouseZones.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

