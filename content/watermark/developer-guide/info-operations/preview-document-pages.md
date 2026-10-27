---
id: "preview-document-pages"
url: "watermark/preview-document-pages"
title: "Preview Document Pages"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
toc: True
---

This REST API allows generating preview images of the document pages. The endpoint accepts the document storage path and the preview options as input payload, saves the page images to the storage and returns the information about each image.

With this API you can:

* Generate previews of all the document pages or only of the selected ones;
* Choose the image format: PNG, JPEG or BMP;
* Set the size of the images or keep the original page size;
* For protected documents, it is required to provide the password.

Here is the list of properties that can be obtained for each page image:

* Page number, starting from 1;
* Path of the image in the storage;
* Download URL of the image;
* Image size in bytes.

The table below contains the full list of properties.

|Name|Description|Comment
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage.|Required.
|FileInfo.StorageName|Storage name|It could be omitted for default storage.
|FileInfo.Password|The password to open file|It should be specified only for password-protected documents.
|OutputFolder|The folder for the page images.|When not set, the default folder is used.
|Format|The image format.|Possible values: PNG, JPEG, BMP. The default value is PNG.
|Width|The image width in pixels.|Width and Height must be set together. When not set, the original page size is used.
|Height|The image height in pixels.|Width and Height must be set together. When not set, the original page size is used.
|PageNumbers|The numbers of the pages to preview, starting from 1.|When empty, all pages are previewed. Pages that do not exist are skipped.

## Resource URI

```html
HTTP POST ~~/watermark/preview
```

[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/Preview/Preview) lets you call this REST API directly from the browser.

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

# Generate document page previews (watermark)
curl -v "https://api.groupdocs.cloud/v1.0/watermark/preview" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{
    "FileInfo": {
        "FilePath": "documents/sample.pdf"
    },
    "OutputFolder": "previews",
    "Format": "PNG",
    "PageNumbers": [1, 2]
}'
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

# Generate document page previews (watermark)
curl.exe -v "https://api.groupdocs.cloud/v1.0/watermark/preview" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{
    'FileInfo': {
        'FilePath': 'documents/sample.pdf'
    },
    'OutputFolder': 'previews',
    'Format': 'PNG',
    'PageNumbers': [1, 2]
}"
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

:: Generate document page previews (watermark)
curl -v "https://api.groupdocs.cloud/v1.0/watermark/preview" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FileInfo\":{\"FilePath\":\"documents/sample.pdf\"},\"OutputFolder\":\"previews\",\"Format\":\"PNG\",\"PageNumbers\":[1,2]}"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
    "pages": [
        {
            "pageNumber": 1,
            "path": "previews/sample_pdf/page_1.png",
            "downloadUrl": "https://api.groupdocs.cloud/v1.0/watermark/storage/file/previews/sample_pdf/page_1.png",
            "size": 24576
        },
        {
            "pageNumber": 2,
            "path": "previews/sample_pdf/page_2.png",
            "downloadUrl": "https://api.groupdocs.cloud/v1.0/watermark/storage/file/previews/sample_pdf/page_2.png",
            "size": 21504
        }
    ]
}
```

{{< /tab >}}
{{< /tabs >}}

## SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it makes the [document page preview](https://apireference.groupdocs.cloud/watermark/#/Preview/Preview) API calls for you and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example2">}}
{{< tab "C#" >}}

```csharp
using GroupDocs.Watermark.Cloud.Sdk.Api;
using GroupDocs.Watermark.Cloud.Sdk.Client;
using GroupDocs.Watermark.Cloud.Sdk.Model;
using GroupDocs.Watermark.Cloud.Sdk.Model.Requests;
using System;
using System.Collections.Generic;
using FileInfo = GroupDocs.Watermark.Cloud.Sdk.Model.FileInfo;

namespace GroupDocs.Watermark.Cloud.Examples.CSharp
{
    /// <summary>
    /// This example demonstrates how to generate document page previews.
    /// </summary>
    public class PreviewDocumentPages
    {
        public static void Run()
        {
            // Get your Client Id and Client Secret at https://dashboard.groupdocs.cloud (free registration is required).
            var configuration = new Configuration("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX", "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX");
            var apiInstance = new PreviewApi(configuration);

            try
            {
                var options = new PreviewOptions
                {
                    FileInfo = new FileInfo
                    {
                        FilePath = "documents/sample.pdf"
                    },
                    OutputFolder = "previews",
                    Format = "PNG",
                    PageNumbers = new List<int?> { 1, 2 }
                };

                var request = new PreviewRequest(options);
                var response = apiInstance.Preview(request);

                foreach (var page in response.Pages)
                {
                    Console.WriteLine("Page " + page.PageNumber + ": " + page.Path + " (" + page.Size + " bytes)");
                }
            }
            catch (Exception e)
            {
                Console.WriteLine("Exception while calling api: " + e.Message);
            }
        }
    }
}
```

{{< /tab >}}
{{< tab "Java" >}}

```java
import java.util.Arrays;
import com.groupdocs.cloud.watermark.api.*;
import com.groupdocs.cloud.watermark.client.*;
import com.groupdocs.cloud.watermark.model.*;
import com.groupdocs.cloud.watermark.model.requests.*;

/**
 * This example demonstrates how to generate document page previews.
 */
public class PreviewDocumentPages {

	public static void main(String[] args) {

		// Get your AppSID and AppKey at https://dashboard.groupdocs.cloud (free registration is required).
		Configuration configuration = new Configuration("XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX", "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX");
		PreviewApi apiInstance = new PreviewApi(configuration);

		try {
			FileInfo fileInfo = new FileInfo();
			fileInfo.setFilePath("documents/sample.pdf");

			PreviewOptions options = new PreviewOptions();
			options.setFileInfo(fileInfo);
			options.setOutputFolder("previews");
			options.setFormat("PNG");
			options.setPageNumbers(Arrays.asList(1, 2));

			PreviewRequest request = new PreviewRequest(options);

			PreviewResult response = apiInstance.preview(request);

			for (PreviewPage page : response.getPages()) {
				System.out.println("Page " + page.getPageNumber() + ": " + page.getPath() + " (" + page.getSize() + " bytes)");
			}

		} catch (ApiException e) {

			System.err.println("Exception while calling api:");
			e.printStackTrace();
		}
	}
}
```

{{< /tab >}}
{{< /tabs >}}
