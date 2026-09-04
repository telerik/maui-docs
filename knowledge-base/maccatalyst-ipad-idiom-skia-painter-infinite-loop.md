---
title: Continuous Invalidation Loop in Mac Catalyst Apps Using iPad Idiom
description: Learn how to resolve an issue where Painter.UpdatePixelScale continuously re-invalidates itself and causes high CPU usage in Mac Catalyst applications using the iPad idiom.
type: troubleshooting
page_title: Fixing Continuous Repainting in Mac Catalyst Apps with Skia Controls
meta_title: Resolving Painter.UpdatePixelScale Invalidation Loop on Mac Catalyst
slug: maccatalyst-ipad-idiom-skia-painter-infinite-loop
tags: maccatalyst, skiapainter, pixelscale, skia, gauge, pdfviewer, high-cpu, ipad-idiom, mac-idiom
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 15.0.0 | Telerik UI for .NET MAUI | [Desislava Yordanova](https://www.telerik.com/blogs/author/desislava-yordanova) |

## Description

When running a .NET MAUI Mac Catalyst application that contains Skia-based controls (such as `RadGauge`, `RadBarcode`, or `RadPdfViewer`), the application may experience continuous repainting and excessive CPU usage even when idle.

This occurs when the Mac Catalyst application is configured using the **iPad idiom** ("Scaled to Match iPad").

### Symptoms

* High CPU usage on macOS while the view is idle.
* Increased battery consumption.
* The internal `Painter.UpdatePixelScale` routine repeatedly detects a scale change and triggers `InvalidateSurface()`.

## Cause

In Mac Catalyst applications configured with the scaled iPad idiom (`UIDeviceFamily` set to `2`), display density calculations can differ between the immediate painting phase and the post-dispatch frame verification in `SkiaPainter.UpdatePixelScale()`. 

Because the calculated scale does not match the cached ratio, `UpdatePixelScale()` invokes `InvalidateSurface()`, which triggers another paint pass and schedules another verification in an endless cycle.

## Solution

Configure the application to use the native **Mac idiom** ("Optimize for Mac") rather than the scaled iPad idiom. In the Mac idiom, macOS renders views at native desktop resolution without fractional scaling factors, providing stable screen scale readings across render cycles.

To enable the Mac idiom:

### Update Info.plist

In your application's `Platforms/MacCatalyst/Info.plist` file, set `UIDeviceFamily` to include `6` (the native Mac idiom identifier):

```xml
<key>UIDeviceFamily</key>
<array>
    <integer>6</integer>
</array>
```

### Update Project File (Optional)

Alternatively, ensure your `.csproj` enables the Mac interface idiom for Mac Catalyst builds:

```xml
<PropertyGroup Condition="$(TargetFramework.Contains('-maccatalyst'))">
    <UseMacUserInterfaceIdiom>true</UseMacUserInterfaceIdiom>
</PropertyGroup>
```

After updating to the Mac idiom, rebuild the application. `Painter.UpdatePixelScale` will read consistent scaling factors and stop triggering recursive repaints.

## See Also

- [RadGauge Overview]({%slug gauge-overview%})
- [PdfViewer Overview]({%slug pdfviewer-overview%})
- [Apple Developer: Choosing a User Interface Idiom for Mac Catalyst](https://developer.apple.com/documentation/uikit/mac_catalyst/choosing_a_user_interface_idiom_for_your_mac_app)
