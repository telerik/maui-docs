---
title: Templates
page_title: .NET MAUI TabView Documentation - Templates
description: Review the customization options of the Telerik TabView for .NET MAUI control.
slug: tabview-templates
tags: tabview, templates, customization
position: 14
---

# .NET MAUI TabView Templates

The TabView provides set of templates for its elements. If you want to change the TabView appearance you can use the provided templates: 

* `HeaderTemplate` (`ControlTemplate`)&mdash;Defines the template of the entire TabView Header. This includes the tabs in the Header (Header area + Header items).
* `HeaderItemTemplate` (`ControlTemplate`)&mdash;Defines the template of the individual header items.
* `ContentTemplate` (`ControlTemplate`)&mdash;Defined the template of the entire TabView Content.

![.NET MAUI TabView Visual Structure](images/visual-structure.png "Visual elements of TabView control")

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

> If you want to review the default TabView `HeaderTemplate`, `HeaderItemTemplate` and `ContentTemplate`, add the [TelerikTheming]({%slug themes-overview%}) to the project and go to `TelerikTheming/Styles/Platform/TabView.xaml` file.
> If you do not want to change the default templates you can customize the look of the TabView, TabView Header, TabView `HeaderItem` and TabView Content using the flexible styling API. For more details review the [TabView Styling article]({%slug tabview-styling%}).

## See Also

- [TabViewItem]({%slug tabview-item%})
- [Selection]({%slug tabview-selection%})
- [Styling]({%slug tabview-styling%})
