---
uid: Systems.Documents.Printouts
---
# Systems.Documents.Printouts Entity

**Namespace:** [Systems.Documents](Systems.Documents.md)  

Contains data about binding of printout layouts to specific user-defined document types. Entity: Gen_Printouts

## Renames

Old name: **General.Printouts**  
New name: **Systems.Documents.Printouts**  
Version: **24.1.5.35**  
Case: **35911**  



## Default Visualization
Default Display Text Format:  
_{Name}_  
Default Search Members:  
_Name_  
Name Data Member:  
_Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  
Aggregate Root:  
[Systems.Documents.DocumentTypes](Systems.Documents.DocumentTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [AllowPrintingOnState](Systems.Documents.Printouts.md#allowprintingonstate) | [AllowPrintingOnState](Systems.Documents.Printouts.md#allowprintingonstate) | The user can print documents only with state equal or greater than Allow_Printing_On_State. `Required` `Default(0)` 
| [ApplicationName](Systems.Documents.Printouts.md#applicationname) | string (64) | The application which stored and uses the printout. `Required` 
| [BackwardCompatibility](Systems.Documents.Printouts.md#backwardcompatibility) | boolean | Obsolete. Not used. `Required` `Default(false)` 
| [Copies](Systems.Documents.Printouts.md#copies) | int32 | Number of copies that should be printed when using direct printing. `Required` `Default(1)` 
| [Definition](Systems.Documents.Printouts.md#definition) | string (max) __nullable__ | Obsolete. Not used. 
| [DefinitionFormat](Systems.Documents.Printouts.md#definitionformat) | string (16) __nullable__ | Obsolete. Not used. `Default("default")` 
| [DisplayText](Systems.Documents.Printouts.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Systems.Documents.Printouts.md#id) | guid |  
| [IsDefault](Systems.Documents.Printouts.md#isdefault) | boolean | True if this is the default printout for the application form. `Required` `Default(false)` `Filter(eq)` 
| [Name](Systems.Documents.Printouts.md#name) | string (64) | The name of the printout. Unique within the application form. `Required` `Filter(like)` 
| [Notes](Systems.Documents.Printouts.md#notes) | string (512) __nullable__ | Notes for this Printout. 
| [ObjectVersion](Systems.Documents.Printouts.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Ord](Systems.Documents.Printouts.md#ord) | int32 | Order in the list of printouts when using direct printing. `Required` `Default(0)` 
| [OrdFilterXml](Systems.Documents.Printouts.md#ordfilterxml) | dataaccessfilter __nullable__ | The condition, required to be matched in order for the printout to be executed upon "Print All" command. `Unit: obj.DocumentType.EntityName` 
| [OrdPriority](Systems.Documents.Printouts.md#ordpriority) | int32 __nullable__ | Ordinal position and priority of the printout, in regard to other printouts within the current document type. Used for sorting, when executing printouts with "Print All" command. `Default(0)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [DocumentType](Systems.Documents.Printouts.md#documenttype) | [DocumentTypes](Systems.Documents.DocumentTypes.md) | The document type to which this printout layout is bound. `Required` `Filter(multi eq)` `Owner` |
| [EnterpriseCompany](Systems.Documents.Printouts.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Printout applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [FiscalReceiptTemplate](Systems.Documents.Printouts.md#fiscalreceipttemplate) | [FiscalReceiptTemplates](Crm.Pos.FiscalReceiptTemplates.md) (nullable) | Template for customizing the fiscal receipt. `Filter(multi eq)` `Introduced in version 24.1.4.56` |
| [PrintoutLayout](Systems.Documents.Printouts.md#printoutlayout) | [PrintoutLayouts](Systems.Documents.PrintoutLayouts.md) (nullable) | The printout layout, that is bound to the document type. `Filter(multi eq)` |
| [Report](Systems.Documents.Printouts.md#report) | [DataSources](Systems.Documents.DataSources.md) (nullable) | If not null points to a custom report that indicates which data will be loaded in the printout. `Filter(multi eq)` |


## Attribute Details

### AllowPrintingOnState

The user can print documents only with state equal or greater than Allow_Printing_On_State. `Required` `Default(0)`

_Type_: **[AllowPrintingOnState](Systems.Documents.Printouts.md#allowprintingonstate)**  
_Category_: **System**  
Allowed values for the `AllowPrintingOnState`(Systems.Documents.Printouts.md#allowprintingonstate) data attribute  
_Allowed Values (Systems.Documents.PrintoutsRepository.AllowPrintingOnState Enum Members)_  

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
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
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

The condition, required to be matched in order for the printout to be executed upon "Print All" command. `Unit: obj.DocumentType.EntityName`

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

_Type_: **[DocumentTypes](Systems.Documents.DocumentTypes.md)**  
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

_Type_: **[PrintoutLayouts](Systems.Documents.PrintoutLayouts.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Report

If not null points to a custom report that indicates which data will be loaded in the printout. `Filter(multi eq)`

_Type_: **[DataSources](Systems.Documents.DataSources.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **CannotBeShown**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
_Return Type_: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
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

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
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
    The notification subject.  
    _Type_: string  

  * **priority**  
    The notification priority.  
    _Type_: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    _Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)_  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Background' |
    | Low | Low value. Stored as 2. <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Low' |
    | Normal | Normal value. Stored as 3. <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Normal' |
    | High | High value. Stored as 4. <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Urgent' |

     _Optional_: True  
    _Default Value_: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
_Return Type_: **EntityObject**  
_Declaring Type_: **EntityObject**  
_Domain API Request_: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Systems.Documents.Printouts erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Documents.Printouts erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Documents_Printouts

Domain API Entity Type: 
Systems_Documents_Printout

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Documents_Printouts?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Documents_Printouts?$top=10>

