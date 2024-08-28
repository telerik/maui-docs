---
title: .NET MAUI Editor Inside ScrollView
description: Learn how to scroll the .NET MAUI Editor when the component is nested in a ScrollView and the user scrolls the Editor's text, which is wrapped in a border.
type: how-to
page_title: How to Scroll the Editor in a ScrollView - Editor for .NET MAUI
slug: dotnet-maui-editor-scroll-inside-scrollview
tags: editor, scrollview, scrolling, .NET MAUI, scrollable editor, dotnet maui, maui
res_type: kb
---

## Environment

| Product | Author |
| --- | --- |
| Editor for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)|

## Description

I want the <a href="https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/editor?view=net-maui-8.0" target="_blank">Editor for .NET MAUI</a> to scroll on Android when added inside a ScrollView.

This KB article also answers the following questions:
- How to use the .NET MAUI Editor, so the Editor scrolls when having more input elements on the page?
- How to use the .NET MAUI Editor, so the Editor resizes to accommodate new input?
- How to make the scenarios described above work correctly when wrapping the .NET MAUI Editor inside a border?

## Solution

To scroll the .NET MAUI Editor on Android when the Editor is inside a ScrollView:
1. Use the Editor handler to access the native Android control.
1. Call the `RequestDisallowInterceptTouchEvent` with parameter `false` to the parent view where the Editor is placed.

To scroll the .NET MAUI Editor on iOS and on Android when the Editor is inside a ScrollView and wrapped in a border:
1. Use the Telerik .NET MAUI [`RadBorder`]({%slug border-overview%}) with a nested Editor to enable the Editor to resize when the content changes.
1. Use the Telerik .NET MAUI [`RadBorder`]({%slug border-overview%}) with a nested Editor to enable the Editor to scroll when the content grows.
 
Here is an example that implements the suggested solution:

**1.** Define the custom Editor in C#:

```C#
public class CustomEditor : Editor
{

}
```

**2.** Define the Editor handler:

```C#
public class CustomEditorHandler : EditorHandler
{
#if ANDROID
    protected override AppCompatEditText CreatePlatformView()
    {
        var platfromView = base.CreatePlatformView();
        platfromView.SetOnTouchListener(new CustomTouchListener());
        return platfromView;
    }

    class CustomTouchListener : Java.Lang.Object, IOnTouchListener
    {
        public bool OnTouch(Android.Views.View? v, MotionEvent? e)
        {
            v?.Parent?.RequestDisallowInterceptTouchEvent(true);
            if ((e.Action & MotionEventActions.Up) != 0 &&
                (e.ActionMasked & MotionEventActions.Up) != 0)
            {
                v?.Parent?.RequestDisallowInterceptTouchEvent(false);
            }

            return false;
        }
    }
#endif
}

```

**3.** To resize the Editor to accommodate new input, set its `AutoSize` property to `TextChanges`. 

```XAML
<local:CustomEditor AutoSize="TextChanges" />
```

**4.** Wrap the .NET MAUI Editor in a [`RadBorder`]({%slug border-overview%}) control and place the border inside ScrollView:

```XAML
<ScrollView>
    <Grid RowDefinitions="Auto, Auto, *" Padding="10,5">
        <Label Text="Editor inside RadBorder that resizes when content changes:"/>
        <telerik:RadBorder x:Name="border" 
                            Grid.Row="1"
                            BorderColor="Gray" 
                            CornerRadius="10" 
                            BorderThickness="1">
            <local:CustomEditor AutoSize="TextChanges" 
                                Text="Type here and the Editor will change size to accomodate more text: &#xa;Line1&#xa;Line2" />
        </telerik:RadBorder>
            
        <VerticalStackLayout Grid.Row="2">
            <Label Text="Editor inside RadBorder that scrolls when content grows:"/>
            <telerik:RadBorder BorderColor="Gray" 
                                BorderThickness="1" 
                                CornerRadius="10" 
                                HeightRequest="100">
                <local:CustomEditor Text="Type here and the Editor will not change size to accomodate new text, instead you can scroll the content&#xa;Line1&#xa;Line2" />
            </telerik:RadBorder>

            <BoxView Margin="0,10,0,0" Color="Gray" HeightRequest="1000"/>
        </VerticalStackLayout>
    </Grid>
</ScrollView>
```

This is the result:

![.NET MAUI Editor inside ScrollView](images/editor-android-scrolling.gif)
