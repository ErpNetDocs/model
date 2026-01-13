---
uid: Projects.Classic.WorkReportMaterials
---
# Projects.Classic.WorkReportMaterials Entity

**Namespace:** [Projects.Classic](Projects.Classic.md)  

Each record contains a consumed material, reported by the related Work Report. Entity: Prj_Work_Report_Materials

## Default Visualization
Default Display Text Format:  
_{WorkReport.EntityName}_  
Default Search Members:  
_WorkReport.EntityName_  
Name Data Member:  
_WorkReport.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Projects.Classic.WorkReports](Projects.Classic.WorkReports.md)  
Aggregate Root:  
[Projects.Classic.WorkReports](Projects.Classic.WorkReports.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Projects.Classic.WorkReportMaterials.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Projects.Classic.WorkReportMaterials.md#id) | guid |  
| [ObjectVersion](Projects.Classic.WorkReportMaterials.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [Quantity](Projects.Classic.WorkReportMaterials.md#quantity) | decimal (9, 3) | The consumed quantity of the material. `Required` `Default(0)` `Filter(eq;like)` 
| [QuantityBase](Projects.Classic.WorkReportMaterials.md#quantitybase) | decimal (9, 3) | The equivalence of Quantity in the base measurement unit of the Material. `Required` `Default(0)` `Filter(eq;like)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [MaterialProduct](Projects.Classic.WorkReportMaterials.md#materialproduct) | [Products](General.Products.Products.md) | The consumed material. `Required` `Filter(multi eq)` |
| [ProjectTask](Projects.Classic.WorkReportMaterials.md#projecttask) | [ProjectTasks](Projects.Classic.ProjectTasks.md) | The project task for which the materials are reported. `Required` `Filter(multi eq)` |
| [QuantityUnit](Projects.Classic.WorkReportMaterials.md#quantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) | The measurement unit of Quantity. It is strongly suggested that the same unit is used for planning and usage reporting. `Required` `Filter(multi eq)` |
| [WorkReport](Projects.Classic.WorkReportMaterials.md#workreport) | [WorkReports](Projects.Classic.WorkReports.md) | The <see cref="WorkReport"/> to which this WorkReportMaterial belongs. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

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

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### Quantity

The consumed quantity of the material. `Required` `Default(0)` `Filter(eq;like)`

_Type_: **decimal (9, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

### QuantityBase

The equivalence of Quantity in the base measurement unit of the Material. `Required` `Default(0)` `Filter(eq;like)` `ReadOnly`

_Type_: **decimal (9, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
_Supports Order By_: **False**  
_Default Value_: **0**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`IIF( ( ( obj.QuantityUnit != null) AndAlso ( obj.MaterialProduct != null)), new Quantity( obj.Quantity, obj.QuantityUnit).ConvertTo( obj.MaterialProduct.BaseUnit, obj.MaterialProduct).Value, obj.QuantityBase)`

## Reference Details

### MaterialProduct

The consumed material. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### ProjectTask

The project task for which the materials are reported. `Required` `Filter(multi eq)`

_Type_: **[ProjectTasks](Projects.Classic.ProjectTasks.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`obj.WorkReport.ProjectTask`

_Front-End Recalc Expressions:_  
`obj.WorkReport.ProjectTask`
### QuantityUnit

The measurement unit of Quantity. It is strongly suggested that the same unit is used for planning and usage reporting. `Required` `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### WorkReport

The <see cref="WorkReport"/> to which this WorkReportMaterial belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[WorkReports](Projects.Classic.WorkReports.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  


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

[!list limit=1000 erp.entity=Projects.Classic.WorkReportMaterials erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Projects.Classic.WorkReportMaterials erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Projects_Classic_WorkReportMaterials

Domain API Entity Type: 
Projects_Classic_WorkReportMaterial

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Projects_Classic_WorkReportMaterials?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Projects_Classic_WorkReportMaterials?$top=10>

