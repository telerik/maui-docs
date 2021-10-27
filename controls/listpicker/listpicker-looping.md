---
title: Looping
page_title: .NET MAUI ListPicker Documentation | Looping
description: Check our &quot;Looping&quot; documentation article for Telerik ListPicker for .NET MAUI.
position: 2
slug: listpicker-looping
---

# Looping

ListPicker for .NET MAUI provides looping functionality which allows you to loop the list of items after reaching the last item.

You can achieve this by setting ListPicker `IsLooping`(*bool*) property to *true*.

### Example

The snippet below shows a simple RadListPicker definition:

<snippet id='listpicker-features-looping' />
```XAML
<telerikInput:RadListPicker Placeholder="Pick a City Name!"
							IsLooping="True"
							ItemLength="40"
							ItemSpacing="3"
							ItemsSource="{Binding Items}" 
							DisplayMemberPath="Name">
		<telerikInput:RadListPicker.BindingContext>
			<local:CitiesViewModel/>
		</telerikInput:RadListPicker.BindingContext>
		<telerikInput:RadListPicker.ItemTemplate>
			<DataTemplate>
				<Label Text="{Binding Name}" 
					   HorizontalTextAlignment="Center" 
					   VerticalTextAlignment="Center"/>
			</DataTemplate>
		</telerikInput:RadListPicker.ItemTemplate>
	</telerikInput:RadListPicker>
```

A sample business model:

<snippet id='listpicker-features-businessmodel' />
```C#
public class City
{
	public string Name { get; set; }
	public int Population { get; set; }
}
```

and a ViewModel:

<snippet id='listpicker-features-viewmodel' />
```C#
public class CitiesViewModel
{
	public CitiesViewModel()
	{
		this.Items = new ObservableCollection<City>
		{
			new City { Name = "Tokyo", Population = 13929286 },
			new City { Name = "New York", Population = 8623000 },
			new City { Name = "London", Population = 8908081 },
			new City { Name = "Madrid", Population = 3223334 },
			new City { Name = "Los Angeles", Population = 4000000},
			new City { Name = "Paris", Population = 2141000 },
			new City { Name = "Beijing", Population = 21540000 },
			new City { Name = "Singapore", Population = 5612000 },
			new City { Name = "New Delhi", Population = 18980000 },
			new City { Name = "Bangkok", Population = 8305218 },
			new City { Name = "Berlin", Population = 3748000 },
		};
	}

	public ObservableCollection<City> Items { get; set; }
}
```

This is how the Looping functionality looks:

![ListPicker Looping](images/looping_gif.gif)

>important A sample Looping example can be found in the ListPicker/Looping folder of the [Telerik UI for .NET MAUI SDKBrowser Application]({%slug maui-demo-app%}).

## See Also

- [Templates]({%slug listpicker-templates%})
- [Styling]({%slug listpicker-styling%})
- [Selection]({%slug listpicker-selection%})
- [Commands]({%slug listpicker-commands%})
