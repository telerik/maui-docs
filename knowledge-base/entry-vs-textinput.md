---
title: Comparison Between Entry and TextInput
page_title: Review the differences between the Entry and TextInput controls and their usage - .NET MAUI Knowledge Base
description: Learn what are the differences and the usage of the .NET MAUI Entry and TextInput controls.
type: how-to
slug: entry-vs-textinput
tags: maui, entry, textinput, .net maui entry
res_type: kb
---

## Environment

| Versions | Product | Author | 
| --- | --- | ---- | 
| Telerik UI for .NET MAUI 8.0.0 and above | Entry and TextInput | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

This kb article answers the following questions:
- What are the differences between .NET MAUI Entry and TextInput controls?
- What is the usage of the Entry and the TextInput MAUI controls from Telerik MAUI 8.0.0 version and above?

## Entry and TextInput Differences

The `RadEntry` control is a templated control that is wrapped in a border, uses the [`RadTextInput`]({%slug entry-textinput%}) for entering text, and has a clear button and a validation styling mechanism.

The `RadTextInput` control is a control for entering text. The control does not have a border and a clear button.

## Entry and TextInput Usage

The `RadEntry` is used internally in the `RadChat` and in the different masked entry controls. 

The `RadTextInput` control is part of the `RadAutoComplete`, `RadComboBox`, and `RadNumericInput` control templates.
