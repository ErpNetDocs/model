---
uid: General.ProductGroupsLevelNames
---
# General.ProductGroupsLevelNames View

**Namespace:** [General](General.md)  

Provides the names of the product groups in the same branch from level 1 to 6. Entity: Gen_Product_Groups_Level_Names (Introduced in version 21.1.2.26)

## Default Visualization
Default Display Text Format:  
_{L1Name}: {L2Name}_  
Default Search Members:  
__  
Category:  _Views_  
Show in UI:  _CannotBeShown_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [General.ProductGroupsLevelNames](General.ProductGroupsLevelNames.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [L1Name](General.ProductGroupsLevelNames.md#l1name) | string (180) | The name of the level 1 parent group. `Required` 
| [L2Name](General.ProductGroupsLevelNames.md#l2name) | string (180) | The name of the level 2 parent group. `Required` 
| [L3Name](General.ProductGroupsLevelNames.md#l3name) | string (180) | The name of the level 3 parent group. `Required` 
| [L4Name](General.ProductGroupsLevelNames.md#l4name) | string (180) | The name of the level 4 parent group. `Required` 
| [L5Name](General.ProductGroupsLevelNames.md#l5name) | string (180) | The name of the level 5 parent group. `Required` 
| [L6Name](General.ProductGroupsLevelNames.md#l6name) | string (180) | The name of the level 6 parent group. `Required` 


## Attribute Details

### L1Name

The name of the level 1 parent group. `Required`

_Type_: **string (180)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **180**  
_Show in UI_: **ShownByDefault**  

### L2Name

The name of the level 2 parent group. `Required`

_Type_: **string (180)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **180**  
_Show in UI_: **ShownByDefault**  

### L3Name

The name of the level 3 parent group. `Required`

_Type_: **string (180)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **180**  
_Show in UI_: **ShownByDefault**  

### L4Name

The name of the level 4 parent group. `Required`

_Type_: **string (180)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **180**  
_Show in UI_: **ShownByDefault**  

### L5Name

The name of the level 5 parent group. `Required`

_Type_: **string (180)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **180**  
_Show in UI_: **ShownByDefault**  

### L6Name

The name of the level 6 parent group. `Required`

_Type_: **string (180)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **180**  
_Show in UI_: **ShownByDefault**  


## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_ProductGroupsLevelNames?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_ProductGroupsLevelNames?$top=10>

