---
title: Setting TextColor and SelectedTextColor for RadSegmentedControlItemView in UI for .NET MAUI
description: Learn how to apply TextColor and SelectedTextColor to a custom template in RadSegmentedControlItemView for UI for .NET MAUI.
type: how-to
page_title: Customize TextColor and SelectedTextColor in RadSegmentedControlItemView for UI for .NET MAUI
meta_title: Customize TextColor and SelectedTextColor in RadSegmentedControlItemView for UI for .NET MAUI
slug: customize-textcolor-selectedtextcolor-radsegmentedcontrolitemview-maui
tags: .net maui, segmentedcontrol, radsegmentedcontrolitemview, textcolor, selectedtextcolor
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 14.0.0 | Telerik UI for .NET MAUI SegmentedControl | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

When using a custom `ItemTemplate` in the [RadSegmentedControl]({%slug segmentedcontrol-overview%}) for UI for .NET MAUI, the `TextColor` and `SelectedTextColor` properties of the `RadSegmentedControlItemView` style do not automatically apply to the `Label` elements within the template. These properties only affect the default template. To ensure the colors apply to your custom `ItemTemplate`, you need to bind the `Label`'s `TextColor` to the `ActualTextColor` property of the `RadSegmentedControlItemView`.

This knowledge base article also answers the following questions:
- How do I customize text colors for selected and unselected items in RadSegmentedControl?
- Why is the TextColor property not affecting my custom template in RadSegmentedControl?
- How can I bind the Label's color to the RadSegmentedControlItemView color?

## Solution

To apply the `TextColor` and `SelectedTextColor` to a custom template, bind the `Label`'s `TextColor` to the `ActualTextColor` property of the `RadSegmentedControlItemView`. Follow these steps:

1. Define the styles for the `RadSegmentedControl` and its items.
2. Bind the `Label`'s `TextColor` in the custom `ItemTemplate` to the `ActualTextColor` property of the `RadSegmentedControlItemView`.

Here is the XAML definition:

```xaml
<ContentPage.Resources>
        <ResourceDictionary>
            <Style x:Key="SelectedSegmentStyle" TargetType="telerik:RadBorder">
                <Setter Property="BackgroundColor" Value="LightBlue" />
            </Style>

            <Style x:Key="SegmentedItemViewStyle" TargetType="telerik:RadSegmentedControlItemView">
                <Setter Property="CornerRadius" Value="4" />
                <Setter Property="TextColor" Value="Red"/>
                <Setter Property="SelectedTextColor" Value="Blue" />
                <Setter Property="FontSize" Value="12" />
                <Setter Property="Padding" Value="10,5"/>
                <Setter Property="HorizontalOptions" Value="Center"/>
                <Setter Property="VerticalOptions" Value="Center"/>
                <Setter Property="SizeMode" Value="Star"/>
            </Style>
        </ResourceDictionary>
</ContentPage.Resources>
<VerticalStackLayout>
        <telerik:RadSegmentedControl Grid.Row="1" ItemsSource="{Binding FileCategories}" 
                                     ItemViewStyle="{StaticResource SegmentedItemViewStyle}" 
                                     SelectionIndicatorStyle="{StaticResource SelectedSegmentStyle}" 
                                     SelectionMode="Single" DisplayMemberPath="Category"
                                     SelectedItem ="{Binding SelectedFileCategory, Mode=TwoWay}"
                                     HorizontalOptions="Fill">
            <telerik:RadSegmentedControl.ItemTemplate>
                <DataTemplate>
                    <HorizontalStackLayout Spacing="10" 
                                           VerticalOptions="Center">
                        <Label Text="{Binding Category}"
                               TextColor="{Binding Source={RelativeSource AncestorType={x:Type telerik:RadSegmentedControlItemView}}, Path=ActualTextColor}"
                                   VerticalTextAlignment="Center"
                                   FontSize="12"/>
                        <Label Text="{Binding Count}" 
                               FontSize="12" VerticalTextAlignment="Center"/>
                    </HorizontalStackLayout>
                </DataTemplate>
            </telerik:RadSegmentedControl.ItemTemplate>
        </telerik:RadSegmentedControl>
</VerticalStackLayout>
```


## See Also

- [SegmentedControl Overview](https://www.telerik.com/maui-ui/documentation/controls/segmentedcontrol/overview)
- [SegmentedControl Styling](https://www.telerik.com/maui-ui/documentation/controls/segmentedcontrol/styling)
