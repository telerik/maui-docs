---
title: Commands
page_title: .NET MAUI Entry Documentation - Commands
description: Learn how to use the commands availabe in the Telerik UI for .NET MAUI Entry control.
position: 5
slug: entry-commands
---

# .NET MAUI Entry Commands

When using Telerik UI for .NET MAUI Entry control, you can use the following commands: 


* `ReturnCommand`(`ICommand`)&mdash;Execute when the return key of the keyboard is pressed. 

The `ReturnCommand` has a command parameter&mdash;`ReturnCommandParameter` which can be used to pass a parameter to the command execute method.

When using MVVM design pattern use the Entry's Commands instead of the event handler.

```XAML
<telerik:RadEntry x:Name="entry"
                  ReturnCommand="{Binding EntryReturnCommand}"/>
```

```C#
public MainPage()
{
  InitializeComponent();

  this.BindingContext = new ViewModel();
}
```

```C#
public class ViewModel
{
    public ViewModel()
    {
        EntryReturnCommand = new Command(EntryReturn);
    }

    public Command EntryReturnCommand { get; set; }

    private void EntryReturn()
    {
    // implement your logic here
    }
}
```


## See Also

- [Text Appearance]({% slug entry-text-appearance%})
- [Text Selection]({%slug entry-text-selection %})
- [Events]({% slug entry-events%})
