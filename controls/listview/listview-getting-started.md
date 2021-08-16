---
title: Getting Started
page_title: Getting Started with .NER MAUI ListView Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik ListView for .NET MAUI.
position: 1
slug: listview-getting-started
---

# Getting Started

#### Create the control definition in XAML

The snippet below shows a simple RadListView definition (_Do not use a `StackLayout` or `ScrollView` parent, see the **WARNING** note below_):

```XAML
<telerikDataControls:RadListView x:Name="listView" />
```
```C#
var listView = new RadListView();
```

In addition to this, you need to add the following namespace:

> **WARNING**: RadListView control provides UI virtualization, this feature requires the visual parent to provide vertical or horizontal space. To avoid breaking UI virtualization or gesture mechanisms, please follow these rules: 
>	* **Do not** place the RadListView control inside a `StackLayout`
>	* **Do not** place the RadListVew inside a `ScrollView`
>	* **Do not** set the RadListVew to a Grid `RowDefinition Height="Auto"`
>

## 4. Populating RadListView with data

First, lets create a simple data and view model classes:



Here is the setup of the ListView:


You have to add the following namespaces:

```XAML

```

To visualize RadListView -> Register the Telerik controls through `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the **Startup.cs** file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

 

public void Configure(IAppHostBuilder appBuilder)
{
    appBuilder        
        .UseTelerik()
        .UseMauiApp<App>();
        
}              
```

This is the result:

![RadListView](images/listview-gettingstarted.png)

## See Also

- [Cell Types]({% slug listview-cells%})
- [Selection]({% slug listview-features-selection%})
- [Grouping]({% slug listview-features-grouping%})
