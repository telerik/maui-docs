---
title: Integration
page_title: .NET MAUI BusyIndicator Documentation - ListView Integration
description: Check our &quot;Integration with ListView&quot; documentation article for Telerik BusyIndicator for .NET MAUI control.
position: 2
previous_url: /controls/busyindicator/busyindicator-integrate-with-listview
slug: busyindicator-integrate-with-listview
---

# .NET MAUI BusyIndicator Integration with ListView

The Telerik BusyIndicator for .NET MAUI is useful when you want to display a notification to the end users of the application while a long-running operation, such as loading data from a service, is currently in progress.

The example below demonstrates a sample integration of the BusyIndicator with the ListView control. The ListView loads its data asynchronously (this is simulated for the purpose of the example) and while the load operation is taking place, the `IsBusy` state of the BusyIndicator is enabled.

1. Create a sample `Book` class used for the `ItemsSource` of the ListView:

 <snippet id='busyindicator-withlistview-model' />

1. Add a `ViewModel` class, which provides the following:

  * A collection of `Book` objects that is used for binding the ListView.
  * A Boolean `IsLoading` property to control the Busy state of the BusyIndicator.
  * A `LoadData` command that starts the loading of the items.

 <snippet id='busyindicator-withlistview-csharp' />

1. Add the ListView and BusyIndicator controls to the view:

 ```XAML
<Grid>
    <Grid.RowDefinitions>
            <RowDefinition Height="40" />
            <RowDefinition Height="*" />
        </Grid.RowDefinitions>
        <Button Text="Load Data" Command="{Binding LoadDataCommand}" />
        <Grid  Grid.Row="1">
            <telerik:RadListView ItemsSource="{Binding Source}">
                <telerik:RadListView.ItemTemplate>
                    <DataTemplate>
                        <telerik:ListViewTextCell Text="{Binding Title}" Detail="{Binding Author}"/>
                    </DataTemplate>
                </telerik:RadListView.ItemTemplate>
                <telerik:RadListView.LayoutDefinition>
                    <telerik:ListViewLinearLayout ItemLength="80" VerticalItemSpacing="2" />
                </telerik:RadListView.LayoutDefinition>
            </telerik:RadListView>
            <telerik:RadBusyIndicator x:Name="BusyIndicator"                             
                                VerticalOptions="Center"
                                AnimationContentHeightRequest="100"
                                AnimationContentWidthRequest="100"
                                HeightRequest="100"
                                IsBusy="{Binding IsLoading}" />
    </Grid>
</Grid>
 ```

1. Set the `ViewModel` class as `BindingContext` of the page:

 <snippet id='busyindicator-withlistview-setvm' />


The image below shows the result.

![BusyIndicator with ListView](images/busyindicator-withlistview.png)

## See Also

- [BusyIndicator Animations]({% slug busyindicator-animations %})
