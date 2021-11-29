---
title: Load on Demand
page_title: .NET MAUI ListView Documentation | Load on Demand
description: Check our &quot;Load on Demand&quot; documentation article for Telerik ListView for .NET MAUI.
position: 8
slug: listview-features-load-on-demand
---

# Load on Demand

Loading a large data set on a mobile device has its challenges. One of the most popular approaches is using incremental data loading when the items need to be visualized. The ListView does this by using its load-on-demand functionality.

## Configuration

The following properties control the `LoadOnDemand` feature:

* `IsLoadOnDemandEnabled`(`bool`)&mdash;Used to enable the load on demand mechanism of the ListView.
* `IsLoadOnDemandActive` (`bool`)&mdash;Used to control the loading indicator that is rendered when the data is retrieved asynchronously. Set it to `True` when an async operation is running and items are loading. Set it to `False` when the items are loaded.
* `LoadOnDemandMode`&mdash;Used to set the loading mode. You can select between:
  * `Automatic`&mdash;The data is requested automatically when you scroll near the end of the ListView.
  * `Manual`&mdash;A button is rendered at the end of the ListView. The data is requested explicitly by pressing the button.

## Methods to Load Data on Demand

There are three ways to load the data on demand, regardless of whether you use the `Automatic` or `Manual` loading mode:

