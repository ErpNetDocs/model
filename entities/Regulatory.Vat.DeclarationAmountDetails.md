---
uid: Regulatory.Vat.DeclarationAmountDetails
---
# Regulatory.Vat.DeclarationAmountDetails (View)


Base data for calculation of Vat Box amounts.

## General
Namespace: [Regulatory.Vat](Regulatory.Vat.md)  
Repository: Regulatory.Vat.DeclarationAmountDetails  
Introduced In Version: 23.1.2.31  
API access:  ReadWrite  

## Visualization
Display Format: {AmountValue}: {BoxId}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Regulatory.Vat.DeclarationAmountDetails](Regulatory.Vat.DeclarationAmountDetails.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Amount](Regulatory.Vat.DeclarationAmountDetails.md#amount) | [Amount (15, 2)](../data-types.md#amount) | The amount of the operation according to the category. `Currency: BaseCurrency` `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [BaseCurrency](Regulatory.Vat.DeclarationAmountDetails.md#basecurrency) | [Currencies](General.Currencies.Currencies.md) | The base currency for summary reporting for Enterprise Company at the moment of entry generation. `Required` `Filter(multi eq)` `Inherited from VAT_Entries_Table.Base_Currency_Id` `Introduced in version 25.1.3.53` |
| [Box](Regulatory.Vat.DeclarationAmountDetails.md#box) | [BoxTypes](Regulatory.Vat.BoxTypes.md) | The type of box in a VAT declaration. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Box_Types_Table.Box_Type_Id` |
| [Declaration](Regulatory.Vat.DeclarationAmountDetails.md#declaration) | [Declarations](Regulatory.Vat.Declarations.md) | The VAT declaration. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Declarations_Table.Declaration_Id` |
| [VATEntry](Regulatory.Vat.DeclarationAmountDetails.md#vatentry) | [Entries](Regulatory.Vat.Entries.md) | Unique identification number of this VAT entry. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Entries_Table.Entry_Id` |


## Attribute Details

### Amount

The amount of the operation according to the category. `Currency: BaseCurrency` `Required`

Type: **[Amount (15, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  


## Reference Details

### BaseCurrency

The base currency for summary reporting for Enterprise Company at the moment of entry generation. `Required` `Filter(multi eq)` `Inherited from VAT_Entries_Table.Base_Currency_Id` `Introduced in version 25.1.3.53`

Type: **[Currencies](General.Currencies.Currencies.md)**  
Category: **System**  
Inherited From: **VAT_Entries_Table.Base_Currency_Id**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Box

The type of box in a VAT declaration. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Box_Types_Table.Box_Type_Id`

Type: **[BoxTypes](Regulatory.Vat.BoxTypes.md)**  
Category: **System**  
Inherited From: **VAT_Box_Types_Table.Box_Type_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### Declaration

The VAT declaration. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Declarations_Table.Declaration_Id`

Type: **[Declarations](Regulatory.Vat.Declarations.md)**  
Category: **System**  
Inherited From: **VAT_Declarations_Table.Declaration_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  

### VATEntry

Unique identification number of this VAT entry. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Entries_Table.Entry_Id`

Type: **[Entries](Regulatory.Vat.Entries.md)**  
Category: **System**  
Inherited From: **VAT_Entries_Table.Entry_Id**  
Supported Filters: **Equals, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Regulatory_Vat_DeclarationAmountDetails

Domain API Entity Type: 
Regulatory_Vat_DeclarationAmountDetail

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Vat_DeclarationAmountDetails?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Vat_DeclarationAmountDetails?$top=10>

