---
uid: Logistics.Inventory.Stores
---
# Logistics.Inventory.Stores


Represents the physical warehouses.

## General
Namespace: [Logistics.Inventory](Logistics.Inventory.md)  
Repository: Logistics.Inventory.Stores  
Inherited From: [General.Contacts.Parties](General.Contacts.Parties.md)  
Base Table: Inv_Stores  
API access:  ReadWrite  

## Visualization
Display Format: {PartyName:T}  
Search Members: Code; PartyName  
Code Member: Code  
Name Member: PartyName  
Category:  Definitions  
Show in UI:  ShownByDefault  
Layout category By:  PartyType  

## Track Changes  
Min level:  4 - Track object attribute and blob changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Tree  
* [Logistics.Inventory.Stores](Logistics.Inventory.Stores.md)  
  * [Logistics.Inventory.StoreBins](Logistics.Inventory.StoreBins.md)  
  * [Logistics.Inventory.StoreResponsibleParties](Logistics.Inventory.StoreResponsibleParties.md)  
  * [General.Contacts.PartyContactMechanisms](General.Contacts.PartyContactMechanisms.md)  
  * [General.Contacts.PartyRelationships](General.Contacts.PartyRelationships.md)  
  * [General.Contacts.PartyApplicableLegislations](General.Contacts.PartyApplicableLegislations.md)  
  * [General.Contacts.PartyBankAccounts](General.Contacts.PartyBankAccounts.md)  
  * [General.Contacts.PartyLocationNumbers](General.Contacts.PartyLocationNumbers.md)  
  * [General.Contacts.PartyPictures](General.Contacts.PartyPictures.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [<s>Active</s>](Logistics.Inventory.Stores.md#active) | boolean __nullable__ | **OBSOLETE! Do not use!** Obsolete - Use Gen_Parties.Is_Active. `Obsolete` `Obsoleted in version 22.1.6.61` 
| [Code](Logistics.Inventory.Stores.md#code) | string (16) | The unique code of the Store. `Required` `Filter(eq;like)` `ORD` 
| [CreationTime](Logistics.Inventory.Stores.md#creationtime) | datetime __nullable__ | Date and time when the Store was created. `Filter(ge;le)` `ReadOnly` 
| [CreationUser](Logistics.Inventory.Stores.md#creationuser) | string (64) __nullable__ | Login name of the user, who created the Store. `Filter(like)` `ReadOnly` 
| [DefaultSupplyStoreId](Logistics.Inventory.Stores.md#defaultsupplystoreid) | guid __nullable__ | The store from which goods are usually supplied to this store. `Filter(multi eq)` 
| [GLN](Logistics.Inventory.Stores.md#gln) | string (13) __nullable__ | Global Location Number used by EDI systems. `Filter(multi eq)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [IsActive](Logistics.Inventory.Stores.md#isactive) | boolean | Specifies whether the current party is active in the system or not. `Required` `Default(true)` `Filter(eq)` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [Name](Logistics.Inventory.Stores.md#name) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | Name of the store. `Required` `Filter(like)` 
| [NumberOfDimensions](Logistics.Inventory.Stores.md#numberofdimensions) | int32 | Number of dimensions in the coordinate system of the storage bins. 0 means single-bin store. Currently, this is only stored for information and is not used for automatical generation of store bins, as it was intended. `Required` `Default(0)` `Filter(eq)` 
| [PartyCode](Logistics.Inventory.Stores.md#partycode) | string (16) | The unique code of the party. `Required` `Filter(eq;like)` `ORD` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyCreationTime](Logistics.Inventory.Stores.md#partycreationtime) | datetime __nullable__ | Date and time when the Party was created. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyCreationUser](Logistics.Inventory.Stores.md#partycreationuser) | string (64) __nullable__ | Login name of the user, who created the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyName](Logistics.Inventory.Stores.md#partyname) | [MultilanguageString (254)](../data-types.md#multilanguagestring) | The name of the party. `Required` `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyNotes](Logistics.Inventory.Stores.md#partynotes) | string (254) __nullable__ | Notes for this Party. (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyType](Logistics.Inventory.Stores.md#partytype) | [PartyType](Logistics.Inventory.Stores.md#partytype) | Type of party. Currently supported are P=Person, C=Company, S=Store, L=Company Location, V=Division. `Required` `Default("P")` `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUniqueNumber](Logistics.Inventory.Stores.md#partyuniquenumber) | string (16) __nullable__ | Unique number of the party (National number for persons, Registration number for companies). `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUpdateTime](Logistics.Inventory.Stores.md#partyupdatetime) | datetime __nullable__ | Date and time when the Party was last updated. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [PartyUpdateUser](Logistics.Inventory.Stores.md#partyupdateuser) | string (64) __nullable__ | Login name of the user, who last updated the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md)) 
| [SchemaXML](Logistics.Inventory.Stores.md#schemaxml) | string (max) __nullable__ | Obsolete. Not used. 
| [Unmanaged](Logistics.Inventory.Stores.md#unmanaged) | boolean | If false the system will expect the user to process the store transactions. If true the system will auto-generate them. `Required` `Default(true)` 
| [UpdateTime](Logistics.Inventory.Stores.md#updatetime) | datetime __nullable__ | Date and time when the Store was last updated. `Filter(ge;le)` `ReadOnly` 
| [UpdateUser](Logistics.Inventory.Stores.md#updateuser) | string (64) __nullable__ | Login name of the user, who last updated the Store. `Filter(like)` `ReadOnly` 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [AccessKey](Logistics.Inventory.Stores.md#accesskey) | [AccessKeys](Systems.Security.AccessKeys.md) (nullable) | The access key, containing the permissions for this Store. An empty value means that all users have unlimited permissions. `Filter(multi eq)` |
| [AdministrativeRegion](Logistics.Inventory.Stores.md#administrativeregion) | [AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable) | The administrative region in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [Area](Logistics.Inventory.Stores.md#area) | [Areas](General.Geography.Areas.md) (nullable) | The area in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [Currency](Logistics.Inventory.Stores.md#currency) | [Currencies](General.Currencies.Currencies.md) (nullable) | The currency for the warehouse cost calculations. When null, the base currency for the enterprise company will be used. `Filter(multi eq)` |
| [DefaultProductCodingSystem](Logistics.Inventory.Stores.md#defaultproductcodingsystem) | [CodingSystems](General.Products.CodingSystems.md) (nullable) | When not null, specifies coding system for products, which is required by the party. The coding system is used primarily for document printouts and document import/exports. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [DefaultStoreBin](Logistics.Inventory.Stores.md#defaultstorebin) | [StoreBins](Logistics.Inventory.StoreBins.md) (nullable) | To be used when store bin is unknown. `Filter(multi eq)` |
| [EnterpriseCompany](Logistics.Inventory.Stores.md#enterprisecompany) | [EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable) | The Enterprise Company to which this Store applies, or null if it is for all enterprise companies. `Filter(multi eq)` |
| [EnterpriseCompanyLocation](Logistics.Inventory.Stores.md#enterprisecompanylocation) | [CompanyLocations](General.Contacts.CompanyLocations.md) (nullable) | The Enterprise Company Location to which this Store applies, or null if it is for all enterprise company locations. `Filter(multi eq)` |
| [Parent](Logistics.Inventory.Stores.md#parent) | [Stores](Logistics.Inventory.Stores.md) (nullable) | Obsolete. Not used. (Hierarchy of the stores is now represented by the Store Groups entity). `Filter(multi eq)` |
| [ParentParty](Logistics.Inventory.Stores.md#parentparty) | [Parties](General.Contacts.Parties.md) (nullable) | Organizational unit (branch from the hierarchy of all parties) to which this party is referred to. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md)) |
| [ResponsibleParty](Logistics.Inventory.Stores.md#responsibleparty) | [Parties](General.Contacts.Parties.md) (nullable) | Primary responsible party (usually employee) for the stock in the store. `Filter(multi eq)` |
| [StoreGroup](Logistics.Inventory.Stores.md#storegroup) | [StoreGroups](Logistics.Inventory.StoreGroups.md) | The store group, to which this store belongs. `Required` `Filter(multi eq)` |
| [TaxWarehouse](Logistics.Inventory.Stores.md#taxwarehouse) | [TaxWarehouses](Regulatory.Excise.TaxWarehouses.md) (nullable) | Excise Tax Warehouse for this Store. null means that the Store is not an Excise Tax Warehouse. `Filter(multi eq)` `Introduced in version 21.1.3.93` |
| [Warehouse](Logistics.Inventory.Stores.md#warehouse) | [Warehouses](Logistics.Wms.Warehouses.md) (nullable) | Specifies, the warehouse, which manages the warehouse operations for the store. null for stores, which do not have managed operations. `Filter(multi eq)` `Introduced in version 20.1` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Logistics.Inventory.Stores.md#id) | guid |  
| [ObjectVersion](Logistics.Inventory.Stores.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [ExternalId](Logistics.Inventory.Stores.md#externalid) | string | The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89] 
| [ExternalSystem](Logistics.Inventory.Stores.md#externalsystem) | string | The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89] 
| [AggregateLastUpdateTimeUtc](Logistics.Inventory.Stores.md#aggregatelastupdatetimeutc) | datetime | The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1] 
| [DisplayText](Logistics.Inventory.Stores.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 

## Child Collections

| Name | Type | Description |
| ---- | ---- | --- |
| ApplicableLegislations | [PartyApplicableLegislations](General.Contacts.PartyApplicableLegislations.md) | List of `PartyApplicable<br />Legislation`(General.Contacts.PartyApplicable<br />Legislations.md) child objects, based on the `General.Contacts.PartyApplicableLegislation.Party`(General.Contacts.PartyApplicable<br />Legislations.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| BankAccounts | [PartyBankAccounts](General.Contacts.PartyBankAccounts.md) | List of `PartyBankAccount`(General.Contacts.PartyBankAccounts.md) child objects, based on the `General.Contacts.PartyBankAccount.Party`(General.Contacts.PartyBankAccounts.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Bins | [StoreBins](Logistics.Inventory.StoreBins.md) | List of `StoreBin`(Logistics.Inventory.StoreBins.md) child objects, based on the `Logistics.Inventory.StoreBin.Store`(Logistics.Inventory.StoreBins.md#store) back reference 
| ContactMechanisms | [PartyContactMechanisms](General.Contacts.PartyContactMechanisms.md) | List of `PartyContactMechanism`(General.Contacts.PartyContactMechanisms.md) child objects, based on the `General.Contacts.PartyContactMechanism.Party`(General.Contacts.PartyContactMechanisms.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| LocationNumbers | [PartyLocationNumbers](General.Contacts.PartyLocationNumbers.md) | List of `PartyLocationNumber`(General.Contacts.PartyLocationNumbers.md) child objects, based on the `General.Contacts.PartyLocationNumber.Party`(General.Contacts.PartyLocationNumbers.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Pictures | [PartyPictures](General.Contacts.PartyPictures.md) | List of `PartyPicture`(General.Contacts.PartyPictures.md) child objects, based on the `General.Contacts.PartyPicture.Party`(General.Contacts.PartyPictures.md#party) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| Relationships | [PartyRelationships](General.Contacts.PartyRelationships.md) | List of `PartyRelationship`(General.Contacts.PartyRelationships.md) child objects, based on the `General.Contacts.PartyRelationship.FromParty`(General.Contacts.PartyRelationships.md#fromparty) back reference (Inherited from [Parties](General.Contacts.Parties.md)) 
| ResponsibleParties | [StoreResponsibleParties](Logistics.Inventory.StoreResponsibleParties.md) | List of `StoreResponsibleParty`(Logistics.Inventory.StoreResponsibleParties.md) child objects, based on the `Logistics.Inventory.StoreResponsibleParty.Store`(Logistics.Inventory.StoreResponsibleParties.md#store) back reference 


## Attribute Details

### Active

**OBSOLETE! Do not use!** Obsolete - Use Gen_Parties.Is_Active. `Obsolete` `Obsoleted in version 22.1.6.61`

Type: **boolean __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **CannotBeShown**  

### Code

The unique code of the Store. `Required` `Filter(eq;like)` `ORD`

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.Code, null, "00000")`

### CreationTime

Date and time when the Store was created. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### CreationUser

Login name of the user, who created the Store. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### DefaultSupplyStoreId

The store from which goods are usually supplied to this store. `Filter(multi eq)`

Type: **guid __nullable__**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### GLN

Global Location Number used by EDI systems. `Filter(multi eq)` `ORD` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (13) __nullable__**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Supports Order By: **True**  
Maximum Length: **13**  
Show in UI: **ShownByDefault**  

### IsActive

Specifies whether the current party is active in the system or not. `Required` `Default(true)` `Filter(eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **boolean**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### Name

Name of the store. `Required` `Filter(like)`

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### NumberOfDimensions

Number of dimensions in the coordinate system of the storage bins. 0 means single-bin store. Currently, this is only stored for information and is not used for automatical generation of store bins, as it was intended. `Required` `Default(0)` `Filter(eq)`

Type: **int32**  
Category: **System**  
Supported Filters: **Equals**  
Supports Order By: **False**  
Default Value: **0**  
Show in UI: **ShownByDefault**  

### PartyCode

The unique code of the party. `Required` `Filter(eq;like)` `ORD` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (16)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **True**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`obj.IncMax( o => o.PartyCode, null, "00000")`

### PartyCreationTime

Date and time when the Party was created. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PartyCreationUser

Login name of the user, who created the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### PartyName

The name of the party. `Required` `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[MultilanguageString (254)](../data-types.md#multilanguagestring)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### PartyNotes

Notes for this Party. (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (254) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **254**  
Show in UI: **ShownByDefault**  

### PartyType

Type of party. Currently supported are P=Person, C=Company, S=Store, L=Company Location, V=Division. `Required` `Default("P")` `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[PartyType](Logistics.Inventory.Stores.md#partytype)**  
Category: **System**  
Allowed values for the PartyType data attribute  
Allowed Values (General.Contacts.PartiesRepository.PartyType Enum Members)  

| Value | Description |
| ---- | --- |
| Company | Company value. Stored as 'C'. <br /> Database Value: 'C' <br /> Model Value: 0 <br /> Domain API Value: 'Company' |
| CompanyLocation | CompanyLocation value. Stored as 'L'. <br /> Database Value: 'L' <br /> Model Value: 1 <br /> Domain API Value: 'CompanyLocation' |
| Person | Person value. Stored as 'P'. <br /> Database Value: 'P' <br /> Model Value: 2 <br /> Domain API Value: 'Person' |
| Store | Store value. Stored as 'S'. <br /> Database Value: 'S' <br /> Model Value: 3 <br /> Domain API Value: 'Store' |
| CompanyDivision | CompanyDivision value. Stored as 'V'. <br /> Database Value: 'V' <br /> Model Value: 4 <br /> Domain API Value: 'CompanyDivision' |

Supported Filters: **Equals, EqualsIn**  
Supports Order By: **False**  
Default Value: **Person**  
Show in UI: **ShownByDefault**  

### PartyUniqueNumber

Unique number of the party (National number for persons, Registration number for companies). `Filter(eq;like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (16) __nullable__**  
Category: **System**  
Supported Filters: **Equals, Like**  
Supports Order By: **False**  
Maximum Length: **16**  
Show in UI: **ShownByDefault**  

### PartyUpdateTime

Date and time when the Party was last updated. `Filter(ge;le)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### PartyUpdateUser

Login name of the user, who last updated the Party. `Filter(like)` `ReadOnly` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

### SchemaXML

Obsolete. Not used.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **CannotBeShown**  

### Unmanaged

If false the system will expect the user to process the store transactions. If true the system will auto-generate them. `Required` `Default(true)`

Type: **boolean**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Default Value: **True**  
Show in UI: **ShownByDefault**  

### UpdateTime

Date and time when the Store was last updated. `Filter(ge;le)` `ReadOnly`

Type: **datetime __nullable__**  
Category: **System**  
Supported Filters: **GreaterThanOrLessThan**  
Supports Order By: **False**  
Show in UI: **HiddenByDefault**  

### UpdateUser

Login name of the user, who last updated the Store. `Filter(like)` `ReadOnly`

Type: **string (64) __nullable__**  
Category: **System**  
Supported Filters: **Like**  
Supports Order By: **False**  
Maximum Length: **64**  
Show in UI: **HiddenByDefault**  

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

### ExternalId

The id of the object, when it is imported/synchronized with external system. Used by sync apps to identify the object in external systems. [Filter(multi eq)] [ORD] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### ExternalSystem

The name of the external system from which the object is imported/synchronized. [Filter(multi eq)] [Introduced in version 24.1.0.89]

Type: **string**  
Category: **Extensible Data Object**  
Supported Filters: **NotFilterable**  
Supports Order By: ****  
Show in UI: **HiddenByDefault**  

### AggregateLastUpdateTimeUtc

The exact server time (in UTC) of the last modification of the object represented by this system object. null means that it is unknown. [Filter(ge;le)] [ORD] [Introduced in version 19.1]

Type: **datetime**  
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

### AccessKey

The access key, containing the permissions for this Store. An empty value means that all users have unlimited permissions. `Filter(multi eq)`

Type: **[AccessKeys](Systems.Security.AccessKeys.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  


Remarks  
Supported permissions

| Permission | Type |
| --- | --- |
| Update | - |
| Delete | - |
| Administer (manage security)| - |
| Release Receipt Store Transactions | Permission1 |
| Release Issue Store Transactions | Permission2 |
### AdministrativeRegion

The administrative region in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[AdministrativeRegions](General.Geography.AdministrativeRegions.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Area

The area in which the party is situated. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[Areas](General.Geography.Areas.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Currency

The currency for the warehouse cost calculations. When null, the base currency for the enterprise company will be used. `Filter(multi eq)`

Type: **[Currencies](General.Currencies.Currencies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

Front-End Recalc Expressions:  
`IIF( ( obj.EnterpriseCompany != null), obj.EnterpriseCompany.BaseCurrency, obj.Transaction.CurrentEnterpriseCompany.BaseCurrency)`
### DefaultProductCodingSystem

When not null, specifies coding system for products, which is required by the party. The coding system is used primarily for document printouts and document import/exports. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[CodingSystems](General.Products.CodingSystems.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### DefaultStoreBin

To be used when store bin is unknown. `Filter(multi eq)`

Type: **[StoreBins](Logistics.Inventory.StoreBins.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompany

The Enterprise Company to which this Store applies, or null if it is for all enterprise companies. `Filter(multi eq)`

Type: **[EnterpriseCompanies](General.EnterpriseCompanies.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **HiddenByDefault**  

### EnterpriseCompanyLocation

The Enterprise Company Location to which this Store applies, or null if it is for all enterprise company locations. `Filter(multi eq)`

Type: **[CompanyLocations](General.Contacts.CompanyLocations.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Parent

Obsolete. Not used. (Hierarchy of the stores is now represented by the Store Groups entity). `Filter(multi eq)`

Type: **[Stores](Logistics.Inventory.Stores.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **CannotBeShown**  

### ParentParty

Organizational unit (branch from the hierarchy of all parties) to which this party is referred to. `Filter(multi eq)` (Inherited from [Parties](General.Contacts.Parties.md))

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### ResponsibleParty

Primary responsible party (usually employee) for the stock in the store. `Filter(multi eq)`

Type: **[Parties](General.Contacts.Parties.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### StoreGroup

The store group, to which this store belongs. `Required` `Filter(multi eq)`

Type: **[StoreGroups](Logistics.Inventory.StoreGroups.md)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### TaxWarehouse

Excise Tax Warehouse for this Store. null means that the Store is not an Excise Tax Warehouse. `Filter(multi eq)` `Introduced in version 21.1.3.93`

Type: **[TaxWarehouses](Regulatory.Excise.TaxWarehouses.md) (nullable)**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
Show in UI: **ShownByDefault**  

### Warehouse

Specifies, the warehouse, which manages the warehouse operations for the store. null for stores, which do not have managed operations. `Filter(multi eq)` `Introduced in version 20.1`

Type: **[Warehouses](Logistics.Wms.Warehouses.md) (nullable)**  
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

[!list limit=1000 erp.entity=Logistics.Inventory.Stores erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Logistics.Inventory.Stores erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Logistics_Inventory_Stores

Domain API Entity Type: 
Logistics_Inventory_Store

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Logistics_Inventory_Stores?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Logistics_Inventory_Stores?$top=10>

