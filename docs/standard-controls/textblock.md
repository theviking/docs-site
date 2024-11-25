---
layout: default
title: TextBlock
parent: Standard Controls
nav_order: 9
---

# TextBlock

## References
- [Microsoft Documentation](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/controls/textblock?view=netframeworkdesktop-4.8&viewFallbackFrom=netdesktop-7.0)
- Weave Web Site - [Typography](https://weave.autodesk.com/web/basics/typography-main)
- Weave Figma States (WIP) - [Typography](https://www.figma.com/file/ALLi7jxsFfwlJKiXkz7YAa/2.0-dev-ref?type=design&node-id=603%3A112354&mode=dev)
- Weave MUI Storybook - [Typography](https://pages.git.autodesk.com/design-system/weave-mui/?path=/story/basics-typography--default-story)

## Properties

|**Name**|**Type**|**Default**||
|:-------------|:-------------|:-------------|:-------------|
|Variant|enum|None| None / H1Regular / H1Medium / H1Bold / H2Regular / H2Medium / H2Bold / H3Regular / H3Medium / H3Bold / BodyRegular / BodyMedium / BodyBold / CaptionRegular / CaptionMedium / CaptionBold |

## Notes
The current default is `None` so as to not affect other default styles. To use a `TextBlock` a `Variant` should always be used.

The styles can also be set within `Span` or `Run` elements.
