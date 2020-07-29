---
id: "get-document-information"
url: "watermark/get-document-information"
title: "Get Document Information"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---





# Introduction #

This REST API allows obtaining basic information about the document. The endpoint accepts the document storage path as input payload.

Here is the list of properties that can be obtained for a document:

* Document file extension;
* Document size in bytes;
* Document file format;
* Document page count.

The table below contains the full list of properties.

|#Name|#Description|#Comment
|FileInfo.FilePath|The path of the document, located in the storage.|Required.
|FileInfo.StorageName|Storage name|It could be omitted for default storage.
|FileInfo.Password|The password to open file|It should be specified only for password-protected documents.

## Resource URI ##



HTTP POST ~~/info


[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/Info/GetInfo) lets you call this REST API directly from the browser. 

## cURL Example ##


 Request
```html 

* First get JSON Web Token
* Please get your App Key and App SID from https://dashboard.groupdocs.cloud/#/apps. Kindly place App Key in "client_secret" and App SID in "client_id" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"
   
* cURL example to get document information
curl -v "https://api.groupdocs.cloud/v1.0/watermark/info" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{ FilePath: '/documents/password-protected.docx', Password: 'password' }"

 ```


 Response

```html 

{
    "fileType": {
        "fileFormat": "Microsoft Word Open XML Document",
        "extension": ".docx"
    },
    "size": 10240,
    "pageCount": 4
}

 ```




## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it shows [document information](https://apireference.groupdocs.cloud/watermark/#/Info/GetInfo) API calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###


 C#




{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Get_Document_Info.cs >}}





 Java




{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Get_Document_info.java >}}



