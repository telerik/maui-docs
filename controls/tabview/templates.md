---
title: Templates
page_title: .NET MAUI TabView Documentation | Templates
description: Review the customization options of the Telerik TabView for .NET MAUI control.
slug: tabview-templates
tags: tabview, overview
position: 0
---

# Templates

The TabView provides set of templates for its elements. If you want to fully change the TabView appearance you can use the provided templates: 

* `HeaderTemplate`(`ControlTemplate`)&mdashDefines the template of the entire header area.
* `HeaderitemTemplate`(`ControlTemplate`)&mdashDefines the template of the individual header items.
* `ContentTemplate`(`ControlTemplate`)&mdashDefined the template of the entire content area. 

**Example with TabView templates**

```XAML
<telerik:RadTabView x:Name="tabView">
    <telerik:RadTabView.HeaderItemTemplate>
        <ControlTemplate>
            <!-- the custom HeaderItemTemplate implementation -->
        </ControlTemplate>
    </telerik:RadTabView.HeaderItemTemplate>
    <telerik:RadTabView.HeaderTemplate>
        <ControlTemplate>
            <!-- the custom HeaderTemplate implementation -->
        </ControlTemplate>
    </telerik:RadTabView.HeaderTemplate>
    <telerik:RadTabView.ContentTemplate>
        <ControlTemplate>
             <!-- the custom ContentTemplate implementation -->
        </ControlTemplate>
    </telerik:RadTabView.ContentTemplate>
</telerik:RadTabView>
```

And the namespace used:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

>note If you do not want to change the default templates you can customize the look of the TabView, TabView Header, TabView HeaderItem and TabView Content using the flexible styling API. For more details review the [TabView Styling article]().

## See Also

- [TabViewItem]({%slug %})
- [Selection]({%slug tabview-selection%})
- [Styling]({%slug %})
