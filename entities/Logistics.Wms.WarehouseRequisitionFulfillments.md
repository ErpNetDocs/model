---
uid: Logistics.Wms.WarehouseRequisitionFulfillments
---
# Logistics.Wms.WarehouseRequisitionFulfillments Entity

**Namespace:** [Logistics.Wms](Logistics.Wms.md)  

Fulfillment ledger for warehouse requisitions. Entity: Wms_Warehouse_Requisition_Fulfillments (Introduced in version 20.1)

## Default Visualization
Default Display Text Format:  
_{Id}: {WarehouseRequisitionId}_  
Default Search Members:  
__  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Wms.WarehouseRequisitionFulfillments](Logistics.Wms.WarehouseRequisitionFulfillments.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Logistics.Wms.WarehouseRequisitionFulfillments.md#creationtimeutc) | datetime | The exact time in UTC, when the fulfillment was created in the system. `Required` 
| [DisplayText](Logistics.Wms.WarehouseRequisitionFulfillments.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [FulfillmentType](Logistics.Wms.WarehouseRequisitionFulfillments.md#fulfillmenttype) | string (1) | Type of fulfillment: P=Plan created; C=Requisition completed. `Required` 
| [Id](Logistics.Wms.WarehouseRequisitionFulfillments.md#id) | guid |  
| [IsFinal](Logistics.Wms.WarehouseRequisitionFulfillments.md#isfinal) | boolean | Specifies whether this fulfillment finalizes the requisition line, regardless of any remaining quantities. `Required` 
| [ObjectVersion](Logistics.Wms.WarehouseRequisitionFulfillments.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Logistics.Wms.WarehouseRequisitionFulfillments.md#quantity) | decimal (12, 3) | Quantity fulfilled (in the measurement unit of the requisition line). `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Logistics.Wms.WarehouseRequisitionFulfillments.md#creationuser) | [Users](Systems.Security.Users.md) | The user, who created the record. `Required` `Filter(multi eq)` |
| [WarehouseRequisition](Logistics.Wms.WarehouseRequisitionFulfillments.md#warehouserequisition) | [WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md) | The warehouse requisiton, which is fulfilled. `Required` `Filter(multi eq)` |
| [WarehouseRequisitionLine](Logistics.Wms.WarehouseRequisitionFulfillments.md#warehouserequisitionline) | [WarehouseRequisitionLines](Logistics.Wms.WarehouseRequisitionLines.md) | The requisition line, which is fulfilled. `Required` `Filter(multi eq)` |


## Attribute Details

### CreationTimeUtc

The exact time in UTC, when the fulfillment was created in the system. `Required`

_Type_: **datetime**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### FulfillmentType

Type of fulfillment: P=Plan created; C=Requisition completed. `Required`

_Type_: **string (1)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **1**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsFinal

Specifies whether this fulfillment finalizes the requisition line, regardless of any remaining quantities. `Required`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  

### Quantity

Quantity fulfilled (in the measurement unit of the requisition line). `Required`

_Type_: **decimal (12, 3)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### CreationUser

The user, who created the record. `Required` `Filter(multi eq)`

_Type_: **[Users](Systems.Security.Users.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### WarehouseRequisition

The warehouse requisiton, which is fulfilled. `Required` `Filter(multi eq)`

_Type_: **[WarehouseRequisitions](Logistics.Wms.WarehouseRequisitions.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  

### WarehouseRequisitionLine

The requisition line, which is fulfilled. `Required` `Filter(multi eq)`

_Type_: **[WarehouseRequisitionLines](Logistics.Wms.WarehouseRequisitionLines.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#general.custompropertyvalue)**  
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



## Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseRequisitionFulfillments erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Wms.WarehouseRequisitionFulfillments erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseRequisitionFulfillments?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseRequisitionFulfillments?$top=10>

