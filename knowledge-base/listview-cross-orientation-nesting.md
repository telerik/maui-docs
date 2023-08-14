---
title: Nesting Vertical and Horizontal RadListViews
description: Learn how to use a vertical RadListView inside a horizontal ListView with programmatic scrolling control.
type: how-to
page_title: Nested Vertical and Horizontal RadListViews
slug: listview-cross-orientation-nesting
tags: listview, orientation, layout, nested, nesting, embedded, embedding, scrolling, programmatic
position: 5
ticketid: 1618988
res_type: kb
---

## Environment
<table>
    <tbody>
        <tr>
            <td>Product Version</td>
            <td>6.0.0</td>
        </tr>
        <tr>
            <td>Product</td>
            <td>ListView for MAUI</td>
        </tr>
    </tbody>
</table>


## Description

This how-to article describes how you can use two `RadListView` controls together without running into problems with nesting multiple `ScrollView` elements together.

The example code in this article is going to present a Kanban-like display where the top-level `RadListView` scrolls horizontally, while the inner `RadListView` scrolls vertically. As a bonus feature, the example also demonstrates how you can programmatically access that nested ListView and programmatically scroll its items from the top-level page.

## Solution

The key takeaway in this approach is that the inner/nested ListView inside the parent's `ItemTemplate` has a different scrolling direction. This avoids two ScrollViews using the same scrolling direction, which leads to problems by breaking UI virtualization and significant performance and responsiveness issues.

