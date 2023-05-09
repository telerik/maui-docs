---
title: Item Template
page_title: .NET MAUI SlideView Documentation - Item Template
description: "Get started with the Telerik UI for .NET MAUI SlideView control and add the control to your .NET MAUI project."
position: 2
slug: slideview-item-template
---

# .NET MAUI SlideView Item Template

`SlideView` can be populated with various types of objects (string, int, any business objects, etc.). You can customize the visualization of the views in the ItemsSource of the control using its ItemTemplate property. The template could contain any view that you can use to display the data.

### Еxample

The following example shows how to populate the ItemsSource with business items and customize their appearance.

First, create a sample MyItem class: 

<snippet id='' />

Add a ViewModel containing a collection of MyItem objects:

<snippet id='' />

Then, add the SlideView definition with a sample ItemTemplate applied:

<snippet id='' />

All that is left is to set the BindingContext to the ViewModel:

<snippet id='' />

Here is the result:
	
#### Figure 1: RadSlideView with ItemTemplate applied
![RadSlideView example](images)

### See Also
