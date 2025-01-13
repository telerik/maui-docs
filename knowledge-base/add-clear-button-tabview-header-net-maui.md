---
title: Adding a Clear Button in TabView Header to Remove Tabs in .NET MAUI
description: Learn how to modify the TabView HeaderItemTemplate to add a clear button that removes tabs in a .NET MAUI application.
type: how-to
page_title: How to Add a Remove Tab Button in .NET MAUI TabView Header
slug: add-clear-button-tabview-header-net-maui
tags: tabview, .net maui, headeritemtemplate, clear button, remove tab
res_type: kb
ticketid: 1670259
---

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>TabView for .NET MAUI</td>
</tr>
<tr>
<td>Version</td>
<td>7.1.0</td>
</tr>
</tbody>
</table>

## Description

I want to add a clear button in the header of a tab. After clicking this button, the corresponding tab must be removed from the TabView.

This KB article also answers the following questions:
- How can I remove a tab from TabView in .NET MAUI using a button?
- Is it possible to modify the TabView header to include additional controls like a clear button?
- Can I dynamically remove tabs from the TabView component in a .NET MAUI app?

## Solution

To add a clear button inside the tab header of the [TabView](https://docs.telerik.com/devtools/maui/controls/tabview) for .NET MAUI, which allows the removal of the tab, modify the `HeaderItemTemplate`. 

Below is an example demonstrating how to add a clear button to the tab header and handle its click event to remove the tab:

1. Define the `HeaderItemTemplate` for the TabView in your XAML:

```XAML
<telerik:RadTabView x:Name="tabView" AutomationId="tabView">
    <telerik:RadTabView.HeaderItemTemplate>
        <ControlTemplate>
            <telerik:RadBorder BackgroundColor="{TemplateBinding BackgroundColor}"
                                BorderColor="{TemplateBinding BorderColor}"
                                BorderThickness="{TemplateBinding BorderThickness}"
                                CornerRadius="{TemplateBinding CornerRadius}"
                                Padding="{TemplateBinding ContentPadding}">
                <Grid BindingContext="{TemplateBinding}">
                    <ContentPresenter />
                    <Button Text="{x:Static telerik:TelerikFont.IconReset}"
                            Style="{StaticResource HeaderButtonStyle}"
                            HorizontalOptions="End"
                            Clicked="OnRemoveTabClicked" />
                </Grid>
            </telerik:RadBorder>
        </ControlTemplate>
    </telerik:RadTabView.HeaderItemTemplate>
    <telerik:TabViewItem HeaderText="Home">
        <Label Margin="10" Text="This is the content of the Home tab" />
    </telerik:TabViewItem>
    <telerik:TabViewItem HeaderText="Folder">
        <Label Margin="10" Text="This is the content of the Folder tab" />
    </telerik:TabViewItem>
    <telerik:TabViewItem HeaderText="View">
        <Label Margin="10" Text="This is the content of the View tab" />
    </telerik:TabViewItem>
</telerik:RadTabView>
```

2. Add a sample Style that targets the Button to your page's resources:

```XAML
<Style x:Key="HeaderButtonStyle" TargetType="Button">
    <Setter Property="FontFamily" Value="{x:Static telerik:TelerikFont.Name}"/>
    <Setter Property="TextColor" Value="Gray"/>
    <Setter Property="FontAutoScalingEnabled" Value="True"/>
    <Setter Property="WidthRequest" Value="20"/>
    <Setter Property="HeightRequest" Value="20"/>
    <Setter Property="BackgroundColor" Value="Transparent"/>
    <Setter Property="BorderWidth" Value="0"/>
</Style>
```

3. Implement the `OnRemoveTabClicked` event handler in the code-behind. This method will remove the tab associated with the clicked clear button:

```C#
private void OnRemoveTabClicked(object sender, EventArgs e)
{
    if (sender is Button { BindingContext: TabViewHeaderItem headerItem })
    {
        var tab = tabView.Items.First(i => i.HeaderText == headerItem.Text);
        if (tab != null)
        {
            tabView.Items.Remove(tab);
        }
            
    }
}
```

In this example, the `BindingContext` of the button is used to get the `TabViewItem` that the button belongs to as in the `HeaderItemTemplate` the `BindingContext` of the main Grid element is bound through a `TemplateBinding`. Then, the `TabViewItem` is removed from the `Items` collection of the TabView, effectively removing the tab from the UI.

## See Also

- [TabView Overview](https://docs.telerik.com/devtools/maui/controls/tabview)
- [Feedback Portal Item - TabView: Provide options to rearrange, open, close tabs - desktop-like experience](https://feedback.telerik.com/maui/1610635-tabview-provide-options-to-rearrange-open-close-tabs-desktop-like-experience)
