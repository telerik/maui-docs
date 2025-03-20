---
title: Accessing the NumericInput Inner Entry in .NET MAUI with Telerik UI
description: Learn how to access the RadTextInput inner entry in RadNumericInput when using Telerik MAUI version 8.0.0 or above.
type: how-to
page_title: How to Access RadTextInput Inner Entry in Telerik MAUI NumericInput
slug: access-radtextinput-inner-entry-telerik-maui-numericinput
tags: maui, numericinput, radtextinput, .net9, telerik, inner entry, handler
res_type: kb
---

## Environment


| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI NumericInput | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When migrating an app from .NET8 to .NET9 and updating the Telerik Version from 7.1.0 to 8.0.0 (or the latest 10.0.0), the `RadMauiEntry` is no longer available, and the way to access the entry handler has changed. 

This knowledge base article also answers the following questions:
- How can I access the inner entry of a `NumericInput` in Telerik MAUI?
- What replaces `RadMauiEntry` in Telerik MAUI version 8.0.0 and above?
- How do I subscribe to the handler changes of the `RadTextInput` used in `NumericInput`?

## Solution

To access the inner entry of a `RadNumericInput` when using Telerik MAUI version 8.0.0 or above, you should use the `RadTextInput` control that replaces the `RadMauiEntry`. Follow these steps to access and manipulate the inner entry:


**1.** Define the `RadNumericInput` in your XAML with the `Loaded` event:

   ```xml
   <telerik:RadNumericInput x:Name="numeric" Loaded="OnRadNumericInputLoaded"/>
   ```

**2.** In the code-behind, subscribe to the `RadTextInput.HandlerChanged` event to access the native element:

   ```csharp
   public partial class MainPage : ContentPage
   {
       public MainPage()
       {
           InitializeComponent();
       }

       private void OnRadNumericInputLoaded(object sender, EventArgs e)
       {
           var textInput = ChildOfType<RadTextInput>(this.numeric);
           if (textInput != null)
           {
               var handler = textInput.Handler;
               if (handler == null)
               {
                   textInput.HandlerChanged += this.OnTextInputHandlerChanged;
               }
               else
               {
                   this.UpdateNativeElement(handler);
               }
           }
       }

       internal static T ChildOfType<T>(View visualElement) where T : View
       {
           if (visualElement == null)
           {
               return null;
           }

           foreach (var item in VisualTreeElementExtensions.GetVisualTreeDescendants(visualElement))
           {
               if (item is T targetElement)
               {
                   return targetElement;
               }
           }

           return null;
       }

       private void OnTextInputHandlerChanged(object sender, EventArgs e)
       {
           var textInput = (RadTextInput)sender;
           this.UpdateNativeElement(textInput.Handler);
           textInput.HandlerChanged -= this.OnTextInputHandlerChanged;
       }

       private void UpdateNativeElement(IViewHandler handler)
       {
           var nativeEntry = handler.PlatformView as Telerik.Maui.Platform.RadMauiTextInput;
           if (nativeEntry != null)
           {
               // Add your logic here
           }
       }
   }
   ```

Replace `// Add your logic here` with your specific logic for manipulating the native entry.

## See Also

- [Telerik MAUI NumericInput Documentation](https://docs.telerik.com/devtools/maui/controls/numericinput/overview)
- [MAUI NumericInput Breaking Changes in Version 8.0.0](https://docs.telerik.com/devtools/maui/upgrade/breaking-changes/8-0-0#numericinput)
