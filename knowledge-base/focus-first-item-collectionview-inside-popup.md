```markdown
---
title: Focusing the First Item in CollectionView Inside a Popup in UI for .NET MAUI
description: Learn how to focus the first item in a CollectionView placed inside a RadPopup when the popup opens in UI for .NET MAUI.
type: how-to
page_title: How to Focus First Item in RadCollectionView Inside Popup
meta_title: Focus First Item in CollectionView Inside Popup
slug: focus-first-item-collectionview-inside-popup
tags: collectionview, popup, ui-for-net-maui, focus-item, keyboard-navigation
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 15.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to focus the first item in the [CollectionView](https://www.telerik.com/maui-ui/documentation/controls/collectionview/overview) when it is placed inside a [Popup](https://www.telerik.com/maui-ui/documentation/controls/popup/overview). This should happen automatically when the popup opens, enabling keyboard navigation.

This knowledge base article also answers the following questions:
- How to programmatically set focus on a CollectionView item inside a Popup?
- How to enable keyboard navigation in CollectionView inside Popup?
- How to use reflection to manipulate the focus in CollectionView?

## Solution

To focus the first item in the CollectionView inside the Popup, use the following approach with reflection. This example includes the necessary XAML, data model, and logic to achieve the desired behavior.

### XAML Definition

```xml
<Grid RowDefinitions="Auto,*">
    <VerticalStackLayout>
        <telerik:RadTemplatedButton Content="Show more info" Clicked="ShowPopup">
            <telerik:RadPopup.Popup>
                <telerik:RadPopup x:Name="popup" OutsideBackgroundColor="#66000000">
                    <Grid ColumnDefinitions="180,1" RowDefinitions="Auto, 600" Background="LightBlue">
                        <Grid x:Name="NavGrid" Grid.Column="0" Grid.Row="1">
                            <telerik:RadCollectionView x:Name="collectionView" ItemsSource="{Binding Locations}" SelectionMode="Single">
                                <telerik:RadCollectionView.ItemTemplate>
                                    <DataTemplate>
                                        <Grid>
                                            <Label Text="{Binding City}" />
                                        </Grid>
                                    </DataTemplate>
                                </telerik:RadCollectionView.ItemTemplate>
                            </telerik:RadCollectionView>
                        </Grid>
                        <BoxView Grid.Column="1" Grid.Row="1"/>
                    </Grid>
                </telerik:RadPopup>
            </telerik:RadPopup.Popup>
        </telerik:RadTemplatedButton>
    </VerticalStackLayout>
</Grid>
```

### Data Model and `ViewModel`

```csharp
public class ViewModel : NotifyPropertyChangedBase
{
    public ViewModel()
    {
        this.Locations = new ObservableCollection<DataModel>
        {
            new DataModel { Continent = "Europe", Country = "Austria", City = "Graz", Id = 1 },
            new DataModel { Continent = "Europe", Country = "Austria", City = "Innsbruck", Id = 2 },
            new DataModel { Continent = "Europe", Country = "Austria", City = "Ratz", Id = 3 },
            new DataModel { Continent = "Europe", Country = "Austria", City = "Vienna", Id = 4 },
            new DataModel { Continent = "Europe", Country = "Belgium", City = "Antwerp", Id = 5 },
            new DataModel { Continent = "Europe", Country = "United Kingdom", City = "Manchester", Id = 27 },
            new DataModel { Continent = "North America", Country = "United States", City = "New York", Id = 28 },
        };
    }

    public ObservableCollection<DataModel> Locations { get; set; }
}

public class DataModel : NotifyPropertyChangedBase
{
    private string continent;
    private string country;
    private string city;
    private int id;

    public string Continent
    {
        get => this.continent;
        set => this.UpdateValue(ref this.continent, value);
    }

    public string Country
    {
        get => this.country;
        set => this.UpdateValue(ref this.country, value);
    }

    public string City
    {
        get => this.city;
        set => this.UpdateValue(ref this.city, value);
    }

    public int Id
    {
        get => this.id;
        set => this.UpdateValue(ref this.id, value);
    }
}
```

### Reflection Logic

Use reflection to access the internal content of the `RadCollectionView` and programmatically sets the focus. For Windows, the platform-specific API ensures proper focus management.

```csharp
public partial class MainPage : ContentPage
{
    ViewModel vm;

    public MainPage()
    {
        InitializeComponent();
        this.vm = new ViewModel();
        this.BindingContext = this.vm;
    }

    private void ShowPopup(object sender, EventArgs e)
    {
        popup.IsOpen = true;

        this.Dispatcher.Dispatch(() =>
        {
            var field = this.collectionView.GetType().GetField("content", BindingFlags.Instance | BindingFlags.NonPublic);
            var content = field?.GetValue(this.collectionView);

#if WINDOWS
            if (content is IView mauiView && mauiView.Handler?.PlatformView is Microsoft.UI.Xaml.UIElement nativeElement)
            {
                nativeElement.Focus(Microsoft.UI.Xaml.FocusState.Keyboard);
                return;
            }
#endif

            var focusMethod = content?.GetType().GetMethod("Focus", Type.EmptyTypes);
            focusMethod?.Invoke(content, null);
        });
    }
}
```

## See Also

- [CollectionView](https://www.telerik.com/maui-ui/documentation/controls/collectionview/overview)
- [Popup](https://www.telerik.com/maui-ui/documentation/controls/popup/overview)

```
