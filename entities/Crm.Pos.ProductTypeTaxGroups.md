---
uid: Crm.Pos.ProductTypeTaxGroups
---
# Crm.Pos.ProductTypeTaxGroups Entity

**Namespace:** [Crm.Pos](Crm.Pos.md)  

Contains the tax group codes for the product types. The tax group codes are used when sales documents are printed to fiscal printers or exported to fiscal authorities. Entity: Pos_Product_Type_Tax_Groups (Introduced in version 19.1)

## Default Visualization
Default Display Text Format:  
_{ProductType.Name:T}_  
Default Search Members:  
_ProductType.Name_  
Name Data Member:  
_ProductType.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[General.Products.ProductTypes](General.Products.ProductTypes.md)  
Aggregate Root:  
[General.Products.ProductTypes](General.Products.ProductTypes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ApplicableLegislation](Crm.Pos.ProductTypeTaxGroups.md#applicablelegislation) | [ApplicableLegislation](Crm.Pos.ProductTypeTaxGroups.md#applicablelegislation) | The legislation, for which the tax group is applicable. `Required` `Filter(multi eq)` 
| [DisplayText](Crm.Pos.ProductTypeTaxGroups.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Crm.Pos.ProductTypeTaxGroups.md#id) | guid |  
| [Notes](Crm.Pos.ProductTypeTaxGroups.md#notes) | string (max) __nullable__ | Notes for this ProductTypeTaxGroup. `Filter(eq;like)` 
| [ObjectVersion](Crm.Pos.ProductTypeTaxGroups.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [TaxGroup](Crm.Pos.ProductTypeTaxGroups.md#taxgroup) | [TaxGroup](Crm.Pos.ProductTypeTaxGroups.md#taxgroup) | The tax group of the product type within the specified applicable legislation. `Required` `Filter(multi eq)` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [ProductType](Crm.Pos.ProductTypeTaxGroups.md#producttype) | [ProductTypes](General.Products.ProductTypes.md) | The product type for which the tax group is specified. `Required` `Filter(multi eq)` `Owner` |


## Attribute Details

### ApplicableLegislation

The legislation, for which the tax group is applicable. `Required` `Filter(multi eq)`

_Type_: **[ApplicableLegislation](Crm.Pos.ProductTypeTaxGroups.md#applicablelegislation)**  
_Category_: **System**  
Allowed values for the `ApplicableLegislation`(General.Contacts.PartyApplicableLegislations.md#applicablelegislation) data attribute  
_Allowed Values (General.Contacts.PartyApplicableLegislationsRepository.ApplicableLegislation Enum Members)_  

| Value | Description |
| ---- | --- |
| UnitedArabEmirates | UnitedArabEmirates value. Stored as 'AE'. <br /> _Database Value:_ 'AE' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'UnitedArabEmirates' |
| Australia | Australia value. Stored as 'AU'. <br /> _Database Value:_ 'AU' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Australia' |
| Bulgaria | Bulgaria value. Stored as 'BG'. <br /> _Database Value:_ 'BG' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Bulgaria' |
| Canada | Canada value. Stored as 'CA'. <br /> _Database Value:_ 'CA' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Canada' |
| China | China value. Stored as 'CN'. <br /> _Database Value:_ 'CN' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'China' |
| CzechRepublic | CzechRepublic value. Stored as 'CZ'. <br /> _Database Value:_ 'CZ' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'CzechRepublic' |
| Germany | Germany value. Stored as 'DE'. <br /> _Database Value:_ 'DE' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Germany' |
| Spain | Spain value. Stored as 'ES'. <br /> _Database Value:_ 'ES' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'Spain' |
| EuropeanUnion | EuropeanUnion value. Stored as 'EU'. <br /> _Database Value:_ 'EU' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'EuropeanUnion' |
| France | France value. Stored as 'FR'. <br /> _Database Value:_ 'FR' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'France' |
| Greece | Greece value. Stored as 'GR'. <br /> _Database Value:_ 'GR' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'Greece' |
| Hungary | Hungary value. Stored as 'HU'. <br /> _Database Value:_ 'HU' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'Hungary' |
| India | India value. Stored as 'IN'. <br /> _Database Value:_ 'IN' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'India' |
| Italy | Italy value. Stored as 'IT'. <br /> _Database Value:_ 'IT' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'Italy' |
| Japan | Japan value. Stored as 'JP'. <br /> _Database Value:_ 'JP' <br /> _Model Value:_ 14 <br /> _Domain API Value:_ 'Japan' |
| Macedonia | Macedonia value. Stored as 'MK'. <br /> _Database Value:_ 'MK' <br /> _Model Value:_ 15 <br /> _Domain API Value:_ 'Macedonia' |
| Poland | Poland value. Stored as 'PL'. <br /> _Database Value:_ 'PL' <br /> _Model Value:_ 16 <br /> _Domain API Value:_ 'Poland' |
| Portugal | Portugal value. Stored as 'PT'. <br /> _Database Value:_ 'PT' <br /> _Model Value:_ 17 <br /> _Domain API Value:_ 'Portugal' |
| Romania | Romania value. Stored as 'RO'. <br /> _Database Value:_ 'RO' <br /> _Model Value:_ 18 <br /> _Domain API Value:_ 'Romania' |
| Serbia | Serbia value. Stored as 'RS'. <br /> _Database Value:_ 'RS' <br /> _Model Value:_ 19 <br /> _Domain API Value:_ 'Serbia' |
| Russia | Russia value. Stored as 'RU'. <br /> _Database Value:_ 'RU' <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'Russia' |
| Turkey | Turkey value. Stored as 'TR'. <br /> _Database Value:_ 'TR' <br /> _Model Value:_ 21 <br /> _Domain API Value:_ 'Turkey' |
| UnitedKingdom | UnitedKingdom value. Stored as 'UK'. <br /> _Database Value:_ 'UK' <br /> _Model Value:_ 22 <br /> _Domain API Value:_ 'UnitedKingdom' |
| UnitedStates | UnitedStates value. Stored as 'US'. <br /> _Database Value:_ 'US' <br /> _Model Value:_ 23 <br /> _Domain API Value:_ 'UnitedStates' |
| SouthAfrica | SouthAfrica value. Stored as 'ZA'. <br /> _Database Value:_ 'ZA' <br /> _Model Value:_ 24 <br /> _Domain API Value:_ 'SouthAfrica' |

_Supported Filters_: **Equals, EqualsIn**  
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

### Notes

Notes for this ProductTypeTaxGroup. `Filter(eq;like)`

_Type_: **string (max) __nullable__**  
_Category_: **System**  
_Supported Filters_: **Equals, Like**  
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

### TaxGroup

The tax group of the product type within the specified applicable legislation. `Required` `Filter(multi eq)`

_Type_: **[TaxGroup](Crm.Pos.ProductTypeTaxGroups.md#taxgroup)**  
_Category_: **System**  
Allowed values for the `TaxGroup`(Crm.Pos.ProductTypeTaxGroups.md#taxgroup) data attribute  
_Allowed Values (Crm.Pos.ProductTypeTaxGroupsRepository.TaxGroup Enum Members)_  

| Value | Description |
| ---- | --- |
| Zero | Zero value. Stored as 0. <br /> _Database Value:_ 0 <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Zero' |
| One | One value. Stored as 1. <br /> _Database Value:_ 1 <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'One' |
| Two | Two value. Stored as 2. <br /> _Database Value:_ 2 <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Two' |
| Three | Three value. Stored as 3. <br /> _Database Value:_ 3 <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Three' |
| Four | Four value. Stored as 4. <br /> _Database Value:_ 4 <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Four' |
| Five | Five value. Stored as 5. <br /> _Database Value:_ 5 <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Five' |
| Six | Six value. Stored as 6. <br /> _Database Value:_ 6 <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Six' |
| Seven | Seven value. Stored as 7. <br /> _Database Value:_ 7 <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'Seven' |
| Eight | Eight value. Stored as 8. <br /> _Database Value:_ 8 <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'Eight' |

_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### ProductType

The product type for which the tax group is specified. `Required` `Filter(multi eq)` `Owner`

_Type_: **[ProductTypes](General.Products.ProductTypes.md)**  
_Indexed_: **True**  
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

[!list limit=1000 erp.entity=Crm.Pos.ProductTypeTaxGroups erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Crm.Pos.ProductTypeTaxGroups erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Crm_Pos_ProductTypeTaxGroups

Domain API Entity Type: 
Crm_Pos_ProductTypeTaxGroup

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Crm_Pos_ProductTypeTaxGroups?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Crm_Pos_ProductTypeTaxGroups?$top=10>

