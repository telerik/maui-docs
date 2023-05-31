---
title: Item Template
page_title: .NET MAUI SlideView Documentation - Item Template
description: Learn how to customize the visualization of the views in the ItemsSource of the control by using the ItemTemplate property.
position: 6
slug: slideview-item-template
---

# .NET MAUI SlideView Item Template

You can populate the SlideView component with various types of objects, for example, `string`, `int`, business objects, and so on. To customize the visualization of the views in the `ItemsSource` of the control, use its `ItemTemplate` property. The template can contain any of the views that you use to display the data.

### Example

The following example shows how to populate the `ItemsSource` with business items and customize their appearance.

**1.** Create a sample `MyItem` class. 

<snippet id='' />

**2.** Add a View Model containing a collection of `MyItem` objects.

<snippet id='' />

**3.** Add the SlideView definition with a sample `ItemTemplate` applied.

<snippet id='' />

**4.** Set the `BindingContext` to the View Model:

<snippet id='' />

Here is the result:

![RadSlideView with ItemTemplate applied](images)

## See Also
