---
id: "working-with-folder"
url: "watermark/working-with-folder"
title: "Working With Folder"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---






## Get the File Listing of a Specific Folder ##

This API allows you to get a list of all files of a specific folder from the specified Cloud Storage. If you do not pass storage name API will find the folder in GroupDocs Cloud Storage. 

### API Explorer ###

[GroupDocs.Watermark Cloud API Reference](https://apireference.groupdocs.cloud/watermark/) lets you try out [List Files in a Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder/GetFilesList) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs expose.

#### Request parameters ####

|Parameter|Description
|---|---
|**path**|Path of the file including file name and extension e.g. /Folder1/file.ext</br>Required. Can be passed as a query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used

### cURL Example ###

{{< tabs tabTotal="2" tabID="1" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X GET "https://api.groupdocs.cloud/v1.0/watermark/storage/folder/watermarkdocs?storageName#MyStorage" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{
  "value": [
    {
      "name": "four-pages.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:35:38+00:00",
      "size": 8651,
      "path": "/watermarkdocs/four-pages.docx"
    },
    {
      "name": "one-page.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:34+00:00",
      "size": 351348,
      "path": "/watermarkdocs/one-page.docx"
    },
    {
      "name": "password-protected.docx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:35:40+00:00",
      "size": 10240,
      "path": "/watermarkdocs/password-protected.docx"
    },
    {
      "name": "sample.mpp",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:29:10+00:00",
      "size": 289792,
      "path": "/watermarkdocs/sample.mpp"
    },
    {
      "name": "three-layouts.dwf",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:26:42+00:00",
      "size": 15433,
      "path": "/watermarkdocs/three-layouts.dwf"
    },
    {
      "name": "two-hidden-pages.vsd",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:36+00:00",
      "size": 457728,
      "path": "/watermarkdocs/two-hidden-pages.vsd"
    },
    {
      "name": "uses-custom-font.pptx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:32:30+00:00",
      "size": 39823,
      "path": "/watermarkdocs/uses-custom-font.pptx"
    },
    {
      "name": "with-hidden-rows-and-columns.xlsx",
      "isFolder": false,
      "modifiedDate": "2019-03-20T12:17:37+00:00",
      "size": 15986,
      "path": "/watermarkdocs/with-hidden-rows-and-columns.xlsx"
    }
  ]
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="2" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Get_Files_List.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Get_Files_List.java >}}
{{< /tab >}}
{{< /tabs >}}

## Create a New Folder ##

This API allows you to create a new folder in the specified Cloud Storage. If you do not pass storage name API will create New Folder in default Cloud Storage.

### API Explorer ###

[GroupDocs.Watermark Cloud API Reference](https://apireference.groupdocs.cloud/watermark/) lets you try out [Create Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder/CreateFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs expose.

#### Request parameters ####

|Parameter|Description
|---|---
|**path**|Target folder’s path e.g. Folder1/Folder2/. The folders will be created recursively</br>Required. Can be passed as a query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used

### cURL Example ###

{{< tabs tabTotal="2" tabID="3" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X POST "https://api.groupdocs.cloud/v1.0/watermark/folder/watermarkdocs?storageName#MyStorage" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{  
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder/) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="4" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Create_Folder.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Create_Folder.java >}}
{{< /tab >}}
{{< /tabs >}}

## Delete a Particular Folder ##

This API allows you to delete a particular folder in the specified Cloud Storage. If you do not pass storage name API will create New Folder in default Cloud Storage. To remove recursively inner folder/files you need to pass a true value to a recursive parameter in Request. If it is set to false and folder contains data then API throws the exception.

### API Explorer ###

[GroupDocs.Watermark Cloud API Reference](https://apireference.groupdocs.cloud/watermark/#/) lets you try out [Delete a Particular Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder/DeleteFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs expose.

#### Request parameters ####

|Parameter|Description
|---|---
|**path**|Folder path e.g. /Folder1</br>Required. Can be passed as a query string parameter or as part of the URL
|storageName|Name of the storage. If not set, then default storage used

### cURL Example ###

{{< tabs tabTotal="2" tabID="5" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X DELETE "https://api.groupdocs.cloud/v1.0/watermark/storage/folder/parserdocs?storageName#MyStorage&#x26;recursive#true" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{  
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [Delete Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder/DeleteFolder) calls and lets you use GroupDocs for Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="6" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Delete_Folder.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Delete_Folder.java >}}
{{< /tab >}}
{{< /tabs >}}

## Copy Specific Folder ##

This API allows you to copy a folder to another location in the GroupDocs Cloud Storage. If you do not pass source and destination storage names API will copy Folder within default Cloud Storage.

### API Explorer ###

[GroupDocs.Watermark Cloud API Reference](https://apireference.groupdocs.cloud/watermark/#/) lets you try out [Copy Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder/CopyFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs expose.

#### Request parameters ####

|Parameter|Description
|---|---
|**srcPath**|Source folder path e.g. /Folder1</br>Required. Can be passed as a query string parameter or as part of the URL
|**destPath**|Destination folder path. Required
|srcStorageName|Name of the storage of source folder. If not set, then default storage used
|destStorageName|Name of the storage of destination folder. If not set, then default storage used

### cURL Example ###

{{< tabs tabTotal="2" tabID="7" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v1.0/watermark/storage/folder/copy/watermarkdocs?destPath#viewerdocs1&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{  
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [Copy Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder/CopyFolder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="8" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Copy_Folder.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Copy_Folder.java >}}
{{< /tab >}}
{{< /tabs >}}

## Move a Specific Folder ##

This API allows you to move a folder to another location in the GroupDocs Cloud Storage. If you do not pass source and destination storage names API will move Folder within default Cloud Storage.

### API Explorer ###

[GroupDocs.Watermark Cloud API Reference](https://apireference.groupdocs.cloud/watermark/#/) lets you try out [Move a Folder API](https://apireference.groupdocs.cloud/parser/#/Folder/MoveFolder) right away in your browser. It allows you to effortlessly interact and try out every single operation that our APIs expose.

#### Request parameters ####

|Parameter|Description
|---|---
|**srcPath**|Source folder path e.g. /Folder1</br>Required. Can be passed as a query string parameter or as part of the URL
|**destPath**|Destination folder path. Required
|srcStorageName|Name of the storage of source folder. If not set, then default storage used
|destStorageName|Name of the storage of destination folder. If not set, then default storage used

### cURL Example ###

{{< tabs tabTotal="2" tabID="9" tabName1="Request" tabName2="Response" >}}
{{< tab tabNum="1" >}}

```bash
curl -X PUT "https://api.groupdocs.cloud/v1.0/watermark/storage/folder/move/watermarkdocs?destPath#viewerdocs1&#x26;srcStorageName#MyStorage&#x26;destStorageName#MyStorage" \
-H  "accept: application/json" \
-H  "authorization: Bearer [Access Token]"  
```

{{< /tab >}}
{{< tab tabNum="2" >}}

```json
{  
  "code": 200,
  "status": "OK"
}
```

{{< /tab >}}
{{< /tabs >}}

### SDKs ###

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it hides the [Move Folder API](https://apireference.groupdocs.cloud/watermark/#/Folder/MoveFolder) calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

#### SDK Examples ####

{{< tabs tabTotal="2" tabID="10" tabName1="C#" tabName2="Java" >}}
{{< tab tabNum="1" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Move_Folder.cs >}}
{{< /tab >}}
{{< tab tabNum="2" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Move_Folder.java >}}
{{< /tab >}}
{{< /tabs >}}
