---
id: "search-watermarks"
url: "watermark/search-watermarks"
title: "Search Watermarks"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---

This REST API allows finding watermarks in the document.

The API supports a rich set of search criteria that allows finding images and texts that may be possible watermarks.

The **Search** operation response contains not only watermark properties, but also IDs that can be used in **Remove** operation.

The table below contains the full list of properties.

|Name|Description|Comment
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage|Required
|FileInfo.StorageName|Storage name|Could be omitted for default storage
|FileInfo.Password|The password to open file|Should be specified only for password-protected documents
|OutputFolder|The folder for the resultant file|"watermark/found_watermark" is default
|SaveFoundImages|Indicates whether found images should be saved.|
|TextSearchCriteria|Search criteria allowing filtering by watermark text|
|TextSearchCriteria.SearchText|The exact string to search for|
|ImageSearchCriteria|Search criteria for finding images|
|ImageSearchCriteria.ImageFileInfo|Image to search for.|
|ImageFileInfo.FilePath|The path of the image, located in the storage|Required
|ImageFileInfo.StorageName|Storage name|
|ImageFileInfo.Password|The password to open image|
|SizeSearchCriteria|Search criteria allowing filtering by watermark size|
|SizeSearchCriteria.Dimension|The dimension of the watermark to search by|Possible values: Height, Width
|SizeSearchCriteria.Maximum|Dimension ending value|
|SizeSearchCriteria.Minimum|Dimension starting value|
|RotateAngleSearchCriteria|Search criteria allowing filtering by watermark rotate angle|
|RotateAngleSearchCriteria.MaximumAngle|Ending angle in degrees|
|RotateAngleSearchCriteria.MinimumAngle|Starting angle in degrees|
|TextFormattingSearchCriteria|Search criteria allowing filtering by text formatting|
|TextFormattingSearchCriteria.ForegroundColorRange|The range of colors which are used to filter watermarks by text foreground color|
|TextFormattingSearchCriteria.BackgroundColorRange|The range of colors which are used to filter watermarks by the text background color.|
|TextFormattingSearchCriteria.FontName|Name of the font which is used in possible watermark text formatting.|
|TextFormattingSearchCriteria.MinFontSize|Starting value of the font size.|
|TextFormattingSearchCriteria.MaxFontSize|Ending value of the font size.|
|TextFormattingSearchCriteria.FontBold|Indicating whether the font used in watermark text formatting is bold.|
|TextFormattingSearchCriteria.FontUnderline|Indicating whether the font used in watermark text formatting is underline.|
|TextFormattingSearchCriteria.FontStrikeout|Indicating whether the font used in watermark text formatting is a strikeout.|
|TextFormattingSearchCriteria.FontItalic|Indicating whether the font used in watermark text formatting is italic.|
|ObjectsToSearch|Searchable objects options.|
|ObjectsToSearch.WordProcessingObjects|The word processing searchable objects.|Possible values: All, Hyperlinks, Text, Shapes, None
|ObjectsToSearch.SpreadsheetObjects|The spreadsheet searchable objects.|Possible values: All, AttachedImages, Hyperlinks, Cells, WorksheetBackgrounds, HeadersFooters, ChartsBackgrounds, Shapes, None
|ObjectsToSearch.PresentationObjects|The presentation searchable objects.|Possible values: All, Hyperlinks, SlidesBackgrounds, ChartsBackgrounds, Shapes, None
|ObjectsToSearch.DiagramObjects|The diagram searchable objects.|Possible values: All, Hyperlinks, HeadersFooters, Comments, Shapes, None
|ObjectsToSearch.PdfObjects|The pdf searchable objects.|Possible values: All, AttachedImages, Hyperlinks, Text, Annotations, Artifacts, XObjects, None
|ObjectsToSearch.EmailObjects|The email searchable objects.|Possible values: All, EmbeddedImages, AttachedImages, HtmlBody, PlainTextBody, Subject, None

## ColorRange

|Name|Description|Comment
|---|---|---
|Color|The exact color from which the range is created|
|IsEmpty|Indicates whether only the empty color is in range|
|MaxBrightness|The ending brightness value.|
|MaxHue|The ending hue value, in degrees.|
|MaxSaturation|The ending saturation value.|
|MinBrightness|The starting brightness value.|
|MinHue|The starting hue value, in degrees.|
|MinSaturation|The starting saturation value.|

## Color

|Name|Description|Comment
|---|---|---
|A|The alpha component value of the color|
|R|The red component value of the color|
|G|The green component value of the color|
|B|The blue component value of the color|
|ARGB|The 32-bit ARGB value|
|Name|A system-defined color name|
|IsEmpty|Indicates whether Color is uninitialized|

## Resource URI

```html
HTTP POST ~~/watermark/search
```

