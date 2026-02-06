---
uid: Systems.Core.AttributeChanges
---
# Systems.Core.AttributeChanges (View)


Attribute values of an object change

## General
Namespace: [Systems.Core](Systems.Core.md)  
Repository: Systems.Core.AttributeChanges  
Introduced In Version: 23.1.2.71  
API access:  ReadWrite  

## Visualization
Display Format: {ObjectChangeId}: {AttributeName}  
Search Members:   
Category:  Views  
Show in UI:  ShownByDefault  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Core.ObjectChanges](Systems.Core.ObjectChanges.md)  
Aggregate Root:  
[Systems.Core.ObjectChangesets](Systems.Core.ObjectChangesets.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AttributeName](Systems.Core.AttributeChanges.md#attributename) | string (64) | The attribute name[Required] [Filter(eq)] [Inherited from Sys_Attribute_<br />Changes_Table.Attribute_Name] 
| [NewValue](Systems.Core.AttributeChanges.md#newvalue) | string (max) __nullable__ | The new value[Filter(eq;like)] [Inherited from Sys_Attribute_<br />Changes_Table.New_Value] 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ObjectChange](Systems.Core.AttributeChanges.md#objectchange) | [ObjectChanges](Systems.Core.ObjectChanges.md) | The object change |


## Attribute Details

### AttributeName

The attribute name[Required] [Filter(eq)] [Inherited from Sys_Attribute_Changes_Table.Attribute_Name]

Type: **string (64)**  
Category: **System**  
Inherited From: **Sys_Attribute_Changes_Table.Attribute_Name**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **ShownByDefault**  

### NewValue

The new value[Filter(eq;like)] [Inherited from Sys_Attribute_Changes_Table.New_Value]

Type: **string (max) __nullable__**  
Category: **System**  
Inherited From: **Sys_Attribute_Changes_Table.New_Value**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  


## Reference Details

### ObjectChange

The object change

Type: **[ObjectChanges](Systems.Core.ObjectChanges.md)**  
Category: **System**  
Inherited From: **Sys_Attribute_Changes_Table.Object_Change_Id**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  


## API

Domain API Entity Set: 
Systems_Core_AttributeChanges

Domain API Entity Type: 
Systems_Core_AttributeChange

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Core_AttributeChanges?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Core_AttributeChanges?$top=10>

