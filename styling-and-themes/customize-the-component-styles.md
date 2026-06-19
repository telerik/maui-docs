---
title: Customizing the Controls' Styles
page_title: Customizing the Controls' Styles
description: Learn how to customize Telerik UI for .NET MAUI control styles in XAML or dedicated resource dictionaries for reusable, consistent app theming.
slug: theme-component-styles-customization
tags: telerik,.net maui,theme,custom
position: 5
---

# Customizing the Controls' Styles

Use Telerik UI for .NET MAUI theme resources to customize control styles beyond color swatches. This article shows two approaches: a quick per-page customization and a reusable resource dictionary workflow for multi-app consistency.

## Choose the Right Customization Approach

Use the following guidance to decide which approach fits your scenario:

| Scenario | Recommended approach | Why |
|---|---|---|
| One-off visual tweak in a single view | Customize in control declaration | Fast to apply and validate during prototyping |
| Reusable branding across multiple views or apps | Customize in dedicated dictionary | Centralizes styles and reduces duplication |
| Team-managed design system | Customize in dedicated dictionary | Improves consistency and maintenance |

## Prerequisites

Before you customize component styles, ensure that:

1. Telerik theming is enabled in the app. For setup details, see [Enable Telerik theming in .NET MAUI]({%slug themes-overview%}#using-the-maui-theming).
1. The `\TelerikTheming\Styles` folder exists in your project output and contains control-specific resource dictionaries.
1. You already defined your base theme colors, if needed. For details, see [Customize Telerik theme colors]({%slug themes-customization %}).

>note
> Keep your custom style keys unique to avoid accidental overrides when merging multiple dictionaries.

## Customizing the Control in Its Declaration

Use this approach when you need a local style override in one XAML page, such as `MainPage.xaml`.

In the following example, the DataGrid applies custom alternate row and selection styles copied from `\TelerikTheming\Styles\DataGrid.xaml` and then adjusted locally:

```xaml
<telerik:RadDataGrid x:Name="grid"
                     ItemsSource="{Binding Clubs}">
    <telerik:RadDataGrid.BindingContext>
        <local:ViewModel />
    </telerik:RadDataGrid.BindingContext>

        <!--Adding custom styles for alternating rows. The source file is `\TelerikTheming\Styles\DataGrid.xaml`.-->
        <telerik:RadDataGrid.AlternateRowBackgroundStyle>
            <Style TargetType="telerik:DataGridAlternateRowBackgroundAppearance">
                <Setter Property="BackgroundColor" Value="#F2FAF9" />
            </Style>
        </telerik:RadDataGrid.AlternateRowBackgroundStyle>

        <!--Adding custom styles for the selected content. The source file is `\TelerikTheming\Styles\DataGrid.xaml`.-->
        <telerik:RadDataGrid.SelectionStyle>
            <Style TargetType="telerik:DataGridSelectionAppearance">
                <Setter Property="BackgroundColor" Value="{DynamicResource RadPrimaryColor}" />
                <Setter Property="BorderColor" Value="{DynamicResource RadBorderColor}" />
                <Setter Property="BorderThickness" Value="1" />
            </Style>
        </telerik:RadDataGrid.SelectionStyle>

    </telerik:RadDataGrid>
```

## Customizing the Control in a Dedicated Dictionary

The Telerik theme lets you customize and at the same time unify the styles of your applications. You can do this at scale by using the styles that come with the Telerik theme and placing them in a dedicated resource dictionary.

A common scenario is to apply your company's colors by [modifying the theme swatch]({%slug themes-customization %}) and then to additionally adjust the styles of a specific control by using your custom colors. This allows you to address specific design or accessibility requirements. As the colors and styles live in dedicated resource dictionaries, you can copy them to other applications, achieving consistent styles.

To customize the desired control-specific theme styles:

1. [Customize the theme colors]({%slug themes-customization %}).
1. Copy the theme resources that target the desired control and apply your changes.
1. Handle any style dependencies.

### Copy and Modify Theme Resources

To modify the Telerik theme styles of a certain control, use the available resource dictionaries in the `\TelerikTheming\Styles` folder as a starting point. These files are generated when you enable the Telerik theming and serve as a reference for your customizations.

The next steps illustrate how to customize the theme styles of the DataGrid control and assume that you've already [customized the colors]({%slug themes-customization %}) of the theme:

1. Go to the `Resources\Styles` folder and create a resource dictionary file, for example, `CustomGridStyles.xaml`.

1. Add the `telerik` namespace:

```xaml
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

1. Open `\TelerikTheming\Styles\DataGrid.xaml` and copy the templates and styles you want to modify.
1. Paste the copied definitions into `Resources\Styles\CustomGridStyles.xaml`.
1. Update the copied definitions with your design values.

The following example customizes drag and reorder visuals and applies them through a custom based-on style:

**5.** Apply the desired changes to the theme styles of the control in the `CustomGridStyles.xaml` file, for example:

```xaml
    <DataTemplate x:Key="DataGridColumnHeaderDragVisualTemplate">
        <!--Customize the 'BackgroundColor' and the 'CornerRadius'.-->
        <telerik:RadBorder BackgroundColor="{DynamicResource RadPrimarySubtleActiveColor}"
                           CornerRadius="4"
                           MinimumWidthRequest="{Binding ActualWidth}"
                           MinimumHeightRequest="30"
                           Padding="8, 4">
            <Label Text="{Binding HeaderText, FallbackValue='dragging...'}"
                   TextColor="{DynamicResource RadOnPrimaryColor}"
                   VerticalTextAlignment="Center" />
        </telerik:RadBorder>
    </DataTemplate>

    <DataTemplate x:Key="DataGridColumnReorderIndicatorTemplate">
        <!--Customize the 'BackgroundColor'.-->
        <telerik:RadBorder BackgroundColor="{DynamicResource RadPrimarySubtleActiveColor}"
                           WidthRequest="1"
                           HorizontalOptions="Start"
                           InputTransparent="True" />
    </DataTemplate>

    <Style x:Key="CustomRadDataGridStyle" TargetType="telerik:RadDataGrid" BasedOn="{StaticResource RadDataGridStyle}">
        <Setter Property="ColumnHeaderDragVisualTemplate" Value="{StaticResource DataGridColumnHeaderDragVisualTemplate}" />
        <Setter Property="ColumnReorderIndicatorTemplate" Value="{StaticResource DataGridColumnReorderIndicatorTemplate}" />
    </Style>
```

1. In `MainPage.xaml`, apply the custom style to the DataGrid declaration.

```xaml
<telerik:RadDataGrid x:Name="grid"
                     Style="{StaticResource CustomRadDataGridStyle}"
                     ItemsSource="{Binding Clubs}">
    <telerik:RadDataGrid.BindingContext>
        <local:ViewModel />
    </telerik:RadDataGrid.BindingContext>
</telerik:RadDataGrid>
```

1. In `App.xaml.cs`, merge the custom dictionary after the Telerik theme dictionary.

```C#
    public App()
    {
        InitializeComponent();

        TelerikThemeResources.AppTheme = TelerikTheme.TelerikPurple;

        //Merge the custom Grid styles resource dictionary.                    
        this.Resources.MergedDictionaries.Add(new CustomGridStyles());
    }

    protected override Window CreateWindow(IActivationState? activationState)
    {
        return new Window(new MainPage());
    }
```

>important
> Merge your custom dictionary after Telerik theme resources. If you merge it earlier, Telerik default styles can override your custom setters.

### Verify the Result

After you apply the custom dictionary, validate the behavior:

1. Run the app and open the page that hosts the DataGrid.
1. Confirm that the column header drag visual uses the custom background and corner radius.
1. Confirm that the column reorder indicator uses the custom color.
1. If you changed swatch colors, verify that dynamic resources resolve correctly in light and dark app themes.

### Troubleshoot Common Issues

If the styles are not applied, check the following:

1. The custom style uses `BasedOn="{StaticResource RadDataGridStyle}"` and the base style key exists.
1. `CustomGridStyles.xaml` is merged in `App.xaml.cs` after Telerik theme resources.
1. The DataGrid `Style` property points to `CustomRadDataGridStyle`.
1. Dynamic resource keys, such as `RadPrimarySubtleActiveColor`, are defined in the active theme dictionaries.

## See Also

* [Customizing the Telerik Theme Colors]({%slug themes-customization %})
* [Themes Overview]({%slug themes-overview%})
