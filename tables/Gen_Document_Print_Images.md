# Table Gen_Document_Print_Images


## Entity

Entity: [Systems.Core.DocumentPrintImages](~/entities/Systems.Core.DocumentPrintImages.md)

Contains the data of a printout of a document as it was obtained from the data source in the moment of printing. Entity: Gen_Document_Print_Images

## Summary

| Name | Type | Description |
| - | - | --- |
|[Document_Print_Image_Id](#document_print_image_id)|`uniqueidentifier` `PK`||
|[Print_Image](#print_image)|`varbinary` |The data of the printout, stored in the format, specified in Print Image Format.|
|[Print_Image_Format](#print_image_format)|`nvarchar(3)` |The format, which is used to represent the print image. Currently, only 'CDS' = Compressed Data Set is supported.|
|[Printout_Layout_Id](#printout_layout_id)|`uniqueidentifier` |The print layout, which was used for the current printout.|
|[Row_Version](#row_version)|`timestamp` ||

## Columns

### Document_Print_Image_Id

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|NewGuid|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|yes (order: 1)|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|

#### Document_Print_Image_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|yes|
|GreaterThanOrLessThan|None|no|yes|

### Print_Image


The data of the printout, stored in the format, specified in Print Image Format.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|varbinary|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

### Print_Image_Format


The format, which is used to represent the print image. Currently, only 'CDS' = Compressed Data Set is supported.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|CDS|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|3|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(3)|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

### Printout_Layout_Id


The print layout, which was used for the current printout.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|Referenced Table|[Gen_Printout_Layouts](Gen_Printout_Layouts.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier|
|UI Memo Editor|no|
|UI Width|100|
|User Login|no|
|Visible|yes|

#### Printout_Layout_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Row_Version

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|timestamp|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|no|


