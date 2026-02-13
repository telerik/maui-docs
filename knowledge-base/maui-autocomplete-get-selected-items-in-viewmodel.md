---
title: Retrieving Selected Items / Tokens in ViewModel for MAUI RadAutoComplete Control
description: Learn how to get tokens in the ViewModel for the MAUI RadAutoComplete control.
type: how-to
meta_title: How to Bind Tokens Collection in MAUI RadAutoComplete Control
slug: maui-autocomplete-get-selected-items-in-viewmodel
tags: autocomplete, ui-for-maui, tokens, viewmodel, xaml, collectionchanged
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 13.0.0 | Telerik UI for .NET MAUI AutoComplete | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to know how to retrieve selected items in the ViewModel for the MAUI AutoComplete control. The tokens collection is read-only, so it does not support two-way binding. 

This knowledge base article also answers the following questions:
- How can I bind selected items in MAUI AutoComplete control?
- How to use tokens with MAUI AutoComplete?
- How to track changes in selected items for MAUI AutoComplete?

## Solution

To retrieve selected items in the ViewModel, bind the `Tokens` property of the [AutoComplete](https://www.telerik.com/maui-ui/documentation/controls/autocomplete/overview) control using `Mode=OneWayToSource`. Then, handle changes in the selection within the ViewModel.

**1.** Define the `RadAutoComplete` control with the `Tokens` property bound to the `SelectedTokens` property in the ViewModel.

```xaml
<VerticalStackLayout>
    <telerik:RadAutoComplete x:Name="autoCompleteView"
                              ItemsSource="{Binding Source}"
                              TextSearchPath="Name" 
                              Tokens="{Binding SelectedTokens, Mode=OneWayToSource}"
                              DisplayMode="Tokens"/>
    <Label Text="{Binding SelectedTokens.Count}" />
</VerticalStackLayout>
```

**2.** Implement the `ViewModel` with an observable collection for `SelectedTokens`. Use the `CollectionChanged` event to track changes in the selected items.

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }
}

public class ViewModel : NotifyPropertyChangedBase
{
    private ObservableCollection<object> selection;

    public ViewModel()
    {
        this.Source = new ObservableCollection<Customer>()
        {
            new Customer("Freda Curtis", ""),
            new Customer("Jeffery Francis", ""),
            new Customer("Eva Lawson", ""),
            new Customer("Emmett Santos", ""),
            new Customer("Theresa Bryan", ""),
            new Customer("Jenny Fuller", ""),
            new Customer("Terrell Norris", ""),
        };
    }

    public ObservableCollection<Customer> Source { get; set; }

    public ObservableCollection<object> SelectedTokens
    {
        get => this.selection;
        set
        {
            if (this.selection != value)
            {
                if (this.selection != null)
                {
                    this.selection.CollectionChanged -= SelectedItems_CollectionChanged;
                }

                this.selection = value;
                Device.StartTimer(TimeSpan.FromMicroseconds(300), () =>
                {
                    this.selection.Add(this.Source[0]);
                    return false;
                });

                this.OnPropertyChanged();

                if (this.selection != null)
                {
                    this.selection.CollectionChanged += SelectedItems_CollectionChanged;
                }
            }
        }
    }

    private void SelectedItems_CollectionChanged(object? sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
    {
        if (e.Action == NotifyCollectionChangedAction.Add)
        {
            // Add logic for added items here
        }
        else if (e.Action == NotifyCollectionChangedAction.Remove)
        {
            // Add logic for removed items here
        }
    }
}

public class Customer
{
    public Customer(string name, string email)
    {
        this.Name = name;
        this.Email = email;
    }
    public string Name { get; set; }
    public string Email { get; set; }
}
```

## See Also

- [AutoComplete Overview](https://www.telerik.com/maui-ui/documentation/controls/autocomplete/overview)
- [Tokens Documentation](https://www.telerik.com/maui-ui/documentation/controls/autocomplete/tokens-support)
