---
title: Error when Using Hot Restart
description: error message when deploying on an iPhone device using Visual Studio for Windows
type: troubleshooting
page_title: Error when using Hot Restart
slug: telerik-maui-hot-restart
position: 
tags: maui, visual studio, hot restart, iPhone, device, error
ticketid: 1604908
res_type: kb
---

## Environment
<table>
	<tbody>
		<tr>
			<td>Product Version</td>
			<td>5.1.0</td>
		</tr>
		<tr>
			<td>Product</td>
			<td>Progress® Telerik® UI for .NET MAUI</td>
		</tr>
	</tbody>
</table>


## Description

This article describes the behavior that occurs when using Hot Restart feature - deploying on iPhone device thorugh Visual Studio for Windows. Some of the Telerik .NET MAUI controls use static libraries, and when using hot restart an exception is thrown. The behavior occurs as Hot Restart has a limitation - does not support static libraries. 
The error message is described below: 

## Error Message

The following error message is received when trying to deploy on iPhone device using Hot Restart feature from Visual Studio for Windows. 

 ```
NSForwarding: warning: does not implement methodSignatureForSelector:

NSForwarding: warning: does not implement doesNotRecognizeSelector:
```

## Table of Compatibility

The table below shows a list of controls and their compatibility with Hot Restart feaure. 

| Control | Results | Error message | Comments | Exception Details |
| ------------- | --------------- | ------ | ------ | ------ |
| Accordion | Pass | - | - | - |
| AutoComplete | Fail | Yes | - | Telerik_Maui_InputElement_RadTextField does not implement methodSignatureForSelector |
| BadgeView | Fail | No | No crash, but nothing rendered | - |
| Barcode | Fail | No | No crash, but nothing rendered | - |
| Border | Pass | - | - | - |
| Button | Pass | - | - | - |
| Chart | Fail | Yes | - | Telerik_Maui_Controls_Compatibility_ChartRenderer_iOS_TKExtendedChart does not implement methodSignatureForSelector |
| CheckBox | Pass | - | - | - |
| ComboBox | Fail | Yes | - | Telerik_Maui_InputElement_RadTextField does not implement methodSignatureForSelector |
| DataForm | Fail | Yes | - | Telerik_Maui_InputElement_RadTextField does not implement methodSignatureForSelector |
| DataGrid | Partial | Yes | Works until an editor needs a TextField, then crashes | Telerik_Maui_InputElement_RadTextField does not implement methodSignatureForSelector |
| DatePicker, DateTimePicker, TimePicker, TimeSpanPicker | Partial | Yes | Works in Popup mode, crashes with DropDown mode | No exception details in VS output |
| DockLayout | Pass | - | - | - |
| Entry | Fail | Yes | - | Telerik_Maui_InputElement_RadTextField does not implement methodSignatureForSelector |
| Expander | Pass | - | - | - |
| Gauge | Fail | Yes | - | Failed at Telerik.Maui.Controls.SkiaSharp.SkiaUtilities.TryCreateTextPaint |
| ImageEditor | Fail | Yes | - | No exception details in VS output |
| ItemsControl | Pass | - | - | - |
| ListPicker | Pass | - | - | - |
| ListView | Fail | Yes | - | Telerik_Maui_Controls_Compatibility_DataControlsRenderer_iOS_TKExtendedListView' does not implement methodSignatureForSelector |
| Map | Fail | Yes | - | Failed at Telerik.Maui.Controls.Compatibility.Map.ShapefileLayer.GenerateFillPaint |
| NumericInput | Fail | Yes | - | Telerik_Maui_InputElement_RadTextField does not implement methodSignatureForSelector |
| MaskedEntry | Fail | Yes | - | Telerik_Maui_InputElement_RadTextField does not implement methodSignatureForSelector |
| Path | Fail | No | No crash, but nothing rendered | - |
| Popup | Pass | - | - | - |
| ProgressBar | Pass | - | - | - |
| Rating | Fail | No | No crash, but nothing rendered | - |
| SegmentedControl | Pass | - | - | - |
| SideDrawer | Fail | Yes | - | Could not create an native instance of the type TelerikUI.TKSideDrawerView: the native class hasn't been loaded |
| SignaturePad | Fail | No | - | User gestures are not rendered |
| TabView | Pass | - | - | - |
| TemplatedPicker | Pass | - | - | - |
| Toolbar | Pass | - | - | - |
| WrapLayout | Pass | - | - | - |

## Workaround

For now we cannot suggest a workaround for this error message. We have a [feature request](https://feedback.telerik.com/maui/1582732-support-for-hot-restart-feature) for providing support for Hot Restart. 

