---
title: Exporting DataGrid to PDF in .NET MAUI
description: Learn how to export Telerik UI for .NET MAUI DataGrid to a PDF using RadPdfProcessing.
type: how-to
page_title: How to Export Telerik UI for .NET MAUI DataGrid to PDF
meta_title: Export Telerik UI for .NET MAUI DataGrid to PDF
slug: export-datagrid-to-pdf-net-maui
tags: datagrid, ui for .net maui, export, pdf, pdfprocessing, radpdfprocessing
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

Exporting the [UI for .NET MAUI DataGrid](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview) directly to PDF is not supported. However, you can achieve this functionality by manually creating a `.pdf` file using the [RadPdfProcessing](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview) library.

This knowledge base article also answers the following questions:
- How to generate a PDF from Telerik UI for .NET MAUI DataGrid?
- Is there a workaround for exporting DataGrid to PDF?
- How to use `RadPdfProcessing` to export grid data?

## Solution

At this time, there is no built-in method to export the DataGrid to PDF. However, you can create a PDF document manually by utilizing the [RadPdfProcessing library](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview) to format and populate the data from the DataGrid.

To export Telerik UI for .NET MAUI DataGrid to PDF, follow these steps:

1. Define the DataGrid and a button in XAML to trigger the export command:

    ```xaml
    <Grid RowDefinitions="*, Auto">
        <telerik:RadDataGrid AutoGenerateColumns="False"
                             SelectionMode="None"
                             UserGroupMode="Disabled"
                             UserFilterMode="Disabled"
                             UserSortMode="None"
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
                           Text="Generate and open the .pdf file"
                           Command="{Binding GeneratePdfCommand}" />
    </Grid>
    ```

2. Define a data model to represent the grid data:

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

3. Create a `ViewModel` with sample data and a command for generating the PDF:

```csharp
public class ExportToPdfViewModel : NotifyPropertyChangedBase
{
	private Random random;
	private FixedContentEditor pageEditor;
	private const string TitleColumnHeader = "TITLE";
	private const string UniversityColumnHeader = "UNIVERSITY";
	private const string ProgressColumnHeader = "PROGRESS";
	private const int CoursesCount = 30;
	private const string FileName = "my_courses.pdf";
	private static readonly string[] CourseNames = new string[]
	{
		"Data Science",
		"Machine Learning",
		"Big Data",
		"Product Management",
		"Business Foundations",
		"Python for Everybody",
		"Finance",
		"Manufacturing Engineering",
		"Architecture",
		"Art and Design",
		"Biological Sciences",
		"Chemical Engineering",
		"Chemistry",
		"Marketing",
		"Robotics"
	};
	private static readonly string[] Universities = new string[] { "John Hopkins University", "University of Washington", "University of California", "University of Pennsylvania", "University of Michigan", "Harvard University", "Stanford University" };

	private ObservableCollection<CourseViewModel> courses;
	private ICommand generatePdfCommand;

	public ExportToPdfViewModel()
	{
		this.random = new Random(30);
		this.GeneratePdfCommand = new Command(this.GeneratePdf);
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

	public ICommand GeneratePdfCommand
	{
		get
		{
			return this.generatePdfCommand;
		}
		private set
		{
			if (this.generatePdfCommand != value)
			{
				this.generatePdfCommand = value;
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

	private async void GeneratePdf(object obj)
	{
		RadFixedDocument document = this.CreateDocument();

		using (MemoryStream stream = new MemoryStream())
		{
			PdfFormatProvider pdfProvider = new PdfFormatProvider();
			pdfProvider.Export(document, stream, TimeSpan.FromMinutes(1));
			await DependencyService.Get<IFileViewerService>().View(stream, FileName);
		}
	}

	public RadFixedDocument CreateDocument()
	{
		RadFixedDocument document = new RadFixedDocument();
		RadFixedPage page = document.Pages.AddPage();
		page.Size = new Size(688, 918);

		this.pageEditor = new FixedContentEditor(page);
		this.DrawTableContent(this.pageEditor);

		return document;
	}

	private void DrawTableContent(FixedContentEditor editor)
	{
		RgbColor headerColor = new RgbColor(51, 51, 51);
		RgbColor bordersColor = new RgbColor(205, 205, 205);
		RgbColor alternatingRowColor = new RgbColor(243, 243, 243);

		Telerik.Windows.Documents.Fixed.Model.Editing.Border border = new Telerik.Windows.Documents.Fixed.Model.Editing.Border(1, Telerik.Windows.Documents.Fixed.Model.Editing.BorderStyle.Single, bordersColor);

		Table table = new Table();
		table.Borders = new TableBorders(border);
		table.LayoutType = TableLayoutType.FixedWidth;
		table.DefaultCellProperties.Borders = new TableCellBorders(border, border, border, border);
		table.DefaultCellProperties.Padding = new Telerik.Documents.Primitives.Thickness(4);

		TableRow headerRow = table.Rows.AddTableRow();

		List<string> columns = new List<string> { TitleColumnHeader, UniversityColumnHeader, ProgressColumnHeader };

		foreach (string column in columns)
		{
			TableCell headerCell = headerRow.Cells.AddTableCell();
			headerCell.Background = headerColor;

			Block block = headerCell.Blocks.AddBlock();
			block.GraphicProperties.FillColor = RgbColors.White;
			block.HorizontalAlignment = Telerik.Windows.Documents.Fixed.Model.Editing.Flow.HorizontalAlignment.Center;
			block.InsertText(column);
	
		}

		for (int i = 0; i < this.Courses.Count; i++)
		{
			RgbColor rowColor = i % 2 == 0 ? alternatingRowColor : RgbColors.White;
			CourseViewModel course = this.Courses[i];

			TableRow courseRow = table.Rows.AddTableRow();

			TableCell cell = courseRow.Cells.AddTableCell();
			cell.Background = rowColor;

			Block block = cell.Blocks.AddBlock();
			block.InsertText(course.CourseName);

			cell = courseRow.Cells.AddTableCell();
			cell.Background = rowColor;

			block = cell.Blocks.AddBlock();
			block.InsertText(course.University);

			cell = courseRow.Cells.AddTableCell();
			cell.Background = rowColor;

			block = cell.Blocks.AddBlock();
			block.HorizontalAlignment = Telerik.Windows.Documents.Fixed.Model.Editing.Flow.HorizontalAlignment.Right;
			block.InsertText(string.Format("{0:P0}", (double)course.Progress / 100));
		}

		table.Draw(editor, new Rect(40, 40, 608, double.PositiveInfinity));
	}
}
 ```

## See Also

- [PdfProcessing Overview](https://docs.telerik.com/devtools/document-processing/libraries/radpdfprocessing/overview)
- [UI for .NET MAUI DataGrid Documentation](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
- [Telerik Document Processing Library](https://docs.telerik.com/devtools/document-processing/introduction)
