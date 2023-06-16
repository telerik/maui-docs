---
title: Customize Entry Cursor Color
description: How to access the native entry element to customize the cursor
type: how-to
page_title: Customize Entry Cursor
slug: entry-cursor-customization
position: 
tags: maui, entry, radentry, cursor, caret, color, styling
ticketid: 1612671
res_type: kb
---

## Environment
<table>
	<tbody>
		<tr>
			<td>Product Version</td>
			<td>5.2.0</td>
		</tr>
		<tr>
			<td>Product</td>
			<td>Progress® Telerik® UI for .NET MAUI</td>
		</tr>
	</tbody>
</table>


## Description

This article shows you how to access the native element through the .NET MAUI handler for RadEntry via the RadMauiEntry object.

### Step 1.

Subscribe to the HandlerChanged event of the RadEntry you want to customize.

```csharp
MyRadEntry.HandlerChanged += Entry1_HandlerChanged;
```

### Step 2.

In the event handler, access the RadEntry Handler's PlatformView property. From there, you can access all the native platform's features.

```csharp
private void Entry1_HandlerChanged(object sender, EventArgs e)
{
    // Make sure the PlatformView is available
    if ((sender as RadEntry)?.Handler?.PlatformView is RadMauiEntry nativeEntry)
    {
        // Step 3. change the desired native-specific properties
#if ANDROID
        nativeEntry.EditText.TextCursorDrawable?.SetColorFilter(new Android.Graphics.PorterDuffColorFilter(Android.Graphics.Color.Red, Android.Graphics.PorterDuff.Mode.Darken));
#elif __IOS__
        nativeEntry.TextField.TintColor = UIKit.UIColor.White;
#endif
    }
}
```

## Alternate Approach

If you have many instances of the control on a single view, or throughout your app, you may want to consider creating your own custom class and subclassing the RadEntry. In the custom control's class you can override the OnHandlerChanged instead of subscribing to an event handler.

```csharp
public class MyCustomTelerikEntry : Telerik.Maui.Controls.RadEntry
{
    protected override void OnHandlerChanged()
    {
        // DO NOT SKIP THIS, or you risk breaking internal logic
        base.OnHandlerChanged();

        // Step 1. Make sure the PlatformView is available
        if (this.Handler?.PlatformView is RadMauiEntry nativeEntry)
        {
            // Step 2. change the desired native-specific properties
#if ANDROID
        nativeEntry.EditText.TextCursorDrawable?.SetColorFilter(new Android.Graphics.PorterDuffColorFilter(Android.Graphics.Color.Red, Android.Graphics.PorterDuff.Mode.Darken));
#elif __IOS__
            nativeEntry.TextField.TintColor = UIKit.UIColor.White;
#endif
        }
    }
}
```

### Known Limitations

It is not possible to apply caret customization on the following platforms:

- Windows - WinUI3, and WinApp SDK, just does not have any access the caret of the native TextBox.
- MacCatalyst - Due to a .NET MAUI issue, manually TextField.HintColor is not respected on MacCatalyst.

If either of those situations change, then these limitations may be outdated and you can attempt the customization again.

## See Also

-[Entry Styling]({%slug entry-styling%}})
