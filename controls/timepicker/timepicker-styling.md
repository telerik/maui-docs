---
title: Styling
page_title: .NET MAUI TimePicker Documentation | Styling
description: Check our &quot;Styling&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 8
slug: timepicker-styling
---

# Styling

## TimePicker Styling

The TimePicker control provides the following `Style` properties for customizing its look:

* `SpinnerStyle`(of type `Style` with target type `telerikDataControls:RadSpinner`)&mdash;Defines the style applied to the spinner item and to the selected item.
* `SpinnerHeaderStyle`(of type `Style` with target type `Label`)&mdash;Specifies the style applied to the spinner header labels.
* `SelectionHighlightStyle`(of type `Style` with target type `telerikPrimitives:RadBorder`)&mdash;Specifies the style applied to the selection inside the popup.
* `PlaceholderLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the style applied to the placeholder label.
* `DisplayLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the style applied to the label which is visualized when time is selected.

In addition, the TimePicker exposes the following properties for specifying its border style and background color:

* `BackgroundColor`&mdash;Defines the background color of the picker.
* `BorderColor`&mdash;Defines the border color of the picker.
* `BorderThickness`&mdash;Specifies the border thickness of the picker. The default value is `new Thickness(0,0,0,1)`.
* `CornerRadius`&mdash;Specifies the corner radius of the picker.

## Popup Styling

By using the `SelectorSettings` property (of type `Telerik.XamarinForms.Input.PickerPopupSelectorSettings`) of the TimePicker, you can modify the appearance of the dialog (popup).

The `PickerPopupSelectorSettings` class exposes the following `Style` properties:

* `PopupViewStyle`(of type `Style` with target type `telerikInput:PickerPopupContentView`)&mdash;Defines the popup view style.
* `HeaderStyle`(of type `Style` with target type `telerikInput:PickerPopupHeaderView`)&mdash;Defines the popup header style.
* `HeaderLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the popup header label style.
* `FooterStyle`(of type `Style` with target type `telerikInput:PickerPopupFooterView`)&mdash;Defines the popup footer style.
* `AcceptButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Accept** button style.
* `CancelButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Cancel** button style.

The `SelectorSettings` also provides the following properties for popup customization:

* `PopupOutsideBackgroundColor`&mdash;Defines the color outside of the popup.
* `IsPopupModal`(`bool`)&mdash;Defines a boolean value indicating if the popup will be closed when users click outside of the popup.
	* When `IsPopupModal="True"`, the UI behind the popup gets inactive and cannot be used until the popup is closed.
	* When `IsPopupModal="False"`, the popup can be closed when clicking outside the popup. By default, the value of the `IsPopupModal` is `False`.

* `HeaderLabelText`(`string`)&mdash;Specifies the text visualized in the popup header.
* `IsHeaderVisible`(`bool`)&mdash;Specifies whether the Popup header is currently visible. By default, the value is `True`.
* `IsFooterVisible`(`bool`)&mdash;Specifies whether the Popup footer is currently visible. By default, the value is `True`.
* `AcceptButtonText`(`string`)&mdash;Defines the text visualized for the accept button. By default, the text is `OK`.
* `CancelButtonText`(`string`)&mdash;Defines the text visualized for the cancel button. By default, the text is `Cancel`.

## Namespaces

When defining some of these styles, you need to include additional namespaces, so that the target types are properly resolved.

When you use `PopupViewStyle`, `HeaderStyle`, or `FooterStyle`, you will need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

When you use `SelectionHighlightStyle`, you need to add the following namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

When you use `SpinnerStyle`, you need to add the following namespace:

```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
```

## Example

The following example shows how the styling properties are applied.

```XAML
<telerikInput:RadTimePicker SpinnerHeaderStyle="{StaticResource spinnerHeaderStyle}"
                                    SpinnerStyle="{StaticResource spinnerStyle}"
                                    SelectionHighlightStyle="{StaticResource selectionHighlightStyle}"
                                    DisplayLabelStyle="{StaticResource displayLabelStyle}"
                                    PlaceholderLabelStyle="{StaticResource placeholderLabelStyle}"
                                    DisplayStringFormat="HH:mm">
    <telerikInput:RadTimePicker.SelectorSettings>
        <telerikInput:PickerPopupSelectorSettings PopupOutsideBackgroundColor="#D9D9D9CC"
                                                  PopupViewStyle="{StaticResource popupViewStyle}"
                                                  HeaderStyle="{StaticResource headerStyle}"
                                                  HeaderLabelText="Time Picker"
                                                  HeaderLabelStyle="{StaticResource headerLabelStyle}"
                                                  FooterStyle="{StaticResource footerStyle}"
                                                  AcceptButtonStyle="{StaticResource acceptButtonStyle}"
                                                  CancelButtonStyle="{StaticResource cancelButtonStyle}"/>
    </telerikInput:RadTimePicker.SelectorSettings>
