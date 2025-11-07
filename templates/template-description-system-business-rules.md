---
uid: system-business-rules
---

# System Business Rules

## What is a System Business Rule?

The System Business Rules specify a specific action that the system must take to verify and/or modify data that is entered into the database.

Аccording to their аction, there are two main types of business rules:

- **rules that validate the data that has been entered** - e.g. if a particular field has a value, if the value is valid, if the value interferes with the values of the other fields, settings, or business logics.
- **rules that modify something** - e.g. sets a value in a particular field, triggers an event for another entity, and others.

## Documentation

Each System Business Rule whose code is with the format 'R' + 'digit number', e.g. R27179, has a documentation topic.

The topic is available in the Business Rules section of the Model Documentation for the particular Entity e.g. Sales Orders's [Business Rules](https://docs.erp.net/model/entities/Crm.Sales.SalesOrders.html#business-rules).

Every topic includes a standardized table that contains detailed information about the rule. The standardized table allows us to organize data in a structured way and helps the reader to navigate through the info quickly.

## The Table Columns and Content Explained

| Column Name | Column Description |
| ---- | ----- |
| Code | Unique System Business Rule code. Always starts with "R" and continues with a digit number. |
| Entity | The entity for which the Action of the System Business Rule is executed. |
| Name | The name of the System Business Rule. The name is unique per entity.<br/> Usually, the name is simply the name of the attribute for which the rule is created. |
| Attribute | This is the attribute (field) of the entity object to which the rule applies. There may be rules that do not apply to any particular field. |
| Layer | The layer where the System Business Rule is executed. Possible values are: <br/>- Front-End - the rule is executed on the client-side of the application i.e. in the user interface while the data is being modified by the user. <br/> - Back-End - the rule is executed on the server side of the application, regardless of whether the information is entered through a user interface or through the API |
| Events | The events that trigger the execution of the rule. Possible events are: <br/> *Front-End Events* <br/> - **ClientCommit** – Occurs when the data is saved into the database, but only when the saving is initiated by a client application. If the object is modified by the server side, this event is not triggered. <br/> - **AttributeChanged (TheAttribute)** – Occurs when an attribute/field value is changed. The attribute(s) whose value is being changed is/are specified in brackets. <br/> *Back-End Events*<br/> - **Commit** – Occurs when the data is saved into the database. <br/> - **Aggregate Commit** – Occurs for the aggregate root when saving a change of an aggregate object. <br/> - **Aggregate Committed** – Occurs for the aggregate root after a change is made to an aggregate object. <br/> - **Planning +** – Occurs during the document state change to Planned or higher. *(Applies only to documents.)* <br/> - **Planned +** – Occurs after the document state changes to Planned or higher. It happens after all other validations on Planning +. *(Applies only to documents.)* <br/> - **FirmPlanning +** – Occurs during the document state change to FirmPlanned or higher. *(Applies only to documents.)* <br/> - **FirmPlanned +** – Occurs after the document state changes to FirmPlanned or higher. It happens after all other validations on FirmPlanning +. *(Applies only to documents.)* <br/> - **Releasing +** – Occurs during the document state change to Released or higher. *(Applies only to documents.)* <br/> - **Released +** – Occurs after the document state changes to Released or higher. It happens after all other validations on Releasing +. *(Applies only to documents.)* <br/> - **Completing +** – Occurs during the document state change to Completed or higher. *(Applies only to documents.)* <br/> - **Completed +** – Occurs after the document state changes to Completed or higher. It happens after all other validations on Completing +. *(Applies only to documents.)* <br/> - **Closed** – Occurs when the document state is changed to Closed. *(Applies only to documents.)* <br/> - **Voiding** – Occurs when a document is being voided. *(Applies only to documents.)* |
| Priority | Possible values are Early, Normal, or Late. <br/> The priority is taken into account in the execution order. The rules with an Early priority are executed first, followed by those with Normal priority, and rules with a Late priority are executed last. |
| Modify | Shows explicitly whether the rule modifies the entity's data. Possible values are YES and NO. <br/> If the rule only checks if a particular field is filled in or not, then Modify = NO. But if the rule checks if a particular field is filled in and if it is not - sets a value in it, then Modify = YES. |
| Applicable Legislations | Specifies whether the rule has to be executed according to the particular party's applicable legislation. Possible values are:<br/> - 'ALL // no condition needed' - There is no condition and the rule will be executed regardless of the legislation of the related parties.<br/>- The legislation abbreviation (the conditional Party), e.g. BG (EnterpriseCompany.Company) - The rule will be executed only if in the Applicable Legislation child table of the particular Party there is a record with the specified Legislation. |
| Action | Technical description of the conditions and the operation of the rule. |
| Description | Text description of the rule - conditions, operation, the business logic behind it, related topics, and others. |
| Message| The message that is shown in the client application if the conditions of the business rule are not met. Applicable only for validation rules. <br/><br/> May contain additional information about *"Sort Messages By Attribute:"* - Тhe attribute by whose value the message appearance is ordered - if the message is repeated more than once. <br/>If we are editing a document, for example, and the message has to be thrown for a couple of its lines, then it will probably be far easier for the user to follow them if they are sorted by the "Line Number" of the document lines. |
| Version | A list with all versions in which the Business Rule has been somehow changed. Usually contains two types of records: <br/>- 'Introduced: 2xxx.x' - the version since which the Business Rule type is available;<br/>- 'Updated: 2xxx.x' - the version in which the Business Rule has been changed plus a short description of the changes. There could be non or multiple records of this type. |
| Revocable | Shows whether the rule can be revoked for a particular database or not. In order to be revoked - the rule's code has to be specified in the list of the registry key 'RevokedBusinessRules'. (for more information, see key number 37 in the todo:(Config Options Reference topic)) |
