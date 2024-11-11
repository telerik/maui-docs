---
title: Customize the Telerik Theme
page_title: Customize the Telerik Theme
description: Learn how to customize the Telerik Theme for your .NET MAUI application and alter the default appearance of the UI for .NET MAUI components.
slug: themes-customization
tags: telerik,.net maui,theme,custom
position: 1
---

## Customize the Telerik Theme

There are several ways to customize the visual appearance of the Telerik .NET MAUI controls depending on the needed changes. You can modify only the colors in a certain color variation and that will affect all the controls or you can make more specific cbange in the styles and templates of a certain Telerik UI for .NET MAUI component.

Either approach requires copying the needed resources in a separate resource dictionary, modifying it and merging it after the Telerik theme resources.

Check the detailed steps below:

### Copy and modify the theme resources

Inside the **Telerik Theming** folder you have all the theme color variations (inside the **Swatches** folder) as well as the styles and templates of the Telerik .NET MAUI controls (inside the **Styles** folder).

**1.** Go to the Resources/Styles folder and create a `ResourceDictionary` file without a code-behind file in a similar way as the default **Styles.xaml** and **Colors.xaml**:

![Telerik .NET MAUI Theming Custom Colors](images/theming-custom-swatch.png)

**2.** Copy the needed Colors or Styles from the swatch you'd need to modify into the newly created `ResourceDictionary` file and modify them according to the design requirements you have. For example let's modify the swatch primary colors:

```XAML
<?xml version="1.0" encoding="UTF-8" ?>
<?xaml-comp compile="true" ?>
<ResourceDictionary 
    xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
    xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui">

    <!-- Primary -->
    <Color x:Key="RadPrimarySubtleColor">#D0E3EE</Color>
    <Color x:Key="RadPrimarySubtleHoverColor">#B8D5E6</Color>
    <Color x:Key="RadPrimarySubtleActiveColor">#A0C7DE</Color>
    <Color x:Key="RadPrimaryColor">#74AC12</Color>
    <Color x:Key="RadPrimaryHoverColor">#689B10</Color>
    <Color x:Key="RadPrimaryActiveColor">#5D8A0E</Color>
    <Color x:Key="RadPrimaryEmphasisColor">#ACCD71</Color>
    <Color x:Key="RadPrimaryOnSubtleColor">#2E4507</Color>
    <Color x:Key="RadOnPrimaryColor">#FFFFFF</Color>
    <Color x:Key="RadPrimaryOnSurfaceColor">#74AC12</Color>

    <telerik:ColorFilter x:Key="RadPrimaryColorAlpha4" Color="{StaticResource RadPrimaryColor}" Alpha="0.04" />
    <telerik:ColorFilter x:Key="RadPrimaryColorAlpha16" Color="{StaticResource RadPrimaryColor}" Alpha="0.16" />
    <telerik:ColorFilter x:Key="RadPrimaryColorDarken4" Color="{StaticResource RadPrimaryColor}" Lighten="-0.04" />
    <telerik:ColorFilter x:Key="RadPrimaryColorDarken12" Color="{StaticResource RadPrimaryColor}" Lighten="-0.12" />
</ResourceDictionary>
```

### Merge the new ResourceDictionary in App.xaml

The next step is to add the resource dictionary with the customized colors to "App.xaml" - make sure the `CustomTelerikSwatch.xaml` is merged after the `TelerikTheming` file:

```XAML
<Application.Resources>
    <ResourceDictionary>
        <ResourceDictionary.MergedDictionaries>
            <ResourceDictionary Source="Resources/Styles/Colors.xaml" />
            <ResourceDictionary Source="Resources/Styles/Styles.xaml" />
            <local:TelerikTheming />

            <!-- Customize a swatch -->
            <ResourceDictionary Source="Resources/Styles/CustomTelerikSwatch.xaml" />
        </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
</Application.Resources>
```

Here is the result:

![Telerik .NET MAUI Theming Custom Colors](images/telerik-theming-customized.png)

If you need to modify the Style or ControlTemplate of a certain control, for example `RadComboBox`, you need to copy the `ComboBox.xaml` file in the same way in the app Resources and merge it inside `App.xaml`, then make the needed changes.

Some of the controls' XAML files have dependencies on other XAML files, you can check this inside the constructor of that file, for example, the `ComboBox.xaml` has a dependency on `Core.xaml`:

```C#
public partial class ComboBox : ResourceDictionary
{
	public ComboBox(ResourceDictionary core)
	{
		this.MergedDictionaries.Add(core);
		InitializeComponent();
	}
}
```

In this case, to modify the ComboBox, you'd need to copy and merge the content of both `Core.xaml` and `ComboBox.xaml` files.