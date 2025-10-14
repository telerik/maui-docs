---
title: Defining Styles for CollectionView in XAML and C#
description: Learn how to define styles for the CollectionView in UI for .NET MAUI using both XAML and C#. Control the background color in normal and selected states and adjust item spacing.
type: how-to
page_title: Styling CollectionView in XAML and C# for Background and Spacing
meta_title: Styling CollectionView in XAML and C# for Background and Spacing
slug: styling-radcollectionview-xaml-csharp-background-spacing
tags: collectionview, .net maui, radcollectionview, styles, xaml, csharp, itemstyle, itemlayout
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need to define styles for the [CollectionView](https://www.telerik.com/maui-ui/documentation/controls/collectionview/overview) in both XAML and C#. The styles should control the background color of list items in normal and selected states and manage the spacing between list items.

This knowledge base article also answers the following questions:
- How to set item background color and spacing in CollectionView?
- How to apply styles to CollectionView in XAML?
- How to define styles for CollectionView programmatically in C#?

## Solution

Here is an example how to define styles in XAML and C#.

### Styling in XAML

Define implicit styles in the `ContentPage.Resources` section. Use `VisualStateManager` to control the background color for normal and selected states, and set `ItemsLayout` for spacing.

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style x:Key="CityStyle" TargetType="telerik:RadCollectionViewItemView">
            <Setter Property="BorderColor" Value="#80CBC4" />
            <Setter Property="BorderThickness" Value="1" />
            <Setter Property="CornerRadius" Value="5" />
            <Setter Property="VisualStateManager.VisualStateGroups">
                <VisualStateGroupList>
                    <VisualStateGroup Name="CommonStates">
                        <VisualState Name="Normal" />
                        <VisualState Name="Selected">
                            <VisualState.Setters>
                                <Setter Property="BackgroundColor" Value="#C4E6E3" />
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateGroupList>
            </Setter>
        </Style>

        <Style TargetType="telerik:RadCollectionView">
            <Setter Property="ItemsLayout">
                <telerik:CollectionViewLinearLayout Orientation="Vertical" ItemSpacing="10" />
            </Setter>
            <Setter Property="ItemViewStyle" Value="{StaticResource CityStyle}" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>

<telerik:RadCollectionView ItemsSource="{Binding Locations}"
                           SelectionMode="Multiple"
                           DisplayMemberPath="City"/>
```

### Styling in C#

1. Apply the styles programmatically using the `Style` class and `VisualStateManager.VisualStateGroupsProperty`. Attach the styles to the `RadCollectionView` in the code-behind.

```csharp
private void Button_Clicked(object sender, EventArgs e)
{
    SetStyle();
}

public void SetStyle()
{
    this.collectionView.ItemsLayout = new CollectionViewLinearLayout()
    {
        Orientation = Telerik.Maui.Orientation.Vertical,
        ItemSpacing = 10
    };

    this.collectionView.ItemViewStyle = new Style(typeof(RadCollectionViewItemView))
    {
        Setters =
        {
            new Setter
            {
                Property = RadCollectionViewItemView.BorderColorProperty,
                Value = Color.FromHex("#80CBC4")
            },
            new Setter
            {
                Property = RadCollectionViewItemView.BorderThicknessProperty,
                Value = 1
            },
            new Setter
            {
                Property = RadCollectionViewItemView.CornerRadiusProperty,
                Value = 5
            },
            new Setter
            {
                Property = VisualStateManager.VisualStateGroupsProperty,
                Value = new VisualStateGroupList()
                {
                    new VisualStateGroup
                    {
                        Name = "CommonStates",
                        States =
                        {
                            new VisualState
                            {
                                Name = "Normal",
                            },
                            new VisualState
                            {
                                Name = "Selected",
                                Setters =
                                {
                                    new Setter
                                    {
                                        Property = RadCollectionViewItemView.BackgroundColorProperty,
                                        Value = Color.FromHex("#C4E6E3")
                                    },
                                }
                            }
                        }
                    }
                }
            },
        }
    };
}
```

2. Define the CollectionView in XAML.

```xaml
<Grid RowDefinitions="Auto, *" Padding="10">
    <Button Text="Set style through code" Clicked="Button_Clicked" />
    <telerik:RadCollectionView ItemsSource="{Binding Locations}"
                               Grid.Row="1"
                               x:Name="collectionView"
                               SelectionMode="Multiple"
                               DisplayMemberPath="City"/>
</Grid>
```

## See Also

- [VisualStateManager Overview](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/visual-states?view=net-maui-9.0)
