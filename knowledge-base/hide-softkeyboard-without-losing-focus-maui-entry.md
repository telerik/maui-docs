---
title: Hiding the SoftKeyboard without Losing Focus on the Entry
description: Learn how to hide the SoftKeyboard without losing focus on the Entry control in MAUI.
type: how-to
page_title: How to Hide SoftKeyboard without Losing Focus on the MAUI Entry
slug: hide-softkeyboard-without-losing-focus-maui-entry
tags: maui, entry, softkeyboard, hide, focus
res_type: kb
---
## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.8.0 | Telerik UI for .NET MAUI Entry| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

This article describes how to hide the soft keyboard without losing the focus on the Entry control.

## Solution

Use either of the following options to hide the SoftKeyboard without losing focus on the Entry control:

* [Hide when tapping outside of the Entry control](#option-1:-hide-the-keyboard-when-tapping-outside-of-the-entry-control)
* [Hide manually by using the Navive Views](#option-2:-manually-hide-the-keyboard-using-the-native-views)

### Option 1: Hide the Keyboard When Tapping Outside of the Entry Control

To achieve this, set the `HideSoftInputOnTapped` property to the page where the Entry control is used. Here's an example:

```XAML
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:local="clr-namespace:MauiApp5"
             HideSoftInputOnTapped="True"
             x:Class="MauiApp5.MainPage">
    <VerticalStackLayout>
        <Entry Placeholder="maui entry" x:Name="maui"/>
        <telerik:RadEntry Placeholder="telerik entry" x:Name="telerik"/>
    </VerticalStackLayout>
</ContentPage>
```

### Option 2: Manually Hide the Keyboard Using the Native Views

You can also manually hide the SoftKeyboard by implementing a hide keyboard function for Android and iOS. Here's an example:

```C#
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
    }
    
    public void HideKeyboard()
    {
#if ANDROID
        var imm = (Android.Views.InputMethods.InputMethodManager)MauiApplication.Current.GetSystemService(Android.Content.Context.InputMethodService);
        if (imm != null)
        {
            var activity = Microsoft.Maui.ApplicationModel.Platform.CurrentActivity;
            Android.OS.IBinder wToken = activity.CurrentFocus?.WindowToken;
            imm.HideSoftInputFromWindow(wToken, 0);
        }
#elif IOS
        {
            var window = UIKit.UIApplication.SharedApplication?.KeyWindow;
            if (window != null)
            {
                window.EndEditing(true);
            }
        }
#endif
    }

    private void Button_Clicked(object sender, EventArgs e)
    {
        this.HideKeyboard();
    }
}
```
