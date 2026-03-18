---
title: Getting Selected Items in AutoComplete for .NET MAUI
description: Learn how to get selected items from AutoComplete in a .NET MAUI application using a ViewModel.
type: how-to
page_title: How to Retrieve Selected Items in .NET MAUI AutoComplete
meta_title: Retrieve Selected Items in .NET MAUI AutoComplete
slug: retrieve-selected-items-maui-autocomplete
tags: autocomplete, maui, tokens, observablecollection, viewmodel
res_type: kb
---

## Environment


| Version | Product | Author | 
| --- | --- | ---- | 
| 13.1.0 | Telerik UI for .NET MAUI AutoComplete | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need to get the selected items from AutoComplete for .NET MAUI in a ViewModel. Since the tokens collection is read-only, I can’t use two-way binding directly.

This knowledge base article also answers the following questions:
- How to bind selected tokens from AutoComplete to a ViewModel.
- How to manage selected tokens in .NET MAUI AutoComplete.
- How to implement logic for selected items in AutoComplete for .NET MAUI.

## Solution

To retrieve selected items in AutoComplete for .NET MAUI, bind the `Tokens` property using `Mode=OneWayToSource`. Use an observable collection in the ViewModel to track the selected tokens. Below is the implementation:

1. AutoComplete definition in XAML:

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

2. `ViewModel` Implementation

Define a `SelectedTokens` property that listens for changes in the collection and handles logic accordingly:

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

    private void SelectedItems_CollectionChanged(object sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
    {
        if (e.Action == NotifyCollectionChangedAction.Add)
        {
            // Add custom logic for new items
        }
        else if (e.Action == NotifyCollectionChangedAction.Remove)
        {
            // Add custom logic for removed items
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
- [Tokens in AutoComplete](https://www.telerik.com/maui-ui/documentation/controls/autocomplete/tokens-support)
