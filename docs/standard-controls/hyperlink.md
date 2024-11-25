---
layout: default
title: Hyperlink
parent: Standard Controls
nav_order: 4
---

# Hyperlink

## References
- [Microsoft Documentation](https://learn.microsoft.com/en-us/dotnet/api/system.windows.documents.hyperlink?view=windowsdesktop-7.0)
- Weave Web Site - [Text Links](https://weave.autodesk.com/web/components/text-links)
- Weave Figma States (WIP) - [Text link](https://www.figma.com/file/ALLi7jxsFfwlJKiXkz7YAa/2.0-dev-ref?type=design&node-id=603%3A112274&mode=dev)
- Weave MUI Storybook - [Links](https://pages.git.autodesk.com/design-system/weave-mui/?path=/story/components-link-text-links--default-story)

## Properties

|**Name**|**Type**|**Default**| |
|:-------------|:-------------|:-------------|:-------------|
| Variant | enum | Primary | Primary / Secondary |

## Notes
Hyperlinks must be used within a TextBlock.

```xml
<TextBlock> 
  <Hyperlink>Hyperlink Text</Hyperlink>
</TextBlock>
```