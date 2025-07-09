---
title: Forcing Commit Command When Tapping Outside the DataGrid in MAUI
description: Learn how to force the CommitEdit command in the DataGrid for MAUI when tapping outside the control or interacting with another grid.
type: how-to
page_title: Triggering CommitEdit in MAUI DataGrid on External UI Tap or Second DataGrid Interaction
meta_title: Triggering CommitEdit in MAUI DataGrid on External UI Tap or Second DataGrid Interaction
slug: force-commit-command-maui-datagrid-outside-tap
tags: datagrid,maui,commitedit,celltap,tapgesture,programmatic
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need a way to force the first DataGrid in MAUI to commit edits when interacting with external UI elements or a second DataGrid in the same page. Specifically, when editing a cell in the first grid and tapping on another grid or external UI, the edit should be committed programmatically.

This knowledge base article also answers the following questions:
- How to force `CommitEdit` in MAUI DataGrid when tapping outside the grid?
- How to use `CommitEdit` with multiple MAUI DataGrids?
- How to programmatically commit edits in MAUI DataGrid?

## Solution

To force the `CommitEdit` command when tapping outside the MAUI DataGrid or another grid, follow one of the solutions suggested below.

### Solution 1: Tapping on External UI

Use a `TapGestureRecognizer` on an external UI element to programmatically execute the `CommitEdit` command.

**1.** The DataGrid definition in XAML:

```xaml
<Grid RowDefinitions="auto,*">
    <Grid BackgroundColor="LightBlue" HeightRequest="200">
        <Grid.GestureRecognizers>
            <TapGestureRecognizer Tapped="TapGestureRecognizer_Tapped" />
        </Grid.GestureRecognizers>
    </Grid>

    <telerik:RadDataGrid x:Name="grid"
                         Grid.Row="1"
                         ItemsSource="{Binding Clubs}" 
                         AutoGenerateColumns="False" />
</Grid>
```

**2.** Execute the `CommitEdit` command inside the gesture recognizer event handler:

```csharp
private void TapGestureRecognizer_Tapped(object sender, TappedEventArgs e)
{
    this.grid.CommandService.ExecuteCommand(DataGridCommandId.CommitEdit, new EditContext(null, ActionTrigger.Programmatic, null));
}
```

### Solution 2: Interaction with a Second DataGrid

Define a custom command for the second MAUI DataGrid's `CellTap`. This command will execute the `CommitEdit` command for the first grid.

**1.** Define the DataGrid in XAML:

```xaml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:local="clr-namespace:MauiApp13"
             Padding="20"
             x:Name="myPage"
             x:Class="MauiApp13.MainPage">
    <Grid RowDefinitions="*,*">
        <telerik:RadDataGrid x:Name="dataGrid" />
        <telerik:RadDataGrid x:Name="dataGrid1" Grid.Row="1" />
    </Grid>
</ContentPage>
```

**2.** Add a sample data and custom `CellTap` command definition. Inside the `Execute` method, execute the `CommitEdit` command of the first DataGrid:

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();

        this.dataGrid.ItemsSource = new List<Data>
        {
            new Data { Country = "India", Capital = "New Delhi" },
            new Data { Country = "South Africa", Capital = "Cape Town" },
        };

        this.dataGrid1.ItemsSource = new List<Data>
        {
            new Data { Country = "India", Capital = "New Delhi" },
            new Data { Country = "South Africa", Capital = "Cape Town" },
            new Data { Country = "Nigeria", Capital = "Abuja" },
            new Data { Country = "Singapore", Capital = "Singapore" }
        };

        this.dataGrid1.Commands.Add(new CellTapUserCommand(this.myPage));
    }
}

public class Data
{
    public string Country { get; set; }
    public string Capital { get; set; }
}

public class CellTapUserCommand : DataGridCommand
{
    ContentPage myPage;

    public CellTapUserCommand(ContentPage myPage)
    {
        Id = DataGridCommandId.CellTap;
        this.myPage = myPage;
    }

    public override bool CanExecute(object parameter)
    {
        return true;
    }

    public override void Execute(object parameter)
    {
        var context = parameter as DataGridCellInfo;
        var cellTap = $"You tapped on {context.Value} inside {context.Column.HeaderText} column \n";
        Application.Current.MainPage.DisplayAlert("CellTap Command: ", cellTap, "OK");
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CellTap, parameter);

        List<IVisualTreeElement> items = (List<IVisualTreeElement>)this.myPage.GetVisualTreeDescendants();
        foreach (IVisualTreeElement myControl in items)
        {
            if (myControl is RadDataGrid)
            {
                RadDataGrid control = (RadDataGrid)myControl;
                control.CommandService.ExecuteCommand(DataGridCommandId.CommitEdit, new EditContext(null, ActionTrigger.Programmatic, null));
                return;
            }
        }
    }
}
```

## See Also

- [DataGrid for MAUI Overview]({%slug datagrid-overview%})
- [DataGrid Commands Documentation]({%slug datagrid-commands-overview%})
- [MAUI Gesture Recognizers](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/gestures/tap)
