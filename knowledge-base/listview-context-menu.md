---
title: add context menu to the ListView Item
description: Add context menu to the Telerik .NET MAUI ListView Item
type: how-to
page_title: How to add context menu to the ListView Item
slug: chart-multiple-axis
position: 
tags: maui, listview, item, context menu, dotnet maui
res_type: kb
---

## Environment

<table>
	<tbody>
		<tr>
			<td>Product Version</td>
			<td>4.0.0</td>
		</tr>
		<tr>
			<td>Product</td>
			<td>ListView for .NET MAUI</td>
		</tr>
	</tbody>
</table>

## Description

This article shows how to add a context menu to the ListView item.

## Solution

This scenario could be achieved for example, with [RadButton]({%slug button-overview%}), [RadPopup]({%slug popup-overview%}) controls.

## Example

Let's create a business model for the items:

```C#
public class DataItem : Telerik.Maui.Controls.NotifyPropertyChangedBase
{
    private string name;
    private bool isPopupOpen;

    public DataItem(string personName)
    {
        Name = personName;
    }

    public string Name
    {
        get => name;
        set => UpdateValue(ref name, value);
    }

    public bool IsPopupOpen
    {
        get => isPopupOpen;
        set => UpdateValue(ref isPopupOpen, value);
    }
}
```

Then, in the view model, let's create some sample names to populate the data source and a command that will toggle the IsPopupOpen property of that item (the command opens the context menu):

```C#
public class ViewModel
{
    public ViewModel()
    {
        this.People = new ObservableCollection<DataItem>()
        {
            new DataItem("Freda Curtis"),
            new DataItem("Jeffery Francis"),
            new DataItem("Eva Lawson"),
            new DataItem("Emmett Santos"),
            new DataItem("Theresa Bryan"),
            new DataItem("Jenny Fuller")
        };

        OpenContextMenuCommand = new Command<DataItem>(item => item.IsPopupOpen = !item.IsPopupOpen);
    }

    public ObservableCollection<DataItem> People { get; set; }
    public Command<DataItem> OpenContextMenuCommand { get; }
}
```

The XAML, uses a `RadPopup` in the `ItemTemplate` with a slight offset. Here are the important takeaways:

    * The control's IsOpen property is bound to the model's IsPopupOpen property.

    * The RadButton Command uses x:Reference to get to the view model command property.

```XAML
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:local="clr-namespace:TESTNet7"
             x:Class="TESTNet7.MainPage">
    <ContentPage.BindingContext>
        <local:ViewModel x:Name="PageViewModel" />
    </ContentPage.BindingContext>

    <Grid>
        <telerik:RadListView x:Name="listView"
                                         ItemsSource="{Binding People}"
                                         SelectionMode="None">
            <telerik:RadListView.ItemTemplate>
                <DataTemplate>
                    <telerik:ListViewTemplateCell>
                        <Grid x:Name="ItemGrid"
                              BackgroundColor="WhiteSmoke"
                              HeightRequest="70">
                            <Grid.ColumnDefinitions>
                                <ColumnDefinition Width="*" />
                                <ColumnDefinition Width="45" />
                            </Grid.ColumnDefinitions>

                            <Label x:Name="ListItemDisplayLabel"
                                   Text="{Binding Name}"
                                   HorizontalOptions="Center"
                                   VerticalOptions="Center"
                                   FontSize="18" />

                            <BoxView x:Name="ItemSpacerBoxView"
                                     HorizontalOptions="Fill"
                                     VerticalOptions="End"
                                     HeightRequest="1" />

                            <!-- If you want just the ellipsis to open the context menu, use a Button instead. 
                                 Since the command is in the page's ViewModel, so we use x:Reference to escape the BindingContext of the DataTemplate -->
                            <Button Text=":"
                                    Command="{Binding BindingContext.OpenContextMenuCommand, Source={x:Reference listView}}"
                                    CommandParameter="{Binding}"
                                    TextColor="DarkGray"
                                    BackgroundColor="Transparent"
                                    VerticalOptions="Center"
                                    HorizontalOptions="Center"
                                    Grid.Column="1">
                                <telerik:RadPopup.Popup>
                                    <!-- The BindingContext of the popup is the item, so we can bind to IsPopupOpen and Name. -->
                                    <telerik:RadPopup IsOpen="{Binding IsPopupOpen}"
                                                                HorizontalOffset="-25">
                                        <StackLayout BackgroundColor="White"
                                                     Padding="10"
                                                     Spacing="5">
                                            <Label Text="Menu" FontAttributes="Bold"/>
                                            <Label Text="{Binding Name, StringFormat='Name: {0}'}" />
                                        </StackLayout>
                                    </telerik:RadPopup>
                                </telerik:RadPopup.Popup>
                            </Button>
                        </Grid>
                    </telerik:ListViewTemplateCell>
                </DataTemplate>
            </telerik:RadListView.ItemTemplate>
        </telerik:RadListView>
    </Grid>
</ContentPage>
```

And the final result:

![.NET MAUI ListView context menu](images/listview-context-menu.png)
