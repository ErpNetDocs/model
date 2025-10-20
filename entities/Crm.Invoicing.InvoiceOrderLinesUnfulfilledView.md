---
uid: Crm.Invoicing.InvoiceOrderLinesUnfulfilledView
---
# Crm.Invoicing.InvoiceOrderLinesUnfulfilledView View

**Namespace:** [Crm.Invoicing](Crm.Invoicing.md)  

Returns the uninvoiced (unfulfilled) Invoice Order Lines from Invoice Orders, which are Released. Is_Fulfilled and Is_QuantityFulfilled can be used to filter out lines which appear fulfilled. For best performance, the invoice orders should be finished after fulfilling. Entity: Crm_Invoice_Order_Lines_Unfulfilled_View (Introduced in version 24.1.5.17)

## Default Visualization
Default Display Text Format:  
_{IsFulfilled}: {IsQuantityFulfilled}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _CannotBeShown_  
API access:  _ReadWrite_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Invoicing.InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)  
Aggregate Root:  
[Crm.Invoicing.InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsFulfilled](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#isfulfilled) | boolean | Returns true when both the Quantity and Amount are fulfilled or only negligible (less than 0.001 for qty and 0.01 for amount) sums remain. Please note, that filtering by this field forces full scan and calculation of remaining quantities and amounts for all non-finished invoice orders. For best performance, the invoice orders should be finished after fulfilling. `Required` `Filter(eq)` 
| [IsQuantityFulfilled](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#isquantityfulfilled) | boolean | Returns true when the Quantity is fulfilled or only negligible (less than 0.001) sum remains. Please note, that filtering by this field forces full scan and calculation of remaining quantities and amounts for all non-finished invoice orders. For best performance, the invoice orders should be finished after fulfilling. `Required` `Filter(eq)` 
| [OrderRemainingLineAmount](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#orderremaininglineamount) | decimal (38, 2) | The uninvoiced (unfulfilled) line amount of the invoice order line. `Required` `Filter(multi eq;ge;le)` 
| [OrderRemaining<br />StandardQuantity](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#orderremainingstandardquantity) | decimal (38, 6) | The uninvoiced (unfulfilled) quantity of the invoice order line in base measurement unit. `Required` `Filter(multi eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [InvoiceOrder](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#invoiceorder) | [InvoiceOrders](Crm.Invoicing.InvoiceOrders.md) | The invoice order to which the invoice order line belongs. `Required` `Filter(multi eq)` `Inherited from Crm_Invoice_Order_<br />Lines_Table.Invoice_Order_Id` `Introduced in version 24.1.5.19` `Owner` |
| [InvoiceOrderLine](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#invoiceorderline) | [InvoiceOrderLines](Crm.Invoicing.InvoiceOrderLines.md) (nullable) | Invoice order line which is invoiced by this line. `Filter(multi eq)` `Inherited from Crm_Invoice_Lines_Table.Invoice_Order_Line_Id` `Introduced in version 24.1.5.19` `FilterableReference` |
| [SalesOrder](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | When not null specifies the Sales Order that is ordered to be invoiced by this line. `Filter(multi eq)` `Inherited from Crm_Invoice_Order_<br />Lines_Table.Sales_Order_Id` `Introduced in version 24.1.5.19` |
| [SalesOrderLine](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#salesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable) | When not null specifies the Sales Order line that is ordered to be invoiced by this line. `Filter(multi eq)` `Inherited from Crm_Invoice_Order_<br />Lines_Table.Sales_Order_Line_Id` `Introduced in version 24.1.5.19` |
| [TransactionLine](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable) | The store transaction line that is to be invoiced by this line, for Business Reason = S. `Filter(multi eq)` `Inherited from Crm_Invoice_Order_<br />Lines_Table.Transaction_Line_Id` `Introduced in version 24.1.5.19` |


## Attribute Details

### IsFulfilled

Returns true when both the Quantity and Amount are fulfilled or only negligible (less than 0.001 for qty and 0.01 for amount) sums remain. Please note, that filtering by this field forces full scan and calculation of remaining quantities and amounts for all non-finished invoice orders. For best performance, the invoice orders should be finished after fulfilling. `Required` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### IsQuantityFulfilled

Returns true when the Quantity is fulfilled or only negligible (less than 0.001) sum remains. Please note, that filtering by this field forces full scan and calculation of remaining quantities and amounts for all non-finished invoice orders. For best performance, the invoice orders should be finished after fulfilling. `Required` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OrderRemainingLineAmount

The uninvoiced (unfulfilled) line amount of the invoice order line. `Required` `Filter(multi eq;ge;le)`

_Type_: **decimal (38, 2)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OrderRemainingStandardQuantity

The uninvoiced (unfulfilled) quantity of the invoice order line in base measurement unit. `Required` `Filter(multi eq;ge;le)`

_Type_: **decimal (38, 6)**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### InvoiceOrder

The invoice order to which the invoice order line belongs. `Required` `Filter(multi eq)` `Inherited from Crm_Invoice_Order_Lines_Table.Invoice_Order_Id` `Introduced in version 24.1.5.19` `Owner`

_Type_: **[InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)**  
_Category_: **System**  
_Inherited From_: **Crm_Invoice_Order_Lines_Table.Invoice_Order_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### InvoiceOrderLine

Invoice order line which is invoiced by this line. `Filter(multi eq)` `Inherited from Crm_Invoice_Lines_Table.Invoice_Order_Line_Id` `Introduced in version 24.1.5.19` `FilterableReference`

_Type_: **[InvoiceOrderLines](Crm.Invoicing.InvoiceOrderLines.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Crm_Invoice_Lines_Table.Invoice_Order_Line_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### SalesOrder

When not null specifies the Sales Order that is ordered to be invoiced by this line. `Filter(multi eq)` `Inherited from Crm_Invoice_Order_Lines_Table.Sales_Order_Id` `Introduced in version 24.1.5.19`

_Type_: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Crm_Invoice_Order_Lines_Table.Sales_Order_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### SalesOrderLine

When not null specifies the Sales Order line that is ordered to be invoiced by this line. `Filter(multi eq)` `Inherited from Crm_Invoice_Order_Lines_Table.Sales_Order_Line_Id` `Introduced in version 24.1.5.19`

_Type_: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Crm_Invoice_Order_Lines_Table.Sales_Order_Line_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### TransactionLine

The store transaction line that is to be invoiced by this line, for Business Reason = S. `Filter(multi eq)` `Inherited from Crm_Invoice_Order_Lines_Table.Transaction_Line_Id` `Introduced in version 24.1.5.19`

_Type_: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable)**  
_Category_: **System**  
_Inherited From_: **Crm_Invoice_Order_Lines_Table.Transaction_Line_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set:
Crm_Invoicing_InvoiceOrderLinesUnfulfilledView

Domain API Entity Type:
Crm_Invoicing_InvoiceOrderLinesUnfulfilledViewEntry

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/Crm_Invoicing_InvoiceOrderLinesUnfulfilledView?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#Crm_Invoicing_InvoiceOrderLinesUnfulfilledView?$top=10>

