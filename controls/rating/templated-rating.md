---
title: Templated Rating
page_title: .NET MAUI Rating Documentation - Templated Rating
description: Check our &quot;Templated Rating&quot; documentation article for Telerik Rating for .NET MAUI.
position: 5
previous_url: /controls/rating/rating-templated-rating
slug: rating-templated-rating
---

# Templated Rating

The `RadTemplatedRating` component is designed for cases where it is easier to provide a template (for example, an image) for the rating items instead of creating custom `RadPathGeometry`.

On top of the [common Rating API]({%slug rating-configuration%}), this component adds the following members:

* `ItemTemplate` (`DataTemplate`)&mdash;Defines the template used in the rating item.
* `SelectedItemTemplate` (`DataTemplate`)&mdash;Specifies the template used in the selected rating item.

> Set both the `ItemTemplate` and `SelectedItemTemplate` templates.

![Rating Template](images/rating-templates.png)

The following example demonstrates how to define `RadTemplatedRating` in XAML:

<snippet id='rating-templates' />

## See Also

- [Configuration of the Rating]({% slug rating-configuration%})
- [Shape Rating]({% slug rating-shape-rating%})
