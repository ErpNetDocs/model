---
uid: Crm.Marketing.MarketingActivityLines
---
# Crm.Marketing.MarketingActivityLines Entity

**Namespace:** [Crm.Marketing](Crm.Marketing.md)  

Detail records (lines) of the marketing activities. Entity: Crm_Marketing_Activity_Lines (Introduced in version 22.1.5.56)

## Default Visualization
Default Display Text Format:  
_{LineNo}. {MarketingActivity.DocumentNo} {MarketingActivity.DocumentType.TypeName:T}_  
Default Search Members:  
_MarketingActivity.DocumentNo_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Crm.Marketing.MarketingActivities](Crm.Marketing.MarketingActivities.md)  
Aggregate Root:  
[Crm.Marketing.MarketingActivities](Crm.Marketing.MarketingActivities.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [CompetitorPrice](Crm.Marketing.MarketingActivityLines.md#competitorprice) | decimal (15, 5) __nullable__ | Price of the competitor. 
| [DisplayText](Crm.Marketing.MarketingActivityLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Marketing.MarketingActivityLines.md#id) | guid |  
| [InStoreAvailableQuantity](Crm.Marketing.MarketingActivityLines.md#instoreavailablequantity) | [Quantity (10, 3)](../data-types.md#quantity) __nullable__ | The quantity found in store (in Quantity Unit). null means that count was not performed. `Unit: OrderQuantityUnit` `Filter(eq;ge;le)` 
| [InStoreLocation](Crm.Marketing.MarketingActivityLines.md#instorelocation) | string (32) __nullable__ | Location in store, like row, stand, etc. 
| [InStorePrice](Crm.Marketing.MarketingActivityLines.md#instoreprice) | decimal (15, 5) __nullable__ | Price displayed in store. `Filter(eq;ge;le)` 
| [LineNo](Crm.Marketing.MarketingActivityLines.md#lineno) | int32 | Consecutive line number, unique within the marketing activity. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` `Filter(eq)` 
| [Notes](Crm.Marketing.MarketingActivityLines.md#notes) | string (max) __nullable__ | Notes for this MarketingActivityLine. 
| [ObjectVersion](Crm.Marketing.MarketingActivityLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [OrderQuantity](Crm.Marketing.MarketingActivityLines.md#orderquantity) | [Quantity (15, 3)](../data-types.md#quantity) __nullable__ | Recommended quantity (in Quantity Unit) for  new order as a result of the marketing activity. null means that there is no specific recommendation. `Unit: OrderQuantityUnit` `Filter(eq;ge;le)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [Competitor](Crm.Marketing.MarketingActivityLines.md#competitor) | [Competitors](Crm.Marketing.Competitors.md) (nullable) | Competitor where marketing activity was held. `Filter(multi eq)` |
| [Document](Crm.Marketing.MarketingActivityLines.md#document) | [MarketingActivities](Crm.Marketing.MarketingActivities.md) | The owner document. Marketing activity. `Required` `Filter(multi eq)` |
| [MarketingActivity](Crm.Marketing.MarketingActivityLines.md#marketingactivity) | [MarketingActivities](Crm.Marketing.MarketingActivities.md) | Marketing activity. `Required` `Filter(multi eq)` `Owner` |
| [MarketingActivityLineType](Crm.Marketing.MarketingActivityLines.md#marketingactivitylinetype) | [MarketingActivityLineTypes](Crm.Marketing.MarketingActivityLineTypes.md) | Describes what the purpose of the marketing activity is. `Required` `Filter(multi eq)` |
| [OrderQuantityUnit](Crm.Marketing.MarketingActivityLines.md#orderquantityunit) | [MeasurementUnits](General.Products.MeasurementUnits.md) (nullable) | The measurement unit of In_Store_Available_<br />Quantity and Order_Quantity. `Filter(multi eq)` |
| [Product](Crm.Marketing.MarketingActivityLines.md#product) | [Products](General.Products.Products.md) | The specific product that was target of the marketing activity. `Required` `Filter(multi eq)` |


## Attribute Details

### CompetitorPrice

Price of the competitor.

_Type_: **decimal (15, 5) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

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

### InStoreAvailableQuantity

The quantity found in store (in Quantity Unit). null means that count was not performed. `Unit: OrderQuantityUnit` `Filter(eq;ge;le)`

_Type_: **[Quantity (10, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### InStoreLocation

Location in store, like row, stand, etc.

_Type_: **string (32) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **32**  
_Show in UI_: **ShownByDefault**  

### InStorePrice

Price displayed in store. `Filter(eq;ge;le)`

_Type_: **decimal (15, 5) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LineNo

Consecutive line number, unique within the marketing activity. Usually is increasing in steps of 10, like in 10, 20, 30, etc. `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.MarketingActivity.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`

_Front-End Recalc Expressions:_  
`( obj.MarketingActivity.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 1)`
### Notes

Notes for this MarketingActivityLine.

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **2147483647**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### OrderQuantity

Recommended quantity (in Quantity Unit) for  new order as a result of the marketing activity. null means that there is no specific recommendation. `Unit: OrderQuantityUnit` `Filter(eq;ge;le)`

_Type_: **[Quantity (15, 3)](../data-types.md#quantity) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### Competitor

Competitor where marketing activity was held. `Filter(multi eq)`

_Type_: **[Competitors](Crm.Marketing.Competitors.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Document

The owner document. Marketing activity. `Required` `Filter(multi eq)`

_Type_: **[MarketingActivities](Crm.Marketing.MarketingActivities.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### MarketingActivity

Marketing activity. `Required` `Filter(multi eq)` `Owner`

_Type_: **[MarketingActivities](Crm.Marketing.MarketingActivities.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### MarketingActivityLineType

Describes what the purpose of the marketing activity is. `Required` `Filter(multi eq)`

_Type_: **[MarketingActivityLineTypes](Crm.Marketing.MarketingActivityLineTypes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### OrderQuantityUnit

The measurement unit of In_Store_Available_Quantity and Order_Quantity. `Filter(multi eq)`

_Type_: **[MeasurementUnits](General.Products.MeasurementUnits.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

_Front-End Recalc Expressions:_  
`obj.Product.MeasurementUnit`
### Product

The specific product that was target of the marketing activity. `Required` `Filter(multi eq)`

_Type_: **[Products](General.Products.Products.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
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

[!list limit=1000 erp.entity=Crm.Marketing.MarketingActivityLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Marketing.MarketingActivityLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Marketing_MarketingActivityLines

Domain API Entity Type: 
Crm_Marketing_MarketingActivityLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Marketing_MarketingActivityLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Marketing_MarketingActivityLines?$top=10>

