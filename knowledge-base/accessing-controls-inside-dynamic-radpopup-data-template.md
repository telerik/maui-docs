---
title: Accessing Controls Inside Dynamic Popup Loaded from DataTemplate in ResourceDictionary
description: Learn how to dynamically load Popup content from a DataTemplate in a ResourceDictionary in UI for .NET MAUI and update the controls inside.
type: how-to
page_title: Updating Controls Inside Popup Loaded Dynamically from DataTemplate in ResourceDictionary
meta_title: Updating Controls Inside Popup Loaded Dynamically from DataTemplate in ResourceDictionary
slug: accessing-controls-inside-dynamic-radpopup-data-template
tags: popup, datatemplate, radpopup, maui, binding
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | Popup for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to load a `RadPopup` dynamically using a `DataTemplate` defined in a `ResourceDictionary` and access or update the controls (e.g., `Label`) inside the template. However, accessing controls using `x:Name` is not working. I need a solution to update the control's properties, such as the `Text` property of a `Label`, when the popup opens.

This knowledge base article also answers the following questions:
- How to bind and update controls in a `RadPopup` `DataTemplate` in .NET MAUI?
- How to dynamically modify the content of `RadPopup` in .NET MAUI?
- How to set control properties inside `RadPopup` using bindings or code?

## Solution

To achieve this, you can use one of two approaches: 
* [Binding the controls to a `ViewModel`](#option-1-using-binding-with-viewmodel)
* Programmatically accessing the controls inside the `DataTemplate`. 

### Option 1: Using Binding with ViewModel

Use bindings to update the control properties inside the `DataTemplate`. Bind the `Label`'s `Text` property to a `ViewModel` and ensure the binding mode is set to `TwoWay`.

**1.** Define a `ViewModel` with a property for binding:

```csharp
public class ViewModel : NotifyPropertyChangedBase
{
    private string myValue;

    public ViewModel()
    {
        this.myValue = "hello";
    }

    public string MyValue
    {
        get => this.myValue;
        set => this.UpdateValue(ref this.myValue, value);
    }
}
```

**2.** Set the `BindingContext` in your code-behind:

```csharp
public partial class MainPage : ContentPage
{
    ViewModel vm;

    public MainPage()
    {
        InitializeComponent();
        this.vm = new ViewModel();
        this.BindingContext = this.vm;
    }

    private void CheckBoxIsCheckedChanged(object sender, IsCheckedChangedEventArgs e)
    {
        if (e.NewValue == true)
        {
            this.popup.IsOpen = true;
            this.vm.MyValue = "value changed";
        }
    }
}
```

**3.** Define the `DataTemplate` in XAML and bind the `Label`'s `Text` property:

```xml
<DataTemplate x:Key="PopupTemplate">
    <telerik:RadBorder CornerRadius="8"
                       BackgroundColor="#F9F9F9"
                       BorderColor="Red"
                       BorderThickness="1"
                       WidthRequest="300"
                       Padding="12">
        <VerticalStackLayout Spacing="8">
            <Label Text="{Binding MyValue, Mode=TwoWay}" />
        </VerticalStackLayout>
    </telerik:RadBorder>
</DataTemplate>
```

### Option 2: Accessing Controls Programmatically

Directly access the controls inside the `DataTemplate` programmatically and update their properties.

**1.** Define the `DataTemplate` in XAML:

```xml
<DataTemplate x:Key="PopupTemplate">
    <telerik:RadBorder CornerRadius="8"
                       BackgroundColor="#F9F9F9"
                       BorderColor="Red"
                       BorderThickness="1"
                       WidthRequest="300"
                       Padding="12">
        <VerticalStackLayout Spacing="8">
            <Label />
        </VerticalStackLayout>
    </telerik:RadBorder>
</DataTemplate>
```

**2.** In the code-behind, dynamically load the content and update the control properties:

```csharp
private void CheckBoxIsCheckedChanged(object sender, IsCheckedChangedEventArgs e)
{
    if (e.NewValue == true)
    {
        this.popup.IsOpen = true;
        var dataTemplate = this.myPage.Resources["PopupTemplate"] as DataTemplate;

        var popupcontent = dataTemplate.CreateContent() as View;
        this.popup.Content = popupcontent;

        List<IVisualTreeElement> items = (List<IVisualTreeElement>)this.popup.Content.GetVisualTreeDescendants();
        foreach (IVisualTreeElement myControl in items)
        {
            if (myControl is Label)
            {
                Label control = (Label)myControl;
                control.Text = "popup content has been changed when opened";
                return;
            }
        }
    }
}
```

### Key Considerations:

- Accessing controls inside a `DataTemplate` using `x:Name` is not possible due to the general behavior of the MAUI framework.
- Use bindings if you want to follow MVVM principles.
- For direct control access, ensure the `DataTemplate` content is created and assigned to the popup before attempting to modify controls.

## See Also

- [.NET MAUI Popup Documentation](https://docs.telerik.com/devtools/maui/controls/popup/overview)
