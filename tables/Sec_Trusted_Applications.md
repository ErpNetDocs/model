# Table Sec_Trusted_Applications


## Entity

Entity: [Systems.Security.TrustedApplications](~/entities/Systems.Security.TrustedApplications.md)

Application, which is trusted to access the ERP data. Entity: Sec_Trusted_Applications (Introduced in version 19.1)

## Summary

| Name | Type | Description |
| - | - | --- |
|[Application_Secret_Hash](#application_secret_hash)|`nvarchar(250)` |Hash of the secret of the client application. The secret is used when the client application needs to authorize itself in front of the identity provider.|
|[Application_Uri](#application_uri)|`nvarchar(254)` |Application globally unique Uri in reverse host name format. For example: "com.manufacturer/app".|
|[Basic_Authentication_Allowed](#basic_authentication_allowed)|`bit` |If true, this application allows login with user name and password. When a client application uses basic authentication it must provide the application uri along with user name and password. Use with caution, because basic authentication is less secure than oauth! If a user is specified in System User, the basic authentication is allowed only for this user.|
|[Client_Type](#client_type)|`char(1)` Allowed: `C`, `P`|Specifies the client type, according to RFC 6749, e.g. the confidentiality of the client app. P=Public (e.g. browser or native app); C=Confidential (e.g. web server app).|
|[Creation_Time_Utc](#creation_time_utc)|`datetime` Readonly|Date and time (in UTC) when the application was registered.|
|[Impersonate_As_Community_User_Allowed](#impersonate_as_community_user_allowed)|`bit` |Allows the application to request login from external users and operate on their behalf.|
|[Impersonate_As_Internal_User_Allowed](#impersonate_as_internal_user_allowed)|`bit` |Allows the application to request login from internal users and operate on their behalf.|
|[Impersonate_Login_Url](#impersonate_login_url)|`nvarchar(500)` |The login Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas.|
|[Impersonate_Logout_Url](#impersonate_logout_url)|`nvarchar(500)` |The logout Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas.|
|[Is_Enabled](#is_enabled)|`bit` |Specifies whether the application is enabled for login.|
|[Notes](#notes)|`nvarchar(max)` ||
|[Reference_Tokens](#reference_tokens)|`char(3)` Allowed: `NON`, `USR`, `ADM`|Defines who is allowed to issue reference access tokens for this trusted application.|
|[Row_Version](#row_version)|`timestamp` ||
|[Scope](#scope)|`nvarchar(max)` |The scope (according to RFC 6749) for which the application was trusted. The scope is an unordered list of space-delimited case-sensitive strings. Each string denotes a permission (see docs for possible values).|
|[System_User_Allowed](#system_user_allowed)|`bit` |Allows this application to logon as a service.|
|[System_User_Id](#system_user_id)|`uniqueidentifier` |The user, which will be used when the application logins as a service.|
|[System_User_Login_Url](#system_user_login_url)|`nvarchar(254)` |The URL, which will be used by the login process, when the application logs in as a service.|
|[Trusted_Application_Id](#trusted_application_id)|`uniqueidentifier` `PK`||
|[Trusted_Application_Name](#trusted_application_name)|`nvarchar(254)` |The multi-language name of the application.|

## Columns

### Application_Secret_Hash


Hash of the secret of the client application. The secret is used when the client application needs to authorize itself in front of the identity provider.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|250|
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
|Type|nvarchar(250) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Application_Uri


Application globally unique Uri in reverse host name format. For example: "com.manufacturer/app".

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(254)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Application_Uri - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Basic_Authentication_Allowed


If true, this application allows login with user name and password. When a client application uses basic authentication it must provide the application uri along with user name and password. Use with caution, because basic authentication is less secure than oauth! If a user is specified in System User, the basic authentication is allowed only for this user.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|False|
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
|Type|bit|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Basic_Authentication_Allowed - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Client_Type


Specifies the client type, according to RFC 6749, e.g. the confidentiality of the client app. P=Public (e.g. browser or native app); C=Confidential (e.g. web server app).

| Property | Value |
| - | - |
|Allowed Values|`C`, `P`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|C|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|1|
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
|Type|char(1)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Creation_Time_Utc


Date and time (in UTC) when the application was registered.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|CurrentDateTimeUtc|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|-1|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|yes|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|datetime|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Creation_Time_Utc - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|no|

### Impersonate_As_Community_User_Allowed


Allows the application to request login from external users and operate on their behalf.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|False|
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
|Type|bit|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Impersonate_As_Community_User_Allowed - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Impersonate_As_Internal_User_Allowed


Allows the application to request login from internal users and operate on their behalf.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|False|
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
|Type|bit|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Impersonate_As_Internal_User_Allowed - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Impersonate_Login_Url


The login Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|500|
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
|Type|nvarchar(500) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Impersonate_Logout_Url


The logout Url used when an application is impersonated as (usually community) user; may include multiple addresses, separated by commas.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|500|
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
|Type|nvarchar(500) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Is_Enabled


Specifies whether the application is enabled for login.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|True|
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
|Type|bit|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Is_Enabled - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### Notes

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
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
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Reference_Tokens


Defines who is allowed to issue reference access tokens for this trusted application.

| Property | Value |
| - | - |
|Allowed Values|`NON`, `USR`, `ADM`|
|Auto Complete|no|
|Data Filter|no|
|Default Value|NON|
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
|Supports EQUALS_IN|yes|
|Type|char(3)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Reference_Tokens - Supported Filters

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

### Scope


The scope (according to RFC 6749) for which the application was trusted. The scope is an unordered list of space-delimited case-sensitive strings. Each string denotes a permission (see docs for possible values).

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|2147483647|
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
|Type|nvarchar(max) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### System_User_Allowed


Allows this application to logon as a service.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|False|
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
|Type|bit|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### System_User_Allowed - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|

### System_User_Id


The user, which will be used when the application logins as a service.

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
|Referenced Table|[Sec_Users](Sec_Users.md)|
|RTF|no|
|Sortable|no|
|Summary Type|None|
|Supports EQUALS_IN|yes|
|Type|uniqueidentifier (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### System_User_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|yes|no|

### System_User_Login_Url


The URL, which will be used by the login process, when the application logs in as a service.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
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
|Type|nvarchar(254) (Allows NULL)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

### Trusted_Application_Id

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

#### Trusted_Application_Id - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|GreaterThanOrLessThan|None|no|yes|

### Trusted_Application_Name


The multi-language name of the application.

| Property | Value |
| - | - |
|Auto Complete|no|
|Data Filter|no|
|Default Value|None|
|Enter Stop|yes|
|Ignore for Insert Order|no|
|Is Entity Name|no|
|Max Length|254|
|Order|2147483647|
|Ownership Reference|no|
|Pasword|no|
|Picture|no|
|Primary Key|no|
|Readonly|no|
|RTF|no|
|Sortable|yes|
|Summary Type|None|
|Supports EQUALS_IN|no|
|Type|nvarchar(254)|
|UI Memo Editor|no|
|UI Width|Medium|
|User Login|no|
|Visible|yes|

#### Trusted_Application_Name - Supported Filters

| Filter Type | Default | Include Nulls | Hidden by Default |
| - | - | - | - |
|Equals|`NULL`|no|no|
|Like|None|no|no|


