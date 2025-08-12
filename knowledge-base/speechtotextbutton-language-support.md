---
title: SpeechToTextButton Language Support in .NET MAUI
description: Learn what are the supported languages for the SpeechToTextButton in .NET MAUI and how to set them.
type: how-to
page_title: How to check the supported languages for the SpeechToTextButton in .NET MAUI
slug: speechtotextbutton-language-support
tags: .net maui, speechtotext, languages, supported languages, .net maui, microsoft .net maui
res_type: kb
---

## Environment

| Version | Control | Author | 
| ------- | ------- | ------ | 
| SpeechToTextButton for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

This article explains how to check the supported languages for the SpeechToTextButton in .NET MAUI and how to set them.

## Solution

Here is an example of how to check the supported languages for the SpeechToTextButton in .NET MAUI. For the demo we will use 
* An Editor for displaying the recognized text.
* Entry for setting the language.
* Label for displaying whether the language is supported or not.

**1.** Define the `RadSpeechToTextButton` control in XAML. 

```XAML
<Grid RowDefinitions="Auto, *, 4*">
    <Grid ColumnDefinitions="*, *">
        <Entry x:Name="entryLanguage" TextChanged="EntryLanguage_TextChanged" Placeholder="en-US" />
        <Label x:Name="label1" Grid.Column="1" />
    </Grid>
    <Editor x:Name="editor" Grid.Row="1" />
    <telerik:RadSpeechToTextButton x:Name="speechToTextButton"
                                   SpeechRecognized="SpeechToTextButton_SpeechRecognized"
                                   Grid.Row="2"
                                   HorizontalOptions="End"
                                   VerticalOptions="End"
                                   Margin="{OnPlatform Default=0, MacCatalyst='0, 0, 20, 20'}" />
</Grid>
```

**2.** In the code-behind, handle the `TextChanged` event of the Entry to check if the entered language is supported.

```C#
private void EntryLanguage_TextChanged(object sender, Microsoft.Maui.Controls.TextChangedEventArgs e)
{
    bool isSupported = IsLanguageSupported(e.NewTextValue);
    this.label1.Text = isSupported ? "supported" : "not supported";

    if (isSupported)
    {
        this.label1.Text = "supported";
        this.speechToTextButton.LanguageTag = e.NewTextValue;
    }
    else
    {
        this.label1.Text = "not supported";
    }
}

private static bool IsLanguageSupported(string languageTag)
{
    try
    {
#if ANDROID
        //// There is no programmatic way to check if a language is supported on Android but most languages are.
        //// https://cloud.google.com/speech-to-text/docs/speech-to-text-supported-languages
#elif IOS
        var locale =  Foundation.NSLocale.FromLocaleIdentifier(languageTag);
        var localSpeechRecognizer = new Speech.SFSpeechRecognizer(locale);
        localSpeechRecognizer.Dispose();
#elif WINDOWS
        var language = new global::Windows.Globalization.Language(languageTag);
        var localSpeechRecognizer = new global::Windows.Media.SpeechRecognition.SpeechRecognizer(language);
        localSpeechRecognizer.Dispose();
#endif
        return true;
    }
    catch
    {
        return false;
    }
}
```

**3.** Handle the SpeechToTextButton's `SpeechRecognized` event to display the recognized text in the Editor.

```C#
private void SpeechToTextButton_SpeechRecognized(object sender, SpeechRecognizerSpeechRecognizedEventArgs args)
{
    this.editor.Text = args.FullText;
}
```

## See Also

- [SpeechToTextButton for .NET MAUI]({%slug speechtotextbutton-overview%})
- [Configure the SpeechToTextButton]({%slug speechtotextbutton-configuration%})
- [Set Visual States]({%slug speechtotextbutton-visual-states%})
- [Events]({%slug speechtotextbutton-events%})
- [Execute Commands]({%slug speechtotextbutton-commands%})
- [Style the SpeechToTextButton]({%slug speechtotextbutton-styling%})