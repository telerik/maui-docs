---
title: Toolbar Styling
page_title: .NET MAUI RichTextEditor Documentation - RichTextEditor Toolbar Styling
description: Learn more how to style the toolbar items in the Telerik UI for .NET MAUI RichTextEditor control.
position: 2
slug: richtexteditor-toolbar-styling
---

# RichTextEditor Toolbar Styling

The [.NET MAUI RichTextEditor]({%slug richtexteditor-overview%}) provides a flexible styling API for its toolbar items. 

## Style the Toolbar Items

The `RichTextEditorToolbar` is based on the `RadToolbar` control, so the toolbar items in the RichTextEditor use a `ToolbarItem`. 

Each toolbar item has a `Style` property and the target type of the property is the corresponding `ToolbarItemView`:

| Toolbar Item | Style Target Type |
| ------------- | --------------- |
| `RichTextEditorFontFamilyToolbarItem` | `RichTextEditorListPickerToolbarItemView` |
| `RichTextEditorFontSizeToolbarItem` | `RichTextEditorListPickerToolbarItemView` |
| `SeparatorToolbarItem` | `ToolbarItem` |
| `RichTextEditorBoldToolbarItem` | `ToggleButtonToolbarItemView` |
| `RichTextEditorItalicToolbarItem` | `ToggleButtonToolbarItemView` |
| `RichTextEditorUnderlineToolbarItem` | `ToggleButtonToolbarItemView` |
| `RichTextEditorAlignLeftToolbarItem` | `RadioButtonToolbarItemView` |
| `RichTextEditorAlignCenterToolbarItem` | `RadioButtonToolbarItemView` |
| `RichTextEditorAlignRightToolbarItem` | `RadioButtonToolbarItemView` |
| `RichTextEditorAlignJustifyToolbarItem` | `RadioButtonToolbarItemView` |
| `RichTextEditorTextColorToolbarItem` | `RichTextEditorColorPickerToolbarItemView` |
| `RichTextEditorHighlightTextColorToolbarItem` | `RichTextEditorColorPickerToolbarItemView` |
| `RichTextEditorBulletingToolbarItem` | `ToggleButtonToolbarItemView` |
| `RichTextEditorNumberingToolbarItem` | `ToggleButtonToolbarItemView` |
| `RichTextEditorOutdentToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorIndentToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorTextFormattingToolbarItem` | `RichTextEditorListPickerToolbarItemView` |
| `RichTextEditorClearFormattingToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorStrikethroughToolbarItem` | `ToggleButtonToolbarItemView` |
| `RichTextEditorSuperscriptToolbarItem` | `ToggleButtonToolbarItemView` |
| `RichTextEditorSubscriptToolbarItem` | `ToggleButtonToolbarItemView` |
| `RichTextEditorUndoToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorRedoToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorColorPickerToolbarItem` | `RichTextEditorColorPickerToolbarItemView` |
| `RichTextEditorCopyToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorCutToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorPasteHtmlToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorAddOrEditHyperlinkToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorAddHyperlinkToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorRemoveHyperlinkToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorAddOrEditImageToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorHyperlinkNavigationToolbarItem` | `ButtonToolbarItemView` |
| `RichTextEditorImageNavigationToolbarItem` | `ButtonToolbarItemView` |

All styling properties available for the target type [`ButtonToolbarItemView`]({%slug toolbar-items-button%}), [`ToggleButtonToolbarItemView`]({%slug toolbar-items-toggle-button%}), [`RadioButtonToolbarItemView`]({%slug toolbar-items-radio-button%}) are also applicable for the RichTextEditor toolbar items that use this target type. 

## Example for Styling the Toolbar

**1.** RichTextEditor and Toolbar definitions in XAML:

<snippet id='richtexteditor-toolbar-styling-xaml' />

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** And the Styles in the Resources of the page :

<snippet id='richtexteditor-toolbar-styling-resource' />

**4.** This is the result:

![.NET MAUI RichTextEditor Toolbar Styling](../images/richtexteditor-toolbar-styling.png)

> For the RichTextEditor Toolbar Styling example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **RichTextEditor -> Styling**.
