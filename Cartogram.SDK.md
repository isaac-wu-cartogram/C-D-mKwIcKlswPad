# Cartogram SDK Documentation
-   [Authorization](#authorization)
-   [Url Structure](#url-structure)
-   [Base API](#base-api)
	-   [Upload (POST)](#post-api/v1/base/upload)

## Authorization
All Cartogram APIs use authorization keys as a security mechanism. When using an authorization key, add them to *headers* before sending the request to the server. The names of the keys are:

&nbsp;&nbsp;&nbsp;&nbsp;**_ApplicationId_** - Your application id\
&nbsp;&nbsp;&nbsp;&nbsp;**_Authorization_** - Your authorization key for application

If you have an incorrect ApplicationId or Authorization key, you will see the following error:

&nbsp;&nbsp;&nbsp;&nbsp;**_ApplicationId_** error: {"error":"Error:application id is not valid"}\
&nbsp;&nbsp;&nbsp;&nbsp;**_ApplicationId_** error: {"error":"Error:token is not valid"}

## Url Structure

## Base API

### Upload (POST)
###### URL: POST/api/v1/base/upload
Uploads an image to server.\
**_Basic Query_**
|**_Parameter_**|**_Description_**                                |**_Required_**|**_Default_**|
|---------------|-------------------------------------------------|--------------|-------------|
|image          |Image that needs to be uploaded (BASE64 String)  |YES           |-            |

**_Output Fields_**
|**_JSON Field_**|**_Description_**      |**_Always present_**|
|----------------|-----------------------|--------------------|
|url             |Url of uploaded image  |YES                 |

_HTTP 400 ERROR_
|**_Error_**                 |**_Description_**                                                                                     |
|----------------------------|------------------------------------------------------------------------------------------------------|
|Error, image is empty       |You haven't specified the parameter image or it's not uploaded to server                              |
|Error, image does not upload|Some parameters may be missing or Google storage can't process your request right now, try again later|
