---
id: "remove-watermarks"
url: "watermark/remove-watermarks"
title: "Remove Watermarks"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---





# Introduction #

This REST API allows removing watermarks from the document.

The operation performs a search for possible watermarks and then removes them.

The API supports a rich set of search criteria that allows finding images and texts that may be possible watermarks.

There are two popular scenarios to use the **Remove** operation:

1. Remove particular watermarks found by search criteria.
With this scenario Two operations are used: **Search** and **Remove**:
1*. You define the search criteria set;
1*. You first use **Search** operation with the designed criteria and get the response with search results;
1*. You can analyze the response and choose those watermarks that should be deleted;
1*. You then call **Remove** operation with the same set of search criteria;
1*. You also provide **RemoveIds **array with IDs of found watermarks;
1*. Then watermarks with passed IDs will be removed
1. Remove all found watermarks.
With this scenario:
1*. You define search criteria and pass them as parameters
1*. You don't provide **RemoveIds **array
1*. Then all the found watermarks will be removed

The table below contains the full list of properties.

|#Name|#Description|#Comment
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage|Required
|FileInfo.StorageName|Storage name|Could be omitted for default storage
|FileInfo.Password|The password to open file|Should be specified only for password-protected documents
|OutputFolder|The folder for the resultant file|"watermark/removed_watermark" is default
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
|RemoveIds|Collection of possible watermarks IDs to remove.|The array contains IDs returned by Search operation.

In case the array is not passed, all the found possible watermarks are removed.


## ColorRange ##

|#Name|#Description|#Comment
|---|---|---
|Color|The exact color from which the range is created| 
|IsEmpty|Indicates whether only the empty color is in range| 
|MaxBrightness|The ending brightness value.| 
|MaxHue|The ending hue value, in degrees.| 
|MaxSaturation|The ending saturation value.| 
|MinBrightness|The starting brightness value.| 
|MinHue|The starting hue value, in degrees.| 
|MinSaturation|The starting saturation value.| 

### Color ###

|#Name|#Description|#Comment
|---|---|---
|A|The alpha component value of the color| 
|R|The red component value of the color| 
|G|The green component value of the color| 
|B|The blue component value of the color| 
|ARGB|The 32-bit ARGB value| 
|Name|A system-defined color name| 
|IsEmpty|Indicates whether Color is uninitialized| 

## Resource URI ##

|HTTP POST ~~/watermark/remove
|---

[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/Watermark/Remove) lets you call this REST API directly from the browser. 

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
   
* cURL example to get document information
curl -v "https://api.groupdocs.cloud/v1.0/watermark/remove" \
-X POST \
-H "Content-Type: application/json" \
-H "Accept: application/json" \
-H "Authorization: Bearer <jwt token>"
-d "{
    "FileInfo": {
        "FilePath": "with_watermarks\\sample.pdf"
    },
    "OutputFolder": "removed_watermarks",
    "TextSearchCriteria": {
        "SearchText": "Watermark text"
    },
    "ImageSearchCriteria": {
        "ImageFileInfo": {
            "FilePath": "watermark_images\\sample_watermark.png",
            "StorageName": ""
        }
    }
}"

 ```


 Response

```html 
{
    "downloadUrl": "https://api.groupdocs.cloud/v1.0/watermark/storage/file/removed_watermarks/sample_pdf/sample.pdf",
    "path": "removed_watermarks/sample_pdf/sample.pdf"
}

 ```




## SDKs ##

Our API is completely independent of your operating system, database system or development language. You can use any language and platform that supports HTTP to interact with our API. However, manually writing client code can be difficult, error-prone and time-consuming. Therefore, we have provided and support API [SDKs](https://github.com/groupdocs-watermark-cloud) in many development languages in order to make it easier to integrate with us. If you use [SDK](https://github.com/groupdocs-watermark-cloud), it Removes the [Watermark](https://apireference.groupdocs.cloud/watermark/#/Watermark/Remove) API calls and lets you use GroupDocs Cloud features in a native way for your preferred language.
|---|---|---|---|---|---

### SDK Examples ###


 C#




{{< gist groupdocscloud 90da27f305908428852e34cf1ed77ad0 Watermark_CSharp_Remove_Watermark.cs >}}





 Java




{{< gist groupdocscloud 499959a7260c4903f836012226cb2dac Watermark_Java_Remove_Watermark.java >}}



