---
id: "replace-watermarks"
url: "watermark/replace-watermarks"
title: "Replace Watermarks"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---

This REST API allows replacing watermarks in the document.

The operation performs a search for possible watermarks and then performs replacement operations over them.

The API supports a rich set of search criteria that allows finding images and texts that may be possible watermarks.

With this operation, you may replace found watermark properties: watermark image, text or/and text appearance options like font, size, color, etc.

The table below contains the full list of properties.

|Name|Description|Comment
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage|Required
|FileInfo.StorageName|Storage name|Could be omitted for default storage
|FileInfo.Password|Password to open file|Should be specified only for password-protected documents
|OutputFolder|The folder for the resultant file|"watermark/replaced_watermark" is default
|TextSearchCriteria|Search criteria allowing filtering by watermark text|
|TextSearchCriteria.SearchText|The exact string to search for|
|ImageSearchCriteria|Search criteria for finding images|
|ImageSearchCriteria.ImageFileInfo|Image to search for.|
|ImageFileInfo.FilePath|The path of the image, located in the storage|Required
|ImageFileInfo.StorageName|Storage name|
|ImageFileInfo.Password|The password to open image|
|SizeSearchCriteria|Search criteria allowing filtering by watermark size|
|SizeSearchCriteria.Dimension|The dimension of a watermark to search by|Possible values: Height, Width
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
|ReplaceTextOptions|Parameters of text to replace found text watermarks details|
|ReplaceTextOptions.Text|New text for the watermark|Required for text replacement
|ReplaceTextOptions.FontFamily|Font name for a text|Left the same if not specified
|ReplaceTextOptions.Size|Font size for new text|Left the same if not specified
|ReplaceTextOptions.Style|Style of a new text|
|ReplaceTextOptions.ForegroundColor|Foreground color for a new text|
|ReplaceTextOptions.BackgroundColor|Background color for a new text|
|ReplaceImageOptions|Parameters of the image to replace found image watermarks details|
|ReplaceImageOptions.Image|New image for watermark|
|Image.FilePath|The path of the image, located in the storage|Required
|Image.StorageName|Storage name|
|Image.Password|The password to open image|

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
HTTP POST ~~/watermark/replace
```

[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/Watermark/Replace) lets you call this REST API directly from the browser. 

## cURL example

{{< tabs "example1">}}
{{< tab "Linux/MacOS/Bash" >}}

```bash
# Get JSON Web Token
# Provide your Client Id and Client Secret via environment variables CLIENT_ID and CLIENT_SECRET.
curl -v "https://api.groupdocs.cloud/connect/token" \
  -X POST \
  -d "grant_type=client_credentials&client_id=$CLIENT_ID&client_secret=$CLIENT_SECRET" \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -H "Accept: application/json"

# cURL example to replace watermark in a document
curl -v "https://api.groupdocs.cloud/v1.0/watermark/replace" \
  -X POST \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer $JWT_TOKEN" \
  -d '{
    "FileInfo": {
        "FilePath": "with_watermarks/sample.pdf"
    },
    "ReplaceTextOptions": {
        "Text": "New watermark text",
        "Size": 0.0
    },
    "ReplaceImageOptions": {
        "Image": {
            "FilePath": "images/sample.jpg"
        }
    },
    "TextSearchCriteria": {
        "SearchText": "Watermark text"
    },
    "ImageSearchCriteria": {
        "ImageFileInfo": {
            "FilePath": "watermark_images/sample_watermark.png"
        }
    }
}'
```

{{< /tab >}}

{{< tab "Windows PowerShell" >}}

```powershell
# Get JSON Web Token
# Provide your Client Id and Client Secret via environment variables CLIENT_ID and CLIENT_SECRET.
curl.exe -v "https://api.groupdocs.cloud/connect/token" `
  -X POST `
  -d "grant_type=client_credentials&client_id=$env:CLIENT_ID&client_secret=$env:CLIENT_SECRET" `
  -H "Content-Type: application/x-www-form-urlencoded" `
  -H "Accept: application/json"

# cURL example to replace watermark in a document
curl.exe -v "https://api.groupdocs.cloud/v1.0/watermark/replace" `
  -X POST `
  -H "Content-Type: application/json" `
  -H "Accept: application/json" `
  -H "Authorization: Bearer $env:JWT_TOKEN" `
  -d "{
    'FileInfo': {
        'FilePath': 'with_watermarks/sample.pdf'
    },
    'ReplaceTextOptions': {
        'Text': 'New watermark text',
        'Size': 0.0
    },
    'ReplaceImageOptions': {
        'Image': {
            'FilePath': 'images/sample.jpg'
        }
    },
    'TextSearchCriteria': {
        'SearchText': 'Watermark text'
    },
    'ImageSearchCriteria': {
        'ImageFileInfo': {
            'FilePath': 'watermark_images/sample_watermark.png'
        }
    }
}"
```

{{< /tab >}}

{{< tab "Windows CMD" >}}

```cmd
:: Get JSON Web Token
:: Provide your Client Id and Client Secret via environment variables CLIENT_ID and CLIENT_SECRET.
curl -v "https://api.groupdocs.cloud/connect/token" ^
  -X POST ^
  -d "grant_type=client_credentials&client_id=%CLIENT_ID%&client_secret=%CLIENT_SECRET%" ^
  -H "Content-Type: application/x-www-form-urlencoded" ^
  -H "Accept: application/json"

:: cURL example to replace watermark in a document
curl -v "https://api.groupdocs.cloud/v1.0/watermark/replace" ^
  -X POST ^
  -H "Content-Type: application/json" ^
  -H "Accept: application/json" ^
  -H "Authorization: Bearer %JWT_TOKEN%" ^
  -d "{\"FileInfo\":{\"FilePath\":\"with_watermarks/sample.pdf\"},\"ReplaceTextOptions\":{\"Text\":\"New watermark text\",\"Size\":0.0},\"ReplaceImageOptions\":{\"Image\":{\"FilePath\":\"images/sample.jpg\"}},\"TextSearchCriteria\":{\"SearchText\":\"Watermark text\"},\"ImageSearchCriteria\":{\"ImageFileInfo\":{\"FilePath\":\"watermark_images/sample_watermark.png\"}}}"
```

{{< /tab >}}
{{< tab "Response" >}}

```json
{
    "downloadUrl": "https://api.groupdocs.cloud/v1.0/watermark/storage/file/replaced_watermarks/sample_pdf/sample.pdf",
    "path": "replaced_watermarks/sample_pdf/sample.pdf"
}
```

{{< /tab >}}
{{< /tabs >}}

## SDK examples

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it Replaces the [Watermark](https://apireference.groupdocs.cloud/watermark/#/Watermark/Replace) API calls and lets you use GroupDocs Cloud features in a native way for your preferred language.

{{< tabs "example2">}}
{{< tab "C#" >}}
{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Replace_Watermark.cs >}}
{{< /tab >}}
{{< tab "Java" >}}
{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Replace_Watermark.java >}}
{{< /tab >}}
{{< /tabs >}}
