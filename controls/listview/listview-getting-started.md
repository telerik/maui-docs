---
title: Getting Started
page_title: .NET MAUI ListView Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI ListView and add the control to your .NET MAUI project."
position: 1
slug: listview-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI ListView by adding the control to your project.

At the end, you will be able to achieve the following result.

![RadListView](images/listview-gettingstarted.png)

## Prerequisites

Before adding the ListView, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a ListView control to your page. The following example shows a sample ListView definition.

  The ListView provides UI virtualization, which requires the visual parent to provide vertical or horizontal space. To avoid breaking UI virtualization or gesture mechanisms:

  * Do not place the ListView inside a `StackLayout` or inside a `ScrollView`.
  * Do not set the ListVew to a `RowDefinition Height="Auto"` Grid definition.

 ```XAML
<telerikDataControls:RadListView x:Name="listView" />
 ```
 ```C#
var listView = new RadListView();
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
 ```


## Populate the ListView with Data

1. First, let's create simple `Data` and `ViewModel` classes:

 ```C#
public class SourceItem
{
    public SourceItem(string name)
    {
        this.Name = name;
    }

    public string Name { get; set; }
}

public class ViewModel
{
    public ViewModel()
    {
        this.Source = new List<SourceItem> { new SourceItem("Tom"),
											 new SourceItem("Anna"),
											 new SourceItem("Peter"),
											 new SourceItem("Teodor"),
											 new SourceItem("Lorenzo"),
											 new SourceItem("Andrea"),
											 new SourceItem("Martin") };
    }

    public List<SourceItem> Source { get; set; }
}
 ```

1. Set up the ListView:

 ```XAML
<telerikDataControls:RadListView x:Name="listView" ItemsSource="{Binding Source}">
    <telerikDataControls:RadListView.BindingContext>
        <local:ViewModel />
    </telerikDataControls:RadListView.BindingContext>
    <telerikDataControls:RadListView.ItemTemplate>
        <DataTemplate>
            <telerikListView:ListViewTemplateCell>
                <telerikListView:ListViewTemplateCell.View>
                    <Grid>
                        <Label Margin="10" Text="{Binding Name}" />
                    </Grid>
                </telerikListView:ListViewTemplateCell.View>
            </telerikListView:ListViewTemplateCell>
        </DataTemplate>
    </telerikDataControls:RadListView.ItemTemplate>
</telerikDataControls:RadListView>
 ```

1. Add the following namespaces:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the `Startup.cs` file of your project:

 ```C#
 using Telerik.Maui.Controls.Compatibility;

public void Configure(IAppHostBuilder appBuilder)
{
    appBuilder        
        .UseTelerik()
        .UseMauiApp<App>();

}              
 ```

## See Also

- [ListView TextCell]({% slug listview-textcell %})
- [ListView TemplateCell]({% slug listview-templatecell %})
- [Selection]({% slug listview-features-selection%})
- [Grouping]({% slug listview-features-grouping%})