[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/Watermark/Search) lets you call this REST API directly from the browser.

## cURL example

{{< tabs "example1">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
# First get JSON Web Token
# Please get your Client Id and Client Secret from https://dashboard.groupdocs.cloud/applications.
# The credentials are taken from environment variables $CLIENT_ID and $CLIENT_SECRET.
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# cURL example to get document information
curl -v "https://api.groupdocs.cloud/v1.0/watermark/search" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{
    "FileInfo": {
        "FilePath": "with_watermarks\\sample.pdf"
    },
    "OutputFolder": "found_image_watermarks",
    "SaveFoundImages": true,
    "TextSearchCriteria": {
        "SearchText": "Watermark text"
    },
    "ImageSearchCriteria": {
        "ImageFileInfo": {
            "FilePath": "watermark_images\\sample_watermark.png"
        }
    }
}'
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# First get JSON Web Token
# Credentials are read from $env:CLIENT_ID and $env:CLIENT_SECRET.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# cURL example to get document information
curl.exe -v "https://api.groupdocs.cloud/v1.0/watermark/search" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{
    'FileInfo': {
        'FilePath': 'with_watermarks\\sample.pdf'
    },
    'OutputFolder': 'found_image_watermarks',
    'SaveFoundImages': true,
    'TextSearchCriteria': {
        'SearchText': 'Watermark text'
    },
    'ImageSearchCriteria': {
        'ImageFileInfo': {
            'FilePath': 'watermark_images\\sample_watermark.png'
        }
    }
}"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
:: First get JSON Web Token
:: Credentials are taken from %CLIENT_ID% and %CLIENT_SECRET%.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

:: cURL example to get document information
curl -v "https://api.groupdocs.cloud/v1.0/watermark/search" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FileInfo\":{\"FilePath\":\"with_watermarks\\sample.pdf\"},\"OutputFolder\":\"found_image_watermarks\",\"SaveFoundImages\":true,\"TextSearchCriteria\":{\"SearchText\":\"Watermark text\"},\"ImageSearchCriteria\":{\"ImageFileInfo\":{\"FilePath\":\"watermark_images\\sample_watermark.png\"}}}"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
    "watermarks": [
        {
            "id": 0,
            "text": "Watermark text",
            "imageUrl": null,
            "height": 20.0,
            "rotateAngle": 0.0,
            "unitOfMeasurement": "Point",
            "width": 135.57617187499997,
            "x": 229.8719140625,
            "y": 0.0,
            "possibleWatermarkType": "XObject"
        },
        {
            "id": 1,
            "text": null,
            "imageUrl": "https://localhost:5001/v1.0/watermark/storage/file/found_image_watermarks/sample_pdf/watermark_image_0",
            "height": 104.71043478260901,
            "rotateAngle": 0.0,
            "unitOfMeasurement": "Point",
            "width": 297.65999999999997,
            "x": 148.83,
            "y": 368.604782608696,
            "possibleWatermarkType": "XObject"
        },
        {
            "id": 2,
            "text": "Watermark text",
            "imageUrl": null,
            "height": 22.0,
            "rotateAngle": 0.0,
            "unitOfMeasurement": "Point",
            "width": 135.57617187499997,
            "x": 229.8719140625,
            "y": 0.0,
            "possibleWatermarkType": "Text"
        },
        {
            "id": 3,
            "text": "Watermark text",
            "imageUrl": null,
            "height": 20.0,
            "rotateAngle": 0.0,
            "unitOfMeasurement": "Point",
            "width": 135.57617187499997,
            "x": 229.8719140625,
            "y": 0.0,
            "possibleWatermarkType": "XObject"
        },
        {
            "id": 4,
            "text": null,
            "imageUrl": "https://localhost:5001/v1.0/watermark/storage/file/found_image_watermarks/sample_pdf/watermark_image_1",
            "height": 104.71043478260901,
            "rotateAngle": 0.0,
            "unitOfMeasurement": "Point",
            "width": 297.65999999999997,
            "x": 148.83,
            "y": 368.604782608696,
            "possibleWatermarkType": "XObject"
        },
        {
            "id": 5,
            "text": "Watermark text",
            "imageUrl": null,
            "height": 22.0,
            "rotateAngle": 0.0,
            "unitOfMeasurement": "Point",
            "width": 135.57617187499997,
            "x": 229.8719140625,
            "y": 0.0,
            "possibleWatermarkType": "Text"
        }
    ]
}
```

{{< /tab >}}
{{< /tabs >}}

## SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it Searches the [Watermark](https://apireference.groupdocs.cloud/watermark/#/Watermark/Search) API calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example2">}}
{{< tab "C#" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Search_Watermark.cs >}}
{{< /tab >}}
{{< tab "Java" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Search_Watermark.java >}}
{{< /tab >}}
{{< /tabs >}}
