---
uid: Systems.Bpm.CalculatedAttributeExpressions
---
# Systems.Bpm.CalculatedAttributeExpressions Entity

**Namespace:** [Systems.Bpm](Systems.Bpm.md)  

Represent an expression within the calculation of a calculated attribute. Entity: Sys_Calculated_Attribute_Expressions

## Default Visualization
Default Display Text Format:  
_{CalculatedAttribute.Name}_  
Default Search Members:  
_CalculatedAttribute.Name_  
Name Data Member:  
_CalculatedAttribute.Name_  
Category:  _Definitions_  
Show in UI:  _ShownByDefault_  
API access:  _ReadWrite_  

## Track Changes  
Min level:  _0 - Do not track changes_  
Max level:  _4 - Track object attribute and blob changes_  

## Aggregate
An [aggregate](https://docs.erp.net/tech/advanced/concepts/aggregates.html) is a cluster of domain objects that can be treated as a single unit.  

Aggregate Parent:  
[Systems.Bpm.CalculatedAttributes](Systems.Bpm.CalculatedAttributes.md)  
Aggregate Root:  
[Systems.Bpm.CalculatedAttributes](Systems.Bpm.CalculatedAttributes.md)  

## Attributes

| Name | Type | Description |
| ---- | ---- | --- |
| [DisplayText](Systems.Bpm.CalculatedAttributeExpressions.md#displaytext) | string | Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object. 
| [ExpressionNo](Systems.Bpm.CalculatedAttributeExpressions.md#expressionno) | int32 | Unique number of the expression within the attribute. Expression No 0 is the default expression, which provides the result value of the attribute. `Required` 
| [Id](Systems.Bpm.CalculatedAttributeExpressions.md#id) | guid |  
| [Notes](Systems.Bpm.CalculatedAttributeExpressions.md#notes) | string (max) __nullable__ | Notes for this CalculatedAttribute<br />Expression. 
| [ObjectVersion](Systems.Bpm.CalculatedAttributeExpressions.md#objectversion) | int32 | The latest version of the extensible data object for the aggregate root for the time the object is loaded from the database. Can be used for optimistic locking. 
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


## Attribute Details

### DisplayText

Uses the repository DisplayTextFormat to build the display text from the attributes and references of current object.

_Type_: **string**  
_Category_: **Calculated Attributes**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: ****  
_Show in UI_: **HiddenByDefault**  

### ExpressionNo

Unique number of the expression within the attribute. Expression No 0 is the default expression, which provides the result value of the attribute. `Required`

_Type_: **int32**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

_Back-End Default Expression:_  
`( obj.CalculatedAttribute.Expressions.Select( c => c.ExpressionNo).DefaultIfEmpty( 0).Max( ) + 10)`

_Front-End Recalc Expressions:_  
`( obj.CalculatedAttribute.Expressions.Select( c => c.ExpressionNo).DefaultIfEmpty( 0).Max( ) + 10)`
### Id

_Type_: **guid**  
_Indexed_: **True**  
_Category_: **System**  
_Supported Filters_: **Equals, GreaterThanOrLessThan, EqualsIn**  
_Default Value_: **NewGuid**  
_Show in UI_: **CannotBeShown**  

### Notes

Notes for this CalculatedAttributeExpression.

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

### Operator

The exprssion operator. Available operators are limited to a pre-selected list of operators. `Required`

_Type_: **[ExpressionOperator](Systems.Bpm.CalculatedAttributeExpressions.md#operator)**  
_Category_: **System**  
Generic enum type for ExpressionOperator properties  
_Allowed Values (Systems.Bpm.ExpressionOperator Enum Members)_  

| Value | Description |
| ---- | --- |
| ADD | ADD(Number1, Number2) => Numer1 + Number2.. Stored as 'ADD'. <br /> _Database Value:_ 'ADD' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'ADD' |
| ADDDAYS | ADDDAYS(Date, NumDays) => Adds the specified number of days to the date.. Stored as 'ADDDAYS'. <br /> _Database Value:_ 'ADDDAYS' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'ADDDAYS' |
| AND | AND(Condition1, Condition2) => Condition1 AND Condition2.. Stored as 'AND'. <br /> _Database Value:_ 'AND' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'AND' |
| CAST | CAST(Param, Type) => Casts the parameter to the specified type.. Stored as 'CAST'. <br /> _Database Value:_ 'CAST' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'CAST' |
| CEILING | CEILING(Number) => Rounds the number up to the next integer.. Stored as 'CEILING'. <br /> _Database Value:_ 'CEILING' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'CEILING' |
| CONCAT | CONCAT(String1, String2) => Concatenates the strings.. Stored as 'CONCAT'. <br /> _Database Value:_ 'CONCAT' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'CONCAT' |
| CONVERT | CONVERT(Value, NewType) -> Converts a value in the specified new type.. Stored as 'CONVERT'. <br /> _Database Value:_ 'CONVERT' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'CONVERT' |
| COUNT | COUNT(List) -> Gets the number of elements contained in the list. Stored as 'COUNT'. <br /> _Database Value:_ 'COUNT' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'COUNT' |
| DIVIDE | DIVIDE(Number1, Number2) => Numer1 / Number2.. Stored as 'DIVIDE'. <br /> _Database Value:_ 'DIVIDE' <br /> _Model Value:_ 8 <br /> _Domain API Value:_ 'DIVIDE' |
| IN | IN(Input, List) => Returns whether the value of Input is among the specified in the list.. Stored as 'IN'. <br /> _Database Value:_ 'IN' <br /> _Model Value:_ 9 <br /> _Domain API Value:_ 'IN' |
| IIF | IIF(Condition, ResultTrue, ResultFalse) => Depending on Condition, returns the second or third argument.. Stored as 'IIF'. <br /> _Database Value:_ 'IIF' <br /> _Model Value:_ 10 <br /> _Domain API Value:_ 'IIF' |
| INCNUM | The INCNUM operator increases the value of its parameter by 1. The operator can be used only for String values whоose last character is a number.. Stored as 'INCNUM'. <br /> _Database Value:_ 'INCNUM' <br /> _Model Value:_ 11 <br /> _Domain API Value:_ 'INCNUM' |
| EQUAL | EQUAL(Value1, Value2) => Value1 = Value2.. Stored as 'EQUAL'. <br /> _Database Value:_ 'EQUAL' <br /> _Model Value:_ 12 <br /> _Domain API Value:_ 'EQUAL' |
| FILTER | FILTER(List, Condition) => Filters the list by the condition.. Stored as 'FILTER'. <br /> _Database Value:_ 'FILTER' <br /> _Model Value:_ 13 <br /> _Domain API Value:_ 'FILTER' |
| FIRST | FIRST(List) => Returns the first element in the list.. Stored as 'FIRST'. <br /> _Database Value:_ 'FIRST' <br /> _Model Value:_ 14 <br /> _Domain API Value:_ 'FIRST' |
| FLOOR | FLOOR(Number) => Rounds down to integer.. Stored as 'FLOOR'. <br /> _Database Value:_ 'FLOOR' <br /> _Model Value:_ 15 <br /> _Domain API Value:_ 'FLOOR' |
| FORMATSTRING | FORMATSTRING(Object, Format) => Returns String, formatted by the rules in Format.. Stored as 'FORMATSTRING'. <br /> _Database Value:_ 'FORMATSTRING' <br /> _Model Value:_ 16 <br /> _Domain API Value:_ 'FORMATSTRING' |
| GETVALUE | GETVALUE(Value) => Get the value from the current object.. Stored as 'GETVALUE'. <br /> _Database Value:_ 'GETVALUE' <br /> _Model Value:_ 17 <br /> _Domain API Value:_ 'GETVALUE' |
| GETOBJVALUE | GETOBJVALUE(Obj, Value) => obj.Value. Gets the specified value from the object.. Stored as 'GETOBJVALUE'. <br /> _Database Value:_ 'GETOBJVALUE' <br /> _Model Value:_ 18 <br /> _Domain API Value:_ 'GETOBJVALUE' |
| GT | GT(Value1, Value2) => Value1 > Value2.. Stored as 'GT'. <br /> _Database Value:_ 'GT' <br /> _Model Value:_ 19 <br /> _Domain API Value:_ 'GT' |
| GTE | GTE(Value1, Value2) => Value1 >= Value2.. Stored as 'GTE'. <br /> _Database Value:_ 'GTE' <br /> _Model Value:_ 20 <br /> _Domain API Value:_ 'GTE' |
| LIKE | LIKE(String, Mask) => String LIKE Mask (%-match any string. _-match 1 char).. Stored as 'LIKE'. <br /> _Database Value:_ 'LIKE' <br /> _Model Value:_ 21 <br /> _Domain API Value:_ 'LIKE' |
| LIST | LIST(List, Attribute, Separator) => Returns list with the string values of the specified attribute of the list of objects. The values are separated by the specified separator. Stored as 'LIST'. <br /> _Database Value:_ 'LIST' <br /> _Model Value:_ 22 <br /> _Domain API Value:_ 'LIST' |
| LEFT | LEFT(String, NumChars) => Gets the first characters of a string.. Stored as 'LEFT'. <br /> _Database Value:_ 'LEFT' <br /> _Model Value:_ 23 <br /> _Domain API Value:_ 'LEFT' |
| LEN | LEN(String) => Returns the length of the string.. Stored as 'LEN'. <br /> _Database Value:_ 'LEN' <br /> _Model Value:_ 24 <br /> _Domain API Value:_ 'LEN' |
| LT | LT(Value1, Value2) => Value1 < Value2.. Stored as 'LT'. <br /> _Database Value:_ 'LT' <br /> _Model Value:_ 25 <br /> _Domain API Value:_ 'LT' |
| LTE | LTE(Value1, Value2) => Value1 <= Value2.. Stored as 'LTE'. <br /> _Database Value:_ 'LTE' <br /> _Model Value:_ 26 <br /> _Domain API Value:_ 'LTE' |
| MULTIPLY | MULTIPLY(Number1, Number2) => Numer1 * Number2.. Stored as 'MULTIPLY'. <br /> _Database Value:_ 'MULTIPLY' <br /> _Model Value:_ 27 <br /> _Domain API Value:_ 'MULTIPLY' |
| NOT | NOT(Condition) => NOT Condition.. Stored as 'NOT'. <br /> _Database Value:_ 'NOT' <br /> _Model Value:_ 28 <br /> _Domain API Value:_ 'NOT' |
| OR | OR(Condition1, Condition2) => Condition1 OR Condition2.. Stored as 'OR'. <br /> _Database Value:_ 'OR' <br /> _Model Value:_ 29 <br /> _Domain API Value:_ 'OR' |
| ORDERBY | ORDERBY(Attribute, Order, Next_clause) => Clause, specifying a sort order according to Attribute and the specified order (ASC | DESC).. Stored as 'ORDERBY'. <br /> _Database Value:_ 'ORDERBY' <br /> _Model Value:_ 30 <br /> _Domain API Value:_ 'ORDERBY' |
| POS | POS(Term, String) => Searches term in String, returns first position or -1 if not found.. Stored as 'POS'. <br /> _Database Value:_ 'POS' <br /> _Model Value:_ 31 <br /> _Domain API Value:_ 'POS' |
| REGEX | REGEX(String, Mask) => Returns whether the string matches the regex mask.. Stored as 'REGEX'. <br /> _Database Value:_ 'REGEX' <br /> _Model Value:_ 32 <br /> _Domain API Value:_ 'REGEX' |
| REPLACE | REPLACE(String, OldValue, NewValue) => Replaces old with new value in string.. Stored as 'REPLACE'. <br /> _Database Value:_ 'REPLACE' <br /> _Model Value:_ 33 <br /> _Domain API Value:_ 'REPLACE' |
| RIGHT | RIGHT(String, NumChars) => Gets the last characters of a string.. Stored as 'RIGHT'. <br /> _Database Value:_ 'RIGHT' <br /> _Model Value:_ 34 <br /> _Domain API Value:_ 'RIGHT' |
| ROUND | ROUND(Number, DecimalPlaces) => Rounds mathematically with the specified precision.. Stored as 'ROUND'. <br /> _Database Value:_ 'ROUND' <br /> _Model Value:_ 35 <br /> _Domain API Value:_ 'ROUND' |
| SELECT | SELECT(Repository, Clauses) => Gets the objects, matching the clauses.. Stored as 'SELECT'. <br /> _Database Value:_ 'SELECT' <br /> _Model Value:_ 36 <br /> _Domain API Value:_ 'SELECT' |
| SORT | SORT(List, Attribute, Order) => Sorts the list according to the attribute and the specified order (ASC | DESC).. Stored as 'SORT'. <br /> _Database Value:_ 'SORT' <br /> _Model Value:_ 37 <br /> _Domain API Value:_ 'SORT' |
| SUBSTRING | SUBSTRING(String, Start, Len) => Returns a sub-string with the specified start and length.. Stored as 'SUBSTRING'. <br /> _Database Value:_ 'SUBSTRING' <br /> _Model Value:_ 38 <br /> _Domain API Value:_ 'SUBSTRING' |
| SUM | SUM(List, Value) => Returns the sum of Value for all elements in the list.. Stored as 'SUM'. <br /> _Database Value:_ 'SUM' <br /> _Model Value:_ 39 <br /> _Domain API Value:_ 'SUM' |
| TODAY | TODAY() => Returns the current date.. Stored as 'TODAY'. <br /> _Database Value:_ 'TODAY' <br /> _Model Value:_ 40 <br /> _Domain API Value:_ 'TODAY' |
| TOLOWER | TOLOWER(String) => Returns the string, converted to lower-case.. Stored as 'TOLOWER'. <br /> _Database Value:_ 'TOLOWER' <br /> _Model Value:_ 41 <br /> _Domain API Value:_ 'TOLOWER' |
| TOP | TOP(Number, Clauses) => Clause, returning only the first elements.. Stored as 'TOP'. <br /> _Database Value:_ 'TOP' <br /> _Model Value:_ 42 <br /> _Domain API Value:_ 'TOP' |
| TOUPPER | TOUPPER(String) => Returns the string, converted to upper-case.. Stored as 'TOUPPER'. <br /> _Database Value:_ 'TOUPPER' <br /> _Model Value:_ 43 <br /> _Domain API Value:_ 'TOUPPER' |
| WHERE | WHERE(Condition1, Condition2) => Clause, which filters by Condition1 AND Condition2.. Stored as 'WHERE'. <br /> _Database Value:_ 'WHERE' <br /> _Model Value:_ 44 <br /> _Domain API Value:_ 'WHERE' |
| INTERPOLATE | INTERPOLATE(Object?, InterpolatedString) => Performs string interpolation, according to the context of the passed object.. Stored as 'INTERPOLATE'. <br /> _Database Value:_ 'INTERPOLATE' <br /> _Model Value:_ 45 <br /> _Domain API Value:_ 'INTERPOLATE' |
| DATEDIFF | DATEDIFF(DateTime, DateTime, Interval?) => Returns the difference between dates as the date difference for the specified interval type.. Stored as 'DATEDIFF'. <br /> _Database Value:_ 'DATEDIFF' <br /> _Model Value:_ 46 <br /> _Domain API Value:_ 'DATEDIFF' |
| DATESPAN | DATESPAN(DateTime, DateTime, Interval?) => Returns the difference between dates as a duration in the specified interval type. The interval is fulfilled when the same date and time is reached in the next interval.. Stored as 'DATESPAN'. <br /> _Database Value:_ 'DATESPAN' <br /> _Model Value:_ 47 <br /> _Domain API Value:_ 'DATESPAN' |
| IFERROR | IFERROR(Value, ValueIfError) => Evaluates an expression and returns the value specified in the second parameter, if the expression returns an error. Otherwise returns the value of the expression itself.. Stored as 'IFERROR'. <br /> _Database Value:_ 'IFERROR' <br /> _Model Value:_ 48 <br /> _Domain API Value:_ 'IFERROR' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Parameter1Type

The type of the parameter specifies how to obtain the parameter value.

_Type_: **[ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter1type) __nullable__**  
_Category_: **System**  
Generic enum type for ExpressionParameterType properties  
_Allowed Values (Systems.Bpm.ExpressionParameterType Enum Members)_  

| Value | Description |
| ---- | --- |
| Constant | Constant. Format: Date(yyyy-MM-dd), Decimal(9.9), Int(9), String('...'), True/False.. Stored as 'CONST'. <br /> _Database Value:_ 'CONST' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Constant' |
| Attribute | The value of system or user-defined attribute.. Stored as 'ATTRIB'. <br /> _Database Value:_ 'ATTRIB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Attribute' |
| Reference | Reference to another object.. Stored as 'REF'. <br /> _Database Value:_ 'REF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Reference' |
| ChildList | Child lists return detail objects, related to the current master object.. Stored as 'CHILD'. <br /> _Database Value:_ 'CHILD' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'ChildList' |
| Expression | The value of the expression with the specified number.. Stored as 'EXP'. <br /> _Database Value:_ 'EXP' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Expression' |
| Input | The input parameter for the specified expression number.. Stored as 'INPUT'. <br /> _Database Value:_ 'INPUT' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Input' |
| Repository | A repository.. Stored as 'REPO'. <br /> _Database Value:_ 'REPO' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Repository' |
| System | A system value.. Stored as 'SYS'. <br /> _Database Value:_ 'SYS' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'System' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Parameter1Value

The actual value of parameter 1.

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### Parameter2Type

The type of the parameter specifies how to obtain the parameter value.

_Type_: **[ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter2type) __nullable__**  
_Category_: **System**  
Generic enum type for ExpressionParameterType properties  
_Allowed Values (Systems.Bpm.ExpressionParameterType Enum Members)_  

| Value | Description |
| ---- | --- |
| Constant | Constant. Format: Date(yyyy-MM-dd), Decimal(9.9), Int(9), String('...'), True/False.. Stored as 'CONST'. <br /> _Database Value:_ 'CONST' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Constant' |
| Attribute | The value of system or user-defined attribute.. Stored as 'ATTRIB'. <br /> _Database Value:_ 'ATTRIB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Attribute' |
| Reference | Reference to another object.. Stored as 'REF'. <br /> _Database Value:_ 'REF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Reference' |
| ChildList | Child lists return detail objects, related to the current master object.. Stored as 'CHILD'. <br /> _Database Value:_ 'CHILD' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'ChildList' |
| Expression | The value of the expression with the specified number.. Stored as 'EXP'. <br /> _Database Value:_ 'EXP' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Expression' |
| Input | The input parameter for the specified expression number.. Stored as 'INPUT'. <br /> _Database Value:_ 'INPUT' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Input' |
| Repository | A repository.. Stored as 'REPO'. <br /> _Database Value:_ 'REPO' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Repository' |
| System | A system value.. Stored as 'SYS'. <br /> _Database Value:_ 'SYS' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'System' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Parameter2Value

The actual value of the parameter.

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  

### Parameter3Type

The type of the parameter specifies how to obtain the parameter value.

_Type_: **[ExpressionParameterType](Systems.Bpm.CalculatedAttributeExpressions.md#parameter3type) __nullable__**  
_Category_: **System**  
Generic enum type for ExpressionParameterType properties  
_Allowed Values (Systems.Bpm.ExpressionParameterType Enum Members)_  

| Value | Description |
| ---- | --- |
| Constant | Constant. Format: Date(yyyy-MM-dd), Decimal(9.9), Int(9), String('...'), True/False.. Stored as 'CONST'. <br /> _Database Value:_ 'CONST' <br /> _Model Value:_ 0 <br /> _Domain API Value:_ 'Constant' |
| Attribute | The value of system or user-defined attribute.. Stored as 'ATTRIB'. <br /> _Database Value:_ 'ATTRIB' <br /> _Model Value:_ 1 <br /> _Domain API Value:_ 'Attribute' |
| Reference | Reference to another object.. Stored as 'REF'. <br /> _Database Value:_ 'REF' <br /> _Model Value:_ 2 <br /> _Domain API Value:_ 'Reference' |
| ChildList | Child lists return detail objects, related to the current master object.. Stored as 'CHILD'. <br /> _Database Value:_ 'CHILD' <br /> _Model Value:_ 3 <br /> _Domain API Value:_ 'ChildList' |
| Expression | The value of the expression with the specified number.. Stored as 'EXP'. <br /> _Database Value:_ 'EXP' <br /> _Model Value:_ 4 <br /> _Domain API Value:_ 'Expression' |
| Input | The input parameter for the specified expression number.. Stored as 'INPUT'. <br /> _Database Value:_ 'INPUT' <br /> _Model Value:_ 5 <br /> _Domain API Value:_ 'Input' |
| Repository | A repository.. Stored as 'REPO'. <br /> _Database Value:_ 'REPO' <br /> _Model Value:_ 6 <br /> _Domain API Value:_ 'Repository' |
| System | A system value.. Stored as 'SYS'. <br /> _Database Value:_ 'SYS' <br /> _Model Value:_ 7 <br /> _Domain API Value:_ 'System' |

_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Show in UI_: **ShownByDefault**  

### Parameter3Value

The actual value of the parameter.

_Type_: **string (256) __nullable__**  
_Category_: **System**  
_Supported Filters_: **NotFilterable**  
_Supports Order By_: **False**  
_Maximum Length_: **256**  
_Show in UI_: **ShownByDefault**  


## Reference Details

### CalculatedAttribute

The <see cref="CalculatedAttribute"/> to which this CalculatedAttributeExpression belongs. `Required` `Filter(multi eq)` `Owner`

_Type_: **[CalculatedAttributes](Systems.Bpm.CalculatedAttributes.md)**  
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

