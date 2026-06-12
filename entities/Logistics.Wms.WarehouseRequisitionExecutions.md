---
uid: Logistics.Wms.WarehouseRequisitionExecutions
---
# Logistics.Wms.WarehouseRequisitionExecutions Entity

Execution ledger for warehouse requisitions. Entity: Wms_Warehouse_Requisition_Executions (Introduced in version 20.1)

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationTimeUtc](Logistics.Wms.WarehouseRequisitionExecutions.md#creationtimeutc) | datetime | The exact time in UTC, when the execution was created in the system. [Required] 
| [ExecutedQuantity](Logistics.Wms.WarehouseRequisitionExecutions.md#executedquantity) | decimal | The executed quantity (in the measurement unit of the requisition line). [Required] 
| [ExecutionType](Logistics.Wms.WarehouseRequisitionExecutions.md#executiontype) | string | Type of execution: P=Plan created; C=Requisition completed. [Required] 
| [Id](Logistics.Wms.WarehouseRequisitionExecutions.md#id) | guid |  
| [IsFinal](Logistics.Wms.WarehouseRequisitionExecutions.md#isfinal) | boolean | Specifies whether this execution will finalize the execution of the requisition line, regardless of any remaining quantities. [Required] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CreationUser](Logistics.Wms.WarehouseRequisitionExecutions.md#creationuser) | [Users](Systems.Security.Users.md) | The user, who created the record. [Required] [Filter(multi eq)] |
| [WarehouseRequisitionLine](Logistics.Wms.WarehouseRequisitionExecutions.md#warehouserequisitionline) | [WarehouseRequisitionLines](Logistics.Wms.WarehouseRequisitionLines.md) | The requisition line, which is executed. [Required] [Filter(multi eq)] |


## Attribute Details

### CreationTimeUtc

The exact time in UTC, when the execution was created in the system. [Required]

_Type_: **datetime**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ExecutedQuantity

The executed quantity (in the measurement unit of the requisition line). [Required]

_Type_: **decimal**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### ExecutionType

Type of execution: P=Plan created; C=Requisition completed. [Required]

_Type_: **string**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### IsFinal

Specifies whether this execution will finalize the execution of the requisition line, regardless of any remaining quantities. [Required]

_Type_: **boolean**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  


## Reference Details

### CreationUser

The user, who created the record. [Required] [Filter(multi eq)]

_Type_: **[Users](Systems.Security.Users.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### WarehouseRequisitionLine

The requisition line, which is executed. [Required] [Filter(multi eq)]

_Type_: **[WarehouseRequisitionLines](Logistics.Wms.WarehouseRequisitionLines.md)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Logistics.Wms.WarehouseRequisitionExecutions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Logistics.Wms.WarehouseRequisitionExecutions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Logistics_Wms_WarehouseRequisitionExecutions?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Logistics_Wms_WarehouseRequisitionExecutions?$top=10>

