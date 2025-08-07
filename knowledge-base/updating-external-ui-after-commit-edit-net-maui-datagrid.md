---
title: Updating External UI After Commit Edit Command is Executed in DataGrid for .NET MAUI
description: Learn how to update external UI elements after committing edited values in the DataGrid for UI for .NET MAUI.
type: how-to
page_title: Displaying Updated Values in External UI After Commit Edit Command in .NET MAUI DataGrid
meta_title: Displaying Updated Values in External UI After Commit Edit Command in .NET MAUI DataGrid
slug: updating-external-ui-after-commit-edit-net-maui-datagrid
tags: datagrid, ui-for-dotnet-maui, commit-edit-command, external-ui-update
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | DataGrid for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to display calculated values from two edited DataGrid cells in an external UI element, such as a `Label`. I use the `CommitEditCommand` in the UI for .NET MAUI DataGrid to run the calculation after editing the cells. However, the `CommitEditCommand` does not seem to have the updated cell values. 

This knowledge base article also answers the following questions:
- How to use `CommitEditCommand` to update an external UI component in .NET MAUI DataGrid?
- How to bind external UI elements to calculated cell values in .NET MAUI DataGrid?
- How to handle updates after cell edits in .NET MAUI DataGrid?

## Solution

To successfully update external UI elements with calculated values after editing DataGrid cells, follow these steps:

**1.** Define the `CommitEditCommand` to perform custom logic after committing the edited values of the DataGrid cells. Use the `DataGridCommandId.CommitEdit` to invoke the default commit functionality.

```csharp
public class CommitEditCommand : DataGridCommand
{
    private readonly Data _dataContext;
    private readonly Label _externalLabel;

    public CommitEditCommand(Data data, Label label)
    {
        _dataContext = data;
        _externalLabel = label;
        this.Id = DataGridCommandId.CommitEdit;
    }

    public override void Execute(object parameter)
    {
        var context = (EditContext)parameter;
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CommitEdit, context);

        // Update external UI element after committing the values
        double total = _dataContext.Totale;
        _externalLabel.Text = "Importo Totale: " + total.ToString();
    }
}
```

**2.** Bind the external UI element (e.g., `Label`) to the calculated value after updating it in the `CommitEditCommand` logic.

```xaml
<Grid RowDefinitions="*,auto">
    <telerik:RadDataGrid ItemsSource="{Binding Items}" UserEditMode="Cell"
                         ListenForNestedPropertyChange="True" x:Name="datagrid" AutoGenerateColumns="False">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridNumericalColumn PropertyName="Descrizione" />
            <telerik:DataGridNumericalColumn PropertyName="Importo" />
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>

    <VerticalStackLayout Grid.Row="1">
        <Label BackgroundColor="LightBlue" HorizontalOptions="Start" 
               x:Name="label" FontSize="22" Padding="8" Margin="8" WidthRequest="100" />
    </VerticalStackLayout>
</Grid>
```

**3.** Add sample `Data` model and `ViewModel`

```csharp
public class Data : NotifyPropertyChangedBase
{
    private double _descrizione;
    private double _importo;

    public double Descrizione
    {
        get => _descrizione;
        set => this.UpdateValue(ref _descrizione, value);
    }

    public double Importo
    {
        get => _importo;
        set => this.UpdateValue(ref this._importo, value);
    }

    public double Totale => this.Importo * this.Descrizione;
}

public class ViewModel : NotifyPropertyChangedBase
{
    public ObservableCollection<Data> Items { get; }
    public Data Item { get; set; }

    public ViewModel()
    {
        Items = new ObservableCollection<Data>
        {
            new Data { Importo = 0.0, Descrizione = 1 },
        };
        Item = Items[0];
    }
}
```

**4.**  In page's code-behind:

* Set the `ViewModel`.
* Add the `CommitEditCommand` to the DataGrid `Commands` collection.

```csharp
public partial class MainPage : ContentPage
{
    private readonly ViewModel _viewModel;

    public MainPage()
    {
        InitializeComponent();
        _viewModel = new ViewModel();
        this.BindingContext = _viewModel;

        var item = _viewModel.Items[0];
        datagrid.Commands.Add(new CommitEditCommand(item, label));
        label.Text = "Importo Totale: " + item.Totale.ToString();
    }
}
```

## See Also

- [DataGrid Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [DataGrid Commands Documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/commands/overview)
