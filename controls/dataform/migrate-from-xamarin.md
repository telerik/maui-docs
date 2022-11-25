---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI DataForm Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms DataForm to .NET MAUI DataForm control."
position: 2
slug: dataform-migrate-from-xamarin
---

# Migrate from Xamarin.Forms DataForm to .NET MAUI DataForm

Overall, Telerik .NET MAUI DataForm control is a complete new control with new API, improvements and flexible styling mechanisum implemented.

Compared API changes in Xamarin.Forms DataForm and .NET MAUI DataForm are described in the table below:

| Xamarin DataForm | .NET MAUI DataForm |
| ------------- | --------------- |
| Source | gets the data directly from the set BindingContext |
| Telerik.XamarinForms.Common.DataAnnotations| System.ComponentModel.DataAnnotations.DatаAnnotations |
| Validation modes - Immediate, OnLostFocus, Manual | Validation modes - PropertyChanged, LostFocus, Explicit |
| FormValidationCompleted,PropertyValidationCompleted | - |
| ValidateAll, ValidateProperty | - |
| - | ValidateChanges |
| - | ValidateCommand, CancelCommand, CommitCommand |
| Commit modes - Immediate, OnLostFocus, Manual| Commit modes - PropertyChanged, LostFocus, Explicit |
| CommitAll, CommitProperty | CommitChanges |
| - | CancelChanges |
| DataFormGroupStackLayoutDefinition | DataFormVerticalStackLayout |
| DataFormGroupGridLayoutDefinition  | DataFormGridLayout  |
| -  | DataFormCustomLayout  |
| DataFormGroupGridLayoutDefinition  | DataFormGridLayout |
| -  | DataFormCustomLayout |
