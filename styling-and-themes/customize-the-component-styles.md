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

To customize the desired control-specific theme styles:

1. Copy the theme resources that target the desired control and apply your changes.
1. Handle any style dependencies.
1. Merge the new resource dictionary after the built-in Telerik theme resources.

Before proceeding with the next steps, make sure the [Telerik theming is enabled]({%slug themes-overview%}#using-the-maui-theming).

## Customizing a Specific Control

To modify the Telerik theme styles of a certain control, use the available resource dictionaries in the `\TelerikTheming\Styles` folder as a starting point. These files are generated when you enable the Telerik theming and serve as a reference for your customizations.

The next steps illustrate how to customize the theme styles of the DataGrid control:

1. Go to the `Resources\Styles` folder and create a resource dictionary file, for example, `CustomDataGrid.xaml`.

    * The new file must have no code-behind file, similar to the `Styles.xaml` and `Colors.xaml` files in a project that uses the default MAUI application template by Microsoft.
    * If you already have a [customized color swatch]({%slug themes-customization %}) with its own resource dictionary XAML file, use that file to append the custom DataGrid styles&mdash;you don't need to create a new one.

1. Open the `\TelerikTheming\Styles\DataGrid.xaml` resource dictionary and copy the styles and control templates that you intend to modify, for example:

    <!-- List three custom styles to illustrate the procedure. -->

1. Paste the copied styles and control templates into the file that you created in the `Resources\Styles` folder, for example, into the `Resources\Styles\CustomDataGrid.xaml` file.

1. Apply the desired changes to the theme styles of the control, for example:

    <!-- List the content of the XAML file.-->

## Handle Any Dependencies

Some of the styles and control templates that you can copy from `\TelerikTheming\Styles` have dependencies on other XAML files. To identify these dependencies, look for the comments in the XAML files under `\TelerikTheming\Styles`.

For example, the styles and control templates in the `\TelerikTheming\Styles\DataGrid.xaml` file depend on `\TelerikTheming\Styles\Core.xaml` as indicated by the following comment:

```XAML
<!-- Dependencies: Core.xaml -->
```

The comment above shows that using any of the resources in the `\TelerikTheming\Styles\DataGrid.xaml` reference file also requires you to copy the content of the `\TelerikTheming\Styles\Core.xaml` into your custom resource dictionary that you created in the `Resources\Styles` folder.

## Merge the New Resource Dictionary

Once you customize the styles in the newly created resource dictionary under `Resources\Styles`, configure the application to use them: add the new resource dictionary to the `App.xaml` and make sure you merge your customized `Resources\Styles\CustomDataGrid.xaml` resource dictionary after the `TelerikTheming`:

```XAML
<Application.Resources>
    <ResourceDictionary>
        <ResourceDictionary.MergedDictionaries>
            <ResourceDictionary Source="Resources/Styles/Colors.xaml" />
            <ResourceDictionary Source="Resources/Styles/Styles.xaml" />
            <local:TelerikTheming />

            <!-- Add your customized DataGrid styles after the TelerikTheming resources.-->
            <ResourceDictionary Source="Resources/Styles/CustomDataGrid.xaml" />
        </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
</Application.Resources>
```

The next image illustrates the effects of customizing the primary color of the theme swatch:

<!-- Add a sample image here.-->

![Telerik UI for .NET MAUI Theming Custom Grid Styles](images/telerik-theming-customized-grid-theme.png)


## See Also

* [Customizing the Telerik Theme Colors]({%slug themes-customization %})
* [Themes Overview]({%slug themes-overview%})
