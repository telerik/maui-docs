---
title: Customizing the Controls' Styles
page_title: Customizing the Controls' Styles
description: Learn how to customize Telerik UI for .NET MAUI control styles in XAML or dedicated resource dictionaries for reusable, consistent app theming.
slug: theme-component-styles-customization
tags: telerik,.net maui,theme,custom
position: 5
components: ["general"]
---

# Customizing the Controls' Styles

Use Telerik UI for .NET MAUI theme resources to customize control styles beyond color swatches. This article shows two approaches: a local page customization and a reusable resource dictionary workflow.

## Prerequisites

Before you customize component styles, ensure that:

1. Telerik theming is enabled in the app. For setup details, see [Enable Telerik theming in .NET MAUI]({%slug themes-overview%}#using-the-maui-theming).
2. The `\TelerikTheming\Styles` folder exists in your project output and contains the theme-specific control resource dictionaries.
3. You already defined your base theme colors, if needed. For details, see [Customize Telerik theme colors]({%slug themes-customization%}).

>note
> Keep your custom style keys unique to avoid accidental overrides when merging multiple dictionaries.

## Customizing the Control in Its Declaration

Use this approach when you need a local style override in one XAML page, such as `MainPage.xaml`.

In the following example, the DataGrid applies custom alternate row and selection styles copied from the selected theme folder, such as `\TelerikTheming\Styles\Telerik\DataGrid.xaml`, and then adjusted locally:

```XAML
<telerik:RadDataGrid x:Name="grid"
                     ItemsSource="{Binding Clubs}">
    <telerik:RadDataGrid.BindingContext>
        <local:ViewModel />
    </telerik:RadDataGrid.BindingContext>

    <!-- Add a custom style for alternating rows from the selected theme's DataGrid.xaml file. -->
    <telerik:RadDataGrid.AlternateRowBackgroundStyle>
        <Style TargetType="telerik:DataGridRowBackgroundAppearance">
            <Setter Property="BackgroundColor" Value="#F2FAF9" />
        </Style>
    </telerik:RadDataGrid.AlternateRowBackgroundStyle>

    <!-- Add a custom style for selected content from the selected theme's DataGrid.xaml file. -->
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

The Telerik theme lets you customize and unify styles across applications. Use the theme styles as a starting point, then place your changes in a dedicated resource dictionary.

A common scenario is to apply your company's colors by [modifying the theme swatch]({%slug themes-customization%}) and then adjust the styles of a specific control with your custom colors. This helps you address design or accessibility requirements. Because the colors and styles live in dedicated resource dictionaries, you can copy them to other applications for consistent styling.

### Copying and Modifying Theme Resources

To modify the Telerik theme styles of a control, use the resource dictionaries in the selected theme folder, such as `\TelerikTheming\Styles\Telerik`, as a starting point. These files are generated when you enable Telerik theming and serve as references for your customizations.

The next steps show how to customize DataGrid theme styles. They assume that you have already [customized the theme colors]({%slug themes-customization%}):

1. Go to the `Resources\Styles` folder and create a resource dictionary file, such as `CustomGridStyles.xaml`.

2. Add the `telerik` namespace:

   ```XAML
   xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
   ```

3. Open the `DataGrid.xaml` file in the selected theme folder and copy the templates and styles you want to modify.
4. Paste the copied definitions into `Resources\Styles\CustomGridStyles.xaml`.
5. Update the copied definitions with your design values.

### Applying the Custom Styles

The following steps customize the drag and reorder visuals and apply them through a custom based-on style:

1. Apply the desired changes to the theme styles of the control in the `CustomGridStyles.xaml` file, for example:

   ```XAML
   <DataTemplate x:Key="DataGridColumnHeaderDragVisualTemplate">
       <!-- Customize the BackgroundColor and CornerRadius. -->
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
       <!-- Customize the BackgroundColor. -->
       <telerik:RadBorder BackgroundColor="{DynamicResource RadPrimarySubtleActiveColor}"
                          WidthRequest="1"
                          HorizontalOptions="Start"
                          InputTransparent="True" />
   </DataTemplate>

   <Style x:Key="CustomRadDataGridStyle"
          TargetType="telerik:RadDataGrid"
          BasedOn="{StaticResource RadDataGridStyle}">
       <Setter Property="ColumnHeaderDragVisualTemplate"
               Value="{StaticResource DataGridColumnHeaderDragVisualTemplate}" />
       <Setter Property="ColumnReorderIndicatorTemplate"
               Value="{StaticResource DataGridColumnReorderIndicatorTemplate}" />
   </Style>
   ```

2. In `MainPage.xaml`, apply the custom style to the DataGrid declaration:

   ```XAML
   <telerik:RadDataGrid x:Name="grid"
                        Style="{StaticResource CustomRadDataGridStyle}"
                        ItemsSource="{Binding Clubs}">
       <telerik:RadDataGrid.BindingContext>
           <local:ViewModel />
       </telerik:RadDataGrid.BindingContext>
   </telerik:RadDataGrid>
   ```

3. In `App.xaml`, merge the custom dictionary after the Telerik theme dictionary:

   ```XAML
   <Application.Resources>
       <ResourceDictionary>
           <ResourceDictionary.MergedDictionaries>
               <local:TelerikThemeResources />

               <ResourceDictionary Source="Resources/Styles/CustomGridStyles.xaml" />
           </ResourceDictionary.MergedDictionaries>
       </ResourceDictionary>
   </Application.Resources>
   ```

>important
> Merge your custom dictionary after Telerik theme resources. If you merge it earlier, Telerik default styles can override your custom setters.

### Troubleshooting Common Issues

If the styles are not applied, check the following:

* The custom style uses `BasedOn="{StaticResource RadDataGridStyle}"` and the base style key exists.
* `CustomGridStyles.xaml` is merged in `App.xaml` after Telerik theme resources.
* The DataGrid `Style` property points to `CustomRadDataGridStyle`.
* Dynamic resource keys, such as `RadPrimarySubtleActiveColor`, are defined in the active theme dictionaries.

## See Also

* [Customizing the Telerik Theme Colors]({%slug themes-customization%})
* [Themes Overview]({%slug themes-overview%})
