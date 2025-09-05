---
title: How to Display Only ShowMoreTemplate and Hide TokenTemplate in ComboBox for .NET MAUI
description: Learn how to customize the ComboBox control in .NET MAUI to display only the ShowMoreTemplate and hide the TokenTemplate.
type: how-to
page_title: Customize ComboBox in .NET MAUI to Display ShowMoreTemplate and Hide TokenTemplate
slug: display-showmoretemplate-hide-tokentemplate-combobox-net-maui
tags: [.net-maui, combobox, customization, showmoretemplate, tokentemplate]
res_type: kb
---

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

I want to customize the ComboBox control in .NET MAUI to display only the ShowMoreTemplate and hide the TokenTemplate.

## Solution

To achieve the desired scenario of hiding the tokens and only displaying the ShowMoreTemplate in the ComboBox control, you can follow these steps:

**1.** Create a custom control `MyComboBox` that inherits from the `RadComboBox`.

```C#
public class MyComboBox : RadComboBox
{

}
```

**2.** Add a label to display the selected items count and update the label's text inside the `MyComboBox.SelectionChanged` event.

```C#
public class MyComboBox : RadComboBox
{
    private ContentView selectionToken;
    private RadWrapLayout layout;
    private bool isInitialized;

    public MyComboBox()
    {
        this.Loaded += (_, _) => this.Initialize();
    }

    protected override void OnHandlerChanged()
    {
        base.OnHandlerChanged();
        this.Dispatcher.Dispatch(this.Initialize);
    }

    private void Initialize()
    {
        if (this.isInitialized)
        {
            return;
        }

        this.layout = FindDescendant<RadWrapLayout>(this);
        if (this.layout == null)
        {
            return;
        }

        this.SelectionChanged += this.MyComboBox_SelectionChanged;
        this.isInitialized = true;
    }

    private void MyComboBox_SelectionChanged(object sender, ComboBoxSelectionChangedEventArgs e)
    {
        if (this.layout == null)
        {
            return;
        }

        int count = SelectedItems.Count;
        if (count > 0)
        {
            if (this.selectionToken == null)
            {
                var label = new Label
                {
                    VerticalOptions = LayoutOptions.Center,
                    HorizontalOptions = LayoutOptions.Center
                };
                label.SetBinding(Label.TextProperty, new Binding("Count")
                {
                    Source = SelectedItems,
                    StringFormat = "{0} selected"
                });

                this.selectionToken = new ContentView { Content = label };
            }

            if (!this.layout.Contains(this.selectionToken))
            {
                this.layout.Insert(0, this.selectionToken);
            }
        }
        else if (this.layout.Contains(this.selectionToken))
        {
            this.layout.Remove(this.selectionToken);
        }
    }

    private static T FindDescendant<T>(Element parent) where T : Element
    {
        if (parent is T match) return match;

        if (parent is IElementController controller)
        {
            foreach (var child in controller.LogicalChildren)
            {
                var result = FindDescendant<T>(child);
                if (result != null)
                {
                    return result;
                }
            }
        }

        return null!;
    }
}
```

**4.** Override the default `TokenTemplate` to hide the tokens.

```xaml
<local:MyComboBox x:Name="comboBox"
                  ItemsSource="{Binding Items}"
                  SelectionMode="Multiple"
                  IsEditable="True"
                  DisplayMemberPath="Email"
                  AutomationId="comboSelectedItemMultiple"
                  WidthRequest="200">
    <local:MyComboBox.TokenTemplate>
        <DataTemplate>
            <!-- hide the token view -->
            <ContentView IsVisible="False">
            </ContentView>
        </DataTemplate>
    </local:MyComboBox.TokenTemplate>
    <local:MyComboBox.SelectedItemTemplate>
        <DataTemplate>
            <telerik:RadBorder>
                <VerticalStackLayout>
                    <Label Text="{Binding Email}"
                           FontSize="16"
                           FontAttributes="Bold"
                           Padding="18, 14"/>
                </VerticalStackLayout>
            </telerik:RadBorder>
        </DataTemplate>
    </local:MyComboBox.SelectedItemTemplate>
</local:MyComboBox>
```

You can use this custom control in your .NET MAUI application to achieve the desired behavior.
