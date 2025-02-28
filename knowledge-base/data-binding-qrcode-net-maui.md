---
title: Data Binding with QRCode in .NET MAUI Applications
description: Learn how to bind a QRCode to a property in the ViewModel in a .NET MAUI application using the Telerik Barcode component.
type: how-to
page_title: How to Implement Data Binding for QRCode in .NET MAUI
slug: data-binding-qrcode-net-maui
tags: barcode, qrcode, databinding, .net maui, viewmodel, bindingcontext
res_type: kb
ticketid: 1680174
---

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>Barcode for .NET MAUI</td>
</tr>
<tr>
<td>Version</td>
<td>9.0.0</td>
</tr>
</tbody>
</table>

## Description

As with any other bindable property, you can bind the `Value` property of the [`RadBarcode`](https://docs.telerik.com/devtools/maui/controls/barcode/2d-barcodes/qrcode-overview) to a property in the view model, allowing dynamic updates of the QR code in the UI.

## Solution

To achieve dynamic updates of a QRCode in a .NET MAUI application, follow these steps:

1. Ensure the `RadBarcode` is properly configured in your XAML with the correct binding to the view model property. Use the `Value` attribute to bind to the view model property.

```xml
<telerik:RadBarcode WidthRequest="160" HeightRequest="160"
                    HorizontalOptions="Center" VerticalOptions="Center"
                    Margin="0, 10, 0, 0" Value="{Binding SelectedCity}">
    <telerik:RadBarcode.Symbology>
        <telerik:QRCode SizingMode="Stretch" CodeMode="Byte"
                        ErrorCorrectionLevel="H" ECIMode="ISO8859_1"
                        FNC1Mode="SecondPosition" ApplicationIndicator="00"/>
    </telerik:RadBarcode.Symbology>
</telerik:RadBarcode>
```

2. In your ViewModel, implement the property to which the RadBarcode's `Value` is bound. Ensure this property notifies the UI of changes, typically by implementing the `INotifyPropertyChanged` interface.

```csharp
public class MainPageViewModel : Telerik.Maui.Controls.NotifyPropertyChangedBase
{
    private string selectedCity;

    public ObservableCollection<string> Cities { get; set; }

    public string SelectedCity
    {
        get => selectedCity;
        set => UpdateValue(ref selectedCity, value);
    }

    public MainPageViewModel()
    {
        Cities = new ObservableCollection<string>
        {
            "Madrid", "Los Angeles", "Paris", "Beijing",
            "Singapore", "New Delhi", "Bangkok", "Berlin"
        };

        SelectedCity = Cities.FirstOrDefault();
    }
}
```

3. Bind the ViewModel to the View's `BindingContext` to establish the data binding.

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        BindingContext = new MainPageViewModel();
    }
}
```

4. Optionally, use a control like `RadComboBox` to change the selected city and see the QRCode update in real-time.

```xml
<telerik:RadComboBox ItemsSource="{Binding Cities}" 
                     SelectedItem="{Binding SelectedCity, Mode=TwoWay}"
                     WidthRequest="200" HorizontalOptions="Center"
                     VerticalOptions="Center" Grid.Row="1"/>
```

## See Also

- [Barcode Overview](https://docs.telerik.com/devtools/maui/controls/barcode/overview)
- [QRCode Symbology](https://docs.telerik.com/devtools/maui/controls/barcode/2d-barcodes/qrcode-overview)
- [Binding in .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/fundamentals/data-binding)

---
