---
uid: Finance.Excise.TaxWarehouseMeasuringTransactions
---
# Finance.Excise.TaxWarehouseMeasuringTransactions Entity

Transaction of product input or output, measured with specialized measuring device for excise purposes. Entity: Exc_Tax_Warehouse_Measuring_Transactions (Introduced in version 21.1.1.9)

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AlcoholDegree](Finance.Excise.TaxWarehouseMeasuringTransactions.md#alcoholdegree) | int32 (nullable) | For alcoholic products, contains the percentage of pure alcohol. null when the transaction is not for alcoholic products. [Filter(multi eq;ge;le)] 
| [AlcoholDensity](Finance.Excise.TaxWarehouseMeasuringTransactions.md#alcoholdensity) | int32 (nullable) | For alcoholic products, contains the average density for the whole transaction. The measurement unit is dependent on the applicable legislation. null for non-alcoholic products. [Filter(multi eq;ge;le)] 
| [AlcoholTemperature](Finance.Excise.TaxWarehouseMeasuringTransactions.md#alcoholtemperature) | int32 (nullable) | For alcoholic products, contains the temperature of the fluid, when Alcohol Degree was calculated. The measurement unit is dependent on the national regulation (usually Celsius). null for non-alcoholic products. [Filter(multi eq;ge;le)] 
| [Direction](Finance.Excise.TaxWarehouseMeasuringTransactions.md#direction) | [Direction](Finance.Excise.TaxWarehouseMeasuringTransactions.md#direction) | The direction of the transaction - IN/OUT. [Required] 
| [EndTimeUtc](Finance.Excise.TaxWarehouseMeasuringTransactions.md#endtimeutc) | datetime | Ending time of the transaction (in UTC time). [Required] [Filter(eq;ge;le)] 
| [Id](Finance.Excise.TaxWarehouseMeasuringTransactions.md#id) | guid |  
| [MeasuringDeviceCode](Finance.Excise.TaxWarehouseMeasuringTransactions.md#measuringdevicecode) | string | The code of the measuring device, used to measure the transaction. [Required] [Filter(multi eq;like)] [ORD] 
| [Notes](Finance.Excise.TaxWarehouseMeasuringTransactions.md#notes) | string (nullable) | Notes for this TaxWarehouseMeasuring<br />Transaction. 
| [Quantity](Finance.Excise.TaxWarehouseMeasuringTransactions.md#quantity) | [Quantity](../data-types.md#quantity) | The quantity of the product, measured with this transaction. [Unit: QuantityUnit] [Required] [Filter(eq;ge;le)] 
| [StartTimeUtc](Finance.Excise.TaxWarehouseMeasuringTransactions.md#starttimeutc) | datetime | Starting time of the transaction (in UTC time). [Required] [Filter(eq;ge;le)] 
| [TransactionNumber](Finance.Excise.TaxWarehouseMeasuringTransactions.md#transactionnumber) | string | Transaction number, unique for the measuring device. [Required] [Filter(multi eq;like)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Product](Finance.Excise.TaxWarehouseMeasuringTransactions.md#product) | [Products](General.Products.Products.md) | The product, which was being measured. [Required] [Filter(multi eq)] |
| [QuantityUnit](Finance.Excise.TaxWarehouseMeasuringTransactions.md#quantityunit) | [MeasurementUnits](General.MeasurementUnits.md) | The measurement unit of Quantity. [Required] [Filter(multi eq)] |
| [TaxWarehouse](Finance.Excise.TaxWarehouseMeasuringTransactions.md#taxwarehouse) | [TaxWarehouses](Finance.Excise.TaxWarehouses.md) | The tax warehouse, where the transaction occurred. [Required] [Filter(multi eq)] |


## Attribute Details

### AlcoholDegree

For alcoholic products, contains the percentage of pure alcohol. null when the transaction is not for alcoholic products. [Filter(multi eq;ge;le)]

_Type_: **int32 (nullable)**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  

### AlcoholDensity

For alcoholic products, contains the average density for the whole transaction. The measurement unit is dependent on the applicable legislation. null for non-alcoholic products. [Filter(multi eq;ge;le)]

_Type_: **int32 (nullable)**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  

### AlcoholTemperature

For alcoholic products, contains the temperature of the fluid, when Alcohol Degree was calculated. The measurement unit is dependent on the national regulation (usually Celsius). null for non-alcoholic products. [Filter(multi eq;ge;le)]

_Type_: **int32 (nullable)**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  

### Direction

The direction of the transaction - IN/OUT. [Required]

_Type_: **[Direction](Finance.Excise.TaxWarehouseMeasuringTransactions.md#direction)**  
Allowed values for the [Direction](Finance.Excise.TaxWarehouseMeasuringTransactions.md#direction) data attribute  
_Allowed Values (Finance.Excise.TaxWarehouseMeasuringTransactionsRepository.Direction Enum Members)_  

| Value | Description |
| ---- | --- |
| IN | IN value. Stored as 'I'. <br /> _Database Value:_ 'I' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'IN' |
| OUT | OUT value. Stored as 'O'. <br /> _Database Value:_ 'O' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'OUT' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### EndTimeUtc

Ending time of the transaction (in UTC time). [Required] [Filter(eq;ge;le)]

_Type_: **datetime**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### Id

_Type_: **guid**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  

### MeasuringDeviceCode

The code of the measuring device, used to measure the transaction. [Required] [Filter(multi eq;like)] [ORD]

_Type_: **string**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **True**  

### Notes

Notes for this TaxWarehouseMeasuringTransaction.

_Type_: **string (nullable)**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  

### Quantity

The quantity of the product, measured with this transaction. [Unit: QuantityUnit] [Required] [Filter(eq;ge;le)]

_Type_: **[Quantity](../data-types.md#quantity)**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### StartTimeUtc

Starting time of the transaction (in UTC time). [Required] [Filter(eq;ge;le)]

_Type_: **datetime**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  

### TransactionNumber

Transaction number, unique for the measuring device. [Required] [Filter(multi eq;like)]

_Type_: **string**  
_Supported Filters_: **Equals, Like, EqualsIn**  
_Supports Order By_: **False**  


## Reference Details

### Product

The product, which was being measured. [Required] [Filter(multi eq)]

_Type_: **[Products](General.Products.Products.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### QuantityUnit

The measurement unit of Quantity. [Required] [Filter(multi eq)]

_Type_: **[MeasurementUnits](General.MeasurementUnits.md)**  
_Supported Filters_: **Equals, EqualsIn**  

### TaxWarehouse

The tax warehouse, where the transaction occurred. [Required] [Filter(multi eq)]

_Type_: **[TaxWarehouses](Finance.Excise.TaxWarehouses.md)**  
_Supported Filters_: **Equals, EqualsIn**  



## Business Rules

[!list erp.entity=Finance.Excise.TaxWarehouseMeasuringTransactions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list erp.entity=Finance.Excise.TaxWarehouseMeasuringTransactions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Finance_Excise_TaxWarehouseMeasuringTransactions?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Finance_Excise_TaxWarehouseMeasuringTransactions?$top=10>

