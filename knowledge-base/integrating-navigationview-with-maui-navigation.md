---
title: Integrating NavigationView with MAUI Navigation
description: Learn how to integrate Telerik UI for .NET MAUI NavigationView with MAUI's navigation system.
type: how-to
page_title: How to Use NavigationView with MAUI's Navigation System
slug: integrating-navigationview-with-maui-navigation
tags: navigationview, .net maui, navigation, ui for .net maui
res_type: kb
---

## Environment

| Versions | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI NavigationView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

Understanding how Telerik UI for .NET MAUI [NavigationView](https://docs.telerik.com/devtools/maui/controls/navigationview/overview) integrates with the .NET MAUI Navigation system is crucial for developing seamless navigation within your application.

This knowledge base article also answers the following questions:

- How do I navigate between pages using NavigationView in a .NET MAUI application?
- Can NavigationView work with MAUI NavigationPage for navigating through pages?
- How to handle selection changes in NavigationView for page navigation?

## Solution

To integrate Telerik UI for .NET MAUI NavigationView with MAUI navigation, first consider the difference between the two: Telerik MAUI `RadNavigationView` is a control for displaying navigation items (views, control, etc.) and does not inherently manage page navigation. In contrast, MAUI `NavigationPage` manages a stack of pages, facilitating navigation and user experience.

Then, once you know the difference between them, you can implement the [navigation logic](#navigationview-implementation).

### NavigationView Implementation

Use the `SelectionChanged` event of the `NavigationView` to implement custom navigation logic. When a navigation item is selected, navigate to the corresponding page using the `Navigation.PushAsync` method.

**1.** Define the `RadNavigationView` in XAML with the navigation items:

```xaml
<telerik:RadNavigationView x:Name="navigationView" SelectionChanged="navigationView_SelectionChanged"
                       HeaderText="Navigation Header">
    <telerik:RadNavigationView.Items>
        <telerik:NavigationViewItem Text="Search"
                                Position="Header"
                                IsSelectable="False">
            <telerik:NavigationViewItem.ImageSource>
                <FontImageSource Glyph="{x:Static telerik:TelerikFont.IconSearch}"
                             FontFamily="{x:Static telerik:TelerikFont.Name}"
                             Size="16" />
            </telerik:NavigationViewItem.ImageSource>
        </telerik:NavigationViewItem>
        <telerik:NavigationViewItem Text="Item 1" />
        <telerik:NavigationViewItem Text="Item 2" />
        <telerik:NavigationViewItem Text="Settings"
                                Position="Footer">
            <telerik:NavigationViewItem.ImageSource>
                <FontImageSource Glyph="{x:Static telerik:TelerikFont.IconMore}"
                             FontFamily="{x:Static telerik:TelerikFont.Name}"
                             Size="16" />
            </telerik:NavigationViewItem.ImageSource>
        </telerik:NavigationViewItem>
    </telerik:RadNavigationView.Items>

    <telerik:RadNavigationView.Content>
        <Grid BackgroundColor="LightBlue">
            <Label Text="Content area where you can add views but not pages"/>
        </Grid>
    </telerik:RadNavigationView.Content>
</telerik:RadNavigationView>
```

**2.** Handle the `SelectionChanged` event to navigate to different pages based on the selected item:

```csharp
private void navigationView_SelectionChanged(object sender, EventArgs e)
{
    var control = sender as RadNavigationView;
    var selItem = control.SelectedItem as NavigationViewItem;
    var selectedItemText = selItem == null ? "null" : selItem.Text;

    if(selectedItemText == "Item 1") 
    {
        Navigation.PushAsync(new NewPage1());
    }
    else if(selectedItemText == "Item 2")
    {
        Navigation.PushAsync(new NewPage2());
    }
}
```

### Using .NET MAUI NavigationPage

For managing a stack of pages and enhancing user experience, utilize the MAUI `NavigationPage`. Review the official [NavigationPage documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/pages/navigationpage?view=net-maui-9.0) for detailed information.

### Using .NET MAUI Shell Navigation

If your application requires shell-like navigation with hosting pages, consider using the .NET MAUI Shell navigation structure. For more details, refer to the official documentation on [Shell navigation](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/shell/navigation?view=net-maui-8.0) and [Shell pages](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/shell/pages?view=net-maui-8.0).

## See Also

- [Telerik UI for .NET MAUI NavigationView Documentation](https://docs.telerik.com/devtools/maui/controls/navigationview/overview)
- [MAUI NavigationPage Documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/pages/navigationpage?view=net-maui-9.0)
- [.NET MAUI Shell Navigation Documentation](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/shell/navigation?view=net-maui-8.0)
