---
id: "add-text-watermarks"
url: "watermark/add-text-watermarks"
title: "Add Text Watermarks"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---





# Introduction #

This REST API allows adding text watermarks to the document.

With this API you can add watermarks with following features:

* For a text watermark, you can use various text options like Font, Size, Style, Foreground and Background colors, etc.;
* There are many watermark positioning and transforming properties;
* There are format-specific options. These options allow to leverage specific format features and often allow to make watermarks stronger;
* For protected documents, it is required to provide the password.

The following example demonstrates how to add watermark to the document. Here you can see how to create a watermark with specific text, font, and color, position, and size.

## cURL Example ##


 Request
```html 

* First get JSON Web Token
* Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications. Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
-X POST \
-d "grant_type#client_credentials&client_id#xxxx&client_secret#xxxx" \
-H "Content-Type: application/x-www-form-urlencoded" \
-H "Accept: application/json"
   
* cURL example to join several documents into one
curl -v "https://api.groupdocs.cloud/v1.0/watermark" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>" \
-d "{
    "FileInfo": {
        "FilePath": "documents\\sample.pdf",
    },
    "WatermarkDetails": [
        {
            "TextWatermarkOptions": {
                "Text": "Watermark text",
                "FontFamilyName": "Arial",
                "FontSize": 20.0,
                "ForegroundColor": {
                    "Name": "red"
                },
                "TextAlignment": "center"
            },
            "Position": {
                "X": 0.0,
                "Y": 0.0,
                "Width": 0.0,
                "Height": 0.0,
                "HorizontalAlignment": "Center",
                "RotateAngle": 0.0,
                "ConsiderParentMargins": false,
                "IsBackground": false
            }
        }
    ]
}"

 ```


 Response

```html 

{
    "downloadUrl": "https://api.groupdocs.cloud/v1.0/watermark/storage/file/watermark/added_watermark/documents/sample_pdf/sample.pdf",
    "path": "watermark/added_watermark/documents/sample_pdf/sample.pdf"
}

 ```




## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it adds the [Watermark API](https://apireference.groupdocs.cloud/watermark/#/Watermark/Add) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

### SDK Examples ###


 C#




{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Add_Text_Watermark.cs >}}





 Java




{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Add_Text_Watermark.java >}}




