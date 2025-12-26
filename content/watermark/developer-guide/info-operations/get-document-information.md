---
id: "get-document-information"
url: "watermark/get-document-information"
title: "Get Document Information"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
toc: True
---

This REST API allows obtaining basic information about the document. The endpoint accepts the document storage path as input payload.

Here is the list of properties that can be obtained for a document:

* Document file extension;
* Document size in bytes;
* Document file format;
* Document page count.

The table below contains the full list of properties.

|Name|Description|Comment
|FileInfo.FilePath|The path of the document, located in the storage.|Required.
|FileInfo.StorageName|Storage name|It could be omitted for default storage.
|FileInfo.Password|The password to open file|It should be specified only for password-protected documents.

## Resource URI

```html
HTTP POST ~~/info
```

[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/Info/GetInfo) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
# Get JSON Web Token
# Ensure CLIENT_ID and CLIENT_SECRET are set in your environment.
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# Get document information (watermark)
curl -v "https://api.groupdocs.cloud/v1.0/watermark/info" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{ "FilePath": "/documents/password-protected.docx", "Password": "password" }'
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# Get JSON Web Token
# Ensure CLIENT_ID and CLIENT_SECRET are set in environment variables.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# Get document information (watermark)
curl.exe -v "https://api.groupdocs.cloud/v1.0/watermark/info" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{ 'FilePath': '/documents/password-protected.docx', 'Password': 'password' }"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
:: Get JSON Web Token
:: Ensure CLIENT_ID and CLIENT_SECRET are set as environment variables.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

:: Get document information (watermark)
curl -v "https://api.groupdocs.cloud/v1.0/watermark/info" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FilePath\":\"/documents/password-protected.docx\",\"Password\":\"password\"}"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
    "fileType": {
        "fileFormat": "Microsoft Word Open XML Document",
        "extension": ".docx"
    },
    "size": 10240,
    "pageCount": 4
}
```

{{< /tab >}}
{{< /tabs >}}

## SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it shows [document information](https://apireference.groupdocs.cloud/watermark/#/Info/GetInfo) API calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example2">}}
{{< tab "C#" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Get_Document_Info.cs >}}
{{< /tab >}}
{{< tab "Java" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Get_Document_Info.java >}}
{{< /tab >}}
{{< /tabs >}}
