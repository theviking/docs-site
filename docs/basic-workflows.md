---
layout: default
title: Basic Workflow
nav_order: 2
---

# Basic workflow

The toolkit is designed to make both new and existing UI Weave-compliant without the need of extensive rewrite, by applying custom styling to the built-in WPF controls and elements. This is achieved by replacing the default built-in WPF styles withe custom Weave styles and control templates at run time. Follow these steps to get started:

## Consume the package
Add `Autodesk.Weave.Wpf` NuGet package to your project.

## Turn on Weave
At this point you will have to make a decision how to use Weave:
- For the entire application, in which case all UI that belongs to the application will get Weave automatically, or
- For individual pieces of UI (e.g. dialogs), in which case only those specific dialogs will be Weave-compliant

There are two major components of the toolkit:
- Styles that can be applied to WPF elements (windows, controls, etc.)
- Themes that are used by the styles; there is always one "current" theme set at any time

Both components have to be applied to get the complete Weave user experience.

### Option 1: Weave styles and theme set on the entire application

In this scenario, both styles and the current theme is set on the application. All of application's UI will be Weave-compliant and share the same theme:

            Autodesk.Weave.Wpf.Utils.ApplyTheme(Application.Current, Autodesk.Weave.Wpf.Utils.ThemeId.WeaveLightGray);
            Autodesk.Weave.Wpf.Utils.ApplyControlStyles(Application.Current);            

Once set up, the application's theme can be changed at any time:

            Autodesk.Weave.Wpf.Utils.ApplyTheme(Application.Current, Autodesk.Weave.Wpf.Utils.ThemeId.WeaveDarkBlue);

_Note: These calls should be made after the application's constructor has finished. It is important to know that they modify the application's resources - they add dictionaries to the application's main resource dictionary. If called inside the application's constructor, they might be overwritten by resources defined in the application's XAML._

There are also corresponding `Remove` functions that can be used to turn Weave off if needed:

            Autodesk.Weave.Wpf.Utils.RemoveControlStyles(Application.Current);
            Autodesk.Weave.Wpf.Utils.RemoveTheme(Application.Current)
            
_Tip: If your product normally doesn't have a valid WPF application running (e.g. a native application using WPF for some parts might not be defining a WPF application), you can just instantiate a dummy one that will only serve to hold the Weave styles and the theme:_

            new Application();  // now you can use Application.Current

### Option 2: Weave styles and theme set on a specific element (less common)

In this scenario, both styles and the current theme is set on specific windows. Only those windows will be Weave-compliant, each window can have its own theme set individually:

XAML:

            <Window ...
                    xmlns:weave="clr-namespace:Autodesk.Weave.Wpf.ElementProperties;assembly=Autodesk.Weave.Wpf"
                    weave:FrameworkElementProperties.WeaveTheme="WeaveLightGray"
                    weave:FrameworkElementProperties.ApplyWeaveStyles="True">
                    ...
            </Window>
            
C#:

            Autodesk.Weave.Wpf.Utils.ApplyTheme(window, Autodesk.Weave.Wpf.Utils.ThemeId.WeaveLightGray);
            Autodesk.Weave.Wpf.Utils.ApplyControlStyles(window);         

_Note: The code-behind calls can be also done in a `Window` constructor, as long as it's after the call to `InitializeComponent()`. Similar to the application, they modify the window's main resource dictionary by adding additional resources to them._

### Option 3: Weave styles set on a specific window, global theme (more common)

In this scenario, styles are set on specific specific windows. Only those windows will be Weave-compliant, but all windows share the same theme that is set on the application. Changing the theme is automatically applied to all the windows:

            Autodesk.Weave.Wpf.Utils.ApplyTheme(Application.Current, Autodesk.Weave.Wpf.Utils.ThemeId.WeaveLightGray);

XAML:

            <Window ...
                    xmlns:weave="clr-namespace:Autodesk.Weave.Wpf.ElementProperties;assembly=Autodesk.Weave.Wpf"
                    weave:FrameworkElementProperties.ApplyWeaveStyles="True">
                    ...
            </Window>
            
C#:

            Autodesk.Weave.Wpf.Utils.ApplyControlStyles(window);         

### Design-time

For developers to preview how their UI will look in run-time, additional _design-time_ properties are available that allow turning on Weave in the Visual Studio XAML Designer environment:

            <Window ...
                    xmlns:weave="clr-namespace:Autodesk.Weave.Wpf.ElementProperties;assembly=Autodesk.Weave.Wpf"
                    xmlns:weave_d="clr-namespace:Autodesk.Weave.Wpf.ElementProperties.DesignTime;assembly=Autodesk.Weave.Wpf"
                    weave:FrameworkElementProperties.ApplyWeaveStyles="True"
                    weave:FrameworkElementProperties.WeaveTheme="WeaveDarkGray"
                    weave_d:FrameworkElementProperties.DesignTimeWeaveTheme="WeaveLightGray">
                    ...
            </Window>

### Remove custom styling from your UI

At this point, your UI should be more or less Weave-compliant, depending on:
- The amount of custom styling that you have set on your controls. Since Weave functions by modifying the default styles for UI elements, any explicit properties and/or custom styles that you set on your controls will override it. To take full advantage of the Weave design system, remove any custom styling. Most visual properties are defined by the design tokens. In particular, avoid setting these properties: `FontFamily`, `FontSize`, `FontWeight`, `Padding`, `Margin`, `Width`, `Height`, colors. Avoid explicit positioning of your controls, rely on the built-in panels and containers to implement a responsive layout.
- The controls you're using. We are aiming to have as many of Weave elements available as possible, but there will be times when an implementation for a particular control is missing. In such cases, contact us or contribute to the project by implementing it.

### Customize

Most of the implemented controls have _variants_ - different flavors of the control. These can be controlled by setting additional Weave-spefic properties. Take a look at the controls listed in the menu for details.</a>.

### Enjoy

Hopefully you can achieve a Weave-compliant WPF UI just by following these steps. If you need more customization, check out the <a href='/docs/using-the-toolkit/custom-workflows'>Custom workflows</a> section.
