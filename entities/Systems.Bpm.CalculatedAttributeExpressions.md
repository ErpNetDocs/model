---
uid: Systems.Bpm.CalculatedAttributeExpressions
---
# Systems.Bpm.CalculatedAttributeExpressions


Represent an expression within the calculation of a calculated attribute.

## General
Namespace: [Systems.Bpm](Systems.Bpm.md)  
Repository: Systems.Bpm.CalculatedAttributeExpressions  
Base Table: Sys_Calculated_Attribute_Expressions  
API access:  ReadWrite  

## Visualization
Display Format: {CalculatedAttribute.Name}  
Search Members: CalculatedAttribute.Name  
Name Member: CalculatedAttribute.Name  
Category:  Definitions  
Show in UI:  ShownByDefault  

## Track Changes  
Min level:  0 - Do not track changes  
Max level:  4 - Track object attribute and blob changes  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.CalculatedAttributes](Systems.Bpm.CalculatedAttributes.md)  
Aggregate Root:  
[Systems.Bpm.CalculatedAttributes](Systems.Bpm.CalculatedAttributes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [ExpressionNo](Systems.Bpm.CalculatedAttributeExpressions.md#expressionno) | int32 | Unique number of the expression within the attribute. Expression No 0 is the default expression, which provides the result value of the attribute. `Required` 
| [Notes](Systems.Bpm.CalculatedAttributeExpressions.md#notes) | string (max) __nullable__ | Notes for this CalculatedAttribute<br />Expression. 
| [Operator](Systems.Bpm.CalculatedAttributeExpressions.md#operator) | [ExpressionOperator](Systems.Bpm.CalculatedAttributeExpressions.md#operator) | The exprssion operator. Available operators are limited to a pre-selected list of operators. `Required` 
| [Parameter1Type](Systems.Bpm.CalculatedAttributeExpressions.md#parameter1type) | [ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter1type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter1Value](Systems.Bpm.CalculatedAttributeExpressions.md#parameter1value) | string (256) __nullable__ | The actual value of parameter 1. 
| [Parameter2Type](Systems.Bpm.CalculatedAttributeExpressions.md#parameter2type) | [ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter2type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter2Value](Systems.Bpm.CalculatedAttributeExpressions.md#parameter2value) | string (256) __nullable__ | The actual value of the parameter. 
| [Parameter3Type](Systems.Bpm.CalculatedAttributeExpressions.md#parameter3type) | [ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter3type) __nullable__ | The type of the parameter specifies how to obtain the parameter value. 
| [Parameter3Value](Systems.Bpm.CalculatedAttributeExpressions.md#parameter3value) | string (256) __nullable__ | The actual value of the parameter. 

## References

| Name | Type | Description |
| ---- | ---- | --- |
| [CalculatedAttribute](Systems.Bpm.CalculatedAttributeExpressions.md#calculatedattribute) | [CalculatedAttributes](Systems.Bpm.CalculatedAttributes.md) | The <see cref="Calculated<br />Attribute"/> to which this CalculatedAttribute<br />Expression belongs. `Required` `Filter(multi eq)` `Owner` |


## System Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [Id](Systems.Bpm.CalculatedAttributeExpressions.md#id) | guid |  
| [ObjectVersion](Systems.Bpm.CalculatedAttributeExpressions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
| [DisplayText](Systems.Bpm.CalculatedAttributeExpressions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 


## Attribute Details

### ExpressionNo

Unique number of the expression within the attribute. Expression No 0 is the default expression, which provides the result value of the attribute. `Required`

Type: **int32**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

Back-End Default Expression:  
`( obj.CalculatedAttribute.Expressions.Select( c => c.ExpressionNo).DefaultIfEmpty( 0).Max( ) + 10)`

Front-End Recalc Expressions:  
`( obj.CalculatedAttribute.Expressions.Select( c => c.ExpressionNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Notes

Notes for this CalculatedAttributeExpression.

Type: **string (max) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **2147483647**  
Show in UI: **ShownByDefault**  

### Operator

The exprssion operator. Available operators are limited to a pre-selected list of operators. `Required`

Type: **[ExpressionOperator](Systems.Bpm.CalculatedAttributeExpressions.md#operator)**  
Category: **System**  
Generic enum type for ExpressionOperator properties  
Allowed Values (Systems.Bpm.ExpressionOperator Enum Members)  

| Value | Description |
| ---- | --- |
| ADD | ADD(Number1, Number2) => Numer1 + Number2.. Stored as 'ADD'. <br /> Database Value: 'ADD' <br /> Model Value: 0 <br /> Domain API Value: 'ADD' |
| ADDDAYS | ADDDAYS(Date, NumDays) => Adds the specified number of days to the date.. Stored as 'ADDDAYS'. <br /> Database Value: 'ADDDAYS' <br /> Model Value: 1 <br /> Domain API Value: 'ADDDAYS' |
| AND | AND(Condition1, Condition2) => Condition1 AND Condition2.. Stored as 'AND'. <br /> Database Value: 'AND' <br /> Model Value: 2 <br /> Domain API Value: 'AND' |
| CAST | CAST(Param, Type) => Casts the parameter to the specified type.. Stored as 'CAST'. <br /> Database Value: 'CAST' <br /> Model Value: 3 <br /> Domain API Value: 'CAST' |
| CEILING | CEILING(Number) => Rounds the number up to the next integer.. Stored as 'CEILING'. <br /> Database Value: 'CEILING' <br /> Model Value: 4 <br /> Domain API Value: 'CEILING' |
| CONCAT | CONCAT(String1, String2) => Concatenates the strings.. Stored as 'CONCAT'. <br /> Database Value: 'CONCAT' <br /> Model Value: 5 <br /> Domain API Value: 'CONCAT' |
| CONVERT | CONVERT(Value, NewType) -> Converts a value in the specified new type.. Stored as 'CONVERT'. <br /> Database Value: 'CONVERT' <br /> Model Value: 6 <br /> Domain API Value: 'CONVERT' |
| COUNT | COUNT(List) -> Gets the number of elements contained in the list. Stored as 'COUNT'. <br /> Database Value: 'COUNT' <br /> Model Value: 7 <br /> Domain API Value: 'COUNT' |
| DIVIDE | DIVIDE(Number1, Number2) => Numer1 / Number2.. Stored as 'DIVIDE'. <br /> Database Value: 'DIVIDE' <br /> Model Value: 8 <br /> Domain API Value: 'DIVIDE' |
| IN | IN(Input, List) => Returns whether the value of Input is among the specified in the list.. Stored as 'IN'. <br /> Database Value: 'IN' <br /> Model Value: 9 <br /> Domain API Value: 'IN' |
| IIF | IIF(Condition, ResultTrue, ResultFalse) => Depending on Condition, returns the second or third argument.. Stored as 'IIF'. <br /> Database Value: 'IIF' <br /> Model Value: 10 <br /> Domain API Value: 'IIF' |
| INCNUM | The INCNUM operator increases the value of its parameter by 1. The operator can be used only for String values whоose last character is a number.. Stored as 'INCNUM'. <br /> Database Value: 'INCNUM' <br /> Model Value: 11 <br /> Domain API Value: 'INCNUM' |
| EQUAL | EQUAL(Value1, Value2) => Value1 = Value2.. Stored as 'EQUAL'. <br /> Database Value: 'EQUAL' <br /> Model Value: 12 <br /> Domain API Value: 'EQUAL' |
| FILTER | FILTER(List, Condition) => Filters the list by the condition.. Stored as 'FILTER'. <br /> Database Value: 'FILTER' <br /> Model Value: 13 <br /> Domain API Value: 'FILTER' |
| FIRST | FIRST(List) => Returns the first element in the list.. Stored as 'FIRST'. <br /> Database Value: 'FIRST' <br /> Model Value: 14 <br /> Domain API Value: 'FIRST' |
| FLOOR | FLOOR(Number) => Rounds down to integer.. Stored as 'FLOOR'. <br /> Database Value: 'FLOOR' <br /> Model Value: 15 <br /> Domain API Value: 'FLOOR' |
| FORMATSTRING | FORMATSTRING(Object, Format) => Returns String, formatted by the rules in Format.. Stored as 'FORMATSTRING'. <br /> Database Value: 'FORMATSTRING' <br /> Model Value: 16 <br /> Domain API Value: 'FORMATSTRING' |
| GETVALUE | GETVALUE(Value) => Get the value from the current object.. Stored as 'GETVALUE'. <br /> Database Value: 'GETVALUE' <br /> Model Value: 17 <br /> Domain API Value: 'GETVALUE' |
| GETOBJVALUE | GETOBJVALUE(Obj, Value) => obj.Value. Gets the specified value from the object.. Stored as 'GETOBJVALUE'. <br /> Database Value: 'GETOBJVALUE' <br /> Model Value: 18 <br /> Domain API Value: 'GETOBJVALUE' |
| GT | GT(Value1, Value2) => Value1 > Value2.. Stored as 'GT'. <br /> Database Value: 'GT' <br /> Model Value: 19 <br /> Domain API Value: 'GT' |
| GTE | GTE(Value1, Value2) => Value1 >= Value2.. Stored as 'GTE'. <br /> Database Value: 'GTE' <br /> Model Value: 20 <br /> Domain API Value: 'GTE' |
| LIKE | LIKE(String, Mask) => String LIKE Mask (%-match any string. _-match 1 char).. Stored as 'LIKE'. <br /> Database Value: 'LIKE' <br /> Model Value: 21 <br /> Domain API Value: 'LIKE' |
| LIST | LIST(List, Attribute, Separator) => Returns list with the string values of the specified attribute of the list of objects. The values are separated by the specified separator. Stored as 'LIST'. <br /> Database Value: 'LIST' <br /> Model Value: 22 <br /> Domain API Value: 'LIST' |
| LEFT | LEFT(String, NumChars) => Gets the first characters of a string.. Stored as 'LEFT'. <br /> Database Value: 'LEFT' <br /> Model Value: 23 <br /> Domain API Value: 'LEFT' |
| LEN | LEN(String) => Returns the length of the string.. Stored as 'LEN'. <br /> Database Value: 'LEN' <br /> Model Value: 24 <br /> Domain API Value: 'LEN' |
| LT | LT(Value1, Value2) => Value1 < Value2.. Stored as 'LT'. <br /> Database Value: 'LT' <br /> Model Value: 25 <br /> Domain API Value: 'LT' |
| LTE | LTE(Value1, Value2) => Value1 <= Value2.. Stored as 'LTE'. <br /> Database Value: 'LTE' <br /> Model Value: 26 <br /> Domain API Value: 'LTE' |
| MULTIPLY | MULTIPLY(Number1, Number2) => Numer1 * Number2.. Stored as 'MULTIPLY'. <br /> Database Value: 'MULTIPLY' <br /> Model Value: 27 <br /> Domain API Value: 'MULTIPLY' |
| NOT | NOT(Condition) => NOT Condition.. Stored as 'NOT'. <br /> Database Value: 'NOT' <br /> Model Value: 28 <br /> Domain API Value: 'NOT' |
| OR | OR(Condition1, Condition2) => Condition1 OR Condition2.. Stored as 'OR'. <br /> Database Value: 'OR' <br /> Model Value: 29 <br /> Domain API Value: 'OR' |
| ORDERBY | ORDERBY(Attribute, Order, Next_clause) => Clause, specifying a sort order according to Attribute and the specified order (ASC | DESC).. Stored as 'ORDERBY'. <br /> Database Value: 'ORDERBY' <br /> Model Value: 30 <br /> Domain API Value: 'ORDERBY' |
| POS | POS(Term, String) => Searches term in String, returns first position or -1 if not found.. Stored as 'POS'. <br /> Database Value: 'POS' <br /> Model Value: 31 <br /> Domain API Value: 'POS' |
| REGEX | REGEX(String, Mask) => Returns whether the string matches the regex mask.. Stored as 'REGEX'. <br /> Database Value: 'REGEX' <br /> Model Value: 32 <br /> Domain API Value: 'REGEX' |
| REPLACE | REPLACE(String, OldValue, NewValue) => Replaces old with new value in string.. Stored as 'REPLACE'. <br /> Database Value: 'REPLACE' <br /> Model Value: 33 <br /> Domain API Value: 'REPLACE' |
| RIGHT | RIGHT(String, NumChars) => Gets the last characters of a string.. Stored as 'RIGHT'. <br /> Database Value: 'RIGHT' <br /> Model Value: 34 <br /> Domain API Value: 'RIGHT' |
| ROUND | ROUND(Number, DecimalPlaces) => Rounds mathematically with the specified precision.. Stored as 'ROUND'. <br /> Database Value: 'ROUND' <br /> Model Value: 35 <br /> Domain API Value: 'ROUND' |
| SELECT | SELECT(Repository, Clauses) => Gets the objects, matching the clauses.. Stored as 'SELECT'. <br /> Database Value: 'SELECT' <br /> Model Value: 36 <br /> Domain API Value: 'SELECT' |
| SORT | SORT(List, Attribute, Order) => Sorts the list according to the attribute and the specified order (ASC | DESC).. Stored as 'SORT'. <br /> Database Value: 'SORT' <br /> Model Value: 37 <br /> Domain API Value: 'SORT' |
| SUBSTRING | SUBSTRING(String, Start, Len) => Returns a sub-string with the specified start and length.. Stored as 'SUBSTRING'. <br /> Database Value: 'SUBSTRING' <br /> Model Value: 38 <br /> Domain API Value: 'SUBSTRING' |
| SUM | SUM(List, Value) => Returns the sum of Value for all elements in the list.. Stored as 'SUM'. <br /> Database Value: 'SUM' <br /> Model Value: 39 <br /> Domain API Value: 'SUM' |
| TODAY | TODAY() => Returns the current date.. Stored as 'TODAY'. <br /> Database Value: 'TODAY' <br /> Model Value: 40 <br /> Domain API Value: 'TODAY' |
| TOLOWER | TOLOWER(String) => Returns the string, converted to lower-case.. Stored as 'TOLOWER'. <br /> Database Value: 'TOLOWER' <br /> Model Value: 41 <br /> Domain API Value: 'TOLOWER' |
| TOP | TOP(Number, Clauses) => Clause, returning only the first elements.. Stored as 'TOP'. <br /> Database Value: 'TOP' <br /> Model Value: 42 <br /> Domain API Value: 'TOP' |
| TOUPPER | TOUPPER(String) => Returns the string, converted to upper-case.. Stored as 'TOUPPER'. <br /> Database Value: 'TOUPPER' <br /> Model Value: 43 <br /> Domain API Value: 'TOUPPER' |
| WHERE | WHERE(Condition1, Condition2) => Clause, which filters by Condition1 AND Condition2.. Stored as 'WHERE'. <br /> Database Value: 'WHERE' <br /> Model Value: 44 <br /> Domain API Value: 'WHERE' |
| INTERPOLATE | INTERPOLATE(Object?, InterpolatedString) => Performs string interpolation, according to the context of the passed object.. Stored as 'INTERPOLATE'. <br /> Database Value: 'INTERPOLATE' <br /> Model Value: 45 <br /> Domain API Value: 'INTERPOLATE' |
| DATEDIFF | DATEDIFF(DateTime, DateTime, Interval?) => Returns the difference between dates as the date difference for the specified interval type.. Stored as 'DATEDIFF'. <br /> Database Value: 'DATEDIFF' <br /> Model Value: 46 <br /> Domain API Value: 'DATEDIFF' |
| DATESPAN | DATESPAN(DateTime, DateTime, Interval?) => Returns the difference between dates as a duration in the specified interval type. The interval is fulfilled when the same date and time is reached in the next interval.. Stored as 'DATESPAN'. <br /> Database Value: 'DATESPAN' <br /> Model Value: 47 <br /> Domain API Value: 'DATESPAN' |
| IFERROR | IFERROR(Value, ValueIfError) => Evaluates an expression and returns the value specified in the second parameter, if the expression returns an error. Otherwise returns the value of the expression itself.. Stored as 'IFERROR'. <br /> Database Value: 'IFERROR' <br /> Model Value: 48 <br /> Domain API Value: 'IFERROR' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Parameter1Type

The type of the parameter specifies how to obtain the parameter value.

Type: **[ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter1type) __nullable__**  
Category: **System**  
Generic enum type for ExpressionParameterType properties  
Allowed Values (Systems.Bpm.ExpressionParameterType Enum Members)  

| Value | Description |
| ---- | --- |
| Constant | Constant. Format: Date(yyyy-MM-dd), Decimal(9.9), Int(9), String('...'), True/False.. Stored as 'CONST'. <br /> Database Value: 'CONST' <br /> Model Value: 0 <br /> Domain API Value: 'Constant' |
| Attribute | The value of system or user-defined attribute.. Stored as 'ATTRIB'. <br /> Database Value: 'ATTRIB' <br /> Model Value: 1 <br /> Domain API Value: 'Attribute' |
| Reference | Reference to another object.. Stored as 'REF'. <br /> Database Value: 'REF' <br /> Model Value: 2 <br /> Domain API Value: 'Reference' |
| ChildList | Child lists return detail objects, related to the current master object.. Stored as 'CHILD'. <br /> Database Value: 'CHILD' <br /> Model Value: 3 <br /> Domain API Value: 'ChildList' |
| Expression | The value of the expression with the specified number.. Stored as 'EXP'. <br /> Database Value: 'EXP' <br /> Model Value: 4 <br /> Domain API Value: 'Expression' |
| Input | The input parameter for the specified expression number.. Stored as 'INPUT'. <br /> Database Value: 'INPUT' <br /> Model Value: 5 <br /> Domain API Value: 'Input' |
| Repository | A repository.. Stored as 'REPO'. <br /> Database Value: 'REPO' <br /> Model Value: 6 <br /> Domain API Value: 'Repository' |
| System | A system value.. Stored as 'SYS'. <br /> Database Value: 'SYS' <br /> Model Value: 7 <br /> Domain API Value: 'System' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Parameter1Value

The actual value of parameter 1.

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### Parameter2Type

The type of the parameter specifies how to obtain the parameter value.

Type: **[ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter2type) __nullable__**  
Category: **System**  
Generic enum type for ExpressionParameterType properties  
Allowed Values (Systems.Bpm.ExpressionParameterType Enum Members)  

| Value | Description |
| ---- | --- |
| Constant | Constant. Format: Date(yyyy-MM-dd), Decimal(9.9), Int(9), String('...'), True/False.. Stored as 'CONST'. <br /> Database Value: 'CONST' <br /> Model Value: 0 <br /> Domain API Value: 'Constant' |
| Attribute | The value of system or user-defined attribute.. Stored as 'ATTRIB'. <br /> Database Value: 'ATTRIB' <br /> Model Value: 1 <br /> Domain API Value: 'Attribute' |
| Reference | Reference to another object.. Stored as 'REF'. <br /> Database Value: 'REF' <br /> Model Value: 2 <br /> Domain API Value: 'Reference' |
| ChildList | Child lists return detail objects, related to the current master object.. Stored as 'CHILD'. <br /> Database Value: 'CHILD' <br /> Model Value: 3 <br /> Domain API Value: 'ChildList' |
| Expression | The value of the expression with the specified number.. Stored as 'EXP'. <br /> Database Value: 'EXP' <br /> Model Value: 4 <br /> Domain API Value: 'Expression' |
| Input | The input parameter for the specified expression number.. Stored as 'INPUT'. <br /> Database Value: 'INPUT' <br /> Model Value: 5 <br /> Domain API Value: 'Input' |
| Repository | A repository.. Stored as 'REPO'. <br /> Database Value: 'REPO' <br /> Model Value: 6 <br /> Domain API Value: 'Repository' |
| System | A system value.. Stored as 'SYS'. <br /> Database Value: 'SYS' <br /> Model Value: 7 <br /> Domain API Value: 'System' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Parameter2Value

The actual value of the parameter.

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
Show in UI: **ShownByDefault**  

### Parameter3Type

The type of the parameter specifies how to obtain the parameter value.

Type: **[ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter3type) __nullable__**  
Category: **System**  
Generic enum type for ExpressionParameterType properties  
Allowed Values (Systems.Bpm.ExpressionParameterType Enum Members)  

| Value | Description |
| ---- | --- |
| Constant | Constant. Format: Date(yyyy-MM-dd), Decimal(9.9), Int(9), String('...'), True/False.. Stored as 'CONST'. <br /> Database Value: 'CONST' <br /> Model Value: 0 <br /> Domain API Value: 'Constant' |
| Attribute | The value of system or user-defined attribute.. Stored as 'ATTRIB'. <br /> Database Value: 'ATTRIB' <br /> Model Value: 1 <br /> Domain API Value: 'Attribute' |
| Reference | Reference to another object.. Stored as 'REF'. <br /> Database Value: 'REF' <br /> Model Value: 2 <br /> Domain API Value: 'Reference' |
| ChildList | Child lists return detail objects, related to the current master object.. Stored as 'CHILD'. <br /> Database Value: 'CHILD' <br /> Model Value: 3 <br /> Domain API Value: 'ChildList' |
| Expression | The value of the expression with the specified number.. Stored as 'EXP'. <br /> Database Value: 'EXP' <br /> Model Value: 4 <br /> Domain API Value: 'Expression' |
| Input | The input parameter for the specified expression number.. Stored as 'INPUT'. <br /> Database Value: 'INPUT' <br /> Model Value: 5 <br /> Domain API Value: 'Input' |
| Repository | A repository.. Stored as 'REPO'. <br /> Database Value: 'REPO' <br /> Model Value: 6 <br /> Domain API Value: 'Repository' |
| System | A system value.. Stored as 'SYS'. <br /> Database Value: 'SYS' <br /> Model Value: 7 <br /> Domain API Value: 'System' |

Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Show in UI: **ShownByDefault**  

### Parameter3Value

The actual value of the parameter.

Type: **string (256) __nullable__**  
Category: **System**  
Supported Filters: **NotFilterable**  
Supports Order By: **False**  
Maximum Length: **256**  
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

### CalculatedAttribute

The <see cref="CalculatedAttribute"/> to which this CalculatedAttributeExpression belongs. `Required` `Filter(multi eq)` `Owner`

Type: **[CalculatedAttributes](Systems.Bpm.CalculatedAttributes.md)**  
Indexed: **True**  
Category: **System**  
Supported Filters: **Equals, EqualsIn**  
[Filterable Reference](https://docs.erp.net/dev/domain-api/filterable-references.html): **True**  
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

[!list limit=1000 erp.entity=Systems.Bpm.CalculatedAttributeExpressions erp.type=business-rule default-text="None"]

## Front-End Business Rules

[!list limit=1000 erp.entity=Systems.Bpm.CalculatedAttributeExpressions erp.type=front-end-business-rule default-text="None"]

## API

Domain API Entity Set: 
Systems_Bpm_CalculatedAttributeExpressions

Domain API Entity Type: 
Systems_Bpm_CalculatedAttributeExpression

Domain API Query:
<https://testdb.my.erp.net/api/domain/odata/Systems_Bpm_CalculatedAttributeExpressions?$top=10>

Domain API Query Builder:
<https://testdb.my.erp.net/api/domain/querybuilder#Systems_Bpm_CalculatedAttributeExpressions?$top=10>

