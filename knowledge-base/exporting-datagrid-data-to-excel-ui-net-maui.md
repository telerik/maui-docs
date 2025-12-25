---
title: Exporting DataGrid Data to Excel in UI for .NET MAUI
description: Learn how to export DataGrid data to Excel in UI for .NET MAUI using Telerik Document Processing Library SpreadStreamProcessing.
type: how-to
page_title: How to Export DataGrid Data to Excel in UI for .NET MAUI
meta_title: How to Export DataGrid Data to Excel in UI for .NET MAUI
slug: exporting-datagrid-data-to-excel-ui-net-maui
tags: ui-for-net-maui, datagrid, export-to-excel, spreadstreamprocessing, telerik-document-processing-library
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- | 
| 12.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to export DataGrid data to an Excel file in UI for .NET MAUI. How can I achieve that?

This knowledge base article also answers the following questions:
- How to export DataGrid data to a spreadsheet in UI for .NET MAUI?
- How to use SpreadStreamProcessing to generate Excel from DataGrid data?
- How do I create an Excel file with DataGrid data in UI for .NET MAUI?

## Solution

To export DataGrid data to Excel, use the Telerik Document Processing Library [SpreadStreamProcessing](https://docs.telerik.com/devtools/document-processing/libraries/radspreadprocessing/overview) and generate a spreadsheet document with the DataGrid data.

1. Define the DataGrid and a button in XAML to trigger the export command.

```xaml
<Grid RowDefinitions="*, Auto">
    <telerik:RadDataGrid x:Name="list"
                         SelectionMode="None"
                         UserGroupMode="Disabled"
                         UserFilterMode="Disabled"
                         UserSortMode="None"
                         AutoGenerateColumns="False"
                         ItemsSource="{Binding Courses}">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridTextColumn PropertyName="CourseName"
                                        HeaderText="Course Name" />
            <telerik:DataGridTextColumn PropertyName="University" />
            <telerik:DataGridNumericalColumn PropertyName="Progress"
                                             HeaderText="Progress (%)"
                                             CellContentFormat="{}{0} %" />
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>

    <telerik:RadButton Grid.Row="1"
                        Text="Generate and open the .xlsx file"
                        Command="{Binding GenerateSpreadsheetCommand}"/>
</Grid>
```

2. Define a data model to represent the grid data.

```csharp
public class CourseViewModel
{
    public CourseViewModel(string courseName, string university, int progress)
    {
        CourseName = courseName;
        University = university;
        Progress = progress;
    }

    public string CourseName { get; private set; }
    public string University { get; private set; }
    public int Progress { get; private set; }
}
```

3. Create a `ViewModel` with sample data and a command for generating the spreadsheet.

```csharp
public class FirstLookViewModel : NotifyPropertyChangedBase
{
    private Random random;
    private const string DocumentTitle = "MY COURSES";
    private const string TitleColumnHeader = "TITLE";
    private const string UniversityColumnHeader = "UNIVERSITY";
    private const string ProgressColumnHeader = "PROGRESS";
    private const int CoursesCount = 30;

    private static readonly string[] CourseNames = new string[] { "Data Science", "Machine Learning", "Big Data", "Product Management", "Business Foundations", "Python for Everybody", "Finance", "Manufacturing Engineering",
                                                                    "Architecture", "Art and Design", "Biological Sciences", "Chemical Engineering", "Chemistry", "Marketing", "Robotics"};
    private static readonly string[] Universities = new string[] { "John Hopkins University", "University of Washington", "University of California", "University of Pennsylvania", "University of Michigan", "Harvard University", "Stanford University" };

    private ObservableCollection<CourseViewModel> courses;
    private ICommand generateSpreadsheetCommand;

    public FirstLookViewModel()
    {
        this.random = new Random(30);
        this.GenerateSpreadsheetCommand = new Command(this.GenerateSpreadsheet);
        this.Courses = new ObservableCollection<CourseViewModel>(this.GenerateCourses());
    }

    public ObservableCollection<CourseViewModel> Courses
    {
        get
        {
            return this.courses;
        }
        private set
        {
            if (this.courses != value)
            {
                this.courses = value;
                this.OnPropertyChanged();
            }
        }
    }

    public ICommand GenerateSpreadsheetCommand
    {
        get
        {
            return this.generateSpreadsheetCommand;
        }
        private set
        {
            if (this.generateSpreadsheetCommand != value)
            {
                this.generateSpreadsheetCommand = value;
                this.OnPropertyChanged();
            }
        }
    }

    private IEnumerable<CourseViewModel> GenerateCourses()
    {
        for (int i = 0; i < CoursesCount; i++)
        {
            int courseIndex = this.random.Next(0, CourseNames.Length);
            int universityIndex = this.random.Next(0, Universities.Length);
            int progress = this.random.Next(0, 101);

            yield return new CourseViewModel(CourseNames[courseIndex], Universities[universityIndex], progress);
        }
    }

    private async void GenerateSpreadsheet(object obj)
    {
        using (MemoryStream stream = new MemoryStream())
        {
            using (IWorkbookExporter workbookExporter = SpreadExporter.CreateWorkbookExporter(SpreadDocumentFormat.Xlsx, stream))
            {
                using (IWorksheetExporter worksheetExporter = workbookExporter.CreateWorksheetExporter("Courses"))
                {
                    ExportColumnWidths(worksheetExporter);
                    ExportDocumentTitleRow(worksheetExporter);
                    ExportDocumentHeaderRow(worksheetExporter);
                    ExportData(worksheetExporter);

                    worksheetExporter.MergeCells(0, 0, 0, 2);
                }
            }

            await DependencyService.Get<IFileViewerService>().View(stream, "my_courses.xlsx");
        }
    }

    private void ExportColumnWidths(IWorksheetExporter worksheetExporter)
    {
        int firstColumnCharactersCount = 0;
        int secondColumnCharactersCount = 0;
        int thirdColumnCharactersCount = 15;

        foreach (CourseViewModel course in this.Courses)
        {
            firstColumnCharactersCount = Math.Max(firstColumnCharactersCount, course.CourseName.Length);
            secondColumnCharactersCount = Math.Max(secondColumnCharactersCount, course.University.Length);
        }

        using (IColumnExporter columnExporter = worksheetExporter.CreateColumnExporter())
        {
            columnExporter.SetWidthInCharacters(firstColumnCharactersCount);
        }

        using (IColumnExporter columnExporter = worksheetExporter.CreateColumnExporter())
        {
            columnExporter.SetWidthInCharacters(secondColumnCharactersCount);
        }

        using (IColumnExporter columnExporter = worksheetExporter.CreateColumnExporter())
        {
            columnExporter.SetWidthInCharacters(thirdColumnCharactersCount);
        }
    }

    private static void ExportDocumentTitleRow(IWorksheetExporter worksheetExporter)
    {
        using (IRowExporter documentTitleRowExporter = worksheetExporter.CreateRowExporter())
        {
            using (ICellExporter cellExporter = documentTitleRowExporter.CreateCellExporter())
            {
                cellExporter.SetValue(DocumentTitle);
                cellExporter.SetFormat(new SpreadCellFormat
                {
                    Fill = SpreadPatternFill.CreateSolidFill(new SpreadColor(10, 144, 208)),
                    ForeColor = new SpreadThemableColor(new SpreadColor(255, 255, 255)),
                    FontSize = 16,
                    FontFamily = new SpreadThemableFontFamily("Arial"),
                    HorizontalAlignment = SpreadHorizontalAlignment.Center
                });
            }
        }
    }

    private static void ExportDocumentHeaderRow(IWorksheetExporter worksheetExporter)
    {
        using (IRowExporter headerRowExporter = worksheetExporter.CreateRowExporter())
        {
            SpreadCellFormat format = new SpreadCellFormat
            {
                Fill = SpreadPatternFill.CreateSolidFill(new SpreadColor(220, 220, 220)),
                FontSize = 14,
                FontFamily = new SpreadThemableFontFamily("Arial"),
            };

            SpreadCellFormat lastCellFormat = new SpreadCellFormat
            {
                Fill = format.Fill,
                FontSize = format.FontSize,
                FontFamily = format.FontFamily,
                HorizontalAlignment = SpreadHorizontalAlignment.Right
            };

            using (ICellExporter cellExporter = headerRowExporter.CreateCellExporter())
            {
                cellExporter.SetValue(TitleColumnHeader);
                cellExporter.SetFormat(format);
            }

            using (ICellExporter cellExporter = headerRowExporter.CreateCellExporter())
            {
                cellExporter.SetValue(UniversityColumnHeader);
                cellExporter.SetFormat(format);
            }

            using (ICellExporter cellExporter = headerRowExporter.CreateCellExporter())
            {
                cellExporter.SetValue(ProgressColumnHeader);
                cellExporter.SetFormat(lastCellFormat);
            }
        }
    }

    private void ExportData(IWorksheetExporter worksheetExporter)
    {
        foreach (CourseViewModel course in this.Courses)
        {
            using (IRowExporter rowExporter = worksheetExporter.CreateRowExporter())
            {
                using (ICellExporter cellExporter = rowExporter.CreateCellExporter())
                {
                    cellExporter.SetValue(course.CourseName);
                }

                using (ICellExporter cellExporter = rowExporter.CreateCellExporter())
                {
                    cellExporter.SetValue(course.University);
                }

                using (ICellExporter cellExporter = rowExporter.CreateCellExporter())
                {
                    cellExporter.SetValue((double)course.Progress / 100);
                    cellExporter.SetFormat(new SpreadCellFormat
                    {
                        NumberFormat = "0 %",
                        HorizontalAlignment = SpreadHorizontalAlignment.Right
                    });
                }
            }
        }
    }
}
```

## See Also

- [SpreadStreamProcessing Overview](https://docs.telerik.com/devtools/document-processing/libraries/radspreadprocessing/overview)
- [UI for .NET MAUI DataGrid Documentation](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
- [Telerik Document Processing Library](https://docs.telerik.com/devtools/document-processing/introduction)