</telerikInput:RadTimePicker>
```

And here are how the styles are defined in the page resources.

## Spinner Style

The following example shows how to set the spinner `ItemStyle` and `SelectedItemStyle`.

```XAML
 <Style TargetType="telerikDataControls:RadSpinner" x:Key="spinnerStyle">
    <Setter Property="ItemStyle">
        <Setter.Value>
            <Style TargetType="telerikDataControls:SpinnerItemView">
                <Setter Property="TextColor" Value="#797979" />
                <Setter Property="BackgroundColor" Value="#F2F2F2" />
                <Setter Property="CornerRadius" Value="10" />
                <Setter Property="Margin" Value="6, 4" />
            </Style>
        </Setter.Value>
    </Setter>
    <Setter Property="SelectedItemStyle">
        <Setter.Value>
            <Style TargetType="telerikDataControls:SpinnerItemView">
                <Setter Property="TextColor" Value="#00B5DC" />
                <Setter Property="BackgroundColor" Value="#E4F3F9" />
                <Setter Property="CornerRadius" Value="10" />
                <Setter Property="Margin" Value="6, 4" />
            </Style>
        </Setter.Value>
    </Setter>
</Style>
```

## SpinnerHeader Style

```XAML
<Style TargetType="Label" x:Key="spinnerHeaderStyle">
    <Setter Property="TextColor" Value="Black"/>
    <Setter Property="FontAttributes" Value="Bold"/>
    <Setter Property="HorizontalOptions" Value="FillAndExpand"/>
    <Setter Property="VerticalOptions" Value="FillAndExpand"/>
    <Setter Property="HorizontalTextAlignment" Value="Center"/>
    <Setter Property="VerticalTextAlignment" Value="Center"/>
</Style>
```

## SelectionHighlight Style

```XAML
<Style TargetType="telerik:RadBorder" x:Key="selectionHighlightStyle">
    <Setter Property="BorderColor" Value="#00B5DC"/>
    <Setter Property="BorderThickness" Value="1"/>
    <Setter Property="Padding" Value="0,6,0,6"/>
    <Setter Property="HeightRequest" Value="40"/>
    <Setter Property="VerticalOptions" Value="Center"/>
</Style>
```

## PlaceholderLabel Style

```XAML
<Style TargetType="Label" x:Key="placeholderLabelStyle">
    <Setter Property="TextColor" Value="#4A4949"/>
    <Setter Property="VerticalTextAlignment" Value="Center"/>
    <Setter Property="HorizontalTextAlignment" Value="Center"/>
    <Setter Property="HeightRequest" Value="50"/>
</Style>
```

## DisplayLabel Style

```XAML
<Style TargetType="Label" x:Key="displayLabelStyle">
    <Setter Property="TextColor" Value="Black"/>
    <Setter Property="VerticalTextAlignment" Value="Center"/>
    <Setter Property="HorizontalTextAlignment" Value="Center"/>
    <Setter Property="HeightRequest" Value="50"/>
</Style>
```

## PopupView Style

```XAML
<Style TargetType="telerikInput:PickerPopupContentView" x:Key="popupViewStyle">
    <Setter Property="BackgroundColor" Value="White"/>
    <Setter Property="WidthRequest" Value="270"/>
</Style>
```

## Header Style

```XAML
<Style TargetType="telerikInput:PickerPopupHeaderView" x:Key="headerStyle">
    <Setter Property="BackgroundColor" Value="#00B5DC"/>
    <Setter Property="HeightRequest" Value="60"/>
    <Setter Property="Margin" Value="0"/>
    <Setter Property="Padding" Value="0"/>
    <Setter Property="HorizontalOptions" Value="FillAndExpand"/>
    <Setter Property="VerticalOptions" Value="FillAndExpand"/>
</Style>
```

## HeaderLabel Style

```XAML
<Style TargetType="Label" x:Key="headerLabelStyle">
    <Setter Property="TextColor" Value="White"/>
    <Setter Property="HorizontalOptions" Value="Center"/>
    <Setter Property="VerticalOptions" Value="Center"/>
    <Setter Property="FontSize" Value="Title"/>
</Style>
```

## Footer Style

```XAMl
<Style TargetType="telerikInput:PickerPopupFooterView" x:Key="footerStyle">
    <Setter Property="BackgroundColor" Value="Transparent"/>
</Style>
```

## AcceptButton Style

```XAML
<Style TargetType="Button" x:Key="acceptButtonStyle">
    <Setter Property="BackgroundColor" Value="Transparent"/>
    <Setter Property="Text" Value="OK"/>
    <Setter Property="TextColor" Value="#00B5DC"/>
</Style>
```

## CancelButton Style

```XAML
<Style TargetType="Button" x:Key="cancelButtonStyle">
    <Setter Property="BackgroundColor" Value="Transparent"/>
    <Setter Property="Text" Value="X"/>
    <Setter Property="TextColor" Value="#00B5DC"/>
</Style>
```

## Namespaces

In addition, add the following namespaces:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
```

The following image shows how the TimePicker control looks when the styles described above are applied.

![Time Picker](images/timepicker_style.png)

## See Also

- [Custom Templates]({%slug timepicker-templates%})
- [Commands]({%slug timepicker-commands%})
- [Visual Structure]({%slug timepicker-visual-structure%})
