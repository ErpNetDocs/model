---
uid: Regulatory.Intrastat.DeclarationLines
---
# Regulatory.Intrastat.DeclarationLines Entity

**Namespace:** [Regulatory.Intrastat](Regulatory.Intrastat.md)  

Contains the details of the Intrastat declarations, issued by the enterprise companies. Entity: Its_Declaration_Lines

## Default Visualization
Default Display Text Format:  
_{IntrastatDeclaration.EntityName}_  
Default Search Members:  
_IntrastatDeclaration.EntityName_  
Name Data Member:  
_IntrastatDeclaration.EntityName_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Regulatory.Intrastat.Declarations](Regulatory.Intrastat.Declarations.md)  
Aggregate Root:  
[Regulatory.Intrastat.Declarations](Regulatory.Intrastat.Declarations.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DeliveryTerms](Regulatory.Intrastat.DeclarationLines.md#deliveryterms) | [DeliveryTerms](Regulatory.Intrastat.DeclarationLines.md#deliveryterms) | Delivery terms - classification according to Intrastat (which uses the common abbreviations). `Required` 
| [DisplayText](Regulatory.Intrastat.DeclarationLines.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [Id](Regulatory.Intrastat.DeclarationLines.md#id) | guid |  
| [InvoicedValueAmountBase](Regulatory.Intrastat.DeclarationLines.md#invoicedvalueamountbase) | [Amount (10, 0)](../data-types.md#amount) | Invoiced value of the goods in the base currency. `Currency: IntrastatDeclaration.BaseCurrency` `Required` 
| [LineAction](Regulatory.Intrastat.DeclarationLines.md#lineaction) | [LineAction](Regulatory.Intrastat.DeclarationLines.md#lineaction) | Line action - 'NEW' = New, 'EDN' = Edited-New, 'EDO' = Edited-Old, 'DEL' = Deleted. `Required` `Default("NEW")` 
| [LineNo](Regulatory.Intrastat.DeclarationLines.md#lineno) | int32 | Consequtive line number within the intrastat declaration. `Required` `Filter(eq)` 
| [NetMassKg](Regulatory.Intrastat.DeclarationLines.md#netmasskg) | decimal (14, 3) | Net mass of the goods in kg. `Required` `Filter(multi eq)` 
| [ObjectVersion](Regulatory.Intrastat.DeclarationLines.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [QuantitySupplementaryUnit](Regulatory.Intrastat.DeclarationLines.md#quantitysupplementaryunit) | decimal (10, 0) __nullable__ | Quantity of the goods in the supplementary unit. null when no supplementary unit is specified. 
| [StatisticalValueAmountBase](Regulatory.Intrastat.DeclarationLines.md#statisticalvalueamountbase) | [Amount (10, 0)](../data-types.md#amount) __nullable__ | Statistical value of the goods in the base currency. `Currency: IntrastatDeclaration.BaseCurrency` 
| [TransactionNature](Regulatory.Intrastat.DeclarationLines.md#transactionnature) | [TransactionNature](Regulatory.Intrastat.DeclarationLines.md#transactionnature) | Transaction nature, according to the Intrastat classification. `Required` 
| [TransportMode](Regulatory.Intrastat.DeclarationLines.md#transportmode) | [TransportMode](Regulatory.Intrastat.DeclarationLines.md#transportmode) | Transportation mode - type of transportation used. `Required` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AdministrativeRegion](Regulatory.Intrastat.DeclarationLines.md#administrativeregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) | Administrative region of the enterprise company at the time of the declaration. `Required` `Filter(multi eq)` |
| [IntrastatCommodityCode](Regulatory.Intrastat.DeclarationLines.md#intrastatcommoditycode) | [CommodityCodes](Regulatory.Intrastat.CommodityCodes.md) | The commodity code of the goods, according to the Intrastat commodity classification. `Required` `Filter(multi eq)` |
| [IntrastatDeclaration](Regulatory.Intrastat.DeclarationLines.md#intrastatdeclaration) | [Declarations](Regulatory.Intrastat.Declarations.md) | The intrastat declaration, to which this line belongs. `Required` `Filter(multi eq)` `Owner` |
| [OriginCountry](Regulatory.Intrastat.DeclarationLines.md#origincountry) | [Countries](General.Geography.Countries.md) (nullable) | The country of origin of the goods. null for outbound declarations. `Filter(multi eq)` |
| [Party](Regulatory.Intrastat.DeclarationLines.md#party) | [Parties](General.Contacts.Parties.md) (nullable) | Partner to whom the goods are dispatched, or partner from whom the goods are received. `Filter(multi eq)` `Introduced in version 22.1.5.58` |
| [PartyCountry](Regulatory.Intrastat.DeclarationLines.md#partycountry) | [Countries](General.Geography.Countries.md) | The country of the partner. `Required` `Filter(multi eq)` |
| [TransportCountry](Regulatory.Intrastat.DeclarationLines.md#transportcountry) | [Countries](General.Geography.Countries.md) | The country of the transportation company. `Required` `Filter(multi eq)` |


## Attribute Details

### DeliveryTerms

Delivery terms - classification according to Intrastat (which uses the common abbreviations). `Required`

_Type_: **[DeliveryTerms](Regulatory.Intrastat.DeclarationLines.md#deliveryterms)**  
_Category_: **System**  
Generic enum type for DeliveryTerms properties  
_Allowed Values (Regulatory.Intrastat.DeliveryTerms Enum Members)_  

| Value | Description |
| ---- | --- |
| ExWorks | ExWorks value. Stored as 'EXW'. <br /> _Database Value:_ 'EXW' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ExWorks' |
| FrancoCarrier | FrancoCarrier value. Stored as 'FCA'. <br /> _Database Value:_ 'FCA' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'FrancoCarrier' |
| FreeAlongsideShip | FreeAlongsideShip value. Stored as 'FAS'. <br /> _Database Value:_ 'FAS' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'FreeAlongsideShip' |
| FreeOnBoard | FreeOnBoard value. Stored as 'FOB'. <br /> _Database Value:_ 'FOB' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'FreeOnBoard' |
| CostAndFreightCF | CostAndFreightCF value. Stored as 'CFR'. <br /> _Database Value:_ 'CFR' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'CostAndFreightCF' |
| CostInsuranceAndFreight | CostInsuranceAndFreight value. Stored as 'CIF'. <br /> _Database Value:_ 'CIF' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'CostInsuranceAndFreight' |
| CarriagePaidTo | CarriagePaidTo value. Stored as 'CPT'. <br /> _Database Value:_ 'CPT' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'CarriagePaidTo' |
| CarriageAndInsurancePaidTo | CarriageAndInsurancePaidTo value. Stored as 'CIP'. <br /> _Database Value:_ 'CIP' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'CarriageAndInsurancePaidTo' |
| DeliveredAtPlace | DeliveredAtPlace value. Stored as 'DAP'. <br /> _Database Value:_ 'DAP' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'DeliveredAtPlace' |
| DeliveredAtTerminal | DeliveredAtTerminal value. Stored as 'DAT'. <br /> _Database Value:_ 'DAT' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'DeliveredAtTerminal' |
| DeliveredDutyPaid | DeliveredDutyPaid value. Stored as 'DDP'. <br /> _Database Value:_ 'DDP' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'DeliveredDutyPaid' |
| DeliveredAtPlaceUnloaded | DeliveredAtPlaceUnloaded value. Stored as 'DPU'. <br /> _Database Value:_ 'DPU' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'DeliveredAtPlaceUnloaded' |

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

### InvoicedValueAmountBase

Invoiced value of the goods in the base currency. `Currency: IntrastatDeclaration.BaseCurrency` `Required`

_Type_: **[Amount (10, 0)](../data-types.md#amount)**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### LineAction

Line action - 'NEW' = New, 'EDN' = Edited-New, 'EDO' = Edited-Old, 'DEL' = Deleted. `Required` `Default("NEW")`

_Type_: **[LineAction](Regulatory.Intrastat.DeclarationLines.md#lineaction)**  
_Category_: **System**  
Allowed values for the `LineAction`(Regulatory.Intrastat.DeclarationLines.md#lineaction) data attribute  
_Allowed Values (Regulatory.Intrastat.DeclarationLinesRepository.LineAction Enum Members)_  

| Value | Description |
| ---- | --- |
| New | New value. Stored as 'NEW'. <br /> _Database Value:_ 'NEW' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'New' |
| EditedNew | EditedNew value. Stored as 'EDN'. <br /> _Database Value:_ 'EDN' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'EditedNew' |
| EditedOld | EditedOld value. Stored as 'EDO'. <br /> _Database Value:_ 'EDO' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'EditedOld' |
| Deleted | Deleted value. Stored as 'DEL'. <br /> _Database Value:_ 'DEL' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'Deleted' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Default Value_: **New**  
_Show in UI_: **ShownByDefault**  

### LineNo

Consequtive line number within the intrastat declaration. `Required` `Filter(eq)`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **Equals**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.IntrastatDeclaration.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.IntrastatDeclaration.Lines.Select( c => c.LineNo).DefaultIfEmpty( 0).Max( ) + 10)`
### NetMassKg

Net mass of the goods in kg. `Required` `Filter(multi eq)`

_Type_: **decimal (14, 3)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### ObjectVersion

The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking.

_Type_: **int32**  
_Category_: **Extensible Data Object**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### QuantitySupplementaryUnit

Quantity of the goods in the supplementary unit. null when no supplementary unit is specified.

_Type_: **decimal (10, 0) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### StatisticalValueAmountBase

Statistical value of the goods in the base currency. `Currency: IntrastatDeclaration.BaseCurrency`

_Type_: **[Amount (10, 0)](../data-types.md#amount) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TransactionNature

Transaction nature, according to the Intrastat classification. `Required`

_Type_: **[TransactionNature](Regulatory.Intrastat.DeclarationLines.md#transactionnature)**  
_Category_: **System**  
Generic enum type for TransactionNature properties  
_Allowed Values (Regulatory.Intrastat.TransactionNature Enum Members)_  

| Value | Description |
| ---- | --- |
| OutrightPurchaseOrSale | OutrightPurchaseOrSale value. Stored as '11'. <br /> _Database Value:_ '11' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'OutrightPurchaseOrSale' |
| SupplyForSale | SupplyForSale value. Stored as '12'. <br /> _Database Value:_ '12' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'SupplyForSale' |
| BarterTrade | BarterTrade value. Stored as '13'. <br /> _Database Value:_ '13' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'BarterTrade' |
| FinancialLeasing | FinancialLeasing value. Stored as '14'. <br /> _Database Value:_ '14' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'FinancialLeasing' |
| OtherTransactions | OtherTransactions value. Stored as '19'. <br /> _Database Value:_ '19' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'OtherTransactions' |
| ReturnStokilizing | ReturnStokilizing value. Stored as '21'. <br /> _Database Value:_ '21' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'ReturnStokilizing' |
| ReplacementFor<br />ReturnedGoods | ReplacementFor<br />ReturnedGoods value. Stored as '22'. <br /> _Database Value:_ '22' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'ReplacementFor<br />ReturnedGoods' |
| ReplacementOfGoods<br />NotBeingReturned | ReplacementOfGoods<br />NotBeingReturned value. Stored as '23'. <br /> _Database Value:_ '23' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'ReplacementOfGoods<br />NotBeingReturned' |
| ReturnOrExchange<br />OfOtherGoods | ReturnOrExchange<br />OfOtherGoods value. Stored as '29'. <br /> _Database Value:_ '29' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'ReturnOrExchange<br />OfOtherGoods' |
| SpecificTransactions | SpecificTransactions value. Stored as '60'. <br /> _Database Value:_ '60' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'SpecificTransactions' |
| OperationsOnJointProjects | OperationsOnJointProjects value. Stored as '70'. <br /> _Database Value:_ '70' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'OperationsOnJointProjects' |
| TransactionsOf<br />ConstructionMaterials<br />AndEquipment | TransactionsOf<br />ConstructionMaterials<br />AndEquipment value. Stored as '80'. <br /> _Database Value:_ '80' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'TransactionsOf<br />ConstructionMaterials<br />AndEquipment' |
| OtherTransactionsLeasing | OtherTransactionsLeasing value. Stored as '91'. <br /> _Database Value:_ '91' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'OtherTransactionsLeasing' |
| OtherTransactionsOther | OtherTransactionsOther value. Stored as '99'. <br /> _Database Value:_ '99' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'OtherTransactionsOther' |
| DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind | DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind value. Stored as '30'. <br /> _Database Value:_ '30' <br /> _Model Value:_ 14 <br /> _Domain API Value:_ 'DealsThatInclude<br />PropertyTransfers<br />WithoutFinancial<br />CompensationOr<br />CompensationIn<br />Kind' |
| GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender | GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender value. Stored as '41'. <br /> _Database Value:_ '41' <br /> _Model Value:_ 15 <br /> _Domain API Value:_ 'GoodsThatAreExpected<br />ToBeReturnedTo<br />Sender' |
| GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender | GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender value. Stored as '42'. <br /> _Database Value:_ '42' <br /> _Model Value:_ 16 <br /> _Domain API Value:_ 'GoodsThatAreNot<br />ExpectedToBeReturned<br />ToSender' |
| GoodsThatAreReturned<br />ToSender | GoodsThatAreReturned<br />ToSender value. Stored as '51'. <br /> _Database Value:_ '51' <br /> _Model Value:_ 17 <br /> _Domain API Value:_ 'GoodsThatAreReturned<br />ToSender' |
| GoodsThatAreNot<br />ReturnedToSender | GoodsThatAreNot<br />ReturnedToSender value. Stored as '52'. <br /> _Database Value:_ '52' <br /> _Model Value:_ 18 <br /> _Domain API Value:_ 'GoodsThatAreNot<br />ReturnedToSender' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### TransportMode

Transportation mode - type of transportation used. `Required`

_Type_: **[TransportMode](Regulatory.Intrastat.DeclarationLines.md#transportmode)**  
_Category_: **System**  
Generic enum type for TransportMode properties  
_Allowed Values (Regulatory.Intrastat.TransportMode Enum Members)_  

| Value | Description |
| ---- | --- |
| Shipping | Shipping value. Stored as '1'. <br /> _Database Value:_ '1' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Shipping' |
| RailwayTransport | RailwayTransport value. Stored as '2'. <br /> _Database Value:_ '2' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'RailwayTransport' |
| RoadTransport | RoadTransport value. Stored as '3'. <br /> _Database Value:_ '3' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'RoadTransport' |
| AirTransport | AirTransport value. Stored as '4'. <br /> _Database Value:_ '4' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'AirTransport' |
| Mail | Mail value. Stored as '5'. <br /> _Database Value:_ '5' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Mail' |
| FixedTransport<br />Installations | FixedTransport<br />Installations value. Stored as '7'. <br /> _Database Value:_ '7' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'FixedTransport<br />Installations' |
| RiverTransport | RiverTransport value. Stored as '8'. <br /> _Database Value:_ '8' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'RiverTransport' |
| SelfPropelled | SelfPropelled value. Stored as '9'. <br /> _Database Value:_ '9' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'SelfPropelled' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### AdministrativeRegion

Administrative region of the enterprise company at the time of the declaration. `Required` `Filter(multi eq)`

_Type_: **[AdministrativeRegions](General.Geography.AdministrativeRegions.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### IntrastatCommodityCode

The commodity code of the goods, according to the Intrastat commodity classification. `Required` `Filter(multi eq)`

_Type_: **[CommodityCodes](Regulatory.Intrastat.CommodityCodes.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### IntrastatDeclaration

The intrastat declaration, to which this line belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[Declarations](Regulatory.Intrastat.Declarations.md)**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html)_: **True**  
_Show in UI_: **ShownByDefault**  

### OriginCountry

The country of origin of the goods. null for outbound declarations. `Filter(multi eq)`

_Type_: **[Countries](General.Geography.Countries.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### Party

Partner to whom the goods are dispatched, or partner from whom the goods are received. `Filter(multi eq)` `Introduced in version 22.1.5.58`

_Type_: **[Parties](General.Contacts.Parties.md) (nullable)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### PartyCountry

The country of the partner. `Required` `Filter(multi eq)`

_Type_: **[Countries](General.Geography.Countries.md)**  
_Category_: **System**  
_Supported Filters_: **Equals, EqualsIn**  
_Show in UI_: **ShownByDefault**  

### TransportCountry

The country of the transportation company. `Required` `Filter(multi eq)`

_Type_: **[Countries](General.Geography.Countries.md)**  
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

[!list limit=1000 erp.entity=Regulatory.Intrastat.DeclarationLines erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Regulatory.Intrastat.DeclarationLines erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Regulatory_Intrastat_DeclarationLines

Domain API Entity Type: 
Regulatory_Intrastat_DeclarationLine

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Regulatory_Intrastat_DeclarationLines?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Regulatory_Intrastat_DeclarationLines?$top=10>

