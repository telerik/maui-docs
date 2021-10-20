---
title: Integration
page_title: .NET MAUI BusyIndicator Documentation | ListView Integration
description: Check our &quot;Integration with ListView&quot; documentation article for Telerik BusyIndicator for .NET MAUI control.
position: 2
slug: busyindicator-integrate-with-listview
---

#  Integration with ListView

Telerik BusyIndicator for .NET MAUI is useful in scenarios whether you'd like to display a notification to the end users of the app while a long-running operation, such as loading data from a service, is currently in progress. 

The example below demonstrates a sample integration of RadBusyIndicator with RadListView control. The ListView loads its data asynchronously (this is simulated for the purpose of the example) and while the load operation is taking place, RadBusyIndicator's IsBusy state is enabled.

First, create a sample **Book** class used for the ItemsSource of the ListView:

<snippet id='busyindicator-withlistview-model' />
```C#
public class Book
{
    public string Title { get; set; }
    public string Author { get; set; }      
}
```

Then, add a ViewModel class, which provides the following:

* Collection of *Book* objects that is used for binding the ListView;
* Boolean *IsLoading* property to control the BusyIndicator's busy state;
* LoadData command that starts the loading of the items;

<snippet id='busyindicator-withlistview-csharp' />
```C#
public class ViewModel : NotifyPropertyChangedBase
{
    private bool _isLoading = false;     
    private ObservableCollection<Book> _source;
    private bool hasStartedLoadingData;

    public ViewModel()
    {
        this.LoadDataCommand = new Command(this.LoadDataAsync, this.CanLoadData);
    }

    public bool IsLoading
    {
        get { return this._isLoading; }
        set { this.UpdateValue(ref this._isLoading, value); }
    }
    public ObservableCollection<Book> Source
    {
        get { return this._source; }
        set { this.UpdateValue(ref this._source, value); }
    }

    public Command LoadDataCommand { get; set; }

    private bool CanLoadData()
    {
        return !this.hasStartedLoadingData;
    }

    public async void LoadDataAsync()
    {
        this.hasStartedLoadingData = true;
        this.LoadDataCommand.ChangeCanExecute();
        this.IsLoading = true;
        this.Source = await GetItemsAsync();
        this.IsLoading = false;
    }

    private Task<ObservableCollection<Book>> GetItemsAsync()
    {
        return Task.Run(async () =>
        {
            await Task.Delay(TimeSpan.FromSeconds(3));

            return new ObservableCollection<Book>
            {
                new Book{ Title = "The Fault in Our Stars ",  Author = "John Green"},
                new Book{ Title = "Divergent",  Author = "Veronica Roth"},
                new Book{ Title = "Gone Girl",  Author = "Gillian Flynn" },
                new Book{ Title = "Clockwork Angel",  Author = "Cassandra Clare"},
                new Book{ Title = "The Martian",  Author = "Andy Weir"},
                new Book{ Title = "Ready Player One",  Author = "Ernest Cline"},
                new Book{ Title = "The Lost Hero",  Author = "Rick Riordan"},
                new Book{ Title = "All the Light We Cannot See",  Author = "Anthony Doerr"},
                new Book{ Title = "Cinder",  Author = "Marissa Meyer"},
                new Book{ Title = "Me Before You",  Author = "Jojo Moyes"},
                new Book{ Title = "The Night Circus",  Author = "Erin Morgenstern"},
            };
        });
    }
}
```

Add the ListView and BusyIndicator controls to the view:

<snippet id='busyindicator-withlistview-xaml' />
```XAML
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="40" />
        <RowDefinition Height="*" />
    </Grid.RowDefinitions>
    <Button Text="Load Data" Command="{Binding LoadDataCommand}" />
    <Grid  Grid.Row="1">
        <telerikDataControls:RadListView ItemsSource="{Binding Source}">
            <telerikDataControls:RadListView.ItemTemplate>
                <DataTemplate>
                    <telerikListView:ListViewTextCell Text="{Binding Title}" Detail="{Binding Author}" />
                </DataTemplate>
            </telerikDataControls:RadListView.ItemTemplate>
            <telerikDataControls:RadListView.LayoutDefinition>
                <telerikListView:ListViewLinearLayout ItemLength="80" VerticalItemSpacing="2" />
            </telerikDataControls:RadListView.LayoutDefinition>
        </telerikDataControls:RadListView>
        <telerikPrimitives:RadBusyIndicator x:Name="BusyIndicator"                             
                            VerticalOptions="Center"
                            AnimationContentHeightRequest="100"
                            AnimationContentWidthRequest="100"
                            HeightRequest="100"
                            IsBusy="{Binding IsLoading}" />
    </Grid>
</Grid>
```

Lastly, set the ViewModel class as BindingContext of the page:

<snippet id='busyindicator-withlistview-setvm' />
```C#
this.BindingContext = new ViewModel();
```

The image below shows the result:

![BusyIndicator with ListView](images/busyindicator-withlistview.png)

## See Also

- [Animations]({% slug busyindicator-animations %})