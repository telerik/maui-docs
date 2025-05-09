---
title: Adding Line Breaks to Header Text and Fitting Tabs to Screen in TabView for .NET MAUI
description: Learn how to add line breaks to header text and adjust tab widths to fit all tabs within the screen in TabView for .NET MAUI.
type: how-to
page_title: Adjusting Header Text and Tab Size in TabView for .NET MAUI
slug: tabview-line-break-header-tabs-fit-screen-dotnet-maui
tags: tabview, .net-maui, headertext, linebreak, fit-screen
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI TabView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to enable line breaks for the header text in the [TabView](https://docs.telerik.com/devtools/maui/controls/tabview/overview) component when the text is lengthy. Additionally, I need all tabs to fit within a single screen when there are multiple tabs.

This knowledge base article also answers the following questions:
- How to make header text wrap in TabView for .NET MAUI?
- How to fit all tabs within the screen in TabView for .NET MAUI?
- How to customize tab headers in TabView for .NET MAUI?

## Solution

To achieve line breaks in the header text and ensure all tabs fit within the screen, follow these steps:

### Step 1: Define a Custom Header Template

Create a `ControlTemplate` that enables line breaks in the header text. Use `LineBreakMode="WordWrap"` in the `Label` element to allow text wrapping.

```xml
<VisualElement.Resources>
    <ControlTemplate x:Key="TabViewHeaderTemplate">
        <Grid local:TabViewUtils.EqualHeaderItemWidth="True" RowDefinitions="Auto, Auto">
            <Image Source="{TemplateBinding ImageSource}" Aspect="Center" />
            <Label Text="{TemplateBinding Text}" Grid.Row="1" LineBreakMode="WordWrap" HorizontalTextAlignment="Center" />
        </Grid>
    </ControlTemplate>
</VisualElement.Resources>
```

### Step 2: Use the Custom Header Template in RadTabView

Apply the custom header template to the TabView and define your tabs.

```xml
<Grid>
    <telerik:RadTabView x:Name="tabView"
                        HeaderItemTemplate="{StaticResource TabViewHeaderTemplate}">
```

### Step 3: Add a Utility Class to Calculate Equal Widths for Tabs

Implement a custom utility class `TabViewUtils` to ensure equal widths for all tabs. The key property here is `EqualHeaderItemWidth`. This class dynamically calculates the width for each tab based on the total width of the TabView and the number of tabs.

Include the following utility class in your application code:

```csharp
public static class TabViewUtils
{
    public static readonly BindableProperty EqualHeaderItemWidthProperty = BindableProperty.Create("EqualHeaderItemWidth", typeof(bool), typeof(TabViewUtils), false, propertyChanged: OnEqualHeaderItemWidthChanged);

    private static readonly BindableProperty SizeHelperProperty = BindableProperty.Create("SizeHelper", typeof(SizeHelper), typeof(TabViewUtils), null);
    private static readonly BindableProperty TabViewProperty = BindableProperty.Create("TabView", typeof(RadTabView), typeof(TabViewUtils), null, propertyChanged: OnTabViewChanged);

    public static bool GetEqualHeaderItemWidth(BindableObject bindable) => (bool)bindable.GetValue(EqualHeaderItemWidthProperty);
    public static void SetEqualHeaderItemWidth(BindableObject bindable, bool value) => bindable.SetValue(EqualHeaderItemWidthProperty, value);

    private static void OnEqualHeaderItemWidthChanged(BindableObject bindable, object oldValue, object newValue)
    {
        VisualElement visualElement = (VisualElement)bindable;

        SizeHelper sizeHelper = (SizeHelper)visualElement.GetValue(SizeHelperProperty);
        if (sizeHelper != null)
        {
            sizeHelper.Disconnect();
            visualElement.SetValue(SizeHelperProperty, null);
            visualElement.RemoveBinding(TabViewUtils.TabViewProperty);
        }

        if ((bool)newValue)
        {
            sizeHelper = new SizeHelper(visualElement);
            visualElement.SetValue(SizeHelperProperty, sizeHelper);
            visualElement.SetBinding(TabViewUtils.TabViewProperty, new Binding { Path = Binding.SelfPath, Source = new RelativeBindingSource(RelativeBindingSourceMode.FindAncestor, typeof(RadTabView)) });
        }
    }

    private static void OnTabViewChanged(BindableObject bindable, object oldValue, object newValue)
    {
        SizeHelper sizeHelper = (SizeHelper)bindable.GetValue(SizeHelperProperty);
        if (sizeHelper != null)
        {
            sizeHelper.TabView = newValue as RadTabView;
        }
    }

    class SizeHelper
    {
        private VisualElement visualElement;
        private RadTabView tabView;
        private IList<TabViewItem> items;

        public SizeHelper(VisualElement visualElement)
        {
            this.visualElement = visualElement;
        }

        internal RadTabView TabView
        {
            set
            {
                if (this.tabView != value)
                {
                    RadTabView oldValue = this.tabView;
                    this.tabView = value;
                    this.OnTabViewChanged(oldValue);
                }
            }
        }

        private IList<TabViewItem> Items
        {
            set
            {
                if (this.items != value)
                {
                    IList<TabViewItem> oldValue = this.items;
                    this.items = value;
                    this.OnItemsChanged(oldValue);
                }
            }
        }

        internal void Disconnect()
        {
            if (this.visualElement != null)
            {
                this.visualElement = null;
            }

            this.TabView = null;
        }

        private void OnTabViewChanged(RadTabView oldValue)
        {
            if (oldValue != null)
            {
                oldValue.PropertyChanged -= this.TabView_PropertyChanged;
            }

            if (this.tabView != null)
            {
                this.tabView.PropertyChanged += this.TabView_PropertyChanged;
            }

            this.Items = this.tabView?.Items;
        }

        private void OnItemsChanged(IList<TabViewItem> oldValue)
        {
            INotifyCollectionChanged incc = oldValue as INotifyCollectionChanged;

            if (incc != null)
            {
                incc.CollectionChanged -= this.Items_CollectionChanged;
            }

            incc = this.items as INotifyCollectionChanged;

            if (incc != null)
            {
                incc.CollectionChanged += this.Items_CollectionChanged;
            }

            this.UpdateSize();
        }

        private void TabView_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs args)
        {
            if (args.PropertyName == nameof(this.tabView.Bounds) || args.PropertyName == nameof(this.tabView.Width))
            {
                this.UpdateSize();
            }
            else if (args.PropertyName == nameof(this.tabView.Items))
            {
                this.Items = this.tabView?.Items;
            }
        }

        private void Items_CollectionChanged(object sender, NotifyCollectionChangedEventArgs args)
        {
            this.UpdateSize();
        }

        private void UpdateSize()
        {
            if (this.visualElement == null || this.tabView == null || this.items == null || this.tabView.Bounds.Width == -1)
            {
                return;
            }

            int count = this.items.Count != 0 ? this.items.Count : 1;
            double newWidth = Math.Max((this.tabView.Bounds.Width / count) - 1, 10);
            this.visualElement.WidthRequest = newWidth;
        }
    }
}

public static class LocalVisualTreeHelper
{
    internal static T ParentOfType<T>(Element element)
        where T : Element
    {
        var parentElement = element.Parent;

        while (parentElement != null)
        {
            var targetElement = parentElement as T;

            if (targetElement != null)
            {
                return targetElement;
            }

            parentElement = parentElement.Parent;
        }

        return null;
    }
}
```

Now, set `local:TabViewUtils.EqualHeaderItemWidth="True"` in the header template to apply equal widths to all tabs.

## See Also

- [TabView Overview](https://docs.telerik.com/devtools/maui/controls/tabview/overview)
