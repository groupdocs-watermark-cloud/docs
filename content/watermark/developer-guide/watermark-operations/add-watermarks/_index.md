---
id: "add-watermarks"
url: "watermark/add-watermarks"
title: "Add Watermarks"
productName: "GroupDocs.Watermark Cloud"
description: ""
keywords: ""
---





## Introduction ##

This REST API allows adding watermarks inside the documents.

With this API you can add watermarks with following features:

* The watermark could be either a text or an image:
  * Image watermark supports various image formats: PNG, GIF, TIFF, JPG.
* You may upload the desired image to the Storage and then pass the path as a parameter of Watermark operation;
  * For a Text watermark, you can use various text options like Font, Size, Style, Foreground and Background colors, etc.;
* There are many watermark positioning and transforming properties;
* There are format-specific options. These options allow to leverage specific format features and often allow to make watermarks stronger;
* For protected documents, it is required to provide the password.

The table below contains the full list of properties that can be specified when creating watermarks inside of the document.

|Name|Description|Comment
|---|---|---
|FileInfo.FilePath|The path of the document, located in the storage. |Required.
|FileInfo.StorageName|Storage name|It could be omitted for default storage.
|FileInfo.Password|The password to open file|It should be specified only for password-protected documents.
|OutputFolder|The folder for the resultant file.|Default value is "/add_watermarks"
|WatermarkDetails|Collection of watermarks to be added.|It contains both text and image watermarks and their details.
|WatermarkDetails.ProtectLevel|Level of document protection.|The default value is 'Document' - adds watermarks only inside the document. Possible values: 'Images' - adds watermarks only on images inside the document. 'DocumentAndImages' - protect both document and images.
|WatermarkDetails.PdfOptions|Specific options for PDF documents.|
|WatermarkDetails.ImageOptions|Specific options for Image documents.|
|WatermarkDetails.PresentationOptions|Specific options for Presentations.|
|WatermarkDetails.WordProcessingOptions|Specific options for Word processing documents.|
|WatermarkDetails.SpreadsheetOptions|Specific options for Spreadsheet documents.|
|WatermarkDetails.DiagramOptions|Specific options for Diagram documents.|

### Watermark Details ###

|Name|Description|Comment
|---|---|---
|TextWatermarkOptions|Options for text watermark|Required if text watermark needs to be added
|TextWatermarkOptions.Text|Text to be used as a watermark|Required
|TextWatermarkOptions.FontFamilyName|The family name of the text font|Required
|TextWatermarkOptions.FontSize|Size of the font|Required
|TextWatermarkOptions.FontStyle|Style of the font|Possible values: Bold, Italic, Regular, Strikeout, Underline
|TextWatermarkOptions.ForegroundColor|The foreground color of the text|
|TextWatermarkOptions.BackgroundColor|Background color of the text|
|TextWatermarkOptions.TextAlignment|Text alignment.|Possible values: Left, Right, Center, Justify
|ImageWatermarkOptions|Options for image watermark|Required if image watermark needs to be added
|ImageWatermarkOptions.Image|Image for the watermark|Required
|Image.FilePath|The path of the image, located in the storage. |Required
|Image.StorageName|Storage name|
|Image.Password|The password to open image|
|Position|Watermark position|Defines placement of the watermark on document page
|Position.X|X-coordinate of the watermark|
|Position.Y|Y-coordinate of the watermark|
|Position.Width|Desired width of the watermark|
|Position.Height|The desired height of the watermark|
|Position.HorizontalAlignment|Watermark horizontal alignment|Possible values: Center, Left, Right, None
|Position.VerticalAlignment|Watermark vertical alignment|Possible values: Bottom, Center, Top, None
|Position.Margins|Watermark margin settings|
|Margins.MarginType|Margin type|Possible values: Absolute, RelativeToParentDimensions, RelativeToParentMinDimension
|Margins.Right|Value of right margin|
|Margins.Left|Value of left margin|
|Margins.Top|Value of top margin|
|Margins.Bottom|Value of bottom margin|
|Position.SizingType|Specifies how to watermark size should be calculated|Possible values: Absolute, Auto, ScaleToParentArea, ScaleToParentDimensions
|Position.ScaleFactor|Gets or sets a value that defines how watermark size depends on parent size.|
|Position.RotateAngle|Rotate angle of the watermark|Value in degrees
|Position.ConsiderParentMargins|Indicates whether the watermark size and coordinates are calculated considering parent margins|
|Position.IsBackground|Indicates whether the watermark should be placed at the background.|
|Opacity|The opacity of the watermark|

### PdfOptions ###

|Name|Description|Comment
|---|---|---
|PrintOnlyAnnotationWatermarks|Indicates whether annotation watermarks should be added and should be visible only while printing|
|Rasterize|Indicates whether the document should be rasterized.|Converts all content pages into images.
|RasterizeImageFormat|PDF image conversion format|Possible values: Jpeg, Png, Gif
|Pages|Pages to add watermarks to|

### ImageOptions ###

|Name|Description|Comment
|---|---|---
|Frames|Frames of the multi-frame image to add watermark|

### PresentationOptions ###

|Name|Description|Comment
|---|---|---
|ProtectWithUnreadableCharacters|Indicates whether the text watermark characters are mixed with unreadable characters| This protection applies only when LockWatermarks property is true
|LockWatermarks|Indicates whether editing of the watermark in PowerPoint is forbidden.|
|Slides|Slides to add watermarks to|

### WordProcessingOptions ###

|Name|Description|Comment
|---|---|---
|WatermarkLockType|Type of watermark lock.|Possible values: AllowOnlyComments, AllowOnlyFormFields, AllowOnlyRevisions, NoLock(default), ReadOnly, ReadOnlyWithEditableContent
|WatermarkPassword|Password used to lock the watermark.|
|LockWatermarks|Indicates whether editing of the shape in Word is forbidden.|If true, WatermarkLockType set to ReadOnly.
|Pages|Pages to add watermarks to|It starts from 1.

### SpreadsheetOptions ###

|Name|Description|Comment
|---|---|---
|LockWatermarks|Indicates whether editing of the shape in Excel is forbidden.|
|Worksheets|Worksheets to add watermarks to|

### DiagramOptions ###

|Name|Description|Comment
|---|---|---
|PlacementType|Specifying to what pages a watermark should be added.|Possible values: AllPages, BackgroundPages, Default, ForegroundPages, SeparateBackgrounds. The default is the same as ForegroundPages.
|LockWatermarks|It indicates whether editing of the shape in Visio is forbidden.|
|Worksheets|Worksheets to add watermarks to.|

### Resource URI ###

```html
HTTP POST ~~/watermark
```

[Swagger UI](https://apireference.groupdocs.cloud/watermark/#/watermark) lets you call this REST API directly from the browser.  

### Use Cases ###
