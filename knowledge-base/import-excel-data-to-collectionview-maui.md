---
title: Importing Excel Data into .NET MAUI CollectionView
description: Learn how to pick an Excel file, import its content, and display it in a .NET MAUI CollectionView.
type: how-to
page_title: How to Import Excel Data and Display in CollectionView in .NET MAUI
slug: import-excel-data-to-collectionview-maui
tags: collectionview, .net maui, excel, import, radspreadstreamprocessing
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI CollectionView, Telerik SpreadProcessing | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When implementing a feature to import data from Excel into a .NET MAUI app, it's essential to parse the Excel file and display its contents in a [CollectionView](https://docs.telerik.com/devtools/maui/controls/collectionview/overview). This process involves selecting an Excel file, reading its data, and populating a CollectionView with the parsed information. This KB article also answers the following questions:
- How to select an Excel file in a .NET MAUI app?
- How to parse Excel file data in .NET MAUI?
- How to display Excel data in a CollectionView in .NET MAUI?

## Solution

To achieve the import of Excel data into a CollectionView in a .NET MAUI app, follow these steps:

1. **Parse Excel File Data:**

Use the [SpreadStreamProcessing](https://docs.telerik.com/devtools/document-processing/libraries/radspreadstreamprocessing/overview) library to parse the Excel file. The following code snippet demonstrates how to read the first three columns of data from an Excel file and store them in a collection:

```csharp
List<DataEntry> entries = new List<DataEntry>();

using (System.IO.FileStream fs = new System.IO.FileStream(path, FileMode.Open))
{
    SpreadDocumentFormat format;
    switch (Path.GetExtension(path))
    {
        case ".csv":
            format = SpreadDocumentFormat.Csv;
            break;
        case ".xlsx": 
            format = SpreadDocumentFormat.Xlsx;
            break;
        default:
            format = SpreadDocumentFormat.Xlsx;
            break;  
    }

    using (IWorkbookImporter workBookImporter = SpreadImporter.CreateWorkbookImporter(format, fs))
    {
        foreach (IWorksheetImporter worksheetImporter in workBookImporter.WorksheetImporters)
        {
            foreach (IRowImporter rowImporter in worksheetImporter.Rows)
            {
                DataEntry entry = new DataEntry();

                bool shouldBreak = false;

                foreach (ICellImporter cell in rowImporter.Cells)
                {
                    switch (cell.ColumnIndex)
                    {
                        case 0:
                            entry.Cell1 = cell.Value;
                            break;
                        case 1:
                            entry.Cell2 = cell.Value;
                            break;
                        case 2:
                            entry.Cell3 = cell.Value;
                            break;
                        default:
                            shouldBreak = true;
                            break;
                    }
                    
                    if (shouldBreak)
                    {
                        break;
                    }
                }

                entries.Add(entry);
            }
        }
    }
}

class DataEntry
{
    public string Cell1 { get; set; }
    public string Cell2 { get; set; }
    public string Cell3 { get; set; }
}
```

2. **File Picker Usage:**

For selecting an Excel file, utilize the .NET MAUI File Picker API as described in the official Microsoft documentation. Refer to the Telerik MAUI PDF Viewer example for an implementation sample of the file picker.

3. **Display Data in CollectionView:**

Bind the parsed data collection (`List<DataEntry>`) to the ItemsSource of the CollectionView in your .NET MAUI app to display the data.

This solution provides a way to select an Excel file, parse its first three columns of data, and display the content in a .NET MAUI CollectionView.

## See Also

- [Telerik CollectionView for .NET MAUI Documentation]({%slug collectionview-overview%})
- [RadSpreadStreamProcessing Documentation](https://docs.telerik.com/devtools/document-processing/libraries/radspreadstreamprocessing/overview)
- [Telerik MAUI PDF Viewer File Picker Example](https://github.com/telerik/maui-samples/tree/main/Samples/ControlsSamples/Examples/PdfViewerControl/OpenSaveShareExample)
