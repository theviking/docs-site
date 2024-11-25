---
layout: default
title: TextBox
parent: Standard Controls
nav_order: 10
---

# TextBox

## References
- [Microsoft Documentation](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/controls/textbox?view=netframeworkdesktop-4.8&viewFallbackFrom=netdesktop-7.0)
- Weave Web Site - [Text Inputs](https://weave.autodesk.com/web/components/text-inputs)
- Weave Figma States (WIP) - [Text Inputs](https://www.figma.com/file/ALLi7jxsFfwlJKiXkz7YAa/2.0-dev-ref?type=design&node-id=788%3A90948&mode=dev) and [Numeric Inputs](https://www.figma.com/file/ALLi7jxsFfwlJKiXkz7YAa/2.0-dev-ref?type=design&node-id=807%3A125273&mode=dev)
- Weave MUI Storybook - [Text Inputs](https://pages.git.autodesk.com/design-system/weave-mui/?path=/story/components-textfield-text-inputs--default-story) 

## Properties

|**Name**|**Type**|**Default**||
|:-------------|:-------------|:-------------|:-------------|
|Variant|enum|Box| Line / Box |
|NumericUpDown|Bool|False||
|NumericUpCommand|ICommand|NA|required when NumericUpDown = true|
|NumericUpCommandParameter|object|NA|required when NumericUpDown = true|
|NumericUpCommandTarget|object|NA|required when NumericUpDown = true|
|NumericDownCommand|ICommand|NA|required when NumericUpDown = true|
|NumericDownCommandParameter|object|NA|required when NumericUpDown = true|
|NumericDownCommandTarget|object|NA|required when NumericUpDown = true|
