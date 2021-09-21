---
title: Reorder Items
page_title: .NET MAUI ListView Documentation | Reorder Items
description: Check our &quot;Reorder Items&quot; documentation article for Telerik ListView for .NET MAUI.
position: 
slug: listview-features-reorder-items
---

# Reorder Items

The items reorder feature allows end-users reorder the list view data items. If the feature is enabled, when the user holds on an item, the reorder mode is triggered and the user can move and release the item at the desired position. This will perform reorder operation on the data.

Reorder functionality can be enabled by setting the **IsItemsReorderEnabled** property to `true`.

## Example

This example will demonstrate how to enable the items reorder functionality and style the list view items.

**1.** ListView definition:

```XAML
 <telerikDataControls:RadListView x:Name="listView"
                                         IsItemsReorderEnabled="True"
                                         SelectionMode="None">
    <telerikDataControls:RadListView.ItemTemplate>
        <DataTemplate>
            <telerikListView:ListViewTemplateCell>
                <telerikListView:ListViewTemplateCell.View>
                    <StackLayout Spacing="0">
                        <Label Margin="5,10,5,10"
                           FontSize="16"
                           Text="{Binding}"
                           TextColor="Black"
                           VerticalTextAlignment="Center" />
                        <BoxView Margin="0"
                             BackgroundColor="Gray"
                             HeightRequest="1" />
                    </StackLayout>
                </telerikListView:ListViewTemplateCell.View>
            </telerikListView:ListViewTemplateCell>
        </DataTemplate>
    </telerikDataControls:RadListView.ItemTemplate>
</telerikDataControls:RadListView>
```

**2.** Namespaces:

```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
```

**3.** ListViewItemsSource:

```C#
this.listView.ItemsSource = new ObservableCollection<string>()
{
  "Check weather for London",
  "Call Brian Ingram",
  "Check the childrens' documents",
  "Take care of the dog",
  "Airplane tickets reschedule",
  "Check the trains schedule",
  "Bills due: Alissa's ballet class",
  "Weekly organic basket"
};
```

Here is the result:

![](images/listview-gestures-reorder.png)

>You could also take advantage of the [Reorder Events]({% slug listview-features-events %}#groupreorder-events) for additional control over the reorder functionality of RadListView.

## See Also

- [ListView TextCell]({% slug listview-textcell %})
- [ListView TemplateCell]({% slug listview-templatecell %})
- [Layouts]({% slug listview-features-layouts %})
- [Cell Swipe]({% slug listview-features-cell-swipe %})
- [Pull to Refresh]({% slug listview-features-pull-to-refresh %})
