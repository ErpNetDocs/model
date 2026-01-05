---
uid: Regulatory.Vat.DeclarationAmountDetails
---
# Regulatory.Vat.DeclarationAmountDetails View

**Namespace:** [Regulatory.Vat](Regulatory.Vat.md)  

Base data for calculation of Vat Box amounts. Entity: VAT_Declaration_Box_Deal_Type_Amounts (Introduced in version 23.1.2.31)

## Default Visualization
Default Display Text Format:  
_{AmountValue}: {BoxId}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

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

_Type_: **[Amount (15, 2)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### BaseCurrency

The base currency for summary reporting for Enterprise Company at the moment of entry generation. `Required` `Filter(multi eq)` `Inherited from VAT_Entries_Table.Base_Currency_Id` `Introduced in version 25.1.3.53`

_Type_: **[Currencies](General.Currencies.Currencies.md)**  
_Category_: **System**  
_Inherited From_: **VAT_Entries_Table.Base_Currency_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Box

The type of box in a VAT declaration. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Box_Types_Table.Box_Type_Id`

_Type_: **[BoxTypes](Regulatory.Vat.BoxTypes.md)**  
_Category_: **System**  
_Inherited From_: **VAT_Box_Types_Table.Box_Type_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### Declaration

The VAT declaration. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Declarations_Table.Declaration_Id`

_Type_: **[Declarations](Regulatory.Vat.Declarations.md)**  
_Category_: **System**  
_Inherited From_: **VAT_Declarations_Table.Declaration_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  

### VATEntry

Unique identification number of this VAT entry. `Required` `Default(New Guid)` `Filter(multi eq)` `Inherited from VAT_Entries_Table.Entry_Id`

_Type_: **[Entries](Regulatory.Vat.Entries.md)**  
_Category_: **System**  
_Inherited From_: **VAT_Entries_Table.Entry_Id**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Entity Set: 
Regulatory_Vat_DeclarationAmountDetails

Domain API Entity Type: 
Regulatory_Vat_DeclarationAmountDetail

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Vat_DeclarationAmountDetails?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Vat_DeclarationAmountDetails?$top=10>

