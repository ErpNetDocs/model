---
uid: Crm.Invoicing.InvoiceOrderLinesUnfulfilledView
---
# Crm.Invoicing.InvoiceOrderLinesUnfulfilledView (View)


Returns the uninvoiced (unfulfilled) Invoice Order Lines from Invoice Orders, which are Released. Is_Fulfilled and Is_QuantityFulfilled can be used to filter out lines which appear fulfilled. For best performance, the invoice orders should be finished after fulfilling.

## General
Namespace: [Crm.Invoicing](Crm.Invoicing.md)  
Repository: Crm.Invoicing.InvoiceOrderLinesUnfulfilledView  
Introduced In Version: 24.1.5.17  
API access:  ReadWrite  

## Visualization
Display Format: {IsFulfilled}: {IsQuantityFulfilled}  
Search Members:   
Category:  Views  
Show in UI:  CannotBeShown  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Invoicing.InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)  
Aggregate Root:  
[Crm.Invoicing.InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [IsFulfilled](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#isfulfilled) | boolean | Returns true when both the Quantity and Amount are fulfilled or only negligible (less than 0.001 for qty and 0.01 for amount) sums remain. Please note, that filtering by this field forces full scan and calculation of remaining quantities and amounts for all non-finished invoice orders. For best performance, the invoice orders should be finished after fulfilling.[Required] [Filter(eq)] 
| [IsQuantityFulfilled](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#isquantityfulfilled) | boolean | Returns true when the Quantity is fulfilled or only negligible (less than 0.001) sum remains. Please note, that filtering by this field forces full scan and calculation of remaining quantities and amounts for all non-finished invoice orders. For best performance, the invoice orders should be finished after fulfilling.[Required] [Filter(eq)] 
| [OrderRemainingLineAmount](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#orderremaininglineamount) | decimal (38, 2) | The uninvoiced (unfulfilled) line amount of the invoice order line.[Required] [Filter(multi eq;ge;le)] 
| [OrderRemaining<br />StandardQuantity](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#orderremainingstandardquantity) | decimal (38, 6) | The uninvoiced (unfulfilled) quantity of the invoice order line in base measurement unit.[Required] [Filter(multi eq;ge;le)] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [InvoiceOrder](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#invoiceorder) | [InvoiceOrders](Crm.Invoicing.InvoiceOrders.md) | The invoice order to which the invoice order line belongs. |
| [InvoiceOrderLine](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#invoiceorderline) | [InvoiceOrderLines](Crm.Invoicing.InvoiceOrderLines.md) (nullable) | The line containing the ordered quantity and amount. |
| [SalesOrder](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#salesorder) | [SalesOrders](Crm.Sales.SalesOrders.md) (nullable) | When not NULL specifies the sales order that is ordered to be invoiced by the invoice order line. |
| [SalesOrderLine](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#salesorderline) | [SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable) | When not NULL specifies the sales order line that is ordered to be invoiced by the invoice order line. |
| [TransactionLine](Crm.Invoicing.InvoiceOrderLinesUnfulfilledView.md#transactionline) | [StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable) | When not NULL specifies the store transaction line that is to be invoiced by the invoice order line. |


## Attribute Details

### IsFulfilled

Returns true when both the Quantity and Amount are fulfilled or only negligible (less than 0.001 for qty and 0.01 for amount) sums remain. Please note, that filtering by this field forces full scan and calculation of remaining quantities and amounts for all non-finished invoice orders. For best performance, the invoice orders should be finished after fulfilling.[Required] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### IsQuantityFulfilled

Returns true when the Quantity is fulfilled or only negligible (less than 0.001) sum remains. Please note, that filtering by this field forces full scan and calculation of remaining quantities and amounts for all non-finished invoice orders. For best performance, the invoice orders should be finished after fulfilling.[Required] [Filter(eq)]

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OrderRemainingLineAmount

The uninvoiced (unfulfilled) line amount of the invoice order line.[Required] [Filter(multi eq;ge;le)]

Type: **decimal (38, 2)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### OrderRemainingStandardQuantity

The uninvoiced (unfulfilled) quantity of the invoice order line in base measurement unit.[Required] [Filter(multi eq;ge;le)]

Type: **decimal (38, 6)**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### InvoiceOrder

The invoice order to which the invoice order line belongs.

Type: **[InvoiceOrders](Crm.Invoicing.InvoiceOrders.md)**  
Category: **System**  
Inherited From: **Crm_Invoice_Order_Lines_Table.Invoice_Order_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### InvoiceOrderLine

The line containing the ordered quantity and amount.

Type: **[InvoiceOrderLines](Crm.Invoicing.InvoiceOrderLines.md) (nullable)**  
Category: **System**  
Inherited From: **Crm_Invoice_Lines_Table.Invoice_Order_Line_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### SalesOrder

When not NULL specifies the sales order that is ordered to be invoiced by the invoice order line.

Type: **[SalesOrders](Crm.Sales.SalesOrders.md) (nullable)**  
Category: **System**  
Inherited From: **Crm_Invoice_Order_Lines_Table.Sales_Order_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### SalesOrderLine

When not NULL specifies the sales order line that is ordered to be invoiced by the invoice order line.

Type: **[SalesOrderLines](Crm.Sales.SalesOrderLines.md) (nullable)**  
Category: **System**  
Inherited From: **Crm_Invoice_Order_Lines_Table.Sales_Order_Line_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TransactionLine

When not NULL specifies the store transaction line that is to be invoiced by the invoice order line.

Type: **[StoreTransactionLines](Logistics.Inventory.StoreTransactionLines.md) (nullable)**  
Category: **System**  
Inherited From: **Crm_Invoice_Order_Lines_Table.Transaction_Line_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Crm_Invoicing_InvoiceOrderLinesUnfulfilledView

Domain API Entity Type: 
Crm_Invoicing_InvoiceOrderLinesUnfulfilledViewEntry

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Invoicing_InvoiceOrderLinesUnfulfilledView?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Invoicing_InvoiceOrderLinesUnfulfilledView?$top=10>

