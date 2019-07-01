---
title: "Caliburn.Micro conventions"
date: 2019-07-01
---
# Caliburn.Micro conventions

More details on Caliburn.Micro's [conventions](https://caliburnmicro.com/documentation/conventions)

CM applies a serie of conventions when it comes to binding. When you're using `x:Name="[Property Name]"`, CM will look in its conventions to know what property to bind to.

Those conventions are plateform dependent, for this document I will focus on the WPF
plateform since I'm using this one right now.

|Control|Property Name|Parameter Property |Event triggering the notification|
---|---|---|---
ButtonBase       | `ButtonBase.ContentProperty          `| DataContext | Click
ContentControl   | `ContentControl.ContentProperty      `| DataContext | Loaded
DatePicker       | `DatePicker.SelectedDateProperty     `| SelectedDate| SelectedDateChanged
DocumentViewer   | `DocumentViewer.DocumentProperty     `| DataContext | Loaded
Expander         | `Expander.IsExpandedProperty         `| IsExpanded  | Expanded
FrameworkElement | `FrameworkElement.VisibilityProperty `| DataContext | Loaded
Hyperlink        | `Hyperlink.DataContextProperty       `| DataContext | Click
Image            | `Image.SourceProperty                `| Source      | Loaded
Label            | `Label.ContentProperty               `| Content     | DataContextChanged
Menu             | `Menu.ItemsSourceProperty            `| DataContext | Click
MenuItem         | `MenuItem.ItemsSourceProperty        `| DataContext | Click
PasswordBox      | `null                                `| Password    | PasswordChanged
ProgressBar      | `ProgressBar.ValueProperty           `| Value       | ValueChanged
RichTextBox      | `RichTextBox.DataContextProperty     `| DataContext | TextChanged
Slider           | `Slider.ValueProperty                `| Value       | ValueChanged
StatusBar        | `StatusBar.ItemsSourceProperty       `| DataContext | Loaded
Selector         | `Selector.ItemsSourceProperty        `| SelectedItem| SelectionChanged
Shape            | `Shape.VisibilityProperty            `| DataContext | MouseLeftButtonUp
ToolBar          | `ToolBar.ItemsSourceProperty         `| DataContext | Loaded
ToolBarTray      | `ToolBarTray.VisibilityProperty      `| DataContext | Loaded
TreeView         | `TreeView.ItemsSourceProperty        `| SelectedItem| SelectedItemChanged
TabControl       | `TabControl.ItemsSourceProperty      `| ItemsSource | SelectionChanged
TabItem          | `TabItem.ContentProperty             `| DataContext | DataContextChanged
TextBox          | `TextBox.TextProperty                `| Text        | TextChanged
TextBlock        | `TextBlock.TextProperty              `| Text        | DataContextChanged
ToggleButton     | `ToggleButton.IsCheckedProperty      `| IsChecked   | Click
UserControl      | `UserControl.VisibilityProperty      `| DataContext | Loaded
Window           | `Window.DataContextProperty          `| DataContext | Loaded

Hopefuly this is useful to someone, I have some serious doubt as more and more I look into stackoverflow and more and more I
realise that WPF seems to be a technology of the past.

Anyway I'm still looking for the conventions that are related to the actions.

For instance, did you know that you can enable/disable a button by having a `Can` method ?:
```
# In Xaml
<...:Button x:Name="MyButton" />

# In ViewModel

public string MyButton {get;set;} // allows you to set the Content of the button

public bool CanMyButton(){} // allows you to enable/disable the button

public bool MyButtonIsVisible {get;set;} // allows you to set the visibility of the button
```

And this is all I got for now. I've been looking in the documentation of CM for some time and I could not find anything related
to those functionalities.

I also looked on google, still no luck, all the examples that I gave above have been found by pure coincidence on stackoverflow
on post that were not obviously related to that...

If anyone has some input regarding that, it'd be more than helpful.

Happy Coding.
