---
id: "working-with-files"
url: "watermark/working-with-files"
title: "Working With Files"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---






## Download File API ##

This API allows you to download a file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud).

### API Explorer ###

[GroupDocs.Watermark Cloud API Reference](https://apireference.groupdocs.cloud/watermark/#/) lets you try out [Download a File API](https://apireference.groupdocs.cloud/watermark/#/File/DownloadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs expose.

#### Request parameters ####

|Parameter|Description
|---|---
|**Path**|Path of the file including file name and extension e.g. /Folder1/file.ext</br>Required. Can be passed as a query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|versionId|File version id

### cURL Example ###

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X GET "https://api.groupdocs.cloud/v1.0/watermark/storage/file/one-page.docx?storageName#MyStorage" \
-H  "accept: multipart/form-data" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [File API](https://apireference.groupdocs.cloud/watermark/#/) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="2" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Download_File.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Download_File.java >}}
{{< /tab >}}
{{< /tabs >}}

## Upload File API ##

This API allows you to upload files to the [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer ###

[GroupDocs.Watermark Cloud API Reference](https://apireference.groupdocs.cloud/watermark/#/) lets you try out [Upload a File API](https://apireference.groupdocs.cloud/watermark/#/File/UploadFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs expose.

#### Request Body parameters ####

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext</br>Required. Can be passed as a query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|File|File content

### cURL Example ###

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X POST "https://api.groupdocs.cloud/v1.0/watermark/storage/file/parserdocs%2Fone-page2.docx?storageName#MyStorage" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}
Http status code: 200 (Returns OK and list of errors, which is empty if success.)

```json
{
  "Uploaded": [
    "string"
  ],
  "Errors": [
    {
      "Code": "string",
      "Message": "string",
      "Description": "string",
      "InnerError": {
        "RequestId": "string",
        "Date": "2019-02-27T06:10:08.884Z"
      }
    }
  ]
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [File API](https://apireference.groupdocs.cloud/watermark/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="4" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Upload_File.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Upload_File.java >}}
{{< /tab >}}
{{< /tabs >}}

## Delete File API ##

This API allows you to delete a specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer ###

[GroupDocs.Watermark for Cloud API Reference](https://apireference.groupdocs.cloud/watermark/#/) lets you try out [Delete a File](https://apireference.groupdocs.cloud/watermark/#/File/DeleteFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs expose.

#### Request parameters ####

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext</br>Required. Can be passed as a query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used
|versionId|File version id

### cURL Example ###

{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X DELETE "https://api.groupdocs.cloud/v1.0/watermark/storage/file/watermarkdocs1%2Fone-page1.docx?storageName#MyStorage" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [File API](https://apireference.groupdocs.cloud/watermark/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="6" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Delete_File.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Delete_File.java >}}
{{< /tab >}}
{{< /tabs >}}

## File Copy API ##

This API allows you to copy a specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer ###

[GroupDocs.Watermark for Cloud API Reference](https://apireference.groupdocs.cloud/watermark/#/) lets you try out [Copy File](https://apireference.groupdocs.cloud/watermark/#/File/CopyFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs expose.

####  Request parameters ####

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. /Folder1/file.ext</br>Required. Can be passed as a query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then default storage used
|destStorageName|Name of the storage of destination file. If not set, then default storage used
|versionId|Source file version id

### cURL Example ###

{{< tabs tabTotal="2" tabID="7" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v1.0/watermark/storage/file/copy/watermarkdocs%2Fone-page1.docx?destPath#watermarkdocs1%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [File API](https://apireference.groupdocs.cloud/watermark/#/File) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="8" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Copy_File.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Copy_File.java >}}
{{< /tab >}}
{{< /tabs >}}

## File Move API ##

This API allows you to copy a specific file from [GroupDocs Cloud Storage](https://dashboard.groupdocs.cloud/).

### API Explorer ###

[GroupDocs.Watermark for Cloud API Reference](https://apireference.groupdocs.cloud/watermark/#/) lets you try out [Move File](https://apireference.groupdocs.cloud/watermark/#/File/MoveFile) right away in your browser! It allows you to effortlessly interact and try out every single operation our APIs expose.

####  Request parameters ####

|Parameter|Description
|---|---
|**srcPath**|Path of the source file including file name and extension e.g. /Folder1/file.ext</br>Required. Can be passed as a query string parameter or as part of the URL
|**destPath**|Path of the destination file. Required.
|srcStorageName|Name of the storage of source file. If not set, then default storage used
|destStorageName|Name of the storage of destination file. If not set, then default storage used
|versionId|Source file version id

### cURL Example ###

{{< tabs tabTotal="2" tabID="9" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v1.0/watermark/storage/file/move/watermarkdocs%2Fone-page1.docx?destPath#watermarkdocs1%2Fone-page1.docx'&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{
  "Code": 200,
  "Status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [File API](https://apireference.groupdocs.cloud/watermark/#/File) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="10" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Move_File.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Move_File.java >}}
{{< /tab >}}
{{< /tabs >}}
