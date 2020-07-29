---
id: "features-overview"
url: "watermark/features-overview"
title: "Features Overview"
productName: "GroupDocs.Watermark Cloud"
weight: 2
description: ""
keywords: ""
---





# Overview #

GroupDocs.Watermark Cloud is a REST API for managing watermarks in the documents of different file formats.

It provides easy to use watermarking methods. It also allows you to search and remove previously added watermarks of popular types (including watermarks added by third-party tools) in a document.

The API provides straightforward and easy to use set of methods to add, search, and remove watermarks in supported file formats.

## Adding Watermarks ##

Groupdocs.Watermark Cloud allows to add text/image watermarks to supported document formats and images and save resultant file.

You can specify text style of the watermark, size and font, colors and position. Creating watermarks only for specific pages is also available.

## Searching Watermarks ##

Groupdocs.Watermark Cloud allows to retrieve a collection of text or image watermarks inside a document. It shows you a type of the watermark, text, size and convenient way to distinguish watermark for further usage.

## Replacing Watermarks ##

Groupdocs.Watermark Cloud allows to edit existing not locked watermarks of supported document formats. It is easy to change text, text formatting, colors, position and image.

## Removing Watermarks ##

Groupdocs.Watermark Cloud allows to remove watermarks from document. You may want to specify only particular pages for clearance or ids of the watermarks to remove. Ids could be retrieved from search endpoint.

# API Endpoint Groups Overview #


|Endpoint Group|Description
|Watermark|Contains endpoints for add, remove, replace and search watermarks.
|Info|Contains endpoints for obtaining list of formats supported by GroupDocs.Watermark Cloud, getting basic information about document and its pages.
|File|Contains endpoints for upload, download, copy, move, delete files in the storage
|Folder|Contains endpoints for create, copy, move, delete folders in the storage
|Storage|Contains endpoints for obtaining storage information and file information

# Security and Authentication #

The GroupDocs.Watermark Cloud API is secured and requires authentication. Two keys AppSID and AppKey are required for Authentication which can be created at the [Dashboard](http://dashboard.groupdocs.cloud/). Check [Authenticating API Requests](https://docs.groupdocs.cloud/display/gdtotalcloud/Authenticating+API+Requests) article for complete example.

# SDKs #

Checkout our GitHub [repository](https://github.com/groupdocs-watermark-cloud) for a complete list of GroupDocs.Watermark SDKs along with working examples, to get you started in no time. 

At the moment following SDKs are provided: 

* .NET 2.0 ([Sources](https://github.com/groupdocs-watermark-cloud/groupdocs-watermark-cloud-dotnet), NuGet Package)
* Java ([Sources](https://github.com/groupdocs-watermark-cloud/groupdocs-watermark-cloud-java), Jar)

# API Explorer #

The easiest way to try out our API right away in your browser! With the [GroupDocs Cloud API explorer](https://apireference.groupdocs.cloud/watermark/). This is a collection of Swagger documentation for the GroupDocs Cloud APIs. You can get information about all the resources in the API. It also provides testing and interactivity to our API endpoint documentation.

 