1. Ensure you have the `telerik` namespace in your XAML file:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```


2. Create the needed business objects. For this example, you'll be using a hierarchical object structure, where a parent `KanbanItem` type holds a collection of `KanbanSubItem` children:

    ```C#
    using System.Collections.ObjectModel;
    using Telerik.Maui.Controls.Compatibility.DataControls;

    namespace HorizontalAndVerticalDemo;

    public class KanbanSubItem
    {
        public string Title { get; set; }

        public DateTime Deadline { get; set; }
    }

    public class KanbanItem
    {
        public string WeekName { get; set; }

        public ObservableCollection<KanbanSubItem> SubItems { get; set; }

        public RadListView ListViewHost {get; set; }

        public void ScrollToSubItem(KanbanSubItem item)
        {
            if(ListViewHost == null || item == null)
                return;

            ListViewHost?.ScrollItemIntoView(item);
        }
    }
    ```

3. Create a view model class. For this example, you'll create a `MainViewModel` type, and generate sample data items in the constructor.

    ```C#
    using System.Collections.ObjectModel;

    namespace HorizontalAndVerticalDemo;

    public class MainViewModel
    {
        public MainViewModel()
        {
            var data = new ObservableCollection<KanbanItem>();

            for (int j = 1; j < 5; j++)
            {
                var item = new KanbanItem();
                item.WeekName = $"Week {j}";
            
                item.SubItems = new ObservableCollection<KanbanSubItem>();

                for (int i = 1; i < 31; i++)
                {
                    item.SubItems.Add(new KanbanSubItem {Title = $"Job {i}", Deadline = DateTime.Now.AddDays(i * j)});
                }

                data.Add(item);
            }

            Items = data;
        }

        public ObservableCollection<KanbanItem> Items { get; set; }
    }
    ```

4. On the XAML page, you'll define two `RadListView` controls with the desired design. The important considerations are:
   1. The parent `RadListView` uses a `ListViewLinearLayout` with `Orientation="Horizontal"`.
   2. The `RadListView` in the `ItemTemplate` uses a `ListViewLinearLayout` with `Orientation="Vertical"`.
   3. A `Button` to demonstrate programmatic scrolling.

    ```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                 xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
                 xmlns:local="clr-namespace:HorizontalAndVerticalDemo"
                 x:Class="HorizontalAndVerticalDemo.MainPage">
        <Grid>
            <telerik:RadListView x:Name="listView"
                                 ItemsSource="{Binding Items}">
                <telerik:RadListView.ItemTemplate>
                    <DataTemplate x:DataType="local:KanbanItem">
                        <telerik:ListViewTemplateCell>
                            <Grid RowDefinitions="Auto, *"
                                  WidthRequest="200"
                                  RowSpacing="10"
                                  Padding="10">

                                <Label Text="{Binding WeekName}"
                                       Grid.Row="0" />

                                <telerik:RadListView x:Name="InnerListView"
                                                     ItemsSource="{Binding SubItems}"
                                                     BindingContextChanged="OnListViewBindingContextChanged"
                                                     Grid.Row="1">
                                    <telerik:RadListView.ItemTemplate>
                                        <DataTemplate x:DataType="local:KanbanSubItem">
                                            <telerik:ListViewTemplateCell>
                                                <VerticalStackLayout Padding="10"
                                                                     Spacing="5">
                                                    <Label Text="{Binding Title}"
                                                           FontAttributes="Bold" />
                                                    <Label Text="{Binding Deadline, StringFormat='{0:g}'}" />
                                                </VerticalStackLayout>
                                            </telerik:ListViewTemplateCell>
                                        </DataTemplate>
                                    </telerik:RadListView.ItemTemplate>
                                    <telerik:RadListView.LayoutDefinition>
                                        <telerik:ListViewLinearLayout VerticalItemSpacing="5"
                                                                      Orientation="Vertical" />
                                    </telerik:RadListView.LayoutDefinition>
                                </telerik:RadListView>
                            </Grid>
                        </telerik:ListViewTemplateCell>
                    </DataTemplate>
                </telerik:RadListView.ItemTemplate>
                <telerik:RadListView.LayoutDefinition>
                    <telerik:ListViewLinearLayout HorizontalItemSpacing="20"
                                                  Orientation="Horizontal" />
                </telerik:RadListView.LayoutDefinition>
            </telerik:RadListView>

            <Button Text="Scroll Week 3 to SubItem #25"
                    Clicked="Button_OnClicked"
                    HorizontalOptions="End"
                    VerticalOptions="Center"
                    Margin="10" />

        </Grid>
    </ContentPage>
    ```

> Notice that you're subscribing to the inner ListView's `BindingContextChanged` event. This is used to set the `KanbanItem`'s `ListViewHost` property, which is what enables programmatical scrolling of the inner list. In a real-world project, you will want to set the with a `WeakReference` to avoid memory leaks, or a better approach is to wrap the `DataTemplate` contents into a custom control where you have more control over the lifecycle.

5. Finally, in the view's code behind, you'll: 
   1. Set the view's `BindingContext` to a new instance of `MainViewModel`.
   2. Define the `OnListViewBindingContextChanged` event handler to get a reference to the inner `RadListView`.
   3. Define the `Button_OnClicked` event handler to demonstrate programmatic scrolling of a subitem into view.

    ```C#
    using Telerik.Maui.Controls.Compatibility.DataControls;

    namespace HorizontalAndVerticalDemo;

    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
            BindingContext = new MainViewModel();
        }

        private void OnListViewBindingContextChanged(object sender, EventArgs e)
        {
            if (sender is RadListView { BindingContext: KanbanItem item } lv)
            {
                // Dynamically gets a reference to the view element for programmatic scrolling when the concrete UI is created. 
                // The BindingContextChanged event fires when the RadListView's UI virtualization mechanism recycles the container during initialization and any scrolling.
                item.ListViewHost = lv;
            }
        }

        private void Button_OnClicked(object sender, EventArgs e)
        {
            try
            {
                if (BindingContext is not MainViewModel mainViewModel) 
                    return;

                // To demonstrate programmatic scrolling of any column's inner list, we'll scroll the 3rd column's vertical list to item 25
                var week3 = mainViewModel.Items[2];
                var subItem25 = week3.SubItems[24];

                // Scroll!
                week3.ScrollToSubItem(subItem25);
            }
            catch (Exception exception)
            {
                Console.WriteLine(exception);
            }
        }
    }
    ```

## Screenshots

Here are three screenshots of the design at runtime.

1. At launch, we see the parent horizontal items (which appear as columns) and each's inner vertical items.
   ![launch](https://github.com/telerik/maui-docs/assets/3520532/b2fd2a8f-e54e-42f4-9200-78032b767f03)
2. Here are some callouts to help mentally visualize the layout.
   ![callouts](https://github.com/telerik/maui-docs/assets/3520532/c2661041-fb8f-4a70-8aa3-7cb3c87f0f72)
3. Finally, here's what happens after clicking the button that will scroll the 3rd horizontal item's inner list to the 25th item.
   ![post-click](https://github.com/telerik/maui-docs/assets/3520532/d31d240a-7225-4ef4-85a8-0f909d783284)
