---
title: Fonts
page_title: .NET MAUI PDF Viewer Documentation - Fonts
description: Learn how to register the fonts in the PDF document.
position: 7
slug: pdfviewer-fonts
---

# Fonts

The Telerik UI for .NET MAUI PDF Viewer supports [standard](#standard-fonts) and [embedded fonts](#embedded-fonts). 

## Standard Fonts

There are 14 standard fonts that are not embedded in the document when you use them. As our .NET MAUI PDF Viewer works with the [RadPdfProcessing](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview) model, these fonts can be accessed through the PdfProcessing [`FontsRepository` class](https://docs.telerik.com/devtools/document-processing/api/telerik.windows.documents.fixed.model.fonts.fontsrepository). 

You can find a full list of the provided standard fonts below:

* `Helvetica`
* `Helvetica-Bold`
* `Helvetica-Oblique`
* `Helvetica-BoldOblique`
* `Courier`
* `Courier-Bold`
* `Courier-Oblique`
* `Courier-BoldOblique`
* `Times-Roman`
* `Times-Bold`
* `Times-Italic`
* `Times-BoldItalic`
* `Symbol`
* `ZapfDingbats`

## Embedded Fonts

All fonts except the [14 standard fonts](#standard-fonts) must be embedded in the PDF document. Otherwise, the rendering of the document will lead to unpredictable results as the PDF Viewer renderer falls back to the default fonts.

### Registering a Font

The PDF Viewer for .NET MAUI works with the [RadPdfProcessing library](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview) model. To embed a font, utilize the `RegisterFont` static method provided by the PdfProcessing fonts repository. Use the `RegisterFont` method for `TrueType` fonts as well.

`RegisterFont` requires four parameters: the `FontFamily`, `FontStyle`, and `FontWeight` objects describing the font and a byte array containing the raw font data.

#### Example: Embedding a Non-Standard Font

The following example demonstrates how to embed a non-standard font when working with the PDF Viewer and the PdfProcessing library.

**1**: Add the `.ttf` file containing the font data to your .NET MAUI project. In the example below, the `.ttf` it is placed inside `Resources` folder:

![.NET MAUI PDF Viewer fonts](images/pdf-fonts.png)

>Make sure to update the build action of the `.ttf` file to **Embedded resource**.

**2**: Add a sample implementation for reading the font data from a stream, for example:

```C#
private static byte[] ReadAllBytes(Stream input)
{
	byte[] buffer = new byte[16 * 1024];
	using (MemoryStream ms = new MemoryStream())
	{
		int read;
		while ((read = input.Read(buffer, 0, buffer.Length)) > 0)
		{
			ms.Write(buffer, 0, read);
		}
		return ms.ToArray();
	}
}
```

**3**: Embed the font through the `RegisterFont` method. Here you need to use the `ReadAllBytes` method to read the font data and return it as a byte array:

```C#
Assembly assembly = typeof(MainPage).Assembly;
Stream stream = assembly.GetManifestResourceStream("SampleApp.Resources.SampleFont.ttf");
var fontData = ReadAllBytes(stream);
Telerik.Windows.Documents.Fixed.Model.Fonts.FontsRepository.RegisterFont(
	new FontFamily("Verdana"), FontStyles.Normal, FontWeights.Normal, fontData);
```

**4.** Add the missing namespace related to the PdfProcessing library:

```C#
using Telerik.Documents.Core.Fonts;
```

After completing all steps, the `RadPdfViewer` will use the registered font data when rendering text with the same font set.

## See Also

- [RadPdfProcessing library](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview)
