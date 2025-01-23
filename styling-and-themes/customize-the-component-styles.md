---
title: Customizing the Controls' Styles
page_title: Customizing the Controls' Styles
description: Learn how to customize the styles and appearance of the Telerik UI for .NET MAUI components by using the resource dictionary files provided by the Telerik UI theme.
slug: theme-component-styles-customization
tags: telerik,.net maui,theme,custom
position: 5
---

# Customizing the Controls' Styles

The Telerik UI for .NET MAUI themes let you apply custom styles not only by [changing the colors in the theme swatches]({%slug themes-customization %}), but also by selectively customizing individual controls. You can achieve this by using the control-specific resource dictionaries with styles and templates provided by the Telerik theme.

The Telerik UI for .NET MAUI theme lets you customize individual controls like the DataGrid in two ways:

* By using the provided styles and data templates and applying them directly in the XAML file where you define the control.
* By creating a dedicated resource dictionary where you paste and modify the desired styles and data templates.

Before proceeding with the next steps, make sure that the [Telerik theming is enabled]({%slug themes-overview%}#using-the-maui-theming).

## Customizing the Control in Its Declaration

A quick way to change the appearance of a control is to directly copy styles and control templates from the `\TelerikTheming\Styles` folder and use them in the XAML file where you define the control, for example, `MainPage.xaml`. This approach, however, doesn't scale well if you intend to apply your company's distinctive colors and styles to multiple applications.

```XAML
    <telerik:RadDataGrid x:Name="grid" 
                     ItemsSource="{Binding Clubs}" >
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

>Some control-specific styles and templates depend on the content of the `\TelerikTheming\Styles\Core.xaml` file. In such cases, also copy the content of the `Core.xaml` file.

## Customizing the Control in a Dedicated Dictionary

The Telerik theme lets you customize and at the same time unify the styles of your applications. You can do this at scale by using the styles that come with the Telerik theme and placing them in a dedicated resource dictionary.

A common scenario is to apply your company's colors by [modifying the theme swatch]({%slug themes-customization %}) and then to additionally adjust the styles of a specific control by using your custom colors. This allows you to address specific design or accessibility requirements. As the colors and styles live in dedicated resource dictionaries, you can copy them to other applications, achieving consistent styles.

To customize the desired control-specific theme styles:

1. [Customize the theme colors]({%slug themes-customization %}).
1. Copy the theme resources that target the desired control and apply your changes.
1. Handle any style dependencies.

### Copy and Modify the Theme Resources

To modify the Telerik theme styles of a certain control, use the available resource dictionaries in the `\TelerikTheming\Styles` folder as a starting point. These files are generated when you enable the Telerik theming and serve as a reference for your customizations.

The next steps illustrate how to customize the theme styles of the DataGrid control and assume that you've already [customized the colors]({%slug themes-customization %}) of the theme:

**1.** Go to the `Resources\Styles` folder and create a resource dictionary file, for example, `CustomGridStyles.xaml`.

**2.** Add the Telerik namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Open the `\TelerikTheming\Styles\DataGrid.xaml` resource dictionary and copy the styles and control templates that you intend to modify.

**4.** Paste the copied styles and control templates into the file that you created in the `Resources\Styles` folder, for example, into the `Resources\Styles\CustomGridStyles.xaml` file.

**5.** Apply the desired changes to the theme styles of the control in the `CustomGridStyles.xaml`file, for example:

```XAML
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

**6.** In the `MainPage.xaml`, add the `CustomRadDataGridStyle` to the declaration of the Grid:

```XAML
    <telerik:RadDataGrid x:Name="grid" Style="{StaticResource CustomRadDataGridStyle}"
                     ItemsSource="{Binding Clubs}" >
        <telerik:RadDataGrid.BindingContext>
        <local:ViewModel />
        </telerik:RadDataGrid.BindingContext>
    </telerik:RadDataGrid>
```

**7.** In the `App.xaml.cs` code behind, merge the `CustomGridStyles` resource dictionary after the Telerik theme. This allows the application to load the theme resources first.

```C#
    public App()
    {
        InitializeComponent();

        var telerikTheming = Application.Current
                .Resources
                .MergedDictionaries
                .OfType<TelerikTheming>()
                .Single();
        telerikTheming.Theme = TelerikTheming.Themes
                            .Single(t => t.Theme == "Telerik" && t.Swatch == "Purple");
        //Merge the custom Grid styles resource dictionary.                    
        this.Resources.MergedDictionaries.Add(new CustomGridStyles());
        this.MainPage = new MainPage();
    }
```

### Handle Any Dependencies

Some of the styles and control templates that you can copy from `\TelerikTheming\Styles` have dependencies on other XAML files. To identify these dependencies, look for the comments in the XAML files under `\TelerikTheming\Styles`.

For example, the styles and control templates in the `\TelerikTheming\Styles\DataGrid.xaml` file depend on `\TelerikTheming\Styles\Core.xaml` as indicated by the following comment:

```XAML
<!-- Dependencies: Core.xaml -->
```

The comment above shows that using any of the resources in the `\TelerikTheming\Styles\DataGrid.xaml` reference file also requires you to copy the content of the `\TelerikTheming\Styles\Core.xaml` into your custom resource dictionary that you created in the `Resources\Styles` folder.

## See Also

* [Customizing the Telerik Theme Colors]({%slug themes-customization %})
* [Themes Overview]({%slug themes-overview%})
