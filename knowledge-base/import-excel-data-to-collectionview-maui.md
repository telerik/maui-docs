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

When you implement a feature that imports data from Excel into a .NET MAUI app, it's essential to parse the Excel file and display its contents in a [CollectionView]({%slug collectionview-overview%}). This process involves selecting an Excel file, reading its data, and populating a CollectionView with the parsed information.

This KB article also answers the following questions:
- How to select an Excel file in a .NET MAUI app?
- How to parse Excel file data in .NET MAUI?
- How to display Excel data in a CollectionView in .NET MAUI?

## Solution

To achieve the import of Excel data into a CollectionView in a .NET MAUI app, follow these steps:
1. [Parse the Excel file data](#parse-excel-file-data).
1. [Use the .NET MAUI File Picker](#use-file-picker).
1. [Display the data in the CollectionView](#display-data-in-collectionview).

### Parse Excel File Data

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

### Use File Picker

For selecting an Excel file, utilize the .NET MAUI File Picker API as described in the <a href="https://learn.microsoft.com/en-us/dotnet/maui/platform-integration/storage/file-picker?view=net-maui-8.0&tabs=windows" target="_blank">official Microsoft documentation</a>.

### Display Data in CollectionView

Bind the parsed data collection (`List<DataEntry>`) to the `ItemsSource` of the CollectionView in your .NET MAUI app to display the data.

**1.** Add the following XAML definition for the `RadCollectionView` and the button that opens the file picker:

```XAML
<Grid RowDefinitions="auto,*" Padding="10">
	<Button Text="Import Excel" Clicked="Button_Clicked"/>
	<telerik:RadCollectionView x:Name="collectionView" Grid.Row="1">
		<telerik:RadCollectionView.HeaderTemplate>
			<DataTemplate>
				<HorizontalStackLayout>
					<Label
							 FontAttributes="Bold"
							 Text="Symbol"
							 WidthRequest="100" />
					<Label
							 FontAttributes="Bold"
							 Text="Quantity"
							 WidthRequest="100" />
					<Label
						 FontAttributes="Bold"
						 Text="Price"
						 WidthRequest="100" />
				</HorizontalStackLayout>
			</DataTemplate>
		</telerik:RadCollectionView.HeaderTemplate>
		<telerik:RadCollectionView.ItemTemplate>
			<DataTemplate>
				<HorizontalStackLayout>
					<Label Text="{Binding Cell1}" WidthRequest="100" />
					<Label Text="{Binding Cell2}" WidthRequest="100" />
					<Label Text="{Binding Cell3}" WidthRequest="100" />
				</HorizontalStackLayout>
			</DataTemplate>
		</telerik:RadCollectionView.ItemTemplate>
	</telerik:RadCollectionView>
</Grid>
```

**2.** Implement the code that executes when clicking the button.

**2.1** The code opens a file picker, so the user can pick a `.csv` or `xlsx` files. 
**2.2** Import the selected document.
**2.3** Add the data from the imported document to the collection. The collection is bound to the `RadCollectionView.ItemsSource`.

```C#
public partial class MainPage : ContentPage
{
    ObservableCollection<DataEntry> entries = new ObservableCollection<DataEntry>();
    public MainPage()
    {
        InitializeComponent();
        this.entries = new ObservableCollection<DataEntry>();
    }

    // The following code executes when the button is clicked: 
    private async void Button_Clicked(object sender, EventArgs e)
    {
        try
        {
            var customFileType = new FilePickerFileType(new Dictionary<DevicePlatform, IEnumerable<string>>
            {
                { DevicePlatform.MacCatalyst, new[] { ".csv", ".xlsx", } },
                { DevicePlatform.WinUI, new[] { ".csv", ".xlsx", } },
            });
            var options = new PickOptions
            {
                PickerTitle = "Please select a csv of xlsx file",
                FileTypes = customFileType,
            };
            var selectedFile = await FilePicker.PickAsync(options);


            if (selectedFile != null)
            {
                var data = await selectedFile.OpenReadAsync();


                using (IWorkbookImporter workBookImporter = SpreadImporter.CreateWorkbookImporter(SpreadDocumentFormat.Csv, data))
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

                            this.entries.Add(entry);
                        }
                    }
                }




                this.collectionView.ItemsSource = this.entries;

            }

            return;

        }
        catch (Exception)
        {

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

## See Also

- [Telerik CollectionView for .NET MAUI Documentation]({%slug collectionview-overview%})
- [RadSpreadStreamProcessing Documentation](https://docs.telerik.com/devtools/document-processing/libraries/radspreadstreamprocessing/overview)
- [Telerik MAUI PDF Viewer File Picker Example](https://github.com/telerik/maui-samples/tree/main/Samples/ControlsSamples/Examples/PdfViewerControl/OpenSaveShareExample)
