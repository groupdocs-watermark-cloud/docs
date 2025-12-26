---
id: "get-supported-file-formats"
url: "watermark/get-supported-file-formats"
title: "Get Supported File Formats"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
toc: True
---

This REST API allows getting a list of all [file formats supported]({{< ref "watermark/getting-started/supported-document-types.md" >}}) by GroupDocs.Watermark Cloud product.

## Resource URI

```html
HTTP POST ~~/formats
```

[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/Info/GetSupportedFileFormats) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
# First get JSON Web Token
# Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
# Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# cURL example to get document information
curl -v "https://api.groupdocs.cloud/v1.0/watermark/formats" \
  -X GET \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN"
```

{{< /tab >}}
{{< tab "Windows PowerShell" >}}

```powershell
# First get JSON Web Token
# Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
# Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# cURL example to get document information
curl.exe -v "https://api.groupdocs.cloud/v1.0/watermark/formats" `
  -X GET `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN"
```

{{< /tab >}}
{{< tab "Windows CMD" >}}

```cmd
REM First get JSON Web Token
REM Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
REM Kindly place Client Id in "client_id" and Client Secret in "client_secret" argument.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

REM cURL example to get document information
curl -v "https://api.groupdocs.cloud/v1.0/watermark/formats" ^
  -X GET ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
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

{{< /tab >}}
{{< /tabs >}}

## SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it shows [Document Formats](https://apireference.groupdocs.cloud/watermark/#/Info/GetSupportedFileFormats) API calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example2">}}
{{< tab "C#" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Get_Document_Formats.cs >}}
{{< /tab >}}
{{< tab "Java" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Ge_Document_Formats.java >}}
{{< /tab >}}
{{< /tabs >}}
