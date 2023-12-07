---
title: How to Display a Global Popup
description: This article explains how to create a global popup control in Popup for MAUI that can be displayed on any screen without being specific to a particular page.
type: how-to
page_title: How to Display a Global Popup Irrespective of Screen | Popup for MAUI 
slug: display-popup-irrespective-screen
tags: popup, maui, global, display, page, dotnet, global popup
res_type: kb
---
## Environment

| Property | Value |
| --- | --- |
| Product | Popup for MAUI |
| Version | 6.5.0 |

## Description

To create a global popup control in Popup for MAUI that can be displayed on any screen without being specific to a particular page, follow these steps:

1. Define a single RadPopup on the root ContentPage and expose a public property on the view's class that will let you interact with the popup.
2. Toggle the `IsOpen` property of the `RadPopup` control to show or hide the popup.

## Solution

Here's an example of how to create a global popup control in MAUI:

**1.** Lets start with the `Content` property. The `Content` property of the RadPopup control can be anything of type View. If you want to use the entire `ContentPage` as the placement target, you can define the `RadPopup` on the root `ContentPage` and expose a public property to interact with the popup globally. 

If you're using Shell, there's an `AppShell` class that is the host of all the app's ContentPages, so you can define a single `Popup` instance there:

```xaml
<Shell ...>
    <telerik:RadPopup.Popup>
        <telerik:RadPopup x:Name="MyPopup" Placement="Center">
            <contentViews:PopupContentView />
        </telerik:RadPopup>
    </telerik:RadPopup.Popup>
</Shell>
```

In the `AppShell` class, define a public property to access the `RadPopup`:

```csharp
public partial class AppShell : Shell
{
    public AppShell()
    {
        InitializeComponent();
    }

    public RadPopup GlobalPopup
    {
        get => this.MyPopup;
        set => this.MyPopup = value;
    }
}
```

**2.** To open the popup from a specific page, use the global property by toggling the `RadPopup.IsOpen` property:

```csharp
private void ShowPopup()
{
    (App.Current.MainPage as AppShell).GlobalPopup.IsOpen = true;
}
```

If you need to change the content of the popup dynamically, you can either replace the entire `Content` property or modify a custom `ContentView` within the popup. Here's an example:

```csharp
private void ShowPopup()
{
    var globalPopup = (App.Current.MainPage as AppShell).GlobalPopup;

    // Option 1 - Change the Content property
    globalPopup.Content = new View();

    // Option 2 - Modify a custom ContentView
    ((PopupContentView)globalPopup.Content).TitleLabel.Text = "New Title";
    ((PopupContentView)globalPopup.Content).DescriptionLabel.Text = "New Description";

    globalPopup.IsOpen = true;
}
```

Note: If you need to interact with the global popup from a view model using MVVM, you can use .NET MAUI's Dependency Injection services. Refer to the [CustomMauiExamples repository](https://github.com/xamarin/CustomMauiExamples/tree/main/PopupServiceDemo) for a sample implementation.

That's it! You have now created a global popup control in Popup for MAUI that can be displayed on any screen.
