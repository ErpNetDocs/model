---
uid: Finance.Assets.DepreciationPlanLines
---
# Finance.Assets.DepreciationPlanLines


Each record contains one depreciation plan for one valuation model of one asset.

## General
Namespace: [Finance.Assets](Finance.Assets.md)  
Repository: Finance.Assets.DepreciationPlanLines  
Base Table: Ast_Depreciation_Plan_Lines  
API access:  ReadWrite  

## Visualization
Display Format: {LineNo}. {DepreciationPlan.DocumentNo} {DepreciationPlan.DocumentType.TypeName:T}  
Search Members: DepreciationPlan.DocumentNo  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Finance.Assets.DepreciationPlans](Finance.Assets.DepreciationPlans.md)  
Aggregate Root:  
[Finance.Assets.DepreciationPlans](Finance.Assets.DepreciationPlans.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DepreciationEndDate](Finance.Assets.DepreciationPlanLines.md#depreciationenddate) | datetime | End date of the depreciation plan for this asset. 
| [DepreciationStartDate](Finance.Assets.DepreciationPlanLines.md#depreciationstartdate) | datetime | Start date of the depreciation plan for this asset. 
| [LineNo](Finance.Assets.DepreciationPlanLines.md#lineno) | int32 | Consecutive number of the line within the depreciation plan. 
| [PlanDepreciationValue](Finance.Assets.DepreciationPlanLines.md#plandepreciationvalue) | [Amount (14, 2)](../data-types.md#amount) | The part of the total amount of the asset (in the currency of the asset), which is due for depreciation. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Asset](Finance.Assets.DepreciationPlanLines.md#asset) | [Assets](Finance.Assets.Assets.md) | The asset that is planned for depreciation. |
| [DepreciationMethod](Finance.Assets.DepreciationPlanLines.md#depreciationmethod) | [DepreciationMethods](Finance.Assets.DepreciationMethods.md) | Depreciation method by which the asset will be depreciated. |
| [DepreciationPlan](Finance.Assets.DepreciationPlanLines.md#depreciationplan) | [DepreciationPlans](Finance.Assets.DepreciationPlans.md) | The <see cref="DepreciationPlan"/> to which this DepreciationPlanLine belongs. `Required` `Filter(multi eq)` `Owner` |
| [Document](Finance.Assets.DepreciationPlanLines.md#document) | [DepreciationPlans](Finance.Assets.DepreciationPlans.md) | The owner document. The <see cref="DepreciationPlan"/> to which this DepreciationPlanLine belongs. `Required` `Filter(multi eq)` |
| [ValuationModel](Finance.Assets.DepreciationPlanLines.md#valuationmodel) | [ValuationModels](Finance.Assets.ValuationModels.md) | Valuation model in which the asset is accounted. |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Finance.Assets.DepreciationPlanLines.md#id) | guid |  
| [ObjectVersion](Finance.Assets.DepreciationPlanLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Finance.Assets.DepreciationPlanLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| FixedValues | [DepreciationPlanLineFixedValues](Finance.Assets.DepreciationPlanLineFixedValues.md) | List of `DepreciationPlan<br />LineFixedValue`(Finance.Assets.DepreciationPlan<br />LineFixedValues.md) child objects, based on the `Finance.Assets.DepreciationPlan<br />LineFixedValue.DepreciationPlanLine`(Finance.Assets.DepreciationPlan<br />LineFixedValues.md#depreciationplanline) back reference 


## Attribute Details

### DepreciationEndDate

End date of the depreciation plan for this asset.

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### DepreciationStartDate

Start date of the depreciation plan for this asset.

Type: **datetime**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### LineNo

Consecutive number of the line within the depreciation plan.

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.DepreciationPlan.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.DepreciationPlan.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### PlanDepreciationValue

The part of the total amount of the asset (in the currency of the asset), which is due for depreciation.

Type: **[Amount (14, 2)](../data-types.md#amount)**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **Constant**  
Show in UI: **ShownByDefault**  

### Id

Type: **guid**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, GreaterThanOrLessThan, EqualsIn**  
Default Value: **NewGuid**  
Show in UI: **CannotBeShown**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

Type: **int32**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

Type: **string**  
Category: **Calculated Attributes**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  


## Reference Details

### Asset

The asset that is planned for depreciation.

Type: **[Assets](Finance.Assets.Assets.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DepreciationMethod

Depreciation method by which the asset will be depreciated.

Type: **[DepreciationMethods](Finance.Assets.DepreciationMethods.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DepreciationPlan

The <see cref="DepreciationPlan"/> to which this DepreciationPlanLine belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[DepreciationPlans](Finance.Assets.DepreciationPlans.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
Show in UI: **ShownByDefault**  

### Document

The owner document. The <see cref="DepreciationPlan"/> to which this DepreciationPlanLine belongs. `Required` `Filter(multi eq)`

Type: **[DepreciationPlans](Finance.Assets.DepreciationPlans.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ValuationModel

Valuation model in which the asset is accounted.

Type: **[ValuationModels](Finance.Assets.ValuationModels.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  


## API Methods

Methods that can be invoked in public APIs.

### GetAllowedCustomPropertyValues

Gets the allowed values for the specified custom property for this entity object.              If supported the result is ordered by property value. Some property value sources do not support ordering - in that case the result is not ordered.  
Return Type: **Collection Of [CustomPropertyValue](../data-types.md#systems.bpm.custompropertyvalue)**  
Declaring Type: **EntityObject**  
Domain API Request: **GET**  

**Parameters**  
  * **customPropertyCode**  
    The code of the custom property  
    Type: string  

  * **search**  
    The search text - searches by value or description. Can contain wildcard character %.  
    Type: string  
     Optional: True  
    Default Value: null  

  * **exactMatch**  
    If true the search text should be equal to the property value  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **orderByDescription**  
    If true the result is ordered by Description instead of Value. Note that ordering is not always possible.  
    Type: boolean  
     Optional: True  
    Default Value: False  

  * **top**  
    The top clause - default is 10  
    Type: int32  
     Optional: True  
    Default Value: 10  

  * **skip**  
    The skip clause - default is 0  
    Type: int32  
     Optional: True  
    Default Value: 0  


### CreateNotification

Create a notification immediately in a separate transaction, and send a real-time event to the user.  
Return Type: **void**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  

**Parameters**  
  * **user**  
    The user.  
    Type: [Users](Systems.Security.Users.md)  

  * **notificationClass**  
    The notification class.  
    Type: string  

  * **subject**  
    The notification subject.  
    Type: string  

  * **priority**  
    The notification priority.  
    Type: Systems.Core.NotificationsRepository.Priority  
    Allowed values for the `Priority`(Systems.Core.Notifications.md#priority) data attribute  
    Allowed Values (Systems.Core.NotificationsRepository.Priority Enum Members)  

    | Value | Description |
    | ---- | --- |
    | Background | Background value. Stored as 1. <br /> Model Value: 1 <br /> Domain API Value: 'Background' |
    | Low | Low value. Stored as 2. <br /> Model Value: 2 <br /> Domain API Value: 'Low' |
    | Normal | Normal value. Stored as 3. <br /> Model Value: 3 <br /> Domain API Value: 'Normal' |
    | High | High value. Stored as 4. <br /> Model Value: 4 <br /> Domain API Value: 'High' |
    | Urgent | Urgent value. Stored as 5. <br /> Model Value: 5 <br /> Domain API Value: 'Urgent' |

     Optional: True  
    Default Value: Normal  


### CreateCopy

Duplicates the object and its child objects belonging to the same aggregate.              The duplicated objects are not saved to the data source but remain in the same transaction as the original object.  
Return Type: **EntityObject**  
Declaring Type: **EntityObject**  
Domain API Request: **POST**  


## Business Rules

[!list limit=1000 erp.entity=Finance.Assets.DepreciationPlanLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Finance.Assets.DepreciationPlanLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Finance_Assets_DepreciationPlanLines

Domain API Entity Type: 
Finance_Assets_DepreciationPlanLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Finance_Assets_DepreciationPlanLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Finance_Assets_DepreciationPlanLines?$top=10>

