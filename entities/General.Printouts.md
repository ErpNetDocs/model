---
uid: General.Printouts
---
# General.Printouts Entity

**Namespace:** [General](General.md)  

Contains data about binding of printout layouts to specific user-defined document types. Entity: Gen_Printouts
## Renamed
**New name:** [Systems.Documents.Printouts](Systems.Documents.Printouts.md)  



## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.DocumentTypes](General.DocumentTypes.md)  
Aggregate Root:  
[General.DocumentTypes](General.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowPrintingOnState](General.Printouts.md#allowprintingonstate) | [AllowPrintingOnState](General.Printouts.md#allowprintingonstate) | The user can print documents only with state equal or greater than Allow_Printing_On_State. `Required` `Default(0)` 
| [ApplicationName](General.Printouts.md#applicationname) | string (64) | The application which stored and uses the printout. `Required` 
| [BackwardCompatibility](General.Printouts.md#backwardcompatibility) | boolean | Obsolete. Not used. `Required` `Default(false)` 
| [Copies](General.Printouts.md#copies) | int32 | Number of copies that should be printed when using direct printing. `Required` `Default(1)` 
| [Definition](General.Printouts.md#definition) | string (max) __nullable__ | Obsolete. Not used. 
| [DefinitionFormat](General.Printouts.md#definitionformat) | string (16) __nullable__ | Obsolete. Not used. `Default("default")` 
| [DisplayText](General.Printouts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](General.Printouts.md#id) | guid |  
| [IsDefault](General.Printouts.md#isdefault) | boolean | True if this is the default printout for the application form. `Required` `Default(false)` `Filter(eq)` 
| [Name](General.Printouts.md#name) | string (64) | The name of the printout. Unique within the application form. `Required` `Filter(like)` 
| [Notes](General.Printouts.md#notes) | string (512) __nullable__ | Notes for this Printout. 
| [ObjectVersion](General.Printouts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Ord](General.Printouts.md#ord) | int32 | Order in the list of printouts when using direct printing. `Required` `Default(0)` 
| [OrdFilterXml](General.Printouts.md#ordfilterxml) | dataaccessfilter __nullable__ | The condition, required to be matched in order for the printout to be executed upon "Print All" command. 
| [OrdPriority](General.Printouts.md#ordpriority) | int32 __nullable__ | Ordinal position and priority of the printout, in regard to other printouts within the current document type. Used for sorting, when executing printouts with "Print All" command. `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](General.Printouts.md#documenttype) | [DocumentTypes](General.DocumentTypes.md) | The document type to which this printout layout is bound. `Required` `Filter(multi eq)` `Owner` |
| [EnterpriseCompany](General.Printouts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Printout applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [FiscalReceiptTemplate](General.Printouts.md#fiscalreceipttemplate) | [FiscalReceiptTemplates](Crm.Pos.FiscalReceiptTemplates.md) (nullable) | Template for customizing the fiscal receipt. `Filter(multi eq)` `Introduced in version 24.1.4.56` |
| [PrintoutLayout](General.Printouts.md#printoutlayout) | [PrintoutLayouts](General.PrintoutLayouts.md) (nullable) | The printout layout, that is bound to the document type. `Filter(multi eq)` |
| [Report](General.Printouts.md#report) | [DataSources](Systems.Reporting.DataSources.md) (nullable) | If not null points to a custom report that indicates which data will be loaded in the printout. `Filter(multi eq)` |


## Attribute Details

### AllowPrintingOnState

The user can print documents only with state equal or greater than Allow_Printing_On_State. `Required` `Default(0)`

_Type_: **[AllowPrintingOnState](General.Printouts.md#allowprintingonstate)**  
_Category_: **System**  
Allowed values for the `AllowPrintingOnState`(General.Printouts.md#allowprintingonstate) data attribute  
_Allowed Values (General.PrintoutsRepository.AllowPrintingOnState Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| Planned | Planned value. Stored as 10. <br /> _Database Value:_ 10 <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Planned' |
| FirmPlanned | FirmPlanned value. Stored as 20. <br /> _Database Value:_ 20 <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'FirmPlanned' |
| Released | Released value. Stored as 30. <br /> _Database Value:_ 30 <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'Released' |
| Completed | Completed value. Stored as 40. <br /> _Database Value:_ 40 <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'Completed' |
| Closed | Closed value. Stored as 50. <br /> _Database Value:_ 50 <br /> _Model Value:_ 50 <br /> _Domain API Value:_ 'Closed' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### ApplicationName

The application which stored and uses the printout. `Required`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **CannotBeShown**  

_Back-End Default Expression:_  
`obj.Transaction.ApplicationName`

### BackwardCompatibility

Obsolete. Not used. `Required` `Default(false)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **CannotBeShown**  

### Copies

Number of copies that should be printed when using direct printing. `Required` `Default(1)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **1**  
_Show in UI_: **ShownByDefault**  

### Definition

Obsolete. Not used.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **CannotBeShown**  

### DefinitionFormat

Obsolete. Not used. `Default("default")`

_Type_: **string (16) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **16**  
_Default Value_: **default**  
_Show in UI_: **CannotBeShown**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### IsDefault

True if this is the default printout for the application form. `Required` `Default(false)` `Filter(eq)`

_Type_: **boolean**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Default Value_: **False**  
_Show in UI_: **ShownByDefault**  

### Name

The name of the printout. Unique within the application form. `Required` `Filter(like)`

_Type_: **string (64)**  
_Category_: **System**  
_Supported Filters_: **Like**  
_Supports Order By_: **False**  
_Maximum Length_: **64**  
_Show in UI_: **ShownByDefault**  

### Notes

Notes for this Printout.

_Type_: **string (512) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **512**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Ord

Order in the list of printouts when using direct printing. `Required` `Default(0)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### OrdFilterXml

The condition, required to be matched in order for the printout to be executed upon "Print All" command.

_Type_: **dataaccessfilter __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### OrdPriority

Ordinal position and priority of the printout, in regard to other printouts within the current document type. Used for sorting, when executing printouts with "Print All" command. `Default(0)`

_Type_: **int32 __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### DocumentType

The document type to which this printout layout is bound. `Required` `Filter(multi eq)` `Owner`

_Type_: **[DocumentTypes](General.DocumentTypes.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **CannotBeShown**  

### EnterpriseCompany

The Enterprise Company to which this Printout applies, or null if it is for all enterprise companies. `Filter(multi eq)`

_Type_: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **HiddenByDefault**  

### FiscalReceiptTemplate

Template for customizing the fiscal receipt. `Filter(multi eq)` `Introduced in version 24.1.4.56`

_Type_: **[FiscalReceiptTemplates](Crm.Pos.FiscalReceiptTemplates.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PrintoutLayout

The printout layout, that is bound to the document type. `Filter(multi eq)`

_Type_: **[PrintoutLayouts](General.PrintoutLayouts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Report

If not null points to a custom report that indicates which data will be loaded in the printout. `Filter(multi eq)`

_Type_: **[DataSources](Systems.Reporting.DataSources.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  


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


### CreateNotification

Creates a notification and sends a real time event to the user.  
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
    The subject.  
    _Type_: string  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=General.Printouts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=General.Printouts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Query:
<https://demodb.my.erp.net/api/domain/odata/General_Printouts?$top=10>

Domain API Query Builder:
<https://demodb.my.erp.net/api/domain/querybuilder#General_Printouts?$top=10>