* [Create a ListViewLoadOnDemandCollection instance as a source and pass it to the ListView ItemsSource property](#using-loadondemandcollection).
* [Subscribe to the LoadOnDemand event and add the loaded data to the source](#using-loadondemand-event).
* [Use the LoadOnDemand UserCommand and add the loaded data to the source](#using-loadondemand-command).

>note All three approaches for loading items on demand in the ListView work with both the automatic and manual `LoadOnDemandMode`.

### Using LoadOnDemandCollection

To load items on demand, you can utilize the `ListViewLoadOnDemandCollection` and set it as an `ItemsSource` for the ListView. The `ListViewLoadOnDemandCollection` accepts an action in the constructor and this action is later executed by the ListView in a non-UI thread when new items are requested.

The example below demonstrates how to use the `LoadOnDemandCollection`:

1. Define a sample `ViewModel` class with the `Source` property of type `ListViewLoadOnDemandCollection`:

 ```C#
public class ViewModel
{
    public ListViewLoadOnDemandCollection Source { get; set; }
    private int lodTriggerCount;
    public ViewModel()
    {
        this.Source = new ListViewLoadOnDemandCollection((cancelationToken) =>
        {
            List<string> result = new List<string>();

            try
            {
                //simulates connection latency
                Task.Delay(4000, cancelationToken).Wait();

                this.lodTriggerCount++;
                foreach (string item in Enum.GetNames(typeof(DayOfWeek)))
                {
                    result.Add(string.Format("LOD: {0} - {1}", lodTriggerCount, item));
                }
                return result;
            }
            catch
            {
                //exception is thrown when the task is canceled. Returning null does not affect the ItemsSource.
                return null;
            }
        });

        for (int i = 0; i < 14; i++)
        {
            Source.Add(string.Format("Item {0}", i));
        }
    }
}
 ```

1. Define the ListView instance and bind its `ItemsSource` to the data in the `ViewModel`:

 ```XAML
 <telerikDataControls:RadListView x:Name="listView"
                                             IsLoadOnDemandEnabled="True"
                                             ItemsSource="{Binding Source}"
                                             LoadOnDemandMode="Automatic" >
    <telerikDataControls:RadListView.BindingContext>
        <local:ViewModel />
    </telerikDataControls:RadListView.BindingContext>
</telerikDataControls:RadListView>
 ```

1. Define the ListView namespace:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
 ```

### Using LoadOnDemand Event

Another way to handle loading more items is to use the `LoadOnDemand` event. This event is raised on a UI thread, so in the event handler you can add items right away or asynchronously:

* In case the data is available right away, add the items to the ListView `ItemsSource` in the `LoadOnDemand` event handler.
* If you require an async operation, set the `IsLoadOnDemandActive` property of the ListView to `True`. This notifies the ListView that it must display the loading indicator. Then an async call can be initiated to get the data. When the new items are ready, you must set the `IsLoadOnDemandActive` property to `False` again to notify the ListView that the load-on-demand operation is completed.

The example below demonstrates how to use the LoadOnDemand event:

1. Define the ListView:

 ```XAML
<telerikDataControls:RadListView x:Name="listView"
                                             IsLoadOnDemandEnabled="True"
                                             LoadOnDemand="ListView_LoadOnDemand"
                                             LoadOnDemandMode="Automatic" />
 ```

1. Define the ListView namespace:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikListView="clr-namespace:Telerik.XamarinForms.DataControls.ListView;assembly=Telerik.Maui.Controls.Compatibility"
 ```

1. Set the ListView `ItemsSource` in the page constructor:

 ```C#
this.source = new ObservableCollection<string>();
for (int i = 0; i < 14; i++)
{
    source.Add(string.Format("Item {0}", i));
}
this.listView.ItemsSource = this.source;
 ```

1. Add the following event handler:

 ```C#
private ObservableCollection<string> source;
private int lodCounter = 0;

private async void ListView_LoadOnDemand(object sender, EventArgs e)
{
    // If you need to get new data asynchronously, you must manually update the loading status.
    this.listView.IsLoadOnDemandActive = true;

    IEnumerable<string> newItems = await this.GetNewItems();
    foreach (string newItem in newItems)
    {
        this.source.Add(newItem);
    }

    this.listView.IsLoadOnDemandActive = false;
}

private async Task<IEnumerable<string>> GetNewItems()
{
    this.lodCounter++;
    await Task.Delay(4000);  // Mimic getting data from server asynchronously.
    return Enum.GetNames(typeof(DayOfWeek)).Select(day => string.Format("LOD: {0} - {1}", this.lodCounter, day));
}
 ```

### Using LoadOnDemand Command

This approach is similar to [using the LoadOnDemand event](#using-loadondemand-event), but in this case, the load-on-demand is handled in the `ViewModel` through the `LoadOnDemandUserCommand` exposed by the ListView. In the `Execute` method of the command, you can add items right away or asynchronously:

* If the data is available right away, add the items to the ListView `ItemsSource` in the `LoadOnDemand` command `Execute` method.
* If you require an async operation, set the `IsLoadOnDemandActive` property of the ListView to `True`. This notifies the ListView that it must display the loading indicator. Then an async call can be initiated to get the data. When the new items are ready, you must set the `IsLoadOnDemandActive` property to `False` again to notify the ListView that the load-on-demand operation is completed. You can control the behavior of `IsLoadOnDemandActive` through a binding to a boolean property in the `ViewModel` class.

The example below demonstrates how to use the `LoadOnDemand` command:

1. Create a `ViewModel` class with a `LoadItemsCommand` as well as the `IsLoadingMoreItems` bool property:

 ```C#
public class ViewModel : NotifyPropertyChangedBase
{
    private bool isLoadingMoreItems;
    private int lodCounter = 0;

    public ViewModel()
    {
        this.Source = new ObservableCollection<string>();
        for (int i = 0; i < 14; i++)
        {
            this.Source.Add(string.Format("Item {0}", i));
        }
        this.LoadItemsCommand = new Command(this.LoadItemsCommandExecute);
    }

    public ObservableCollection<string> Source { get; }
    public ICommand LoadItemsCommand { get; set; }

    public bool IsLoadingMoreItems
    {
        get { return this.isLoadingMoreItems; }
        set { this.UpdateValue(ref this.isLoadingMoreItems, value); }
    }

    private async void LoadItemsCommandExecute(object obj)
    {
        // If you need to get new data asynchronously, you must manually update the loading status.
        this.IsLoadingMoreItems = true;

        IEnumerable<string> newItems = await this.GetNewItems();
        foreach (string newItem in newItems)
        {
            this.Source.Add(newItem);
        }

        this.IsLoadingMoreItems = false;
    }

    private async Task<IEnumerable<string>> GetNewItems()
    {
        this.lodCounter++;
        await Task.Delay(4000);  // Mimic getting data from server asynchronously.
        return Enum.GetNames(typeof(DayOfWeek)).Select(day => string.Format("LOD: {0} - {1}", this.lodCounter, day));
    }
}
 ```

1. Define the `RadListView` instance in XAML with the `ListViewUserCommand` defined as well as the `IsLoadOnDemandActive` property bound to the boolean property in the `ViewModel`:

 ```XAML
<telerikDataControls:RadListView x:Name="listView"
                                             ItemsSource="{Binding Source}"
                                             IsLoadOnDemandEnabled="True"
                                             IsLoadOnDemandActive="{Binding IsLoadingMoreItems}"
                                             LoadOnDemandMode="Manual">
                <telerikDataControls:RadListView.BindingContext>
                    <local:ViewModel/>
                </telerikDataControls:RadListView.BindingContext>
                <telerikDataControls:RadListView.Commands>
                    <telerikListViewCommands:ListViewUserCommand Id="LoadOnDemand"
                                                             Command="{Binding LoadItemsCommand}" />
                </telerikDataControls:RadListView.Commands>
            </telerikDataControls:RadListView>
 ```

1. Define the following namespaces:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.XamarinForms.DataControls"
xmlns:telerikListViewCommands="clr-namespace:Telerik.XamarinForms.DataControls.ListView.Commands;assembly=Telerik.XamarinForms.DataControls"
 ```



## Advanced Options

You can also use the ListView options for performing advanced control over its load-on-demand feature.  

### Control the Number of Preloaded Items

This feature works in conjunction with the [LoadOnDemandMode.Automatic mode of the ListView]({%slug listview-features-load-on-demand%}#automatic-mode). You can control the minimum number of items loaded ahead through ListView `LoadOnDemandBufferItemsCount` property. By default, it is set to 10 items. When ListView requests an item in the buffer, it will trigger a new loading batch.

### Change the Appearance of the Manual Load Button

This feature works in conjunction with the [LoadOnDemandMode.Manual mode of the ListView]({%slug listview-features-load-on-demand%}#manual-loading-mode). You can control the content of the Load More Button through the `LoadOnDemandItemTemplate` property.

```XAML
telerikDataControls:RadListView.LoadOnDemandItemTemplate>
    <DataTemplate>
        <Grid BackgroundColor="Red">
            <Label FontSize="24"
               HorizontalOptions="Center"
               Text="Load more items"
               TextColor="Black" />
        </Grid>
    </DataTemplate>
</telerikDataControls:RadListView.LoadOnDemandItemTemplate>
```

### Change the Appearance of the Manual Loading Indicator

This feature works in conjunction with the [LoadOnDemandMode.Manual mode of the ListView]({%slug listview-features-load-on-demand%}#manual-loading-mode).

You can control the content of the Loading Indicator through the `LoadingOnDemandItemTemplate` property.

```XAML
<telerikDataControls:RadListView.LoadingOnDemandItemTemplate>
    <DataTemplate>
        <Grid BackgroundColor="Green">
            <Label FontSize="24"
               HorizontalOptions="Center"
               Text="Loading..."
               TextColor="White" />
        </Grid>
    </DataTemplate>
</telerikDataControls:RadListView.LoadingOnDemandItemTemplate>
```

## See Also

- [Events]({%slug listview-features-events%})
- [Selection]({%slug listview-features-selection%})
- [Reordering]({%slug listview-features-reorder-items%})
