---
layout: default
title: Custom Workflows
nav_order: 3
---


# Custom workflows

The toolkit was designed with the goal of making the Weave adoption as simple process as possible by using the APIs described in the <a href='/docs/using-the-toolkit/basic-workflows'>Basic workflows</a> section, without the need for developers to deal with custom controls, styles or resources. You are, however, free to directly use and/or customize the styles if the simple approach doesnt cut it for you. Implicit and named styles are availble, as are the theme resource dictionaries. Following are some example of what can be done, but like with anything in WPF, there are many more possibilities and ways to achieve the desired experience:

## Using (implicit) Weave styles directly

This example turns on Weave just like the API does, but gives you more control over how your resources are managed:

            <Window ...
                    Style="{DynamicResource WeaveWindowStyle}">
                <Window.Resources>
                    <ResourceDictionary>
                        <ResourceDictionary.MergedDictionaries>
                            <ResourceDictionary Source="/Autodesk.Weave.Wpf;component/Styles/DefaultStyles.xaml" />
                        </ResourceDictionary.MergedDictionaries>
                    </ResourceDictionary>
                </Window.Resources>
            </Window>

It can also be used in the application's XAML to turn Weave on for the entire app:

            <Application ...>
                <Application.Resources>
                    <ResourceDictionary>
                        <ResourceDictionary.MergedDictionaries>
                            <ResourceDictionary Source="/Autodesk.Weave.Wpf;component/Styles/DefaultStyles.xaml" />
                        </ResourceDictionary.MergedDictionaries>
                    </ResourceDictionary>
                </Application.Resources>
            </Window>

**Important:** If you choose to go this way, you will also have to ensure that WeaveWindowStyle is set on every window.

_Note: You will still need to set the theme either by using the API, or by importing the appropriate resources as shown in the next section._

## Setting a theme in resources

This code snippet sets the dark blue theme on the application:

            <Application ...>
                <Application.Resources>
                    <ResourceDictionary>
                        <ResourceDictionary.MergedDictionaries>
                            <ResourceDictionary Source="/Autodesk.Weave.Wpf;component/Themes/wpf.hig-dark-blue.density.high.xaml"/>
                        </ResourceDictionary.MergedDictionaries>
                    </ResourceDictionary>
                </Application.Resources>
            </Window>

Implementing theme switching will be more complicated in this case than it would be using the API.

## Using named styles

If you'd like more granularity, you can set choose to only import styles you really need or use Weave on individual elements:

            <Window ...>
                <Window.Resources>
                    <ResourceDictionary>
                        <ResourceDictionary.MergedDictionaries>
                            <ResourceDictionary Source="/Autodesk.Weave.Wpf;component/Styles/Button.xaml" />
                        </ResourceDictionary.MergedDictionaries>
                    </ResourceDictionary>
                </Window.Resources>
                ...
                <Button Style="{StaticResource WeaveButtonStyle}">Button</Button>
            </Window>

Every implemented control has its own `.xaml` file that defines the style for that control.

You can also import all the styles instead individual controls style, but opt-in when applying them to individual controls:

            <Window ...>
                <Window.Resources>
                    <ResourceDictionary>
                        <ResourceDictionary.MergedDictionaries>
                            <ResourceDictionary Source="/Autodesk.Weave.Wpf;component/Styles/Styles.xaml" />
                        </ResourceDictionary.MergedDictionaries>
                    </ResourceDictionary>
                </Window.Resources>
                ...
                <Button Style="{StaticResource WeaveButtonStyle}">Weave Button</Button>         <!-- Weave -->
                <Button>Regular Button</CheckBox>                                               <!-- No Weave -->
            </Window>

