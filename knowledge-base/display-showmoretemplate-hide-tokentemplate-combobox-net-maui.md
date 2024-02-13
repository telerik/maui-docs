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
| 6.7.0 | Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

I want to customize the ComboBox control in .NET MAUI to display only the ShowMoreTemplate and hide the TokenTemplate.

## Solution

To achieve the desired scenario of hiding the tokens and only displaying the ShowMoreTemplate in the ComboBox control, you can follow these steps:

**1.** Create a custom control. 
**2.** Add a label to display the selected items count. 
**3.** Update the label's text inside the SelectionChanged event.

```C#
public class MyComboBox : RadComboBox
{
    private ContentView selectionToken;
    private RadWrapLayout layout;
    public MyComboBox()
    {
        this.layout = this.Content as RadWrapLayout;
        this.SelectionChanged += MyComboBox_SelectionChanged;
    }

    private void MyComboBox_SelectionChanged(object? sender, ComboBoxSelectionChangedEventArgs e)
    {
        if (this.SelectedItems.Count > 0)
        {
            if (this.layout.Contains(this.selectionToken))
            {
                return;
            }

            if (this.selectionToken == null)
            {
                this.selectionToken = new ContentView();
                var label = new Label(); //create a new label for every newly added token
                label.SetBinding(Label.TextProperty, new Binding()
                {
                    Source = this.SelectedItems,
                    Path = "Count"
                });
                this.selectionToken.Content = label; //set label text to selected items' count
            }

            this.layout.Insert(0, this.selectionToken);
        }
        else
        {
            if (layout.Contains(this.selectionToken))
            {
                layout.Remove(this.selectionToken);
            }
        }
    }
}
```

**4.** Override the default TokenTemplate to hide the tokens.

```xaml
 <local:MyComboBox 
    x:Name="comboBox"
    ItemsSource="{Binding Items}"
    SelectionMode="Multiple"
    IsEditable="True"
    DisplayMemberPath="Name"
    SelectedItems="{Binding SelectedItems}"
    AutomationId="comboSelectedItemMultiple"
    WidthRequest="200">
                <local:MyComboBox.TokenTemplate>
        <DataTemplate>
            <!-- hide the token view -->
            <ContentView IsVisible="False">
            </ContentView>
        </DataTemplate>
    </local:MyComboBox.TokenTemplate>
</local:MyComboBox>
```

You can use this custom control in your .NET MAUI application to achieve the desired behavior.
