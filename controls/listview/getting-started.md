---
title: Getting Started
page_title: .NET MAUI ListView Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI ListView and add the control to your .NET MAUI project.
position: 1
previous_url: /controls/listview/listview-getting-started
slug: listview-getting-started
---

@[template](/_contentTemplates/common/listview-obsolete.md#listview-obsolete)

# Getting Started with the .NET MAUI ListView

This guide provides the information you need to start using the [Telerik UI for .NET MAUI ListView]({%slug listview-overview%}) by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI ListView Getting Started](images/listview-gettingstarted.png)

## Prerequisites

Before adding the ListView, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

When your .NET MAUI application is set up, you are ready to add a ListView control to your page. The following example shows a sample ListView definition populated with sample data.

  The ListView provides UI virtualization, which requires the visual parent to provide vertical or horizontal space. To avoid breaking UI virtualization or gesture mechanisms:

  * Do not place the ListView inside a `StackLayout` or inside a `ScrollView`.
  * Do not set the ListView to a `RowDefinition Height="Auto"` Grid definition.

**1.** Set up the `RadListView` instance:

```XAML
<telerik:RadListView x:Name="listView" ItemsSource="{Binding Source}">
    <telerik:RadListView.BindingContext>
        <local:ViewModel />
    </telerik:RadListView.BindingContext>
    <telerik:RadListView.ItemTemplate>
        <DataTemplate>
            <telerik:ListViewTemplateCell>
                <telerik:ListViewTemplateCell.View>
                    <Grid>
                        <Label Margin="10" Text="{Binding Name}" />
                    </Grid>
                </telerik:ListViewTemplateCell.View>
            </telerik:ListViewTemplateCell>
        </DataTemplate>
    </telerik:RadListView.ItemTemplate>
</telerik:RadListView>
```

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create sample `Data` and `ViewModel` classes:

<snippet id='listview-gettingstarted-source' />

**4.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

public static class MauiProgram
{
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseTelerik()
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
			});

		return builder.Build();
	}
}           
```

## Additional Resources

- [.NET MAUI ListView Product Page](https://www.telerik.com/maui-ui/listview)
- [.NET MAUI ListView Forum Page](https://www.telerik.com/forums/maui?tagId=1829)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [ListView Text Cell]({% slug listview-textcell %})
- [ListView Template Cell]({% slug listview-templatecell %})
- [Selection]({% slug listview-features-selection%})
- [Grouping]({% slug listview-features-grouping%})
