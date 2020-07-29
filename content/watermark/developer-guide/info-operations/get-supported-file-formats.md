---
id: "get-supported-file-formats"
url: "watermark/get-supported-file-formats"
title: "Get Supported File Formats"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---





# Introduction #

This REST API allows getting a list of all [file formats supported ]({{< ref "watermark/getting-started/supported-document-types.md" >}}))by GroupDocs.Watermark Cloud product.

## Resource URI ##



HTTP POST ~~/formats


[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/Info/GetSupportedFileFormats) lets you call this REST API directly from the browser.

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
curl -v "https://api.groupdocs.cloud/v1.0/watermark/formats" \
-X GET \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"

 ```


 Response

```html 

{
  "formats": [    
    {
      "extension": ".doc",
      "fileFormat": "Microsoft Word Document"
    },
    {
      "extension": ".docm",
      "fileFormat": "Word Open XML Macro-Enabled Document"
    },
    {
      "extension": ".docx",
      "fileFormat": "Microsoft Word Open XML Document"
    },
   ...
    {
      "extension": ".xlsx",
      "fileFormat": "Microsoft Excel Open XML Spreadsheet"
    }
  ]
}

 ```



## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it shows [Document Formats](https://apireference.groupdocs.cloud/watermark/#/Info/GetSupportedFileFormats) API calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###


 C#




{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Get_Document_Formats.cs >}}





 Java




{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Get_Document_Formats.java >}}



